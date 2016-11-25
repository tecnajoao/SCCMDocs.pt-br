---
title: Atualizar clientes | System Center Configuration Manager
description: "Obter informações sobre como atualizar clientes no System Center Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 446c83b5-c292-4e74-ba19-0792ac6b3472
caps.latest.revision: 8
author: Mtillman
ms.author: mtillman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 1571d31af1e2697c5ecbdc709a3eea9d6e28dbf0


---
# <a name="upgrade-clients-in-system-center-configuration-manager"></a>Atualizar clientes no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

É possível usar métodos diferentes para atualizar o software cliente do System Center Configuration Manager em computadores Windows, servidores UNIX/Linux e computadores Mac da sua empresa. As seções a seguir descrevem as vantagens e desvantagens de cada método de atualização de cliente para ajudar determinar qual deles é o melhor para sua organização.  

> [!TIP]  
>  Se você estiver atualizando a infraestrutura do servidor de uma versão anterior do Configuration Manager \(como o Configuration Manager 2007 ou o System Center 2012 Configuration Manager\), será recomendável que conclua as atualizações do servidor, incluindo a instalação de todas as atualizações da ramificação atual, antes de atualizar os clientes do Configuration Manager.   A atualização mais recente da ramificação atual contém a última versão do cliente, de modo que é melhor fazer atualizações do cliente depois que você tiver instalado todas as atualizações do Configuration Manager que deseja usar.  

## <a name="group-policy-installation"></a>Instalação de Política de Grupo  
 **Plataforma de cliente com suporte:** Windows  

 **Vantagens**  

-   Não exige que os computadores sejam descobertos para que o cliente possa ser atualizado.  

-   Pode ser usada para novas instalações de cliente ou para atualizações.  

-   Os computadores podem ler as propriedades de instalação de cliente publicadas nos Serviços de Domínio Active Directory .  

-   Não exige que você configure e mantenha uma conta de instalação para o computador cliente desejado.  

 **Desvantagens**  

-   Poderá causar alto tráfego de rede se um grande número de clientes estiver sendo atualizado.  

-   Se o esquema do Active Directory não for estendido para o Configuration Manager, use as configurações de Política de Grupo para adicionar propriedades de instalação de cliente aos computadores em seu site.  

 Para obter mais informações, consulte [How to Install Configuration Manager Clients by Using Group Policy](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientGP) (Como instalar clientes do Configuration Manager usando a política de grupo).  

## <a name="logon-script-installation"></a>Instalação de script de logon  
 **Plataforma de cliente com suporte:** Windows  

 **Vantagens**  

-   Não exige que os computadores sejam descobertos para que o cliente possa ser instalado.  

-   Pode ser usada para novas instalações de cliente ou para atualizações.  

-   Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

 **Desvantagens**  

-   Poderá causar um alto tráfego de rede se um grande número de clientes estiver sendo atualizado em um curto período de tempo.  

-   Poderá demorar muito para ser atualizado em todos os computadores cliente se os usuários não fizerem logon na rede com frequência.  

 Para obter mais informações, consulte [How to Install Configuration Manager Clients by Using Logon Scripts](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientLogonScript) (Como instalar clientes do Configuration Manager usando scripts de logon).  

## <a name="manual-installation"></a>Instalação manual  
 **Plataforma de cliente com suporte:** Windows, UNIX/Linux, Mac OS X  

 **Vantagens**  

-   Não exige que os computadores sejam descobertos para que o cliente possa ser atualizado.  

-   Pode ser útil para fins de teste.  

-   Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

 **Desvantagens**  

-   Sem automação, portanto demorada.  

 Para mais informações, consulte os seguintes tópicos:  

-   [Como instalar manualmente os clientes do Configuration Manager](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_Manual)  

-   [Como atualizar os clientes para servidores Linux e UNIX no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-for-linux-and-unix-servers.md)  

-   [Como atualizar clientes em computadores Mac no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-on-mac-computers.md)  

## <a name="upgrade-installation-application-management"></a>Instalação de atualização (gerenciamento de aplicativo)  
 **Plataforma de cliente com suporte:** Windows  

> [!NOTE]  
>  Não é possível atualizar clientes do Configuration Manager 2007 usando esse método. Nesse cenário, você pode implantar o cliente do Configuration Manager como um pacote do site do Configuration Manager 2007 ou usar a atualização de cliente automática que cria e implanta automaticamente o pacote que contém a versão mais recente do cliente.  

 **Vantagens**  

-   Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

 **Desvantagens**  

-   Pode causar elevado tráfego na rede ao distribuir o cliente para coleções grandes.  

-   Pode ser usada somente para atualizar o software cliente em computadores que foram descobertos e registrados no site.  

 Para obter mais informações, consulte [How to Install Configuration Manager Clients by Using a Package and Program](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientApp) (Como instalar clientes do Configuration Manager usando um pacote e programa).  

## <a name="automatic-client-upgrade"></a>Atualização automática de cliente  

> [!NOTE]  
>  Pode ser usado para atualizar clientes do Configuration Manager 2007 para clientes do System Center Configuration Manager. Um cliente do Configuration Manager 2007 pode atribuir um site do Configuration Manager, mas não pode realizar nenhuma ação além da atualização automática de cliente.  

 **Plataforma de cliente com suporte:** Windows  

 **Vantagens**  

-   Pode ser usada para manter automaticamente clientes em seu site na versão mais recente.  

-   Requer administração mínima pelo usuário administrativo.  

 **Desvantagens**  

-   Pode ser usada somente para atualizar o software cliente e não para instalar um novo cliente.  

-   Não é adequada para a atualização de vários clientes simultaneamente.  

-   Aplica-se a todos os clientes na hierarquia atribuídos a um site. Não pode ser limitada por coleção.  

-   Opções de agendamento limitadas.  

 Para obter mais informações, consulte [Como atualizar clientes para computadores Windows no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-for-windows-computers.md).  

## <a name="client-testing"></a>Teste do cliente  
 **Plataforma de cliente com suporte:** Windows  

 **Vantagens**  

-   Pode ser usado para testar novas versões de cliente em uma coleção de pré-produção menor.  

-   Quando o teste é concluído, os clientes de pré-produção são promovidos para a produção e atualizados automaticamente em todo o site do Configuration Manager.  

 **Desvantagens**  

-   Pode ser usada somente para atualizar o software cliente e não para instalar um novo cliente.  

 [Como testar atualizações do cliente em uma coleção de pré-produção no System Center Configuration Manager](../../../../core/clients/manage/upgrade/test-client-upgrades.md)  



<!--HONumber=Nov16_HO1-->

