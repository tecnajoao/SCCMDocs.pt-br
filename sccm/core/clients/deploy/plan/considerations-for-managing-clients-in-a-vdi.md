---
title: 'Gerenciamento de cliente da VDI (Virtual Desktop Infrastructure) '
titleSuffix: Configuration Manager
description: Gerenciar clientes do System Center Configuration Manager em uma VDI (Virtual Desktop Infrastructure).
ms.date: 04/23/2017
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: abd45393-d84e-4583-bc80-74bbb3709577
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9352d6e5a26afd4cee36f70a19d0566e26643f50
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56130564"
---
# <a name="considerations-for-managing-system-center-configuration-manager-clients--in-a-virtual-desktop-infrastructure-vdi"></a>Considerações para gerenciar clientes do System Center Configuration Manager em uma VDI (Virtual Desktop Infrastructure)

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

O System Center Configuration Manager dá suporte à instalação de cliente do Configuration Manager nos seguintes cenários de VDI (Virtual Desktop Infrastructure):  

- **Máquinas virtuais pessoais** – As máquinas virtuais pessoais geralmente são usadas quando você deseja verificar se os dados do usuário são mantidos nas máquinas virtuais entre sessões.  

- **Sessões de Serviços de Área de Trabalho Remota** – Os Serviços de Área de Trabalho Remota permitem que um servidor hospede várias sessões do cliente simultaneamente. Os usuários podem se conectar a uma sessão e, em seguida, executar aplicativos nesse servidor.  

- **Máquinas virtuais em pool** – As máquinas virtuais em pool não são mantidas entre sessões. Quando uma sessão for fechada, todos os dados e configurações serão descartados. As máquinas virtuais em pool são úteis quando os Serviços de Área de Trabalho Remota não podem ser usados porque um aplicativo de negócios exigido não pode ser executado no Windows Server que hospeda as sessões do cliente.  

  A tabela a seguir lista considerações para gerenciar o cliente do Configuration Manager em uma infraestrutura de área de trabalho virtual.  

|Tipo de máquina virtual|Considerações|  
|--------------------------|--------------------|  
|Máquinas virtuais pessoais|O Configuration Manager trata máquinas virtuais pessoais da mesma maneira que um computador físico. O cliente do Configuration Manager pode ser pré-instalado na imagem da máquina virtual ou implantado depois que a máquina virtual for provisionada.|  
|Serviços de área de trabalho remota|O cliente do Configuration Manager não é instalado para sessões da Área de Trabalho Remota. Em vez disso, o cliente é instalado somente uma vez no servidor de Serviços de Área de Trabalho Remota. Todos os recursos do Configuration Manager podem ser usados no servidor de Serviços de Área de Trabalho Remota.|  
|Máquinas virtuais em pool|Quando uma máquina virtual em pool é encerrada, todas as alterações feitas usando o Configuration Manager são perdidas.<br /><br /> Os dados retornados dos recursos do Configuration Manager, como inventário de hardware e de software, e medição de software podem não ser relevantes a suas necessidades, pois a máquina virtual pode estar operacional somente por um curto período. Considere a exclusão de máquinas virtuais em pool das tarefas de inventário.|  

 Como a virtualização dá suporte a vários clientes do Configuration Manager no mesmo computador físico, muitas operações co cliente têm um atraso aleatório interno para ações agendadas, como inventário de hardware e de software, varreduras antimalware, instalações de software e varreduras de atualização de software. Esse atraso ajuda a distribuir o processamento da CPU e a transferência de dados para um computador com várias máquinas virtuais que executam o cliente do Configuration Manager.  

> [!NOTE]  
>  Com exceção de clientes Windows Embedded em modo de manutenção, os clientes do Configuration Manager que não são executados em ambientes virtualizados também usam esse atraso aleatório. Quando você têm muitos clientes implantados, esse comportamento ajuda a evitar picos na largura de banda de rede e reduz o requisito de processamento da CPU nos sistemas de site do Configuration Manager, como o ponto de gerenciamento e o servidor do site. O intervalo de atraso varia de acordo com a capacidade do Configuration Manager.  
>   
>  O atraso aleatório é desabilitado por padrão para atualizações de software obrigatórias usando a seguinte configuração do cliente: **Agente de computador**: **Desabilitar aleatoriedade de data limite**.
