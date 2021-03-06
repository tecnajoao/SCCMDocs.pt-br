---
title: Definir as configurações do Microsoft Edge
titleSuffix: Configuration Manager
description: Definir as configurações do navegador da Web Microsoft Edge em clientes do Windows 10
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.date: 07/30/2018
ms.topic: conceptual
ms.prod: configuration-manager
ms.technology: configmgr-compliance
ms.assetid: 76477b4d-df41-4b25-8318-7d18d46ca2c6
ms.collection: M365-identity-device-management
ms.openlocfilehash: d97a67dd65dd79ba8b47541d0c7a7cad239dca28
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56126013"
---
# <a name="configure-microsoft-edge-settings-in-system-center-configuration-manager"></a>Definir as configurações do Microsoft Edge no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

<!-- 1357310 --> Começando na versão 1802, para clientes que usam o navegador da Web [Microsoft Edge](https://technet.microsoft.com/microsoft-edge/bb265256) em clientes Windows 10, é possível criar uma política de configurações de conformidade do Configuration Manager para definir várias configurações do Microsoft Edge. 

Essa política se aplica somente aos clientes no Windows 10, versão 1703 ou posterior. <!--511552-->


## <a name="policy-settings"></a>Configurações de política
Esta política atualmente inclui as seguintes configurações:
- **Definir o navegador Microsoft Edge como padrão** : configura a configuração do aplicativo padrão do Windows 10 para o navegador da Web para o Microsoft Edge
- **Permitir lista suspensa de barra de endereços**: requer o Windows 10, versão 1703 ou posterior. Para saber mais, confira a [política de navegador AllowAddressBarDropdown ](/windows/client-management/mdm/policy-csp-browser#browser-allowaddressbardropdown).
- **Permitir a sincronização de favoritos entre navegadores da Microsoft**: requer o Windows 10, versão 1703 ou posterior. Para saber mais, confira a [política de navegador SyncFavoritesBetweenIEAndMicrosoftEdge](/windows/client-management/mdm/policy-csp-browser#browser-syncfavoritesbetweenieandmicrosoftedge).
- **Permitir a limpeza de dados de navegação ao sair**: requer o Windows 10, versão 1703 ou posterior. Para saber mais, confira a [política do navegador ClearBrowsingDataOnExit](/windows/client-management/mdm/policy-csp-browser#browser-clearbrowsingdataonexit).
- **Permitir cabeçalhos Não Rastrear**: para obter mais informações, confira a [Política do navegador AllowDoNotTrack](/windows/client-management/mdm/policy-csp-browser#browser-allowdonottrack).
- **Permitir preenchimento automático**: para obter mais informações, confira a [política do navegador AllowAutofill](/windows/client-management/mdm/policy-csp-browser#browser-allowautofill).
- **Permitir cookies**: para obter mais informações, confira a [política do navegador AllowCookies](/windows/client-management/mdm/policy-csp-browser#browser-allowcookies).
- **Permitir bloqueador de pop-up**: para obter mais informações, confira a [política do navegador AllowPopups](/windows/client-management/mdm/policy-csp-browser#browser-allowpopups).
- **Permitir sugestões de pesquisa na barra de endereços**: para obter mais informações, confira a [política do navegador AllowSearchSuggestionsinAddressBar](/windows/client-management/mdm/policy-csp-browser#browser-allowsearchsuggestionsinaddressbar).
- **Permitir envio de tráfego de intranet ao Internet Explorer**: para obter mais informações, confira a [política do navegador SendIntranetTraffictoInternetExplorer](/windows/client-management/mdm/policy-csp-browser#browser-sendintranettraffictointernetexplorer).
- **Permitir gerenciador de senhas**: para obter mais informações, confira [política do navegador AllowPasswordManager](/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager).
- **Permitir Ferramentas para Desenvolvedores**: para obter mais informações, confira a [política do navegador AllowDeveloperTools](/windows/client-management/mdm/policy-csp-browser#browser-allowdevelopertools).
- **Permitir extensões**: para obter mais informações, confira a [política do navegador AllowExtensions](/windows/client-management/mdm/policy-csp-browser#browser-allowextensions).


### <a name="configure-windows-defender-smartscreen-settings-for-microsoft-edge"></a>Definir as configurações do Windows Defender SmartScreen para o Microsoft Edge
<!--1353701--> Começando na versão 1806, essa política adiciona três configurações ao [Windows Defender SmartScreen](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview). Agora, a política inclui as seguintes configurações adicionais na página **Configurações do SmartScreen**:

- **Permitir SmartScreen**: Especifica se o Windows Defender SmartScreen é permitido. Para obter mais informações, confira a [Política do navegador AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen).
- **Os usuários podem substituir o aviso do SmartScreen para sites**: Especifica se os usuários podem substituir os avisos de Filtro do Windows Defender SmartScreen sobre sites potencialmente mal-intencionados. Para obter mais informações, confira a [Política do navegador PreventSmartScreenPromptOverride](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride).
- **Os usuários podem substituir o aviso do SmartScreen para arquivos**: Especifica se os usuários podem substituir os avisos de Filtro do Windows Defender SmartScreen sobre como baixar arquivos não verificados. Para obter mais informações, confira a [Política do navegador PreventSmartScreenPromptOverrideForFiles](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles).



## <a name="create-the-microsoft-edge-browser-profile"></a>Criar o perfil do navegador Microsoft Edge

1. No console do Configuration Manager, vá até o workspace **Ativos e conformidade**. Expanda **Configurações de Conformidade** e selecione o nó **Perfis de Navegador do Microsoft Edge**. Na faixa de opções, clique na opção **Criar perfil do Microsoft Edge**.
2. Especifique um **Nome** para a política, digite opcionalmente a **Descrição** e clique em **Avançar**.
3. Na página **Configurações Gerais**, altere o valor para **Configurado** para que as configurações sejam incluídas nesta política e clique em **Avançar**. Para continuar, é necessário definir a configuração **Configurar o Navegador Microsoft Edge como o padrão**.
4. Na versão 1806 e posterior, defina as configurações na página **Configurações do SmartScreen** e, em seguida, clique em **Avançar**. 
5. Na página **Plataformas com Suporte**, selecione as versões e arquiteturas do sistema operacional às quais esta política se aplica e clique em **Avançar**. 
6. Conclua o assistente.



## <a name="deploy-the-policy"></a>Implantar a política

1. Selecione sua política e clique na opção da faixa de opções para **Implantar**.
2. Clique em **Procurar** para selecionar a coleção de usuário ou dispositivo para a qual implantar a política. 
3. Selecione as opções adicionais conforme necessário.  
     a. Gerar alertas quando a política não for compatível.  
     b. Defina o agendamento pelo qual o cliente avalia a conformidade do dispositivo com esta política. 
4. Clique em **OK** para criar a implantação.



## <a name="next-steps"></a>Próximas etapas

Como qualquer política de configurações de conformidade, o cliente soluciona as configurações no agendamento especificado. [Monitore e relate a conformidade do dispositivo](/sccm/compliance/deploy-use/monitor-compliance-settings) no console do Configuration Manager.
