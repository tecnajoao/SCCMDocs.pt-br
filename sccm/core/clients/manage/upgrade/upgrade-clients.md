---
title: Atualizar clientes
titleSuffix: Configuration Manager
description: Obter informações sobre como atualizar clientes no System Center Configuration Manager.
ms.date: 04/23/2017
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: 446c83b5-c292-4e74-ba19-0792ac6b3472
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0531c50792b6617eeb5e294bfad3626a0089c1f2
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56131482"
---
# <a name="upgrade-clients-in-system-center-configuration-manager"></a>Atualizar clientes no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

É possível usar métodos diferentes para atualizar o software cliente do System Center Configuration Manager em computadores Windows, servidores UNIX e Linux e computadores Mac. Estas são as vantagens e desvantagens de cada método.  

> [!TIP]  
>  Se você estiver atualizando a infraestrutura do servidor de uma versão anterior do Configuration Manager \(como o Configuration Manager 2007 ou o System Center 2012 Configuration Manager\), será recomendável que conclua as atualizações do servidor, incluindo a instalação de todas as atualizações da ramificação atual, antes de atualizar os clientes do Configuration Manager. Dessa forma, você também terá a versão mais recente do software cliente.  

## <a name="group-policy-installation"></a>Instalação de Política de Grupo  
 **Plataforma de cliente com suporte:** Windows  

#### <a name="advantages"></a>Vantagens  

- Não exige que os computadores sejam descobertos para que o cliente possa ser atualizado.  

- Pode ser usada para novas instalações de cliente ou para atualizações.  

- Os computadores podem ler as propriedades de instalação de cliente publicadas nos Serviços de Domínio Active Directory .  

- Não exige que você configure e mantenha uma conta de instalação para o computador cliente desejado.  

#### <a name="disadvantages"></a>Desvantagens  

- Poderá causar alto tráfego de rede se vários clientes estiverem sendo atualizados.  

- Se o esquema do Active Directory não for estendido para o Configuration Manager, será necessário usar as [configurações de Política de Grupo](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientGP) para adicionar as propriedades de instalação do cliente aos computadores do site.  


## <a name="logon-script-installation"></a>Instalação de script de logon  
 **Plataforma de cliente com suporte:** Windows  

#### <a name="advantages"></a>Vantagens  

- Não exige que os computadores sejam descobertos para que o cliente possa ser instalado.  

- Pode ser usada para novas instalações de cliente ou para atualizações.  

- Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

#### <a name="disadvantages"></a>Desvantagens  

- Poderá causar alto tráfego de rede se vários clientes estiverem sendo atualizados em um curto período.  

- Poderá levar muito tempo para atualizar todos os computadores cliente se os usuários não fizerem logon na rede com frequência.  

  Para obter mais informações, consulte [How to Install Configuration Manager Clients by Using Logon Scripts](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientLogonScript) (Como instalar clientes do Configuration Manager usando scripts de logon).  

## <a name="manual-installation"></a>Instalação manual  
 **Plataforma de cliente com suporte:** Windows, UNIX/Linus, Mac OS X  

#### <a name="advantages"></a>Vantagens  

- Não exige que os computadores sejam descobertos para que o cliente possa ser atualizado.  

- Pode ser útil para fins de teste.  

- Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

#### <a name="disadvantages"></a>Desvantagens  

- Sem automação, portanto demorada.  

  Para mais informações, consulte os seguintes tópicos:  

- [Como instalar manualmente os clientes do Configuration Manager](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_Manual)  

- [Como atualizar os clientes para servidores Linux e UNIX no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-for-linux-and-unix-servers.md)  

- [Como atualizar clientes em computadores Mac no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-on-mac-computers.md)  

## <a name="upgrade-installation-application-management"></a>Instalação de atualização (gerenciamento de aplicativo)  
 **Plataforma de cliente com suporte:** Windows  

> [!NOTE]  
>  Não é possível atualizar clientes do Configuration Manager 2007 com esse método. Nesse cenário, você pode implantar o cliente do Configuration Manager como um pacote do site do Configuration Manager 2007 ou usar a atualização de cliente automática que cria e implanta automaticamente o pacote que contém a versão mais recente do cliente.  

#### <a name="advantages"></a>Vantagens  

- Oferece suporte ao uso de propriedades de linha de comando para o CCMSetup.  

#### <a name="disadvantages"></a>Desvantagens  

- Poderá causar alto tráfego na rede se o cliente for distribuído para coleções grandes.  

- Pode ser usada somente para atualizar o software cliente em computadores que foram descobertos e registrados no site.  

  Para obter mais informações, consulte [How to Install Configuration Manager Clients by Using a Package and Program](../../../../core/clients/deploy/deploy-clients-to-windows-computers.md#BKMK_ClientApp) (Como instalar clientes do Configuration Manager usando um pacote e programa).  

## <a name="automatic-client-upgrade"></a>Atualização automática de cliente  

> [!NOTE]  
>  Pode ser usado para atualizar clientes do Configuration Manager 2007 para clientes do System Center Configuration Manager. Um cliente do Configuration Manager 2007 pode ser atribuído a um site do Configuration Manager, mas não pode realizar nenhuma ação além da atualização automática do cliente.  

 **Plataforma de cliente com suporte:** Windows  

#### <a name="advantages"></a>Vantagens  

- Devido à randomização durante o período especificado, somente a atualização automática é adequada para as atualizações em larga escala do cliente. Os demais métodos são muito lentos em larga escala ou não têm randomização. 

    > [!Note]
    > A pilotagem do cliente não é adequada para larga escala, já que não faz qualquer randomização.  
- Pode ser usada para manter automaticamente clientes em seu site na versão mais recente.  

- Exige administração mínima.  

#### <a name="disadvantages"></a>Desvantagens  

- Pode ser usada somente para atualizar o software cliente e não para instalar um novo cliente.  

- Aplica-se a todos os clientes na hierarquia atribuídos a um site. Não pode ser limitada por coleção.  

- Opções de agendamento limitadas.  

  Para obter mais informações, consulte [Como atualizar clientes para computadores Windows no System Center Configuration Manager](../../../../core/clients/manage/upgrade/upgrade-clients-for-windows-computers.md).  

## <a name="client-testing"></a>Teste do cliente  
 **Plataforma de cliente com suporte:** Windows  

#### <a name="advantages"></a>Vantagens  

- Pode ser usado para testar novas versões de cliente em uma coleção de pré-produção menor.  

- Quando o teste é concluído, os clientes em pré-produção são promovidos para produção e atualizados automaticamente em todo o site do Configuration Manager.  

#### <a name="disadvantages"></a>Desvantagens  

- Pode ser usada somente para atualizar o software cliente e não para instalar um novo cliente.  

  [Como testar atualizações do cliente em uma coleção de pré-produção no System Center Configuration Manager](../../../../core/clients/manage/upgrade/test-client-upgrades.md)  
