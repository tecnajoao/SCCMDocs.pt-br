---
title: Dados de diagnóstico e de uso
titleSuffix: Configuration Manager
description: Saiba mais sobre os dados de diagnóstico e de uso que o System Center Configuration Manager coleta sobre si mesmo.
ms.date: 11/27/2018
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 88ac4e55-d47b-4c94-b9c3-704c6a48b845
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: c4341ba1866405f17d4a4b7b8cb24e933ab57a20
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56119315"
---
# <a name="diagnostics-and-usage-data-for-system-center-configuration-manager"></a>Dados de diagnóstico e de uso para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

O Configuration Manager coleta dados de diagnóstico e de uso sobre si mesmo, que são usados pela Microsoft para aprimorar a experiência de instalação, a qualidade e a segurança de versões futuras.  

 Os dados de diagnóstico e de uso são habilitados para cada hierarquia do Configuration Manager. Eles consistem em consultas do SQL Server que são executadas semanalmente em cada site primário e no site de administração central. Quando a hierarquia usa um site de administração central, os dados dos sites primários são replicados nesse site. No site de nível superior da hierarquia, o ponto de conexão de serviço envia essas informações quando verifica se há atualizações. Se o ponto de conexão de serviço estiver no modo offline, as informações serão transferidas por meio da ferramenta de conexão de serviço.  

> [!NOTE]  
>  O Configuration Manager coleta dados apenas do banco de dados SQL Server do site e não coleta dados diretamente de clientes ou de servidores do site.  

 Para obter mais informações, consulte a [Política de privacidade da Microsoft](https://go.microsoft.com/fwlink/?LinkID=626527).  

## <a name="articles"></a>Artigos
 Saiba mais sobre os dados de diagnóstico e de uso do Configuration Manager nos seguintes artigos:  

-   [Como os dados de diagnóstico e de uso são usados](/sccm/core/plan-design/diagnostics/how-diagnostics-and-usage-data-is-used)  

-   Níveis da coleta de dados de diagnóstico e de uso:
    - [ados de diagnóstico para a versão 1810](/sccm/core/plan-design/diagnostics/levels-of-diagnostic-usage-data-collection-1810)  

    - [Dados de diagnóstico para 1806](/sccm/core/plan-design/diagnostics/levels-of-diagnostic-usage-data-collection-1806)  

    - [Dados de diagnóstico para 1802](/sccm/core/plan-design/diagnostics/levels-of-diagnostic-usage-data-collection-1802)  
    
    - [Dados de diagnóstico para 1710](/sccm/core/plan-design/diagnostics/levels-of-diagnostic-usage-data-collection-1710)  

-   [Como os dados de diagnóstico e de uso são coletados](/sccm/core/plan-design/diagnostics/how-diagnostics-and-usage-data-is-collected)  

-   [Como exibir dados de diagnóstico e de dados](/sccm/core/plan-design/diagnostics/view-diagnostics-and-usage-data)  

-   [CEIP (Programa de Aperfeiçoamento da Experiência do Usuário)](/sccm/core/plan-design/diagnostics/customer-experience-improvement-program-ceip)  

     > [!Note]  
     > A partir do Configuration Manager versão 1802, o recurso Programa de Aperfeiçoamento da Experiência do Usuário é removido do produto.  


-   [Perguntas frequentes sobre dados de diagnóstico e de uso](/sccm/core/understand/frequently-asked-questions-about-diagnostics-and-usage-data)  



## <a name="see-also"></a>Consulte também  
 [Sobre o ponto de conexão de serviço](/sccm/core/servers/deploy/configure/about-the-service-connection-point)
