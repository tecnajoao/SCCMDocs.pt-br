---
title: Firewalls e domínios
titleSuffix: Configuration Manager
description: Configure firewalls, portas e domínios para preparar-se para comunicações do System Center Configuration Manager.
ms.date: 2/6/2017
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: d6993bba-f6bd-4639-adbf-efc1c638b2f3
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cc3a1532a326019db3517c70723831f309be76b
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56127126"
---
# <a name="set-up-firewalls-ports-and-domains-for-system-center-configuration-manager"></a>Configurar firewalls, portas e domínios para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Para preparar sua rede para dar suporte ao System Center Configuration Manager, planeje a configuração da infraestrutura, como firewalls, para passar as comunicações usadas pelo Configuration Manager.  

|Consideração|Detalhes|  
|-------------------|-------------|  
|**Portas e protocolos** usados por diferentes recursos do Configuration Manager. Algumas portas são necessárias, enquanto **domínios e serviços** podem ser personalizados.|A maioria das comunicações do Configuration Manager usa portas comuns, como a porta 80 para HTTP ou 443 para comunicação HTTPS. Entretanto, [algumas funções do sistema de sites dão suporte ao uso de sites personalizados](/sccm/core/plan-design/network/websites-for-site-system-servers) e portas personalizadas.<br /><br /> **Antes de implantar o Configuration Manager**, identifique as portas que você planeja usar e configure os firewalls de acordo.<br /><br /> Mais tarde, **se você precisar alterar uma porta** após instalar o Configuration Manager, não se esqueça de atualizar os firewalls nos dispositivos e na rede, além de alterar a configuração da porta de dentro do Configuration Manager.<br /><br /> Para obter mais informações, consulte: </br>- [Como configurar as portas de comunicação do cliente](../../../core/clients/deploy/configure-client-communication-ports.md) </br>- [Portas usadas no Configuration Manager](../../../core/plan-design/hierarchy/ports.md) </br>- [Requisitos de acesso à Internet para o ponto de conexão de serviço](/sccm/core/servers/deploy/configure/about-the-service-connection-point#bkmk_urls)|  
|**Domínios e serviços** que clientes e servidores de sites talvez precisem acessar.|Os recursos do Configuration Manager podem exigir que clientes e servidores do site tenham acesso a serviços e domínios específicos na Internet, como o Windowsudpate.microsoft.com ou o serviço Microsoft Intune.<br /><br /> Se você usa o Microsoft Intune para gerenciar dispositivos móveis, também deve configurar o acesso a [portas e domínios exigidos pelo Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)|  
|**Servidores proxy** para servidores de sistema de sites e para comunicações do cliente. Você pode especificar servidores proxy separados para clientes e servidores de sistema de sites diferentes.|Como essas configurações são feitas quando você instala uma função de sistema de sites ou cliente, você só precisar tomar conhecimento das configurações do servidor proxy para referência futura ao configurar funções de sistemas de sites e clientes.<br /><br /> Se você não tiver certeza se sua implantação precisará usar servidores proxy, examine [Suporte ao servidor proxy no System Center Configuration Manager](../../../core/plan-design/network/proxy-server-support.md) para saber mais sobre as funções de sistemas de sites e ações de cliente que podem usar um servidor proxy.|   
|  
