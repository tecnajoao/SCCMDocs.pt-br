---
title: Análise de Área de Trabalho
titleSuffix: Configuration Manager
description: Uma visão geral do serviço de análise de área de trabalho integrado com o Configuration Manager.
ms.date: 01/25/2019
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: overview
ms.assetid: 38b2bed2-20dd-4ce1-abc0-219343d2c4b8
author: aczechowski
ms.author: aaroncz
manager: dougeby
ROBOTS: NOINDEX
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8602db7ece8d786598eb419eb855f1c77cff35ca
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56754553"
---
# <a name="what-is-desktop-analytics"></a>O que é análise de área de trabalho?

> [!Note]  
> Essas informações se relaciona a um serviço de visualização que pode ser substancialmente modificado antes do lançamento comercial. A Microsoft não oferece garantias, expressas ou implícitas, quanto às informações fornecidas aqui.  

Análise da área de trabalho é um serviço baseado em nuvem que se integra com o Configuration Manager. O serviço fornece insight e inteligência para que você possa tomar decisões mais informadas sobre a preparação de atualização de seus clientes Windows e do Office. Ele combina dados de sua organização com os dados agregados de milhões de dispositivos conectados aos serviços de nuvem da Microsoft. 

Use análise da área de trabalho com o Configuration Manager para:  

- Criar um inventário de aplicativos em execução em sua organização  

- Avaliar a compatibilidade de aplicativo com as últimas atualizações de recurso do Windows 10 e Office 365 ProPlus  

- Identificar problemas de compatibilidade e receba sugestões de atenuação com base em análises de dados habilitados para a nuvem  

- Criar grupos piloto que representam o estado de aplicativo e o driver inteiro em um conjunto mínimo de dispositivos  

- Implantar o Windows 10 e Office 365 ProPlus em dispositivos de piloto e de gerenciamento de produção  

![Captura de tela da página inicial da área de trabalho de análise no portal do Azure](media/portal-home.png)

> [!Note]  
> Análise da área de trabalho é um sucessor do Windows Analytics. O *Windows Analytics* serviço inclui o Upgrade Readiness, a conformidade da atualização e a integridade do dispositivo. 
> 
> Todos esses recursos são combinados na *análise de área de trabalho* service. Análise da área de trabalho também está mais fortemente integrado com o Configuration Manager e inclui o Windows e do Office. 



## <a name="benefits"></a>Benefícios

Muitos clientes enfrentam desafios para com a obtenção e mantendo-se atualizado com o Windows 10 e Office 365 ProPlus. O principal desafio é testar aplicativos. Esse processo é geralmente manual. Ele é demorado para os administradores de TI e os proprietários do aplicativo analisar continuamente os aplicativos existentes. Em seguida, corrigi quaisquer problemas que surgem. 

Análise da área de trabalho fornece os seguintes benefícios:

- **Inventário de dispositivo e software**: Inventário de fatores importantes, como aplicativos, suplementos, macros e versões do Office e do Windows.  

- **Criar um piloto identificação**: Identificação do menor conjunto de dispositivos que fornecem a cobertura mais ampla de fatores. Ele aborda os fatores que são mais importantes para um piloto de atualizações e upgrades do Windows e do Office. Verificando se que o piloto é mais bem-sucedida permite que você prosseguir com mais rapidez e confiança para implantações amplas em produção.  

- **A identificação do problema**: Usando dados de mercado agregados, juntamente com os dados do seu ambiente, o serviço prevê potencial emite para obtenção e mantendo-se atualizado com o Windows e do Office. Ele sugere possíveis mitigações.  

- **Integração do Configuration Manager**: O serviço de nuvem-permite que sua infraestrutura local existente. Use esses dados e análise para implantar e gerenciar o Windows e do Office em seus dispositivos.  



## <a name="prerequisites"></a>Pré-requisitos

Para usar a análise de área de trabalho, verifique se o que seu ambiente atenda aos seguintes pré-requisitos. 


### <a name="technical"></a>Técnico

- Uma assinatura do Azure Active Directory  

    - **Administrador da empresa** permissões no Azure  

- Configuration Manager, versão 1810 com pacote cumulativo de atualizações 4486457 ou posterior. Para obter mais informações, consulte [atualização do Configuration Manager](/sccm/desktop-analytics/connect-configmgr#bkmk_hotfix).  

    - **Administrador completo** função no Configuration Manager  

- Dispositivos que executam o Windows 7, Windows 8.1 ou Windows 10  

    - Instale as atualizações mais recentes. Para obter mais informações, consulte [atualizar dispositivos](/sccm/desktop-analytics/enroll-devices#update-devices).  

    - Dispositivos também precisam ter o cliente do Configuration Manager, versão 1810 com pacote cumulativo de atualizações 4486457 ou posterior. Para obter mais informações, consulte [atualização do Configuration Manager](/sccm/desktop-analytics/connect-configmgr#bkmk_hotfix).  

- Dados de diagnóstico do Windows. Para obter mais informações, consulte os seguintes artigos:  

    - [Níveis de dados de diagnóstico](/sccm/desktop-analytics/enable-data-sharing#diagnostic-data-levels)  

    - [Privacidade da área de trabalho de análise](/sccm/desktop-analytics/privacy)  

- Conectividade de rede de dispositivos para a nuvem pública da Microsoft. Para obter mais informações, consulte [como habilitar o compartilhamento de dados](/sccm/desktop-analytics/enable-data-sharing)  


### <a name="licensing"></a>Licenciamento

A maioria dos recursos na área de trabalho de análise não exigem qualquer licenças adicionais ou assinaturas. Quando configurado corretamente, o uso da área de trabalho de análise não incorre em custos do Azure. 

Para acessar os insights de integridade do Windows ou para exportar dados, existem requisitos de licença adicionais. Se você não tiver uma das seguintes assinaturas, você pode configurar e usar a análise de área de trabalho, mas você não é licenciados para usar o insights de integridade do Windows ou para exportar dados:

- Windows 10 Enterprise ou Windows 10 Education: por dispositivo com Software Assurance ativo  

- Windows 10 Enterprise E3 ou E5: assinatura por dispositivo ou por usuário (incluída com o Microsoft 365 F1, E3 ou E5)  

- Windows 10 Education A3 ou A5 (incluído com o Microsoft 365 educação A3 ou A5)  

- Windows Virtual Desktop Access E3 ou E5: por dispositivo de assinatura por usuário  

> [!Note]  
> Para licenças por dispositivo, você não precisa ativar cada dispositivo com uma licença. Você precisa apenas licenças suficientes para dispositivos registrados na área de trabalho de análise.  


<!-- 
## Top task
> *Optional*  
> *An effective way to structure your overview article is to create an H2 for the top customer tasks and describe how the product/service helps customers with that task.*  
> *Create a new H2 for each task you list.*  
 -->



## <a name="next-steps"></a>Próximas etapas

O tutorial a seguir fornece um guia passo a passo de Introdução ao Desktop Analytics e o Configuration Manager:  

- [Implantar um piloto do Office 365](/sccm/desktop-analytics/tutorial-office-365)  

<!-- for future
- [Deploy Windows 10 to a pilot](/sccm/desktop-analytics/tutorial-windows)  
-->
