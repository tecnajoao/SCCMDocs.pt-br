---
title: Segurança e privacidade de consultas
titleSuffix: Configuration Manager
description: Entenda as práticas recomendadas de segurança e privacidade quando você consulta informações do banco de dados do site.
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 30080620-20d3-4c38-b8dd-db5516e1acae
author: aczechowski
manager: dougeby
ms.author: aaroncz
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7cdd9731b2ae34e096159b9e73c730fcbd7ac728
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56121525"
---
# <a name="security-and-privacy-for-queries-in-system-center-configuration-manager"></a>Segurança e privacidade de consultas no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

As consultas no System Center Configuration Manager permitem recuperar informações do banco de dados do site com base nos critérios que você especificar. O Configuration Manager coleta informações de banco de dados do site durante a operação padrão. Por exemplo, usando as informações coletadas de descoberta ou inventário, você pode configurar uma consulta para identificar os dispositivos que atendem aos critérios especificados.  

 Para obter mais informações sobre consultas, consulte [Introdução a consultas no System Center Configuration Manager](../../../core/servers/manage/introduction-to-queries.md). Para saber mais sobre as práticas recomendadas de segurança e informações de privacidade para as operações do Configuration Manager que coletam as informações que podem ser recuperadas por meio de consultas, veja [Segurança e privacidade no System Center Configuration Manager](../../../core/plan-design/security/security-and-privacy.md).  

## <a name="security-best-practices-for-queries"></a>Práticas recomendadas de segurança para consultas  
 Use a prática recomendada de segurança a seguir para consultas.  

|Prática recomendada de segurança|Mais informações|  
|----------------------------|----------------------|  
|Ao exportar ou importar uma consulta que é salva em um local da rede, proteja o local e o canal da rede.|Restrinja quem pode acessar a pasta de rede.<br /><br /> Use a assinatura do protocolo SMB ou IPsec entre o local de rede e o servidor do site para impedir que um invasor viole os dados da consulta antes que sejam importados.|  

## <a name="see-also"></a>Consulte também  
 [Referência técnica de consultas no System Center Configuration Manager](../../../core/servers/manage/queries-technical-reference.md)
