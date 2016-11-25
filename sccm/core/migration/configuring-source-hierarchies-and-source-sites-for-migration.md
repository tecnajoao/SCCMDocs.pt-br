---
title: "Hierarquias de origem de migração | System Center Configuration Manager"
description: "Configure uma hierarquia de origem e sites de origem para que você possa migrar dados para seu ambiente do System Center Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ccce7cb5-e18f-4337-8adf-2018edca3c00
caps.latest.revision: 5
caps.handback.revision: 0
author: Brenduns
ms.author: brenduns
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 75b1515f85787cefc60d98d6f6affa3a447a39f2


---
# <a name="configuring-source-hierarchies-and-source-sites-for-migration-to-system-center-configuration-manager"></a>Configurando hierarquias de origem e sites de origem para migração para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Para habilitar a migração de dados para o seu ambiente do System Center Configuration Manager, é necessário configurar uma hierarquia de origem do Configuration Manager com suporte e um ou mais sites de origem nessa hierarquia que contenham os dados que você deseja migrar.  

> [!NOTE]  
>  As operações de migração são executadas no site de nível superior na hierarquia de destino. Se você configurar a migração ao usar um console do Configuration Manager que esteja conectado a um site primário filho, será necessário aguardar para que a configuração replique para o site da administração central, para iniciar e para replicar o status novamente para o site primário ao qual você está conectado.  

 Use as informações e os procedimentos nas seções a seguir para especificar a hierarquia de origem e adicionar outros sites de origem. Após concluir esses procedimentos, você poderá criar trabalhos de migração e começar a migrar dados da hierarquia de origem para a hierarquia de destino.  

-   [Especificar uma hierarquia de origem para migração](#BKBM_ConfigSrcHierarchy)  

-   [Identificar sites de origem adicionais da hierarquia de origem](#BKBM_ConfigSrcSites)  

##  <a name="a-namebkbmconfigsrchierarchya-specify-a-source-hierarchy-for-migration"></a><a name="BKBM_ConfigSrcHierarchy"></a> Especificar uma hierarquia de origem para migração  
 Para migrar dados para a sua hierarquia de destino, é necessário especificar uma hierarquia de destino suportada que contenha os dados que deseja migrar. Por padrão, o site de nível superior dessa hierarquia torna-se um site de origem da hierarquia de origem. Se você migrar de uma hierarquia do Configuration Manager 2007, após a coleta de dados do site de origem inicial, será possível configurar sites de origem adicionais para migração. Se você migrar de uma hierarquia do System Center 2012 Configuration Manager ou do System Center Configuration Manager, não será necessário configurar sites de origem adicionais para migrar dados da hierarquia de origem. Isso se deve ao fato de que estas versões do Configuration Manager usam um banco de dados compartilhado disponível no site de nível superior da hierarquia de origem. O banco de dados compartilhado contém todas as informações que você pode migrar.  

 Use os procedimentos a seguir para especificar uma hierarquia de origem para migração e para identificar sites de origem adicionais em uma hierarquia do Configuration Manager 2007.  

 Realize este procedimento com um console do Configuration Manager conectado à hierarquia de destino.  

#### <a name="to-configure-a-source-hierarchy"></a>Para configurar uma hierarquia de origem  

1.  No console do Configuration Manager, clique em **Administração**.  

2.  No espaço de trabalho **Administração** , expanda **Migração**e clique em **Hierarquia de Origem**.  

3.  Na guia **Início** , no grupo **Migração** , clique em **Especificar Hierarquia de Origem**.  

4.  Na caixa de diálogo **Especificar Hierarquia de Origem** , para **Hierarquia de Origem**, selecione **Nova Hierarquia de Origem**.  

5.  Para **Servidor do site do Configuration Manager da camada superior**, insira o nome ou endereço IP do site de nível superior de uma hierarquia de origem com suporte.  

6.  Especifique as contas de acesso do site de origem que têm as seguintes permissões:  

    -   Conta do site de origem: Permissão de **Leitura** ao Provedor de SMS para o site de nível superior especificado na hierarquia de origem.  

    -   Conta do banco de dados do site de origem: Permissão de **Leitura** e **Executar** ao banco de dados do SQL Server para o site de nível superior especificado na hierarquia de origem.  

     Se você especificar o uso da conta de computador, o Configuration Manager usará a conta de computador do site de nível superior da hierarquia de destino. Para essa opção, certifique-se de que essa conta é membro do grupo de segurança **Distributed COM - Usuários** no domínio em que reside o site de nível superior da hierarquia de origem.  

7.  Para compartilhar pontos de distribuição entre as hierarquias de origem e de destino, marque a caixa de seleção **Habilitar o compartilhamento de ponto de distribuição para o servidor do site de origem** . Se você não habilitar o compartilhamento do ponto de distribuição agora, você poderá fazê-lo após a conclusão da coleta de dados editando as credenciais do site de origem.  

8.  Clique em **OK** para salvar a configuração. Esse procedimento abrirá a caixa de diálogo **Status da Coleta de Dados** , e a coleta de dados será iniciada automaticamente.  

9. Quando a coleta de dados for concluída, clique em **Fechar** para fechar a caixa de diálogo **Status da Coleta de Dados** e concluir a configuração.  

##  <a name="a-namebkbmconfigsrcsitesa-identify-additional-source-sites-of-the-source-hierarchy"></a><a name="BKBM_ConfigSrcSites"></a> Identificar sites de origem adicionais da hierarquia de origem  
 Quando você configura uma hierarquia de origem suportada, o site de nível superior dessa hierarquia é automaticamente configurado como um site de origem e os dados são automaticamente coletados. A próxima ação que você executar dependerá da versão do Configuration Manager executada pela hierarquia de origem:  

-   Para uma hierarquia de origem do Configuration Manager 2007, após a conclusão da coleta de dados para o site de origem inicial, será possível iniciar a migração apenas nesse site de origem ou configurar sites de origem adicionais na hierarquia de origem. Seria possível configurar sites de origem adicionais para uma hierarquia do Configuration Manager 2007 para migrar dados disponíveis apenas de um site filho. Por exemplo, você poderia configurar sites de origem adicionais para coletar dados sobre o conteúdo que você deseja migrar quando este conteúdo foi criado em um site filho na hierarquia de origem e não está disponível no site de nível superior da hierarquia de origem.  

-   Para uma hierarquia de origem do System Center 2012 Configuration Manager ou do System Center Configuration Manager, não é necessário configurar sites de origem adicionais. Isso se deve ao fato de essas versões do Configuration Manager usarem um banco de dados compartilhado disponível no site de nível superior da hierarquia de origem. O banco de dados compartilhado contém todas as informações que você pode migrar de todos os sites na hierarquia de origem. Isso resulta na disponibilização dos dados que você pode migrar do site de nível superior da hierarquia de origem.  

Quando você configura sites de origem adicionais para uma hierarquia de origem do Configuration Manager 2007, é necessário configurar sites de origem adicionais do nível superior até o nível inferior da hierarquia. É necessário configurar um site pai como um site de origem antes de configurar qualquer um de seus sites filho como sites de origem.  

Use o procedimento a seguir para configurar sites de origem adicionais para hierarquias de origem do Configuration Manager 2007.  

#### <a name="to-identify-additional-source-sites-in-the-source-hierarchy"></a>Para identificar sites de origem adicionais na hierarquia de origem  

1.  No console do Configuration Manager, clique em **Administração**.  

2.  No espaço de trabalho **Administração** , expanda **Migração**e clique em **Hierarquia de Origem**.  

3.  Clique no site que deseja configurar como um site de origem.  

4.  Na guia **Início** , no grupo **Site de Origem** , clique em **Configurar**.  

5.  Na caixa de diálogo **Credenciais do Site de Origem** , para as contas de acesso do site de origem, especifique as contas que têm as seguintes permissões:  

    -   Conta do site de origem: Permissão de **Leitura** ao Provedor de SMS para o site de nível superior especificado na hierarquia de origem.  

    -   Conta do banco de dados do site de origem: Permissão de **Leitura** e **Executar** ao banco de dados do SQL Server para o site de nível superior especificado na hierarquia de origem.  

    Se você especificar o uso da conta de computador, o Configuration Manager usará a conta de computador do site de nível superior da hierarquia de destino. Para essa opção, certifique-se de que essa conta é membro do grupo de segurança **Distributed COM - Usuários** no domínio em que reside o site de nível superior da hierarquia de origem.  

6.  Para compartilhar pontos de distribuição entre as hierarquias de origem e de destino, marque a caixa de seleção **Habilitar o compartilhamento de ponto de distribuição para o servidor do site de origem** . Se você não habilitar o compartilhamento do ponto de distribuição agora, você poderá fazê-lo após a conclusão da coleta de dados editando as credenciais do site de origem.  

7.  Clique em **OK** para salvar a configuração. Esse procedimento abrirá a caixa de diálogo **Status da Coleta de Dados** , e a coleta de dados será iniciada automaticamente.  

8.  Quando a coleta de dados for concluída, clique em **Fechar** para finalizar a configuração.  



<!--HONumber=Nov16_HO1-->

