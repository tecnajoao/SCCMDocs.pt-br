---
title: Administrar remotamente um computador Windows | System Center Configuration Manager
description: Administre um computador cliente Windows remoto usando o System Center Configuration Manager.
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 3c9648c4-645e-4e47-ae10-2da817b8c83b
caps.latest.revision: 5
caps.handback.revision: 0
author: nbigman
ms.author: nbigman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 02c11420d3b05ad4eaae31d9413b66459751da70
ms.openlocfilehash: 51a9b7269993bfa133382b88792ac94032824eed


---
# <a name="how-to-remotely-administer-a-windows-client-computer-by-using-system-center-configuration-manager"></a>Como administrar remotamente um computador cliente com Windows usando o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Use o procedimento a seguir para administrar remotamente um computador no System Center Configuration Manager.  

 Antes de começar a usar o controle remoto, certifique-se de que você leu as informações nos seguintes tópicos:  

-   [Pré-requisitos para o controle remoto no System Center Configuration Manager](../../../../core/clients/manage/remote-control/prerequisites-for-remote-control.md)  

-   [Configurando o controle remoto no System Center Configuration Manager](../../../../core/clients/manage/remote-control/configuring-remote-control.md)  

 Você pode iniciar o visualizador de controle remoto do Configuration Manager usando um dos três métodos:  

-   Usando o console do Configuration Manager.  

-   No prompt de comando do Windows.  

-   No menu **Iniciar** do Windows em um computador que executa o console do Configuration Manager no grupo de programas do **Microsoft System Center 2012**.  

### <a name="to-remotely-administer-a-client-computer-from-the-configuration-manager-console"></a>Para administrar remotamente um computador cliente no console do Configuration Manager  

1.  No console do Configuration Manager, clique em **Ativos e Conformidade**.  

2.  No espaço de trabalho **Ativos e Conformidade** , clique em **Dispositivos** e **Coleções de Dispositivos**.  

3.  Selecione o computador que deseja administrar remotamente e, na guia **Início** , no grupo **Dispositivo** , clique em **Iniciar**e em **Controle Remoto**.  

    > [!IMPORTANT]  
    >  Se a permissão **Solicitar o controle remoto ao usuário** da configuração do cliente for definida como **True**, a conexão não será iniciada até que o usuário no computador remoto concorde com o prompt de controle remoto. Para mais informações, consulte [Configurar o controle remoto no System Center Configuration Manager](../../../../core/clients/manage/remote-control/configuring-remote-control.md).  

4.  Depois que a janela **Controle Remoto do Configuration Manager** for aberta, você poderá administrar remotamente o computador cliente. Use as opções a seguir para configurar a conexão.  

    > [!NOTE]  
    >  Se o computador ao qual você se conectar tiver vários monitores, a exibição de todos os monitores será mostrada na janela do controle remoto.  

    -   **Arquivo ‑ Conectar** – Conecte-se a outro computador. Essa opção não está disponível quando uma sessão de controle remoto está ativa.  

    -   **Arquivo ‑ Desconectar** – Desconecta a sessão ativa de controle remoto, mas não fecha a janela **Controle Remoto do Configuration Manager**.  

    -   **Arquivo ‑ Sair** – Desconecta a sessão ativa de controle remoto e fecha a janela **Controle Remoto do Configuration Manager**.  

        > [!NOTE]  
        >  Quando você desconecta uma sessão de controle remoto, o conteúdo da Área de Transferência do Windows no computador que está sendo exibido é excluído.  

    -   **Exibir ‑ Tela Inteira** – Maximiza a janela do **Controle Remoto do Configuration Manager** para preencher todo o espaço de exibição disponível.  

        > [!NOTE]  
        >  Para sair do modo de tela inteira, pressione Ctrl+Alt+Break.  

    -   **Exibição ‑ Dimensionar para Ajustar** – Dimensiona o monitor do computador remoto para se ajustar ao tamanho da janela do **Controle Remoto do Configuration Manager**.  

    -   **Exibir ‑ Barra de Status** – Alterna a exibição da barra de status da janela do **Controle Remoto do Configuration Manager**.  

    -   **Ação ‑ Enviar tecla Ctrl+Alt+Del** – Envia uma combinação de teclas Ctrl+Alt+Del ao computador remoto.  

    -   **Ação ‑ Habilitar o Compartilhamento da Área de Transferência** – Permite copiar e colar itens no computador remoto. Se você alterar esse valor, será necessário reiniciar a sessão de controle remoto para que a alteração tenha efeito.  

        > [!NOTE]  
        >  Se não desejar que o compartilhamento de área de transferência seja habilitado no console do Configuration Manager, no computador que executa o console, defina o valor da chave do Registro, **HKEY_CURRENT_USER\Software\Microsoft\ConfigMgr10\Remote Control\Clipboard Sharing** como **0**.  

    -   **Ação ‑ Bloqueio do Teclado e Mouse Remotos** – Bloqueia o teclado e o mouse para impedir que o usuário opere o computador remoto.  

    -   **Ajuda ‑ Sobre o Controle Remoto** – Exibe informações sobre a versão atual do visualizador de controle remoto.  

5.  Os usuários no computador remoto podem exibir mais informações sobre a sessão de controle remoto ao clicar no ícone **Controle Remoto** do Configuration Manager na área de notificação do Windows ou no ícone na barra da sessão de controle remoto.  

6.  Quando não precisar mais da sessão de controle remoto, use um dos métodos detalhados anteriormente para encerrar a sessão de controle remoto.  

### <a name="to-start-the-remote-control-viewer-from-the-windows-command-line"></a>Para iniciar o visualizador de controle remoto na linha de comando do Windows  

-   No prompt de comando do Windows, digite *<Pasta de instalação do Configuration Manager\>***\AdminConsole\Bin\x64\CmRcViewer.exe**  

    > [!NOTE]  
    >  O CmRcViewer.exe dá suporte às seguintes opções de linha de comando:  
    >   
    >  -   *<Endereço\>* ‑ Especifica o nome NetBIOS, o FQDN (nome de domínio totalmente qualificado) ou o endereço IP do computador cliente ao qual você deseja se conectar.  
    > -   *<Nome do Servidor do Site\>* ‑ Especifica o nome do servidor do site do System Center 2012 Configuration Manager ao qual você deseja enviar mensagens de status relacionadas à sessão de controle remoto.  
    > -   **/?** – Exibe as opções de linha de comando para o visualizador de controle remoto.  
    >   
    >  **Exemplo:CmRcViewer.exe** *<Endereço\>* *<\\\Nome do Servidor do Site>*  



<!--HONumber=Nov16_HO1-->

