---
title: Práticas recomendadas para coleta
titleSuffix: Configuration Manager
description: Veja as práticas recomendadas para coletas no System Center Configuration Manager.
ms.date: 2/22/2017
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: 7a2abb79-9ae5-4a25-9e18-5dcf528de3bf
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c685cf4efd5eca5f93694edd4a01715120df9a8
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56140568"
---
# <a name="best-practices-for-collections-in-system-center-configuration-manager"></a>Práticas recomendadas para coletas no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Use as práticas recomendadas a seguir para coletas no System Center Configuration Manager.  

## <a name="do-not-use-incremental-updates-for-a-large-number-of-collections"></a>Não use atualizações incrementais para um grande número de coleções  
 Quando você habilita a opção **Usar atualizações incrementais para esta coleção** , essa configuração poderá causar atrasos de avaliação ao habilitá-la para várias coleções. O limite é de cerca de 200 coleções em sua hierarquia. O número exato depende dos seguintes fatores:  

-   O número total de coleções  

-   A frequência de novos recursos adicionados e alterados na hierarquia  

-   O número de clientes na hierarquia  

-   A complexidade das regras de associação da coleção na hierarquia  

## <a name="make-sure-that-maintenance-windows-are-large-enough-to-deploy-critical-software-updates"></a>Verifique se as janelas de manutenção são grandes o suficiente para implantar atualizações de software críticas  
 Você pode configurar janelas de manutenção para coleções de dispositivos, para restringir os momentos em que o Configuration Manager pode instalar software nesses dispositivos. Se você configurar a janela de manutenção como muito pequena, o cliente não poderá instalar atualizações críticas de software, o que o deixa vulnerável ao ataque mitigado pela atualização de software.  
