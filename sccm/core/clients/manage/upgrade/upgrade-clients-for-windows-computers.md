---
title: Atualizar clientes | Windows | System Center Configuration Manager
description: Atualizar clientes em computadores Windows no System Center Configuration Manager.
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6143fd47-48ec-4bca-b53b-5b9b9f067bc3
caps.latest.revision: 11
caps.handback.revision: 0
author: Mtillman
ms.author: mtillman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 2b1600e6f04095506f18f4c2cd0988a320fbb951


---
# <a name="how-to-upgrade-clients-for-windows-computers-in-system-center-configuration-manager"></a>Como atualizar clientes para computadores Windows no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

É possível atualizar o cliente em computadores Windows usando métodos de instalação do cliente ou os recursos de atualização automática do cliente do Configuration Manager. Os seguintes métodos de instalação do cliente são maneiras válidas de atualizar o software cliente em computadores Windows:  

-   Instalação da política de grupo  

-   Instalação de script de logon  

-   Instalação manual  

-   Instalação da atualização  

 Se estiver interessado em atualizar o cliente usando métodos de instalação do cliente, saiba mais sobre como usar esses métodos em [Como implantar clientes em computadores Windows no System Center Configuration Manager](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md)  

> [!TIP]  
>  Se você estiver atualizando a infraestrutura do servidor de uma versão anterior do Configuration Manager \(como o Configuration Manager 2007 ou o System Center 2012 Configuration Manager\), será recomendável que conclua as atualizações do servidor, incluindo a instalação de todas as atualizações da ramificação atual, antes de atualizar os clientes do Configuration Manager.   A atualização mais recente da ramificação atual contém a última versão do cliente, de modo que é melhor fazer atualizações do cliente depois que você tiver instalado todas as atualizações do Configuration Manager que deseja usar.  

## <a name="use-automatic-client-upgrade"></a>Usar a atualização automática do cliente  
 Também é possível configurar o Configuration Manager para atualizar automaticamente o software cliente para a versão mais recente do cliente do Configuration Manager quando o Configuration Manager identificar que um cliente atribuído à hierarquia do Configuration Manager é inferior à versão usada na hierarquia. Este cenário inclui a atualização do cliente para a versão mais recente quando ele tenta atribuir a um site do Configuration Manager.  

 Um cliente pode ser atualizado automaticamente nos seguintes cenários:  

-   A versão do cliente é inferior à versão que está sendo usada na hierarquia.  

-   O cliente no site de administração central tem um pacote de idiomas instalado, e o cliente existente não tem.  

-   Um pré-requisito do cliente na hierarquia é uma versão diferente da instalada no cliente.  

-   Um ou mais dos arquivos de instalação do cliente são uma versão diferente.  

> [!NOTE]  
>  Você pode executar o relatório **Contagem de clientes do Gerenciador de Configurações por versões cliente** na pasta de relatórios **Site – Informações de Cliente** para identificar as versões diferentes do cliente do Configuration Manager na sua hierarquia.  

 O Configuration Manager cria um pacote de atualização por padrão que é enviado automaticamente para todos os pontos de distribuição na hierarquia. Se você fizer alterações no pacote do cliente no site de administração central, por exemplo, adicionar um pacote de idiomas do cliente, o Configuration Manager atualizará automaticamente o pacote e o distribuirá a todos os pontos de distribuição na hierarquia. Se a atualização automática do cliente estiver habilitada, cada cliente instalará automaticamente o novo pacote de idiomas do cliente.  

> [!NOTE]  
>  O Configuration Manager não envia automaticamente o pacote de atualização do cliente para os pontos de distribuição baseado em nuvem do Configuration Manager.  

 As atualizações automáticas do cliente são úteis quando você quer atualizar um pequeno número de computadores cliente que podem ter sido perdidos pelo principal método de instalação do cliente. Por exemplo, você completou uma atualização inicial do cliente, mas alguns estavam offline durante a implantação da atualização. Você usa esse método para atualizar o cliente nesses computadores da próxima vez em que estiverem ativos.  

 Use o procedimento a seguir para configurar a atualização automática do cliente. A atualização automática do cliente deve ser configurada em um site de administração central e essa configuração aplica-se a todos os clientes na hierarquia.  

#### <a name="to-configure-automatic-client-upgrades"></a>Para configurar atualizações automáticas do cliente  

1.  No console do Configuration Manager, clique em **Administração**.  

2.  No espaço de trabalho **Administração** , expanda **Configuração do Site**e clique em **Sites**.  

3.  Na guia **Início** , no grupo **Sites** , clique em **Configurações da Hierarquia**.  

4.  Na guia **Atualização do Cliente** da caixa de diálogo **Propriedades das Configurações da Hierarquia** , examine a versão e a data do cliente de produção e verifique se essa é a versão que você deseja usar para atualizar computadores com Windows.  Se essa não for a versão do cliente que você esperava ver, talvez seja necessário promover o cliente de pré-produção para produção. Para mais informações, consulte [Como testar atualizações do cliente em uma coleção de pré-produção no System Center Configuration Manager](../../../../core/clients/manage/upgrade/test-client-upgrades.md).  

5.  Clique em **Atualizar todos os clientes na hierarquia usando o cliente de produção** e clique em **OK** na caixa de diálogo de confirmação.  

6.  Se não quiser que as atualizações do cliente se apliquem a servidores, clique em **Não atualizar servidores**.  

7.  Especifique o número de dias nos quais os computadores devem atualizar o cliente depois de receberem a política do cliente. O cliente será atualizado em um intervalo aleatório dentro desse número de dias. Isso impede cenários onde um grande número de computadores cliente é atualizado simultaneamente.

    > [!NOTE]
    > Um computador deve estar em execução para atualizar o cliente. Se um computador não estiver em execução quando estiver agendado para receber a atualização, esta não ocorrerá. Em vez disso, quando o computador for reiniciado, outra atualização estará agendada para um horário aleatório dentro do número de dias permitido. Se isso ocorrer depois que o número de dias para atualização expirar, a atualização será agendada para ocorrer em um horário aleatório dentro de 24 horas após a reinicialização do computador.
    >     
    > Devido a esse comportamento, computadores que são rotineiramente desligados ao final do dia de trabalho poderão demorar mais do que o esperado para atualizar se o tempo de atualização agendado aleatoriamente não estiver dentro do horário normal de trabalho.

8.  Se desejar que o pacote de instalação do cliente seja copiado nos pontos de distribuição que foram habilitados para o conteúdo pré-configurado, clique em **Distribuir automaticamente o pacote de instalação do cliente para pontos de distribuição que são habilitados para o conteúdo pré-configurado**.  

9. Clique em **OK** para salvar as configurações e fechar a caixa de diálogo **Propriedades das Configurações da Hierarquia** . Os clientes recebem essas configurações no próximo download da política.  



<!--HONumber=Nov16_HO1-->

