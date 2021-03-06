---
title: Technical Preview 1707
titleSuffix: Configuration Manager
description: Saiba mais sobre os recursos disponíveis no Technical Preview versão 1707 do System Center Configuration Manager.
ms.date: 08/14/2017
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: cb405ba0-8792-4ab7-988b-2f835f3a9550
author: aczechowski
ms.author: aaroncz
manager: dougeby
ROBOTS: NOINDEX
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dbd7696821b9c333b556f67e42cdccd086dc2bf
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56132561"
---
# <a name="capabilities-in-technical-preview-1707-for-system-center-configuration-manager"></a>Recursos no Technical Preview 1707 do System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Technical Preview)*

Este artigo apresenta os recursos disponíveis no Technical Preview do System Center Configuration Manager, versão 1707. Você pode instalar esta versão para atualizar e adicionar novas funcionalidades ao seu site do Configuration Manager Technical Preview. Antes de instalar esta versão da visualização técnica, veja [Visualização Técnica do System Center Configuration Manager](../../core/get-started/technical-preview.md), para se familiarizar com os requisitos e limitações gerais de uso de uma visualização técnica, como atualizar entre versões e como fornecer comentários sobre os recursos em uma visualização técnica.     


<!--  Known Issues Template   
**Known Issues in this Technical Preview:**
-   **Issue Name**. Details
    Workaround details.
-->

**Problemas conhecidos nesse Technical Preview:**
- **Atualização para a versão prévia 1707 falha quando você tem um servidor do site no modo passivo**. Quando você executa a versão prévia 1706 e tem um [servidor do site primário no modo passivo](/sccm/core/get-started/capabilities-in-technical-preview-1706#site-server-role-high-availability), precisa desinstalar o servidor do site no modo passivo antes de atualizar seu site de versão prévia para a versão 1707. Depois que seu site executar a versão 1707, você poderá reinstalar o servidor do site no modo passivo.

  Para desinstalar o servidor do site no modo passivo:
  1. No console, acesse **Administração** > **Visão geral** > **Configuração do Site** > **Servidores e Funções do Sistema de Sites** e selecione o servidor de site no modo passivo.
  2. No painel **Funções do Sistema de Site**, clique com o botão direito na função **Servidor do Site** e, em seguida, escolha **Remover Função**.
  3. Clique com o botão direito no servidor do site de modo passivo e, em seguida, escolha **Excluir**.
  4. Após a desinstalação do servidor do site, no servidor do site primário ativo, reinicie o serviço **CONFIGURATION_MANAGER_UPDATE**.



**Veja a seguir os novos recursos que você pode experimentar nesta versão.**  

<!--  Rough Section Template
##  FEATURE

### Procedure 1
### Try it out!  
 Try to complete the following tasks and then send us **Feedback** from the **Home** tab of the Ribbon to let us know how it worked:
 -  Task 1
 -  Task 2              
-->

## <a name="client-peer-cache-support-for-express-installation-files-for-windows-10-and-office-365"></a>Suporte do Cache Par do Cliente para arquivos de instalação expressa para Windows 10 e Office 365
<!-- 1352486 --> A partir desta versão, o Cache Par dá suporte à distribuição de arquivos de instalação expressa de conteúdo para Windows 10 e dos arquivos de atualização para o Office 365. Nenhuma configuração adicional é necessária.

## <a name="surface-device-dashboard"></a>Painel do Surface Device
<!--1355788--> O painel Dispositivo do Surface fornece informações sobre os dispositivos do Surface encontrados no ambiente. No console, vá até **Monitoramento** > **Surface Devices**. É possível exibir o seguinte:
- porcentagem de Surfaces
- porcentagem de modelos do Surface
- as cinco principais versões do sistema operacional

Clique em uma seção do gráfico **Modelos do Surface** para obter uma lista completa dos dispositivos.  

## <a name="configure-and-deploy-windows-defender-application-guard-policies"></a>Configurar e implantar políticas de Proteção de Aplicativos do Windows Defender
<!-- 1351960 -->

O [Windows Defender Application Guard](https://blogs.windows.com/msedgedev/2016/09/27/application-guard-microsoft-edge/#XLxEbcpkuKcFebrw.97) é um novo recurso do Windows que ajuda a proteger os usuários através da abertura de sites não confiáveis em um contêiner isolado seguro que não esteja acessível por outras partes do sistema operacional. Nesse visualização técnica, adicionamos suporte para configurar esse recurso usando as configurações de conformidade do Configuration Manager que você configura e, em seguida, implanta em uma coleção. Este recurso será lançado como versão prévia na versão de 64 bits do Windows 10 Fall Creators Update (codinome: RS3). Para testar esse recurso agora, você deverá estar usando uma versão prévia desta atualização.

### <a name="before-you-start"></a>Antes de começar

Para criar e implantar as políticas do Windows Defender Application Guard, os dispositivos do Windows 10 nos quais você implantará a política deverão ser configurados com uma política de isolamento de rede. Para obter mais detalhes, consulte [esta postagem no blog](https://blogs.windows.com/msedgedev/2016/09/27/application-guard-microsoft-edge/#BmJGKPfSjHHzsMmI.97). Esse recurso só funciona com versões atuais do Windows 10 Insider. Para testá-lo, os clientes deverão estar executando uma versão recente do Windows 10 Insider.

### <a name="try-it-out"></a>Experimente!

#### <a name="to-create-a-policy-and-to-browse-the-available-settings"></a>Para criar uma política e procurar as configurações disponíveis:

1. No console do Configuration Manager, escolha **Ativos e Conformidade**.
2. No workspace **Ativos e Conformidade**, escolha **Visão Geral** > **Endpoint Protection** > **Windows Defender Application Guard**.
3. Na guia **Início**, no grupo **Criar**, clique em **Criar Política do Windows Defender Application Guard**.
4. Usando a postagem no blog como referência, você pode procurar e definir as configurações disponíveis para experimentar o recurso.
5. Nesta versão, adicionamos a nova página **Definição de Rede** ao assistente. Nessa página, especifique a identidade corporativa e defina o limite da rede corporativa.<br>Os computadores Windows 10 armazenam apenas uma lista de isolamento de rede no cliente. Nesta versão, é possível criar dois tipos diferentes de listas de isolamento de rede (uma da Proteção de Informações do Windows e outra do Windows Defender Application Guard) e implantá-las no cliente. Se você implantar as duas políticas, essas listas de isolamento de rede deverão ser correspondentes. Se você implantar listas que não correspondem ao mesmo cliente, a implantação falhará.
É possível localizar mais informações sobre como especificar definições de rede na [documentação da Proteção de Informações do Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-sccm).
6. Quando tiver terminado, conclua o assistente e implante a política para um ou mais dispositivos Windows 10.

### <a name="further-reading"></a>Leitura adicional
Para saber mais sobre o Windows Defender Application Guard, veja [esta postagem no blog](https://blogs.windows.com/msedgedev/2016/09/27/application-guard-microsoft-edge/#BmJGKPfSjHHzsMmI.97). Além disso, para saber mais sobre o modo autônomo do Windows Defender Application Guard, veja [esta postagem no blog](https://techcommunity.microsoft.com/t5/Windows-Insider-Program/Windows-Defender-Application-Guard-Standalone-mode/td-p/66903).

## <a name="add-parameters-when-you-deploy-powershell-scripts-from-configuration-manager"></a>Adicionar parâmetros ao implantar scripts do PowerShell do Configuration Manager

<!-- 1236459 --->

No último Technical Preview, apresentamos uma nova funcionalidade que permite [Criar e executar scripts do PowerShell do console do Configuration Manager](/sccm/core/get-started/capabilities-in-technical-preview-1706#create-and-run-powershell-scripts-from-the-configuration-manager-console).
Neste Technical Preview, expandimos essa funcionalidade. Agora o Configuration Manager lê o script do PowerShell e exibe quaisquer parâmetros no assistente Criar script. É possível fornecer um valor para o parâmetro no assistente que será usado quando o script for executado. Como alternativa, é possível deixar o parâmetro em branco. Se você fizer isso, será necessário fornecer um valor para o parâmetro quando você executar o script.
Nesta visualização técnica, você deve fornecer todos os parâmetros exigidos por um script. Em uma versão futura, planejamos tornar opcional o fornecimento de parâmetros de script.

### <a name="try-it-out"></a>Experimente!

1. Siga as instruções para [Criar e executar scripts do PowerShell do console do Configuration Manager](/sccm/core/get-started/capabilities-in-technical-preview-1706#create-and-run-powershell-scripts-from-the-configuration-manager-console).
2. Na nova página **Parâmetros de Script** do **Assistente Criar script**, escolha um parâmetro e, em seguida, clique em **Editar**.
3. Forneça um valor de parâmetro para o parâmetro selecionado e, em seguida, clique em **OK**.
4. Conclua o assistente.

Quando o script for executado, ele usará quaisquer valores de parâmetro configurados.
