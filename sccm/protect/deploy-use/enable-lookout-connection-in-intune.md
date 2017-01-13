---
title: Habilitar o Lookout MTP no Intune | System Center Configuration Manager
description: "Habilite o Lookout Mobile Threat Protection no console de administração do Intune."
ms.custom: na
ms.date: 11/18/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9536efdd-0f29-47a8-8283-0edea7714319
caps.latest.revision: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: c13c6268fa76ade7feb0981f9c4a6e325e393aca
ms.openlocfilehash: a06f0b3a0080a06a0ccbfa7f3802c575aee2c9b7


---
# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Habilitar a conexão do Lookout MTP no console do Intune

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Este tópico mostra como habilitar a conexão do Lookout MTP no Intune. Você já deve ter configurado o Conector do Intune no console do Lookout antes de realizar essa etapa.  Se você ainda não o fez, siga as etapas descritas em [Set up your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout.md) (Configurar sua assinatura no Lookout Mobile Threat Protection).

Para habilitar a conexão do Lookout MTP no Intune, na página **Administração** no [Console do administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**. Escolha **Status da consulta** e habilite **Sincronização com MTP** usando o botão de alternância.

![captura de tela da página de sincronização do Lookout com o botão de alternância Habilitar realçado](../media/lookout-intune-synchronization.png)

Isso conclui a configuração da integração do Lookout e do Intune no console do administrador do Intune.  As próximas etapas para implementar essa solução envolvem a implantação de [Aplicativos Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) e a configuração da política de [conformidade](enable-device-threat-protection-rule-compliance-policy.md).

>[!IMPORTANT]
> Você **deve** configurar o aplicativo Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo está pronto e disponível para os usuários finais instalarem antes que possam ter acesso ao email ou outros recursos da empresa.

## <a name="next-steps"></a>Próximas etapas
[Configurar aplicativo Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO3-->

