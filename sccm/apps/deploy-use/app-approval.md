---
title: Aprovar aplicativos
titleSuffix: Configuration Manager
description: Saiba mais sobre as configurações e comportamentos para aprovação de aplicativos no Configuration Manager.
ms.date: 11/27/2018
ms.prod: configuration-manager
ms.technology: configmgr-app
ms.topic: conceptual
ms.assetid: 20493c86-6454-4b35-8f22-0d049b68b8bb
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.openlocfilehash: f19146da963055ffc20b274e1017802274844698
ms.sourcegitcommit: 6e42785c8c26e3c75bf59d3df7802194551f58e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52457988"
---
# <a name="approve-applications-in-configuration-manager"></a>Aprovar aplicativos no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Ao [Implantar um aplicativo](/sccm/apps/deploy-use/deploy-applications) no Configuration Manager, você pode exigir aprovação antes da instalação. Os usuários solicitam o aplicativo no Centro de Software e, em seguida, você pode examinar a solicitação no console do Configuration Manager. Você pode aprovar ou negar a solicitação. 



## <a name="bkmk_approval"></a> Configurações de aprovação

O comportamento de aprovação do aplicativo depende da sua versão do Configuration Manager. Uma das seguintes configurações de aprovação será exibida na página **Configurações de Implantação** da implantação do aplicativo:  

#### <a name="require-administrator-approval-if-users-request-this-application"></a>Exibir aprovação do administrador se os usuários solicitarem este aplicativo
*Aplica-se às versões 1710 e anteriores*

O administrador aprova as solicitações do usuário para o aplicativo antes que o usuário possa instalá-los. Essa opção fica desabilitada quando a finalidade da implantação é **Obrigatória** ou quando o aplicativo é implantado em uma coleção de dispositivos.  

As solicitações de aprovação do aplicativo são exibidas no nó **Solicitações de Aprovação**, no **Gerenciamento de Aplicativos** no workspace **Biblioteca de Software**. Se uma solicitação não é aprovada no prazo de 30 dias, ela é removida. A reinstalação do cliente pode cancelar as solicitações de aprovação pendentes.  

Depois de aprovar um aplicativo para instalação, você pode **Negar** a solicitação no console do Configuration Manager. Essa ação não faz com que o cliente desinstale o aplicativo de todos os dispositivos. Ela impede que os usuários instalem novas cópias do aplicativo pelo Centro de Software.  


#### <a name="an-administrator-must-approve-a-request-for-this-application-on-the-device"></a>Um administrador precisa aprovar uma solicitação para este aplicativo no dispositivo
*Aplica-se às versões 1802 e posteriores <sup>[Observação 1](#bkmk_note1)</sup>*

<a name="bkmk_note1"></a>

> [!Note]  
> **Observação 1:** o Configuration Manager não habilita esse recurso opcional por padrão. É necessário habilitar esse recurso antes de usá-lo. Para obter mais informações, consulte [Enable optional features from updates (Habilitar recursos opcionais de atualizações)](/sccm/core/servers/manage/install-in-console-updates#bkmk_options). 
> 
> Se você não habilitar esse recurso, a experiência anterior será exibida.  

O administrador aprova as solicitações do usuário para o aplicativo antes que o usuário possa instalá-los no dispositivo solicitado. Se o administrador aprova o pedido, o usuário só poderá instalar o aplicativo nesse dispositivo. O usuário deve enviar outro pedido para instalar o aplicativo em outro dispositivo. Essa opção fica desabilitada quando a finalidade da implantação é **Obrigatória** ou quando o aplicativo é implantado em uma coleção de dispositivos. <!--1357015-->  

> [!Note]  
> Para aproveitar os novos recursos do Configuration Manager, primeiro atualize os clientes para a versão mais recente. Embora a nova funcionalidade seja exibida no console do Configuration Manager quando você atualiza o site e o console, o cenário completo só funcionará quando a versão do cliente também for a mais recente.<!--SCCMDocs issue 646-->  

Exiba **Solicitações de aprovação**, no **Gerenciamento de aplicativos**, no workspace **Biblioteca de software** do console do Configuration Manager. Agora há uma coluna **Dispositivo** na lista de cada solicitação. Quando você toma ação no pedido, a caixa de diálogo Solicitação de Aplicativo também inclui o nome do dispositivo do qual o usuário enviou a solicitação.  

Se uma solicitação não é aprovada no prazo de 30 dias, ela é removida. A reinstalação do cliente pode cancelar as solicitações de aprovação pendentes.  

Depois de aprovar um aplicativo para instalação, você pode **Negar** a solicitação no console do Configuration Manager. Essa ação não faz com que o cliente desinstale o aplicativo de todos os dispositivos. Ela impede que os usuários instalem novas cópias do aplicativo pelo Centro de Software.  

> [!Important]  
> Começando na versão 1806, *o comportamento mudou* para casos em que você revoga a aprovação de um aplicativo que já foi aprovado e instalado. Agora quando você **Nega** a solicitação do aplicativo, o cliente desinstala o aplicativo do dispositivo do usuário.<!--1357891-->  



## <a name="bkmk_email-approve"></a> Notificações por email
<!--1321550-->

Da versão 1810 em diante, configure notificações por email para solicitações de aprovação do aplicativo. Quando um usuário solicitar um aplicativo, você receberá um email. Clique nos links no email para aprovar ou negar a solicitação sem precisar usar o console do Configuration Manager.


### <a name="prerequisites"></a>Pré-requisitos

#### <a name="to-send-email-notifications-and-take-action-on-internal-network"></a>Para enviar notificações por email e agir na rede interna
Com esses pré-requisitos, os destinatários recebem um email com notificação da solicitação. Se eles estiverem na rede interna, também poderão aprovar ou negar a solicitação de email.

- Habilite o [recurso opcional](/sccm/core/servers/manage/install-in-console-updates#bkmk_options) **Aprovar solicitações de aplicativo para usuários por dispositivo**.  

- Configure [notificações por email para alertas](/sccm/core/servers/manage/use-alerts-and-the-status-system#to-configure-email-notification-for-alerts).  



#### <a name="to-take-action-from-internet"></a>Para executar a ação da Internet
Com esses pré-requisitos opcionais adicionais, os destinatários podem aprovar ou negar a solicitação de qualquer lugar em que tenham acesso à Internet.

- Habilite o serviço de administração do Provedor de SMS por meio do gateway de gerenciamento de nuvem. No console do Configuration Manager, acesse o workspace **Administração**, expanda **Configuração do Site** e selecione o nó **Funções do Sistema de Sites e Servidores**. Selecione o servidor com a função de Provedor de SMS. No painel de detalhes, selecione a função **Provedor de SMS** e selecione **Propriedades** na faixa de opções na guia de Função do Site. Selecione a opção para **Permitir tráfego do gateway de gerenciamento de nuvem do Configuration Manager para o serviço de administração**.  

    - O Provedor de SMS requer **.NET 4.5.2** ou posterior.  

- [Gateway de gerenciamento de nuvem](/sccm/core/clients/manage/cmg/plan-cloud-management-gateway)  

- Integrar o site aos [serviços do Azure](/sccm/core/servers/deploy/configure/azure-services-wizard) para **Gerenciamento de nuvem**  

    - Habilitar a [Descoberta de usuários do Azure AD](/sccm/core/servers/deploy/configure/configure-discovery-methods#azureaadisc)  

    - Defina manualmente as configurações do Azure AD:  

        1. Vá para o [portal do Azure](https://portal.azure.com), selecione **Azure Active Directory** e, em seguida, selecione **Registros de aplicativo**.  

        2. Selecione o aplicativo do tipo **Nativo** que você criou para a integração do **Gerenciamento de Nuvem** do Configuration Manager.  

        3. Nas propriedades do aplicativo, selecione **Configurações** e, em seguida, selecione **URIs de redirecionamento**.  

            1. No painel de URIs de Redirecionamento, cole o seguinte caminho: `https://<CMG FQDN>/CCM_Proxy_ServerAuth/ImplicitAuth`  

            2. Substitua `<CMG FQDN>` pelo FQDN (nome de domínio totalmente qualificado) do serviço CMG (gateway de gerenciamento de nuvem). Por exemplo, GraniteFalls.Contoso.com.  

            3. Em seguida, selecione **Salvar**. Feche o painel **Configurações**.  

        4. Nas propriedades do aplicativo, selecione **Manifesto**.  

            1. No painel Editar manifesto, localize a propriedade **oauth2AllowImplicitFlow**.  

            2. Altere esse valor para **true**. Por exemplo, toda a linha deve ser semelhante à seguinte: `"oauth2AllowImplicitFlow": true,`   

            3. Selecione **Salvar**.  


### <a name="configure-email-approval"></a>Configurar aprovação de email

1. No console do Configuration Manager, [implante um aplicativo](/sccm/apps/deploy-use/deploy-applications) como disponível para uma coleção de usuários. Na página **Configurações de Implantação**, habilite-a para aprovação. Em seguida, insira um ou mais endereços de email para receber uma notificação. Separe os endereços de email com ponto e vírgula (`;`).  

     > [!Note]  
     > Qualquer pessoa na organização do Azure AD que receber o email poderá aprovar a solicitação. Não encaminhe o email para outras pessoas, a menos que você queira que elas realizem alguma ação.  

2. Como usuário, solicite o aplicativo no Centro de Software.  

3. Você receberá uma notificação por email dentro de cinco minutos. O conteúdo do email é semelhante ao exemplo a seguir:  

![Exemplo de notificação por email para aprovação do aplicativo](media/1321550-email.png)

> [!Note]  
> O link para aprovar ou negar é para ser usado uma única vez. Por exemplo, você pode configurar um alias de grupo para receber notificações. Sara aprova a solicitação. E Vinícius já não pode negar a solicitação.  

Examine o arquivo **NotiCtrl.log** no servidor do site para solucionar problemas.


## <a name="maintenance"></a>Manutenção 

O Configuration Manager armazena informações sobre a solicitação de aprovação do aplicativo no banco de dados do site. Para solicitações canceladas ou negadas, o site exclui o histórico de solicitações após 30 dias. Você pode configurar esse comportamento de exclusão com a **tarefa de manutenção do site** [Excluir Dados de Solicitação de Aplicativo](/sccm/core/servers/manage/maintenance-tasks). O site nunca exclui nenhuma solicitação de aplicativo pendente ou aprovada.
