---
title: "Recursos de pré-lançamento | Microsoft Docs"
description: "Recursos de pré-lançamento no System Center Configuration Manager"
ms.custom: na
ms.date: 3/29/2017
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6bce416b-761d-4b23-bd33-5b7c30edb10d
caps.latest.revision: 36
author: Brenduns
ms.author: brenduns
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 6accec2d356861b273b25ba2b6338d9684a46ff6
ms.openlocfilehash: c1c8cf505bbc5cab1b6dfb7637eda4a87941c722
ms.lasthandoff: 03/29/2017


---
# <a name="pre-release-features-in-system-center-configuration-manager"></a>Recursos de pré-lançamento no System Center Configuration Manager
*Aplica-se a: System Center Configuration Manager (Branch Atual)*

 Os recursos de pré-lançamento são recursos que estão incluídos na Ramificação atual para testes iniciais em um ambiente de produção. Esses recursos não devem ser considerados prontos para produção, mas podem ser usados em seu ambiente de produção.

 Antes de poder usar os recursos de pré-lançamento, você deverá dar consentimento para usar Recursos de pré-lançamento dentro do console do Configuration Manager antes de selecionar e habilitar seu uso.  

Dar o consentimento é uma ação única por hierarquia que não pode ser desfeita. Até dar o consentimento, você não pode habilitar novos recursos de pré-lançamento incluídos com a atualização.

Para dar consentimento, no console, vá até **Administração** > **Configuração do Site** > **Sites** e escolha **Configurações da Hierarquia**. Na guia **Geral**, escolha **Consentir com o uso de recursos de pré-lançamento**.

 > [!NOTE]
 > Se você tiver habilitado previamente os recursos de pré-lançamento da Atualização 1602, antes de instalar a versão de atualização mais recente, esses recursos permanecerão habilitados para uso mesmo que você não tenha consentido com o uso dos recursos de pré-lançamento.

Quando você instala uma atualização que inclui recursos de pré-lançamento, esses recursos são visíveis no Assistente de Atualizações e Manutenção com os recursos regulares incluídos na atualização:
  - **Se você tiver consentido:** você poderá habilitar os recursos de pré-lançamento no Assistente de Atualizações e Manutenção quando estiver instalando a atualização. Para fazer isso, selecione os recursos de pré-lançamento como faria com qualquer outro recurso.     

    Você também pode esperar para habilitar um recurso de pré-lançamento mais tarde do nó **Administração** > **Atualizações e Manutenção** > **Recursos** do console. No nó **Recursos**, escolha o recurso e escolha **Ativar**. Essa opção está esmaecida até você dar consentimento. (Antes da versão 1702, Atualizações e Manutenção ficava em **Administração** > **Serviços de Nuvem**.)
  -   **Se você não tiver consentido:** ao instalar uma atualização, os recursos de pré-lançamento ficarão visíveis no Assistente de Atualizações e Manutenção, mas ficarão esmaecidos e não poderão ser habilitados. Após a instalação da atualização, você pode exibir esses recursos no nó **Recursos**, mas não habilitá-los até que você tenha dado o consentimento nas **Configurações da Hierarquia**.

Se você tiver dado consentimento em um site primário autônomo e, depois, expandir a hierarquia instalando um novo site de administração central, você deverá dar consentimento novamente no site de administração central.

**Os seguintes recursos de pré-lançamento estão disponíveis:**

 |Recurso          |Adicionado como pré-lançamento | Adicionado como recurso completo|  
|------------------|---------------------|---------------------|
| Verificar se há arquivos executáveis antes de instalar um aplicativo  |   [Versão 1702](/sccm/apps/deploy-use/deploy-applications#how-to-check-for-running-executable-files-before-installing-an-application) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Ponto de serviço do Data Warehouse  |  [Versão 1702](/sccm/core/servers/manage/data-warehouse) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Cache de Pares para distribuição de conteúdo para clientes |  [Versão 1610](/sccm/core/plan-design/hierarchy/client-peer-cache) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Gateway de gerenciamento de nuvem |  [Versão 1610](/sccm/core/clients/manage/plan-cloud-management-gateway) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Painel Fontes de Dados do Cliente |  [Versão 1610](/sccm/core/servers/deploy/configure/monitor-content-you-have-distributed#client-data-sources-dashboard) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Conector do Microsoft Operations Management Suite  | [Versão 1606](../../../core/clients/manage/sync-data-microsoft-operations-management-suite.md) |![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
| Realização de serviços em uma coleção com reconhecimento de cluster (realização de serviços em um grupo de servidores)| [Versão 1602](../../../core/get-started/capabilities-in-technical-preview-1605.md#BKMK_ServerGroups)|![Ainda não](media/83c5d168-8faf-4e8e-920b-528e3c43ffd4.gif)|
|Acesso condicional para PCs gerenciados pelo System Center Configuration Manager | [Versão 1602](../../../protect/deploy-use/manage-access-to-o365-services-for-pcs-managed-by-sccm.md)     | [Versão 1702](/sccm/mdm/deploy-use/manage-access-to-services)                     |
