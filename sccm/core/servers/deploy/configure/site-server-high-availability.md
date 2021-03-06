---
title: Alta disponibilidade do servidor do site
titleSuffix: Configuration Manager
description: Como configurar a alta disponibilidade para o servidor de site do Configuration Manager com a adição de um servidor do site no modo passivo.
ms.date: 07/30/2018
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 6dcef836-c0d1-40af-ad30-cd8d864b09a9
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: be12cfe29ff470f2f577bab2c685695ae5770bae
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56131414"
---
# <a name="site-server-high-availability-in-configuration-manager"></a>Alta disponibilidade do servidor do site no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

<!--1128774-->

Do Configuration Manager versão 1806 em diante, alta disponibilidade para a função de servidor do site é uma solução com base no Configuration Manager para instalar um servidor do site adicional no modo *passivo*. O servidor do site no modo passivo é usado além do servidor do site existente que está no modo *ativo*. Um servidor do site no modo passivo está disponível para uso imediato quando for necessário. Inclua este servidor do site adicional como parte de seu design geral para tornar o serviço do Configuration Manager [altamente disponível](/sccm/core/servers/deploy/configure/high-availability-options).  

Um servidor do site em modo passivo:
- Usa o mesmo banco de dados do site que o seu servidor do site no modo ativo.
- Não grava dados no banco de dados do site quando ele está em modo passivo.
- Usa a mesma biblioteca de conteúdo que seu servidor do site no modo ativo.

Para fazer o servidor do site no modo passivo ficar ativo, você *promove*-o manualmente. Essa ação alterna o servidor do site no modo ativo para que seja o servidor do site no modo passivo. As funções de sistema de sites disponíveis no servidor de modo ativo original permanecem disponíveis, desde que o computador esteja acessível. Somente a função de servidor do site é alternada entre os modos ativo e passivo.

> [!Note]  
> O Configuration Manager não habilita esse recurso opcional por padrão. É necessário habilitar esse recurso antes de usá-lo. Para obter mais informações, consulte [Enable optional features from updates (Habilitar recursos opcionais de atualizações)](/sccm/core/servers/manage/install-in-console-updates#bkmk_options).



## <a name="prerequisites"></a>Pré-requisitos

- O servidor do site no modo passivo pode ser local ou baseado em nuvem no Azure.  
    > [!Note]  
    > Um servidor do site baseado em nuvem em modo passivo usa a IaaS (infraestrutura como serviço) do Azure. Para obter mais informações, consulte os seguintes artigos:  
    > - [Máquinas virtuais do Azure (para infraestrutura baseada em nuvem)](/sccm/core/understand/use-cloud-services#azure-virtual-machines-for-cloud-based-infrastructure)
    > - [Perguntas frequentes sobre o Configuration Manager no Azure](/sccm/core/understand/configuration-manager-on-azure)  

- Ambos os servidores do site devem ser associados ao mesmo Domínio do Active Directory.  

- O site é primário e autônomo. 

- Ambos os servidores do site devem usar o mesmo banco de dados, que deve ser remoto a cada servidor do site.  

     - Ambos os servidores do site precisam de permissões **sysadmin** na instância do SQL Server que hospeda o banco de dados do site.

     - O SQL Server que hospeda o banco de dados do site pode usar uma instância padrão, uma instância nomeada, o [cluster do SQL Server](/sccm/core/servers/deploy/configure/use-a-sql-server-cluster-for-the-site-database) ou um [Grupo de disponibilidade Always On do SQL Server](/sccm/core/servers/deploy/configure/sql-server-alwayson-for-a-highly-available-site-database).  

     - O servidor do site no modo passivo é configurado para usar o mesmo banco de dados do site que o servidor do site no modo ativo. O servidor do site no modo passivo apenas lê do banco de dados. Ele não grava no banco de dados até depois de ser promovido para o modo ativo.  

- A biblioteca de conteúdo do site deve estar em um compartilhamento de rede remota. Ambos os servidores do site precisam de permissões de Controle Total para o compartilhamento e seu conteúdo. Para obter mais informações, veja [Gerenciar biblioteca de conteúdo](/sccm/core/plan-design/hierarchy/the-content-library#manage-content-library).<!--1357525-->  

    - O servidor do site não pode ter a função de ponto de distribuição. O ponto de distribuição também usa a biblioteca de conteúdo, e essa função não dá suporte para biblioteca de conteúdo remota. Depois de mover a biblioteca de conteúdo, você não pode mais adicionar a função de ponto de distribuição ao servidor do site.  

- O servidor do site em modo passivo:  

     - Deve atender aos [pré-requisitos para instalação de um site primário](/sccm/core/servers/deploy/install/prerequisites-for-installing-sites#primary-sites-and-the-central-administration-site).  

     - Deve ter sua conta de computador no grupo de Administradores local no servidor do site no modo ativo.<!--516036-->

     - Instala usando arquivos de origem que correspondem à versão do servidor do site no modo ativo.  

     - Não é possível ter uma função do sistema do site de nenhum site antes de instalar o servidor do site na função de modo passivo.  

- Ambos os servidores do site podem executar diferentes versões do service pack ou sistema operacional, desde que ambas sejam [compatíveis com o Configuration Manager](/sccm/core/plan-design/configs/supported-operating-systems-for-site-system-servers).  



## <a name="limitations"></a>Limitações
- Há suporte apenas para um único servidor do site de modo passivo em cada site primário.  

- Não há suporte para um servidor do site no modo passivo em uma hierarquia. Uma hierarquia que inclui um site de administração central e um site primário filho. Crie apenas um servidor do site no modo passivo em um site primário autônomo.<!--1358224-->

- Não há suporte para um servidor do site no modo passivo em um site secundário.<!--SCCMDocs issue 680-->  

- A promoção do servidor do site no modo passivo para o modo ativo é manual. Não há failover automático.  

- Funções do sistema do site não podem ser instaladas no novo servidor antes de adicionar o servidor do site no modo passivo.  

    > [!Note]  
    > Depois que ele instala o servidor do site no modo passivo, você pode adicionar mais funções conforme necessário. Por exemplo, o Provedor de SMS ou um ponto de gerenciamento em um site primário.  

- Para funções como o ponto de relatório que usam um banco de dados, hospede o banco de dados em um servidor remoto de ambos os servidores do site.  

- O Provedor de SMS não é instalado no servidor do site no modo passivo. Conecte-se a um provedor para o site promover manualmente o servidor do site no modo passivo para o modo ativo. Instale pelo menos uma instância adicional do provedor em outro servidor. Para obter mais informações, veja [Planejar para o provedor de SMS](/sccm/core/plan-design/hierarchy/plan-for-the-sms-provider).  

- O console do Configuration Manager não é instalado automaticamente no servidor do site no modo passivo.  



## <a name="add-a-site-server-in-passive-mode"></a>Adicionar um servidor do site no modo passivo

Para obter mais informações sobre o processo geral de adição de funções, veja [Instalar funções do sistema de site](/sccm/core/servers/deploy/configure/install-site-system-roles).

1. No console do Configuration Manager, vá para o workspace **Administração**, expanda **Configuração do Site**, selecione o nó **Sites** e clique em **Criar Servidor do Sistema de Sites** na faixa de opções.   

2. Na página **Geral** do Assistente para Criar Servidor do Sistema de Sites, especifique o servidor para hospedar o servidor do site no modo passivo. O servidor especificado não pode hospedar nenhuma função do sistema de sites antes de instalar um servidor do site no modo passivo.  

3. Na página **Seleção de Função do Sistema**, selecione apenas **Servidor do site no modo passivo**.  

    > [!Note]  
    > O assistente executa as seguintes verificações inicias de pré-requisitos nesta página:  
    > - O servidor selecionado não é um servidor do site secundário
    > - O servidor selecionado ainda não é um servidor do site no modo passivo
    > - A biblioteca de conteúdo do site está em um local remoto  
    >  
    > Se essas verificações iniciais de pré-requisitos falharem, você não poderá continuar além dessa página do assistente.  

4. Na página **Servidor do Site no Modo Passivo**, forneça as seguintes informações que são usadas para executar a instalação e instalar a função de servidor do site no servidor especificado:

     - Selecione uma das seguintes opções:  

         - **Copiar os arquivos de origem de instalação na rede do servidor do site em modo ativo**: esta opção cria um pacote compactado e o envia para o novo servidor do site.  

         - **Usar os arquivos de origem no seguinte local no servidor do site em modo passivo**: por exemplo, um caminho local para o qual você já copiou os arquivos de origem. Verifique se que este conteúdo é da mesma versão que o servidor do site no modo ativo.  

         - (*Recomendado*) **Use os arquivos de origem no seguinte local de rede**: especifique o caminho diretamente para os conteúdos da pasta **CD.Latest** do servidor do site no modo ativo. Por exemplo, `\\Server\SMS_ABC\CD.Latest` em que "*Server*" é o nome do servidor do site no modo ativo, e "*ABC*" é o código do site.  

     - Especifique o caminho local no qual instalar o Configuration Manager no novo servidor do site. Por exemplo: `C:\Program Files\Configuration Manager`  

5. Conclua o assistente. Depois, o Configuration Manager instala o servidor do site no modo passivo no servidor especificado.

Para obter o status de instalação detalhado, no console, vá para o workspace **Monitoramento** e selecione o nó **Status do Servidor do Site**. O estado do servidor do site no modo passivo é exibido como **Instalando**. Para obter informações mais detalhadas, selecione o servidor e clique em **Mostrar Status**. Essa ação abre a janela de Status de Instalação do Servidor do Site. Quando o processo for concluído, o estado será exibido como **OK** para ambos os servidores.   

Para obter mais informações sobre o processo de instalação, veja [Fluxograma – configurar um servidor do site no modo passivo](/sccm/core/servers/deploy/configure/passive-site-server-flowchart).

Depois de adicionar um servidor do site no modo passivo, veja ambos os servidores do site na guia **Nós** no nó **Sites** do console. 

Todos os componentes do servidor do site do Configuration Manager estão em espera no servidor do site no modo passivo. Os serviços do Windows ainda estão em execução.



## <a name="site-server-promotion"></a>Promoção do servidor do site  

Da mesma forma que backup e recuperação, planeje e pratique seu processo para mudar os servidores do site. Considere os seguintes pontos em seu plano de promoção:  

- Pratique uma promoção planejada, em que ambos os servidores do site estão online. Também pratique um failover não planejado forçando a desconexão ou o desligamento do servidor do site no modo ativo.  

- Determine seus processos operacionais durante o failover e o que comunicar com outros administradores do Configuration Manager.  

- Antes de uma promoção planejada:  

    - Verifique o status geral do site e componentes do site. Verifique se tudo está íntegro conforme o normal para o seu ambiente.  

    - Verifique o status do conteúdo de todos os pacotes que estão ativamente replicando entre sites.  

    - Não inicie nenhum novo trabalho de distribuição de conteúdo. 

        > [!Note]  
        > Se a replicação de arquivo entre sites estiver em andamento durante o failover, o novo servidor do site poderá não receber o arquivo replicado. Se isso acontecer, redistribua o conteúdo de software depois que o novo servidor do site estiver ativo.<!--515436-->  


### <a name="process-to-promote-the-site-server-in-passive-mode-to-active-mode"></a>Processo para promover o servidor do site do modo passivo para o modo ativo

Esta seção descreve como alterar o servidor do site do modo passivo para o modo ativo. Para acessar o site e fazer essa alteração, você precisa ser capaz de acessar uma instância do Provedor de SMS. Para obter mais informações, veja [Usar vários provedores de SMS](/sccm/core/plan-design/hierarchy/plan-for-the-sms-provider#BKMK_MultiSMSProv).  

> [!Important]  
> Por padrão, somente o servidor do site original tem a função de Provedor de SMS. Se esse servidor estiver offline, você não poderá se conectar ao site como provedor, pois nenhum provedor estará disponível. Quando você adiciona o servidor do site no modo passivo, o Provedor de SMS não é adicionado automaticamente. Adicione pelo menos uma função de Provedor de SMS adicional ao seu site para um serviço altamente disponível.  

> [!Tip]  
> O console do Configuration Manager solicita a lista de Provedores de SMS disponíveis da WMI no servidor do site. Quando você instala vários provedores de SMS em um site, o site atribui aleatoriamente cada nova solicitação de conexão para usar um provedor de SMS instalado. Não é possível especificar o local do Provedor de SMS a ser usado com uma sessão de conexão específica. Se o seu console não conseguir se conectar ao site porque o servidor do site atual está offline, especifique o outro servidor do site na janela Conexão do Site.  

1. No console do Configuration Manager, acesse o workspace **Administração**, expanda **Configuração do Site** e selecione o nó **Sites**. Selecione o site e, em seguida, mude para a guia **Nós**. Selecione o servidor do site no modo passivo e, em seguida, clique em **Promover para ativo** na faixa de opções. Clique em **Sim** para confirmar e continuar.   
  
2. Atualize o nó do console. A coluna **Status** para o servidor que você está promovendo exibe a guia **Nós** como **Promovendo**.  

3. Após a conclusão da promoção, a coluna **Status** mostrará **OK** para o novo servidor do site no modo ativo e para o novo servidor do site no modo passivo. A coluna **Nome do Servidor** para o site agora exibe o nome do novo servidor do site no modo ativo.

Para o status detalhado, vá para o workspace **Monitoramento** e selecione o nó **Status do Servidor do Site**. A coluna **Modo** identifica qual servidor está *Ativo* ou *Passivo*. Ao promover um servidor do modo passivo para o modo ativo, selecione o servidor do site que você está promovendo para ativo e depois escolha **Mostrar Status** na faixa de opções. Essa ação abre a janela Status de Promoção do Servidor do Site, que exibe detalhes adicionais sobre o processo.

Quando um servidor do site no modo ativo mudar para o modo passivo, somente a função de sistema de sites ficará passiva. Todas as outras funções de sistema de sites instaladas nesse computador permanecerão ativas e acessíveis aos clientes.

Para obter mais informações sobre o processo de promoção *planejado*, veja [Fluxograma – promover o servidor do site (planejado)](/sccm/core/servers/deploy/configure/promote-site-server-flowchart).


### <a name="unplanned-failover"></a>Failover não planejado

Se o servidor do site atual no modo ativo estiver offline, o servidor do site para promoção tentará contatar o servidor do site atual no modo ativo por 30 minutos. Se o servidor offline voltar antes dessa hora, ele será notificado com êxito e a alteração continuará normalmente. Caso contrário, o servidor do site para promoção forçará a atualização da configuração do site para que ele esteja ativo. Se o servidor offline voltar após esse período, ele primeiro verificará o estado atual no banco de dados do site. Em seguida, ele continua rebaixando a si mesmo para o servidor do site no modo passivo.

Durante esse período de espera 30 minutos, o site não tem nenhum servidor do site no modo ativo. Os clientes ainda se comunicar com funções voltadas para o cliente, como pontos de gerenciamento, pontos de atualização de software e pontos de distribuição. Os usuários podem instalar software que já esteja implantado. Nenhuma administração de site é possível nesse período. Para obter mais informações, veja [Impactos de falha do site](/sccm/core/servers/manage/site-failure-impacts).  

Se o servidor offline estiver danificado de modo que não possa retornar, exclua esse servidor do site do console. Em seguida, crie um novo servidor do site no modo passivo para restaurar um serviço altamente disponível. 

Para obter mais informações sobre o processo de failover *não planejado*, veja o [Fluxograma – promover o servidor do site (não planejado)](/sccm/core/servers/deploy/configure/promote-site-server-unplanned-flowchart).


### <a name="additional-tasks-after-site-server-promotion"></a>Tarefas adicionais após a promoção do servidor do site  

Depois de alternar os servidores do site, você não precisa executar a maioria das outras tarefas conforme necessário ao [recuperar um site](/sccm/core/servers/manage/recover-sites#post-recovery-tasks). Por exemplo, você não precisa redefinir senhas nem reconectar a sua assinatura do Microsoft Intune.

As etapas a seguir podem ser necessárias em seu ambiente:  

- Se você importar certificados PKI para pontos de distribuição, reimporte o certificado para os servidores afetados. Para obter mais informações, veja [Gerar novamente os certificados para pontos de distribuição](/sccm/core/servers/manage/recover-sites#regenerate-the-certificates-for-distribution-points).  

- Se você integrar o Configuration Manager ao Microsoft Store para Empresas, reconfigure aquela conexão. Para obter mais informações, veja [Gerenciar aplicativos da Microsoft Store para Empresas](/sccm/apps/deploy-use/manage-apps-from-the-windows-store-for-business).  



## <a name="daily-monitoring"></a>Monitoramento diário

Quando você tiver um servidor do site no modo passivo, monitore-o diariamente. Verifique se seu Status permanece OK e está pronto para uso. No console do Configuration Manager, vá até o workspace **Monitoramento** e selecione o nó **Status do Servidor do Site**. Exiba os servidores do site e seu status atual. Também exiba o status no workspace **Administração**. Expanda **Configuração do Site** e selecione o nó **Sites**. Selecione o site e, em seguida, mude para a guia **Nós**. 
