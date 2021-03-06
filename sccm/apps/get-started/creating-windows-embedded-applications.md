---
title: Criar aplicativos Windows Embedded
titleSuffix: Configuration Manager
description: Consulte quais considerações você deverá levar em conta ao criar e implantar aplicativos para dispositivos Windows Embedded.
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.technology: configmgr-app
ms.topic: conceptual
ms.assetid: 16acfd63-0c40-424c-82f4-8c63f7f1c30b
author: aczechowski
manager: dougeby
ms.author: aaroncz
ms.collection: M365-identity-device-management
ms.openlocfilehash: a76ce199b84db200ed023d610f40dbf6f9f989c2
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56120858"
---
# <a name="create-windows-embedded-applications-with-system-center-configuration-manager"></a>Criar aplicativos do Windows Embedded com o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Além dos outros requisitos e procedimentos do System Center Configuration Manager para a criação de um aplicativo, você também precisa levar em conta as considerações a seguir ao criar e implantar aplicativos para dispositivos Windows Embedded.  

## <a name="general-considerations"></a>Considerações gerais  

-   Quando você implantar aplicativos em dispositivos Windows Embedded que são habilitados para gravação de filtragem, é possível especificar se deseja desabilitar o filtro de gravação no dispositivo durante a implantação do aplicativo. Você pode escolher reiniciar o filtro de gravação após a implantação do aplicativo. Se o filtro de gravação não for desabilitado, o software será implantado em uma sobreposição temporária. Isso significa que, a menos que outra implantação faça alterações para persistir, o software não será mais instalado quando o dispositivo for reiniciado.  

-   Quando você implanta um aplicativo a um dispositivo Windows Embedded, verifique se o dispositivo é um membro de uma coleção com uma janela de manutenção configurada. Isso permite que você gerencie se o filtro de gravação é desabilitado e habilitado na reinicialização do dispositivo.  

-   A configuração que controla o comportamento do filtro de gravação é uma caixa de seleção denominada **Confirmar as alterações no prazo ou durante uma janela de manutenção (requer reinicializações)**.  

## <a name="tips-for-deploying-applications"></a>Dicas para implantação de aplicativos  

**Use aplicativos necessários em vez de aplicativos disponíveis para os dispositivos Windows Embedded que têm filtros de gravação habilitados.** Como os usuários não podem instalar aplicativos do Centro de Software em um dispositivo Windows Embedded que tem filtros de gravação habilitados, implante sempre os aplicativos com uma finalidade da implantação **necessária** em vez de **disponível** nesses dispositivos. Geralmente, isso não é um problema porque os computadores que executam um sistema operacional do Windows Embedded normalmente executam um único aplicativo que deve ser executado da mesma forma para vários usuários. É por isso que esses dispositivos são altamente gerenciados e bloqueados pelo departamento de TI. Os aplicativos necessários são ideais para esse cenário.

 No entanto, se os usuários executam mais de um aplicativo nos dispositivos inseridos quando os filtros de gravação estão habilitados, informe a esses usuários sobre as seguintes limitações:  

-   Os usuários não podem instalar o software necessário do Centro de Software.  

-   Os usuários não podem alterar o horário comercial na guia Opções do Centro de Software.  

-   Os usuários não podem adiar a instalação de um aplicativo necessário.  

Além disso, os usuários com direitos limitados não poderão fazer logon durante o período de manutenção se o Configuration Manager estiver fazendo alterações nas instalações e atualizações de software. Durante esse período, os usuários verão uma mensagem informando a eles que o dispositivo encontra-se indisponível por estar em manutenção.  

**Não faça a implantação de aplicativos a dispositivos Windows Embedded que têm filtros de gravação habilitados se os aplicativos necessitam que o usuário aceite os termos de licença.** Quando os filtros de gravação estiverem desabilitados para que o Configuration Manager possa instalar o software nos dispositivos inseridos, os usuários com direitos limitados não poderão fazer logon no dispositivo. Se a instalação necessitar que o usuário aceite os termos de licença, isso não será possível e a instalação falhará. Certifique-se de não implantar software a dispositivos Windows Embedded se a instalação requer a interação do usuário. Você pode usar a lista Plataformas Aplicáveis para filtrar esses sistemas operacionais.  
