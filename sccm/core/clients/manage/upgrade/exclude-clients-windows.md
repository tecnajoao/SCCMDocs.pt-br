---
title: "Excluir atualizações de clientes | Windows | System Center Configuration Manager"
description: "Saiba como excluir clientes Windows de atualizações no System Center Configuration Manager."
ms.custom: na
ms.date: 11/18/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4cd6031f-8844-4d0b-8166-b24d6528a94e
author: nbigman
ms.author: nbigman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 55c953f312a9fb31e7276dde2fdd59f8183b4e4d
ms.openlocfilehash: 6451ce59e01254d96ca4aa9bbe07cde829fae9ce


---
# <a name="how-to-exclude-upgrading-clients-for-windows-computers-in-system-center-configuration-manager"></a>Como excluir clientes de atualizações em computadores Windows no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Começando da versão 1610, você pode excluir uma coleção de clientes da instalação automática de atualizações de versões de cliente. Ela se aplica à atualização automática, bem como a outros métodos, como a atualização baseada na atualização de software, scripts de logon e políticas de grupo. Você pode usar isso em uma coleção de computadores que requerem maior atenção ao atualizar o cliente. Um cliente que estiver em uma coleção excluída ignorará todas as solicitações para instalar o software cliente atualizado.

## <a name="configure-exclusion-for-automatic-upgrades"></a>Configurar a exclusão de atualizações automáticas

1. No console do Configuration Manager, acesse **Administração** > **Configuração do Site** > **Sites** e clique em **Configurações de Hierarquia**.

2. Clique na guia **Atualização do Cliente**.

3. Clique na caixa de seleção **Excluir clientes especificados da atualização** e, para a coleção Exclusão, selecione a coleção que você deseja excluir. É possível selecionar apenas uma coleção para exclusão.

4.  Clique em **OK** para fechar e salvar a configuração. Em seguida, após os clientes atualizarem a política, os clientes na coleção excluída não instalarão automaticamente as atualizações no software cliente. Para obter mais informações, consulte [Como atualizar clientes em computadores Windows](upgrade-clients-for-windows-computers.md).

![Configurações para exclusão de atualizações automáticas](media/automatic_upgrade_exclusion.png)



>[!NOTE]
>Embora a interface do usuário afirme que os clientes não serão atualizados por meio de nenhum método, dois métodos podem ser usados para substituir essas configurações. A instalação do cliente por push e uma instalação manual do cliente podem ser usadas para substituir essa configuração. Para obter mais detalhes, veja a seção seguir.

## <a name="how-to-upgrade-a-client-that-is-in-an-excluded-collection"></a>Como atualizar um cliente que está em uma coleção excluída

Desde que uma coleção esteja configurada para ser excluída, os membros dessa coleção só poderão atualizar o software cliente usando um dos dois métodos, que substituem a exclusão:
 - **Instalação do cliente por push** – você pode usar a instalação do cliente por push para atualizar um cliente que está em uma coleção excluída. Isso é permitido pois é considerado que seja a intenção do administrador, e permite que você atualize os clientes sem remover toda a coleção da exclusão.       

 - **Instalação manual do cliente** – você pode atualizar manualmente os clientes que estão em uma coleção excluída quando usa a seguinte opção de linha de comando com ccmsetup:  ***/ignoreskipupgrade***

  Se você tentar atualizar manualmente um cliente que é um membro da coleção excluída e não usar essa opção, o cliente não instalará o novo software cliente. Para obter mais informações, consulte [Como instalar manualmente os clientes do Configuration Manager](/sccm/core/clients/deploy/deploy-clients-to-windows-computers#BKMK_Manual).

Para obter mais informações sobre os métodos de instalação de clientes, consulte [Como implantar clientes em computadores Windows no System Center Configuration Manager](/sccm/core/clients/deploy/deploy-clients-to-windows-computers).



<!--HONumber=Dec16_HO3-->

