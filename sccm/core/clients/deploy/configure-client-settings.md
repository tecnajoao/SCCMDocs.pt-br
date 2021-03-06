---
title: Definir as configurações do cliente
titleSuffix: Configuration Manager
description: Selecione as configurações do cliente no System Center Configuration Manager.
ms.date: 12/29/2017
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: 95e9858a-bad4-4651-9e61-2e31dc5050fa
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dc3b4d64511e944bd7d03feca7370d1d4b5d8b6
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56135418"
---
# <a name="how-to-configure-client-settings-in-system-center-configuration-manager"></a>Como definir as configurações do cliente no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Gerencie todas as configurações de cliente no System Center Configuration Manager em **Administração** > **Configurações do Cliente**. Modifique as configurações padrão quando quiser definir as configurações para todos os usuários e dispositivos na hierarquia que não possuírem configurações personalizadas aplicadas. Se desejar aplicar configurações diferentes a apenas alguns usuários ou dispositivos, crie configurações personalizadas e implante-as às coleções.  

Para obter informações sobre cada configuração, consulte [Sobre configurações de cliente no System Center Configuration Manager](../../../core/clients/deploy/about-client-settings.md).

> [!NOTE]  
>  É possível também usar itens de configuração para gerenciar clientes para avaliar, acompanhar e corrigir a conformidade de configuração de dispositivos. Para mais informações, consulte [Garantir a conformidade do dispositivo com o System Center Configuration Manager](../../../compliance/understand/ensure-device-compliance.md).  

##  <a name="configure-the-default-client-settings"></a>Definir as configurações padrão do cliente    

1. No console do Configuration Manager, escolha **Administração** > **Configurações do Cliente** > **Configurações do Cliente Padrão**.  

2. Na guia **Início**, escolha **Propriedades**.  

3. Exiba e defina as configurações do cliente para cada grupo de configurações no painel de navegação.  

   Os computadores cliente serão definidos com essas configurações durante o próximo download da política do cliente. Para iniciar a recuperação de política para um único cliente, consulte [Iniciar recuperação de política de um cliente do Configuration Manager](../../../core/clients/manage/manage-clients.md#BKMK_PolicyRetrieval) em [Como gerenciar clientes no System Center Configuration Manager](../../../core/clients/manage/manage-clients.md).  

##  <a name="create-and-deploy-custom-client-settings"></a>Criar e implantar configurações personalizadas do cliente  
Ao implantar essas configurações personalizadas, elas substituirão as configurações do cliente padrão. Para começar esse procedimento, verifique se você tem uma coleção que contenha os usuários ou os dispositivos que requerem essas configurações personalizadas do cliente.  

1. No console do Configuration Manager, escolha **Administração** > **Configurações do Cliente**.  

2. Na guia **Início**, no grupo **Criar**, escolha **Criar Configurações Personalizadas do Cliente** e escolha entre:  

   -   **Criar configurações personalizadas do dispositivo do cliente**  

   -   **Criar configurações personalizadas do usuário**  

3. Especifique um nome exclusivo e uma descrição opcional.  

4. Marque uma ou mais caixas de seleção que exibem um grupo de configurações.  

5. Clique em cada grupo de configurações no painel de navegação e defina as configurações disponíveis, depois clique em **OK**.   

6. Selecione a configuração personalizada do cliente que você criou. Na guia **Início**, no grupo **Configurações do Cliente**, escolha **Implantar**.  

7. Na caixa de diálogo **Selecionar Coleção**, selecione a coleção apropriada e escolha **OK**. Você pode verificar a coleção selecionada se clicar na guia **Implantações** do painel de detalhes.  

8. Exiba a ordem da configuração de cliente personalizada criada. Quando você tem várias configurações personalizadas do cliente, elas são aplicadas de acordo com o número da ordem. Se houver qualquer conflito, a configuração com o menor número de ordem substituirá as demais. Para alterar o número da ordem, na guia **Início**, no grupo **Configurações do Cliente**, escolha **Mover Item para Cima** ou **Mover Item para Baixo**.  

   Os computadores cliente serão definidos com essas configurações durante o próximo download da política do cliente. Para iniciar a recuperação de política para um único cliente, consulte [Iniciar recuperação de política de um cliente do Configuration Manager](../../../core/clients/manage/manage-clients.md#BKMK_PolicyRetrieval) em [Como gerenciar clientes no System Center Configuration Manager](../../../core/clients/manage/manage-clients.md).  



##  <a name="view-client-settings"></a>Exibir configurações do cliente  
 Quando várias configurações de cliente forem implantadas no mesmo dispositivo, usuário ou grupo de usuários, a priorização e a combinação das configurações são complexas. Para exibir as configurações do cliente:  

1.  No console do Configuration Manager, clique em **Ativos e Conformidade** > **Dispositivos** > **Usuários** ou **Coleções do Usuário**.  

3.  Selecione um dispositivo, usuário ou grupo de usuários no grupo **Configurações do Cliente** , selecione **Configurações do Cliente Resultante**.  

4.  Selecione uma configuração de cliente no painel esquerdo, e as configurações serão exibidas. Nesse modo, as configurações são somente leitura. 

    > [!NOTE]  
    >  Para exibir as configurações do cliente, você deve ter acesso de leitura às Configurações do Cliente.  

    
