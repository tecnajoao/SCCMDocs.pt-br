---
title: "Segurança e privacidade do gerenciamento de energia | System Center Configuration Manager"
description: "Obtenha as informações de segurança e privacidade do gerenciamento de energia no System Center Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 469ff35f-59a1-484d-902b-107dd6070baf
caps.latest.revision: 5
caps.handback.revision: 0
author: robstackmsft
ms.author: robstack
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 26880f6682e2bdf61cb7f29416e5dfded3559e8e


---
# <a name="security-and-privacy-for-power-management-in-system-center-configuration-manager"></a>Segurança e privacidade do gerenciamento de energia no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Esta seção contém as informações de segurança e privacidade do gerenciamento de energia no System Center Configuration Manager.  

## <a name="security-best-practices-for-power-management"></a>Práticas recomendadas de segurança para o gerenciamento de conteúdo  
 Não há práticas recomendadas relacionadas à segurança para o gerenciamento de energia.  

## <a name="privacy-information-for-power-management"></a>Informações sobre privacidade para o gerenciamento de conteúdo  
 O gerenciamento de energia usa recursos que são integrados ao Windows para monitorar o consumo de energia e aplicar as configurações de energia a computadores durante o horário comercial e fora dele. O Configuration Manager coleta informações de consumo de energia de computadores, o que inclui dados sobre o período em que um usuário está usando um computador. Embora o Configuration Manager monitore o consumo de energia para uma coleção em vez de para cada computador, uma coleção pode conter apenas um computador. Por padrão, o gerenciamento de energia não está habilitado e deve ser configurado por um administrador.  

 As informações de consumo de energia são armazenadas no banco de dados do Configuration Manager e não são enviadas à Microsoft. As informações detalhadas são mantidas no banco de dados durante 31 dias e as informações resumidas são mantidas por 13 meses. Não é possível configurar o intervalo de exclusão.  

 Antes de configurar o gerenciamento de energia, considere seus requisitos de privacidade.  



<!--HONumber=Nov16_HO1-->

