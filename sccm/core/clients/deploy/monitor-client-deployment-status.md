---
title: Monitorar o status de implantação do cliente
titleSuffix: Configuration Manager
description: Monitore o status de implantação do cliente no System Center Configuration Manager.
ms.date: 04/23/2017
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: 20a573b3-53cb-4ed5-bae1-7542f533ed20
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55fea1e8453837538c5e7059dc5257037dd3eb38
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56120432"
---
# <a name="how-to-monitor-client-deployment-status-in-system-center-configuration-manager"></a>Como monitorar o status de implantação do cliente no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Implantar clientes no seu site leva tempo e algumas instalações não são bem-sucedidas na primeira vez. O console do System Center Configuration Manager fornece uma maneira de você ficar de olho nas implantações do cliente em uma coleção ao relatar o status da implantação do cliente em tempo real.  

> [!NOTE]  
>  A melhor e mais confiável maneira de monitorar a implantação do cliente é com o console do Configuration Manager (conforme descrito neste artigo). A seção **Status do Cliente** do workspace **Monitoramento** no console fornece o status da implantação do cliente de modo preciso e em tempo real. Você pode monitorar implantações do cliente com outras ferramentas, como o Gerenciador de Servidores no Windows Server ou o System Center Operations Manager, mas pode receber alarmes da atividade normal de instalação do cliente. Devido ao modo que o programa de instalação do cliente (CCMSetup.exe) é executado em vários ambientes, essas outras ferramentas podem gerar falsos alarmes e avisos que não refletem precisamente o estado das implantações do cliente.  

 No workspace **Monitoramento** do console, é possível monitorar os status a seguir de implantações do cliente, que ocorrem em uma coleção que você especifica:  

- compatível  

- Em andamento  

- Não compatível  

- Falha  

- Desconhecida  

  O Configuration Manager relata as implantações de clientes de produção ou clientes de pré-produção. O console do Configuration Manager também fornece um gráfico de implantações do cliente que falharam por um período especificado, a fim de ajudar você a determinar se as ações executadas para solucionar problemas de implantação estão aumentando a taxa de implantações bem-sucedidas ao longo do tempo.  

## <a name="to-monitor-client-deployments"></a>Para monitorar implantações do cliente  

- No console do Configuration Manager, clique em **Monitoramento** > **Status do Cliente**.  

- Clique em **Implantação do Cliente de Produção** ou **Implantação do Cliente de Pré-Produção**, dependendo da versão do cliente que você deseja monitorar.  

- Revise os gráficos do status de implantação do cliente e falha de implantação do cliente.  

- Se você quiser alterar o escopo do relatório, clique em **Procurar...** e escolha outra coleção.  

  Para saber mais sobre implantações de cliente em pré-produção, consulte [Como testar atualizações de cliente em uma coleção de pré-produção no System Center Configuration Manager](../../../core/clients/manage/upgrade/test-client-upgrades.md).

  > [!NOTE]
  > O status da implantação em computadores que hospedam funções de sistema de sites em uma coleção de pré-produção pode ser relatado como **Não compatível** mesmo que o cliente tenha sido implantado com êxito. Quando você promove o cliente para produção, o status da implantação é relatado corretamente.   

  Para monitorar o status de clientes implantados, confira [Como monitorar clientes no System Center Configuration Manager](../../../core/clients/manage/monitor-clients.md)  

  Você pode usar relatórios do Configuration Manager para obter mais informações sobre o status dos clientes no seu site. Para obter mais informações sobre como executar relatórios, consulte [Relatórios no System Center Configuration Manager](../../../core/servers/manage/reporting.md).  
