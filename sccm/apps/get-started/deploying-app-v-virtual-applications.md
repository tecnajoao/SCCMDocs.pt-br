---
title: Implantar aplicativos virtuais do App-V | System Center Configuration Manager
description: "Confira as considerações que você deve levar em conta ao criar e implantar aplicativos virtuais."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-app
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ddcad9f2-a542-4079-83ca-007d7cb44995
caps.latest.revision: 11
caps.handback.revision: 0
author: robstackmsft
ms.author: robstack
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: d6e787d5968b281afe4e4b475287944563c8a77f


---
# <a name="deploy-app-v-virtual-applications-with-system-center-configuration-manager"></a>Implantar aplicativos virtuais do App-V com o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Além dos outros requisitos e procedimentos do System Center Configuration Manager para a criação de um aplicativo, você também precisa levar em conta as considerações a seguir ao criar e implantar aplicativos virtuais.  

 Quando você usa o Configuration Manager para gerenciar aplicativos virtuais, obtém os seguintes benefícios:  

-   Usar uma única infraestrutura de gerenciamento  

-   Recursos de distribuição de conteúdo, como coleções e afinidade de dispositivo de usuário, implantação e escalabilidade  

-   Aproveitar os recursos de gerenciamento de aplicativos avançados que o Configuration Manager fornece  

-   Usar recursos do Configuration Manager, como implantação de sistema operacional, inventário de hardware e software, medição de software e Asset Intelligence para dar suporte a aplicativos virtuais  

Para obter mais informações sobre como criar e sequenciar aplicativos com App-V, consulte [Application Virtualization (Virtualização de aplicativos)](https://technet.microsoft.com/library/cc843848.aspx) na biblioteca TechNet.  

Para implantar aplicativos virtuais em computadores, você deve ter o cliente do Configuration Manager e o Cliente App-V instalados nos computadores. Os dispositivos de clientes podem incluir área de trabalho e computadores portáteis, e clientes da VDI (Virtual Desktop Infrastructure). O Configuration Manager e o software App-V Client trabalham juntos para entregar, localizar e iniciar pacotes de aplicativos virtuais. O cliente do Configuration Manager gerencia a entrega de pacotes de aplicativos virtuais para o Cliente App-V. O Cliente App-V executa o aplicativo virtual no cliente.  

-   Para implantar um aplicativo virtual, você deve primeiro criar o aplicativo virtual usando o App-V Application Virtualization Sequencer. O sequenciador monitora o processo de instalação e configuração de um aplicativo e registra as informações necessárias para a execução do aplicativo em um ambiente virtual. Você também pode usar o sequenciador para configurar quais arquivos e configurações se aplicam a todos os usuários e quais configurações os usuários podem personalizar.  

-   Ao sequenciar um aplicativo, você deve salvar o pacote em um local que possa ser acessado pelo Configuration Manager. Em seguida, você pode criar uma implantação de aplicativo que contém o aplicativo virtual.  

-   O Configuration Manager não dá suporte ao uso do recurso de cache somente leitura compartilhado do App-V.  

-   O Configuration Manager dá suporte ao recurso de repositório de conteúdo compartilhado no App-V 5.  

-   Quando você cria um tipo de implantação para um aplicativo virtual, o Configuration Manager cria o tipo de implantação usando o conteúdo do arquivo de manifesto do aplicativo. Este é um arquivo XML que contém informações sobre o aplicativo virtual. Além disso, o Configuration Manager cria requisitos para o tipo de implantação com base no conteúdo do arquivo App-V .osd que contém informações sobre os sistemas operacionais com suporte para o aplicativo virtual.  

-   Para implantar aplicativos virtuais no Configuration Manager, os computadores cliente devem ter, no mínimo, o App-V 4.6 SP1 ou uma versão posterior do cliente instalada.  

-   Além disso, para implantar com êxito os aplicativos virtuais, você deve atualizar o cliente App-V com o hotfix descrito no artigo da Base de Dados de Conhecimento [2645225](https://support.microsoft.com/kb/2645225).  
  
-   Ao usar grupos de conexão no Microsoft Application Virtualization 5.0, seus aplicativos virtuais implantados podem compartilhar o mesmo sistema de arquivos e Registro em computadores cliente. Ao contrário de aplicativos virtuais padrão, esses aplicativos podem compartilhar dados entre si. Além disso, os grupos de conexão preservam as configurações de usuário para os aplicativos que eles contêm. Os ambientes virtuais App-V no Configuration Manager são utilizados para configurar grupos de conexão em computadores cliente. Os ambientes virtuais são criados ou alterados em computadores cliente quando o aplicativo é instalado ou quando os clientes avaliam seus aplicativos instalados. Você pode priorizar esses aplicativos para que quando vários aplicativos tentarem alterar um sistema de arquivo ou um valor de registro, o aplicativo com a mais alta prioridade tenha precedência. Para mais informações, confira [Criar ambientes virtuais App-V](../../apps/deploy-use/create-app-v-virtual-environments.md).  

##  <a name="supported-app-v-versions"></a>Versões do App-V com suporte  
 O Configuration Manager dá suporte às seguintes versões do App-V:  

-   **App-V 4.6:** para usar aplicativos virtuais no Configuration Manager, os computadores cliente devem ter o cliente App-V 4.6 SP1, App-V 4.6 SP2 ou App-V 4.6 SP3 instalado.  

     Você também deve atualizar o cliente do App-V 4.6 SP1 com o hotfix descrito na Base de Dados de Conhecimento, artigo [2645225](http://go.microsoft.com/fwlink/p/?LinkId=237322) para poder implantar com sucesso aplicativos virtuais.  

-   **App-V 5, App-V 5.0 SP1, App-V 5.0 SP2, App-V 5.0 SP3 e App-V 5.1:** Para o App-V 5.0 SP2, é necessário instalar o [Hotfix 5](https://support.microsoft.com/en-us/kb/2963211) ou usar o App-V 5.0 SP3.  

##  <a name="steps-to-manage-app-v-virtual-applications"></a>Etapas para gerenciar aplicativos virtuais do App-V  
 Para gerenciar aplicativos virtuais do App-V, conclua as seguintes etapas:  

-   **Sequenciamento** - O sequenciamento é o processo de converter um aplicativo em um aplicativo virtual usando um sequenciador do App-V.  

-   **Criar aplicativos do Configuration Manager** – Use o Assistente para Criar Tipo de Implantação para importar o aplicativo sequenciado para um tipo de implantação do Configuration Manager que você possa adicionar a um aplicativo. Você também pode criar ambientes virtuais que permitem que vários aplicativos virtuais compartilhem as configurações.  

-   **Distribuição** – A distribuição é o processo de disponibilizar aplicativos do App-V em pontos de distribuição do Configuration Manager.  

-   **Implantação** – A implantação é o processo de disponibilizar o aplicativo em computadores cliente. Isso é chamado de streaming em uma infraestrutura completa do App-V. O Configuration Manager fornece duas opções para a implantação de aplicativos virtuais: **streaming** e **baixar e executar**.  

##  <a name="configuration-manager-virtual-application-delivery-methods"></a>Métodos de entrega de aplicativos virtuais do Configuration Manager  
 O Configuration Manager dá suporte a dois métodos de entrega de aplicativos virtuais a clientes: entrega por streaming e entrega local (baixar e executar):  

-   **Entrega por streaming**  

     Quando você usa o Configuration Manager para gerenciar o cliente App-V, ele dá suporte ao streaming de aplicativos virtuais via HTTP ou HTTPS de um ponto de distribuição. O streaming via HTTP ou HTTPS é habilitado por padrão e está configurado na caixa de diálogo de propriedades do ponto de distribuição. Quando você implanta um aplicativo virtual em computadores cliente e um usuário executa o aplicativo virtual, o cliente do Configuration Manager entra em contato com um ponto de gerenciamento para determinar qual ponto de distribuição será usado, em seguida, o aplicativo é transmitido do ponto de distribuição.  

-   **Entrega local (baixar e executar)**  

     Quando você usa este método de entrega, o cliente do Configuration Manager primeiro baixa o pacote de aplicativos virtuais inteiro no cache do cliente do Configuration Manager e ele instrui o Cliente App-V a transmitir o aplicativo do cache do Configuration Manager para o cache do App-V. Se você implantar um aplicativo virtual em computadores cliente e seu conteúdo não estiver no cache do App-V, o Cliente App-V transmitirá o conteúdo do aplicativo do cache do cliente do Configuration Manager para o cache do App-V e executará o aplicativo. Depois que o aplicativo for executado com êxito, você poderá configurar o cliente do Configuration Manager para excluir todas as versões mais antigas do pacote no próximo ciclo de exclusão ou mantê-las no cache do cliente do Configuration Manager.  

 Quando decidir qual método de entrega do aplicativo virtual do Configuration Manager será usado, compare o requisito de espaço em disco reduzido para entrega por streaming em relação à disponibilidade garantida de aplicativos do App-V usando a entrega local. O aumento do espaço em disco do cliente exigido para entrega local pode ser melhor que a entrega de streaming para que os usuários sempre tenham o aplicativo disponível de qualquer local.  

 Use as informações nas tabelas a seguir para ajudá-lo a escolher o melhor método de entrega.  

 **Entrega por streaming**  

|Vantagens|Desvantagens|  
|----------------|-------------------|  
|Este método usa protocolos de rede padrão para transmitir o conteúdo do pacote de pontos de distribuição.<br /><br /> Atalhos do programa para aplicativos virtuais invocam uma conexão ao ponto de distribuição, assim a entrega do aplicativo virtual é feita sob demanda.<br /><br /> Esse método funciona bem para clientes com conexões de alta largura de banda aos pontos de distribuição.<br /><br /> Os aplicativos virtuais atualizados distribuídos na empresa são disponibilizados à medida que os clientes recebem a política que os informa que a versão atual foi substituída, e eles baixam somente as alterações da versão anterior.<br /><br /> As permissões de acesso são definidas no ponto de distribuição para impedir que os usuários acessem aplicativos ou pacotes não autorizados.|Os aplicativos virtuais não são transmitidos até que o usuário execute o aplicativo pela primeira vez. Nesse cenário, um usuário pode receber atalhos de programa para aplicativos virtuais e desconectá-los da rede antes de executar os aplicativos virtuais pela primeira vez. Se o usuário tentar executar o aplicativo virtual enquanto o cliente estiver offline, o usuário verá um erro e não poderá executar o aplicativo virtualizado, pois um ponto de distribuição do Configuration Manager não estará disponível para transmitir o aplicativo. O aplicativo estará indisponível até que o usuário se reconecte à rede e execute o aplicativo.<br /><br /> Para evitar isso, você pode usar o método de entrega local para entrega de aplicativos virtuais a clientes ou você pode habilitar o gerenciamento de clientes baseado na Internet para entrega por streaming.|  

 **Entrega local**  

|Vantagens|Desvantagens|  
|----------------|-------------------|  
|A funcionalidade do ponto de distribuição padrão é usada para baixar o pacote usando o BITS (Serviço de Transferência Inteligente de Plano de Fundo).<br /><br /> O conteúdo do pacote do aplicativo virtual é entregue localmente ao cliente, o que significa que os usuários podem executá-lo quando o computador não estiver conectado à rede.<br /><br /> Esse método é adequado para conexões de rede lentas ou não confiáveis e para computadores que só ocasionalmente se conectam à rede.<br /><br /> O Configuration Manager usa a RDC (Compactação Diferencial Remota) para enviar aos clientes somente os bytes dentro dos arquivos que foram alterados quando o conteúdo do pacote de aplicativos virtuais foi atualizado. O cliente do Configuration Manager usa a RDC para criar uma nova versão de um pacote de aplicativos virtuais com base na versão atual do pacote e de quaisquer alterações enviadas ao cliente.<br /><br /> Esse método oferece resiliência de aplicativos para usuários móveis ou desconectados. Os administradores poderão optar por manter o pacote no cache do Configuration Manager depois da entrega se o aplicativo virtual foi implantado com uma ação Instalar. O pacote no cache do cliente do Configuration Manager serve como uma fonte de streaming local e confiável para que o Cliente App-V puxe o pacote para seu cache.|É necessário o dobro do tamanho de espaço em disco do pacote de aplicativos virtuais no cliente quando o aplicativo virtual é mantido no cache do Configuration Manager.|  

 Você também pode pré-instalar aplicativos virtuais em um computador e criar uma imagem desse computador para implantação em outros computadores. No entanto, se o pacote de aplicativos virtuais foi criado em um site diferente, a replicação delta binária não será usada para baixar atualizações para o aplicativo. Essa opção pode ser útil em uma infraestrutura de área de trabalho virtual quando você deseja que os aplicativos fiquem disponíveis imediatamente em vez de baixá-los após o logon do usuário.  

##  <a name="migrating-from-an-app-v-infrastructure-to-a-configuration-manager-and-app-v-infrastructure"></a>Migrando de uma infraestrutura do App-V para uma infraestrutura do Configuration Manager e do App-V  
 Use a tabela a seguir para ajudá-lo a planejar uma migração de uma infraestrutura existente do App-V para o gerenciamento de aplicativos virtuais com o Configuration Manager.  

|Etapa|Mais informações|  
|----------|----------------------|  
|Examinar seus aplicativos virtuais atuais para escolher os aplicativos que você deseja migrar para a infraestrutura do Configuration Manager.|Nenhuma informação adicional.|  
|Avaliar os usuários e dispositivos nos quais os aplicativos virtuais serão implantados.|Crie coleções do Configuration Manager para agrupar os usuários e dispositivos nos quais você deseja implantar os aplicativos virtuais. Para mais informações, confira [Introduction to collections](/sccm/core/clients/manage/collections/introduction-to-collections) (Introdução às coleções).|  
|Migrar grupos de conexões do App-V 5 para os ambientes virtuais do Configuration Manager.|Para mais informações, confira a seção [Migrar grupos de conexões do App-V 5 para os ambientes virtuais do Configuration Manager](/sccm/apps/get-started/deploying-app-v-virtual-applications#migrate-app-v-5-connection-groups-to-configuration-manager-virtual-environments) neste tópico.|  
|Investigar para descobrir se algum dos aplicativos virtuais existe como aplicativo completo na infraestrutura do Configuration Manager.|Para gerenciamento mais fácil, você pode adicionar o aplicativo virtual como um novo tipo de implantação ao aplicativo completo existente. Para obter mais informações sobre como criar tipos de implantação, confira [Create applications](../../apps/deploy-use/create-applications.md) (Criar aplicativos).|  
|Criar aplicativos para substituir os pacotes existentes do App-V.|Para obter mais informações sobre como criar aplicativos do Configuration Manager, confira [Introduction to application management](/sccm/apps/understand/introduction-to-application-management) (Introdução ao gerenciamento de aplicativos) e [Create applications](../../apps/deploy-use/create-applications.md) (Criar aplicativos).|  
|O Configuration Manager começa a gerenciar aplicativos virtuais em um cliente após a primeira implantação de um aplicativo virtual. Depois disso, todos os aplicativos do App-V no computador devem ser gerenciados pelo Configuration Manager.|Nenhuma informação adicional.|  
|Distribuir o conteúdo para os pontos de distribuição apropriados para permitir a entrega local de aplicativos.|Para mais informações, confira [Manage content and content infrastructure](../../core/servers/deploy/configure/manage-content-and-content-infrastructure.md) (Gerenciar o conteúdo e a infraestrutura de conteúdo).|  
|Implantar o aplicativo para clientes do Configuration Manager.<br /><br /> Se o aplicativo do App-V foi criado com uma versão anterior do sequenciador que não cria um arquivo XML do manifesto, você pode abri-lo e salvá-lo em uma versão mais recente do sequenciador para criar o arquivo. Este arquivo é necessário para implantar aplicativos virtuais com o Configuration Manager.<br /><br /> O App-V oferece suporte a pacotes de aplicativos virtuais criados com as versões do SoftGrid 4.1 SP1 ou 4.2 do Sequencer.<br /><br /> Se os aplicativos foram instalados de modo local anteriormente, você deve desinstalá-los para poder implantar uma versão virtual do aplicativo.|Para obter informações, confira [Deploy applications](../../apps/deploy-use/deploy-applications.md) (Implantar aplicativos).|  
|O System Center Configuration Manager não dá mais suporte usando pacotes e programas que contêm aplicativos virtuais. Quando você migra do Configuration Manager 2007 para o System Center Configuration Manager, o Configuration Manager converte esses pacotes em aplicativos.<br /><br /> Os anúncios do Configuration Manager 2007 são convertidos nos seguintes tipos de implantação:<br /><br /> – Migração de pacotes App-V sem anúncios: um tipo de implantação que usa configurações de tipo de implantação padrão.<br /><br /> – Migração de pacotes do App-V com um anúncio: um tipo de implantação que usa as mesmas configurações que o <br />                anúncio do Configuration Manager 2007.<br /><br /> – Migração de pacotes do App-V com vários anúncios: um tipo de implantação para cada <br />                anúncio do Configuration Manager 2007 que usa as mesmas configurações que esse anúncio.|Para mais informações, confira [Planejamento da migração de objetos do Configuration Manager para o System Center Configuration Manager](../../core/migration/planning-for-the-migration-of-objects.md).|  

##  <a name="migrate-app-v-5-connection-groups-to-configuration-manager-virtual-environments"></a>Migrar grupos de conexões do App-V 5 para os ambientes virtuais do Configuration Manager  
 Os ambientes virtuais do App-V no Configuration Manager permitem que os aplicativos virtuais que você implantou compartilhem o mesmo sistema de arquivos e Registro em computadores cliente. Isso significa que, diferentemente dos aplicativos virtuais padrão, esses aplicativos podem compartilhar dados entre si. Os ambientes virtuais são criados ou modificados em computadores cliente quando o aplicativo é instalado ou quando os clientes avaliam em seguida seus aplicativos instalados. Os ambientes virtuais são semelhantes aos grupos de conexão no App-V 5 autônomo.  

 Ao migrar grupos de conexões do App-V 5 autônomo para ambientes virtuais do Configuration Manager, você deve garantir que os grupos de conexão que já existem em computadores cliente sejam gerenciados corretamente pelo Configuration Manager e se o ambiente do usuário nesses grupos de conexão esteja preservado.  

 Use o procedimento a seguir como auxílio para converter com êxito os grupos de conexões do App-V 5 em ambientes virtuais do Configuration Manager.  
  
### <a name="convert-app-v-5-connection-groups-to-configuration-manager-virtual-environments"></a>Converter grupos de conexões do App-V 5 em ambientes virtuais do Configuration Manager  
  
1.  Crie aplicativos do Configuration Manager para todos os aplicativos que existiram no App-V.  

2.  Implante os aplicativos nos usuários ou dispositivos com o objetivo de implantação **Necessário**. As implantações em usuários devem ser feitas nos mesmos usuários que utilizaram o aplicativo em App-V, e as implantações em computadores devem ser feitas nos mesmos computadores cujo aplicativo era App-V.  

3.  Depois de concluída a implantação, crie ambientes virtuais que correspondam aos grupos de conexão publicados no App-V autônomo. O ambiente virtual deve conter os mesmos pacotes, especificamente, os tipos de implantação do App-V 5, na mesma ordem.  

Para obter mais informações sobre como criar um ambiente virtual App-V, confira [Como criar ambientes virtuais do App-V](../../apps/deploy-use/create-app-v-virtual-environments.md).  

Alternativamente, você pode excluir todos os grupos de conexões do Cliente App-V antes de iniciar a implantação de aplicativos com o Configuration Manager. No entanto, isso fará com que todas as configurações que usuários possam ter salvo em grupos de conexão do App-V sejam perdidas.  

##  <a name="dynamic-suite-composition-in-app-v-46"></a>Dynamic Suite Composition no App-V 4.6  
 O Dynamic Suite Composition é um recurso que fornece a capacidade de definir um pacote de aplicativo virtual com uma dependência em outro pacote. Quando o aplicativo é executado, o Cliente App-V hospeda os pacotes primário e dependente no mesmo ambiente virtual para o aplicativo.  

 Para usar esse recurso com o Configuration Manager, ambos os pacotes devem ser implantados e registrados com o Cliente App-V. Para garantir que o conteúdo do pacote dependente seja hospedado localmente no computador cliente, configure a implantação do aplicativo para uma entrega local (download e execução).  

 Para obter mais informações sobre o Dynamic Suite Composition do App-V, consulte a documentação do App-V.  

##  <a name="convert-app-v-46-applications-to-app-v-5-applications"></a>Converter aplicativos do App-V 4.6 para aplicativos do App-V 5  
 O formato do pacote de aplicativos foi alterado entre o App-V 4.6 e o App-V 5. Não há mais suporte para aplicativos que foram sequenciados com o uso do App-V 4.6. No entanto, o App-V 5 tem uma ferramenta de conversor de pacote que você poderá usar para converter aplicativos. Para obter mais informações, consulte a [Documentação do App-V 5](http://technet.microsoft.com/library/jj713472.aspx).  

 Use as seguintes etapas para converter aplicativos do App-V 4.6 em aplicativos do App-V 5:  

1.  Converter ou executar outra sequência de pacotes do App-V 4.6 em formato de App-V 5.  

2.  Implante o cliente App-V 5 em computadores de sua hierarquia.  

3.  Crie novos aplicativos que contenham tipos de implantação para seus aplicativos do App-V 5 e crie regras de substituição para os aplicativos do App-V 4.6.  

4.  Crie ambientes virtuais, conforme necessário.  

5.  Implante novos aplicativos do App-V 5 nos computadores.  

##  <a name="user-and-deployment-configuration-files"></a>Arquivos de configuração de usuário e da implantação  
 Arquivos de configuração de implantação e de usuário contêm configurações que controlam o comportamento de um aplicativo. Você pode usar esses arquivos para alterar as configurações do aplicativo sem ter de criar uma nova sequência do aplicativo.  

 Um aplicativo típico do App-V 5 pode conter os seguintes arquivos:  

-   Um arquivo de pacote do aplicativo (.appv).  

-   Um arquivo de configuração do usuário.  

-   Um arquivo de configuração da implantação.  

 O arquivo de configuração do usuário contém configurações que se aplicam somente ao usuário registrado. Você poderia, por exemplo, editar arquivos de configuração para alterar as informações sobre o atalho do aplicativo que será implantado aos usuários. Você também pode criar um aplicativo do Configuration Manager com vários tipos de implantação, cada um deles podendo conter um arquivo de configuração do usuário diferente e usar regras de requisitos para verificar se estão instalados nos usuários relevantes.  

 O arquivo de configuração de implantação contém configurações que se aplicam ao computador, tais como as configurações do Registro. O arquivo também pode conter configurações de usuário, que serão aplicadas a todos os usuários.  

 Se desejar implantar aplicativos virtuais do App-V 5 com o Configuration Manager, todos os três arquivos deverão estar presentes na mesma pasta em que você criar o tipo de implantação do App-V 5. Se houver vários arquivos na pasta, o Configuration Manager usará o mais recente.  

 Para obter mais informações, consulte a [Documentação do App-V 5](http://technet.microsoft.com/library/jj713466.aspx).  

##  <a name="app-v-local-interaction"></a>Interação local do App-V  
 Em alguns cenários de implantação do aplicativo, os aplicativos são instalados localmente em computadores cliente e outros aplicativos são implantados como aplicativos virtuais para o mesmo computador cliente. Por padrão, os aplicativos que foram instalados localmente não conseguem ver ou se comunicar diretamente com os aplicativos virtualizados. Este é o comportamento pretendido do isolamento de aplicativo fornecido pelo App-V. A interação local é um recurso do Cliente do App-V que pode ser habilitado para cada aplicativo, a fim de permitir que os aplicativos instalados localmente executados em um computador cliente vejam e se comuniquem com os aplicativos virtualizados. O Configuration Manager e o App-V dão suporte completo à interação local.  

 Para obter mais informações sobre o recurso de Integração Local do App-V, consulte a documentação do App-V.  

##  <a name="app-v-5-shared-content-store"></a>Repositório de conteúdo compartilhado do App-V 5  
 O recurso de Repositório de Conteúdo Compartilhado do App-V 5 tem suporte pelo Configuration Manager. Para obter mais informações, consulte [Planejamento para o App-V 5.0 Shared Content Store (SCS)](http://technet.microsoft.com/library/jj713431.aspx).  

##  <a name="monitor-virtual-applications"></a>Monitorar aplicativos virtuais  

### <a name="virtual-application-reports"></a>Relatórios de aplicativos virtuais  
 Você pode usar os relatórios a seguir para monitorar o App-V no ambiente do Configuration Manager:  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|Resultados do Ambiente Virtual do App-V|Exibe informações sobre um ambiente virtual selecionado que está em um estado especificado para uma coleção selecionada (App-V 5 somente).|  
|Resultados do ambiente virtual App-V para ativo|Exibe informações sobre um ambiente virtual selecionado para um ativo especificado e qualquer tipo de implantação do ambiente virtual selecionado (App-V 5 somente).|  
|Status do ambiente virtual do App-V|Exibe as informações de conformidade de um ambiente virtual selecionado para um coletado selecionado. A coluna **Mantido** nesse relatório exibe os ativos nos quais o ambiente virtual configurado anteriormente não é mais aplicável, mas ele é mantido para persistir nas configuração do usuário dos aplicativos que executam no ambiente virtual (App-V 5 somente).|  
|Computadores com um determinado aplicativo virtual|Exibe um resumo de computadores que possuem o atalho do App-V especificado, que foi criado pelo Sequenciador de Gerenciamento de Virtualização de Aplicativo (App-V 4.6 somente).|  
|Computadores com um determinado pacote de aplicativo virtual|Exibe uma lista de computadores que possuem o pacote de aplicativo App-V instalado (apenas para o App-V 4.6).|  
|Contar todas as instâncias de pacotes de aplicativos virtuais|Exibe uma contagem de todos os pacotes de aplicativos do App-V detectados (apenas para o App-V 4.6).|  
|Contar todas as instâncias de aplicativos virtuais|Exibe uma contagem de todos os aplicativos do App-V detectados (apenas para o App-V 4.6).|  

## <a name="log-files"></a>Arquivos de log  
 O Configuration Manager registra informações sobre implantações de aplicativo virtual em arquivos de log. Para obter informações sobre os arquivos de log que são usados por aplicativos virtuais e gerenciamento de aplicativos do Configuration Manager, confira [Log files in System Center Configuration Manager](../../core/plan-design/hierarchy/log-files.md) (Arquivos de log no System Center Configuration Manager).  

 Além disso, você pode encontrar registros para o cliente App-V, nos seguintes locais:  

-   Windows Vista, Windows 7 e Windows 8: **C:\ProgramData\Microsoft\Application Virtualization Client**  



<!--HONumber=Nov16_HO1-->

