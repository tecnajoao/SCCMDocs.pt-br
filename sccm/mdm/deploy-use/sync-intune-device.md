---
title: "Sincronizar remotamente a política para dispositivos registrados com o Intune | Microsoft Docs"
description: "Saiba como sincronizar a política em dispositivos registrados no Intune pelo console do Configuration Manager"
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-hybrid
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b3731ad0-2a24-4042-994e-5e4c1230e3fe
caps.latest.revision: 18
caps.handback.revision: 0
author: robstackmsft
ms.author: robstack
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: dcdccc34fa55ce3d3e4459d209c7aeb74752214b
ms.openlocfilehash: c6496e9694314f1910ca944f6c083a9f3fd2bf79

---
# <a name="remotely-synchronize-policy-on-intune-enrolled-devices-from-the-configuration-manager-console"></a>Sincronizar remotamente a política em dispositivos registrados no Intune pelo console do Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*


Você pode solicitar uma sincronização de política em um dispositivo registrado no Intune pelo console do Configuration Manager, em vez de precisar solicitar uma sincronização no aplicativo Portal da Empresa no próprio dispositivo. 

Para fazer isso:

1.  Selecione um dispositivo em **Ativos e Conformidade** > **Visão Geral** > **Dispositivos**.
2.  Clique em **Enviar Solicitação de Sincronização** no menu **Ações de Dispositivo Remoto**.


Depois de cinco a dez minutos, todas as alterações na política serão sincronizadas com o dispositivo. É possível exibir as informações de estado de solicitação de sincronização em uma nova coluna nos modos de exibição do dispositivo, chamada **Estado de Sincronização Remota**, bem como na seção de dados de descoberta da caixa de diálogo **Propriedades** para cada dispositivo.



<!--HONumber=Dec16_HO3-->

