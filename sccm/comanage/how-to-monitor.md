---
title: Monitorar o cogerenciamento
titleSuffix: Configuration Manager
description: Use o painel de cogerenciamento para examinar as informações sobre dispositivos cogerenciados.
ms.date: 01/14/2019
ms.prod: configuration-manager
ms.technology: configmgr-client
ms.topic: conceptual
ms.assetid: e83a7b0d-b381-4b4a-8eca-850385abbebb
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7c731692bc2277cc5ce97e079387b392ca09ff3e
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56754567"
---
# <a name="how-to-monitor-co-management-in-configuration-manager"></a>Como monitorar o cogerenciamento no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*


Depois de habilitar o cogerenciamento, monitore dispositivos de cogerenciamento usando os seguintes métodos:

- [Painel de cogerenciamento](#co-management-dashboard)  

- [Políticas de implantação](#deployment-policies)

- [Dados de dispositivo do WMI](#wmi-device-data)



## <a name="co-management-dashboard"></a>Painel de cogerenciamento

Iniciando na versão 1802, exiba um painel com informações sobre cogerenciamento. O painel ajuda você a analisar os computadores cogerenciados no ambiente. Os grafos podem ajudar a identificar os dispositivos que podem precisar de atenção.<!--1356648-->

No console do Configuration Manager, vá até o workspace **Monitoramento** e selecione o nó **Cogerenciamento**.

Da versão 1810 em diante, o painel de cogerenciamento foi aprimorado com informações mais detalhadas. <!--1358980-->

![Captura de tela do painel de cogerenciamento](media/co-management-dashboard.png)


### <a name="co-managed-devices"></a>Dispositivos cogerenciado

*Aplica-se às versões 1802 e 1806*

Mostra o percentual de dispositivos cogerenciados no seu ambiente.

![Bloco de dispositivos cogerenciados](media/co-management-dashboard/Percent-Co-managed-graph.PNG)


### <a name="client-os-distribution"></a>Distribuição do sistema operacional cliente

*Aplica-se a todas as versões* 

Mostra o número de dispositivos do cliente por sistema operacional por versão. Este usa os seguintes agrupamentos:  
- Windows 7 e 8.x  
- Windows 10 inferior a 1709  
- Windows 10 1709 e posterior  

    > [!Tip]  
    > O Windows 10, versão 1709 e posterior, é um pré-requisito para o cogerenciamento.  

Focalize uma seção do gráfico para mostrar o percentual de dispositivos nesse grupo de sistema operacional.

![Bloco de distribuição do sistema operacional do cliente](media/co-management-dashboard/Co-management-OS-distribution-graph.PNG)


### <a name="co-management-status-donut"></a>Status de cogerenciamento (rosca)

*Aplica-se às versões 1802 e 1806*

Mostra a divisão de êxito ou falha do dispositivo nas seguintes categorias:
- Sucesso, Ingressado no Azure AD híbrido  
- Sucesso, Ingressado no Azure AD  
- Falha: falha no registro automático  

Focalize uma seção do gráfico para mostrar o percentual de dispositivos nessa categoria. 

![Bloco de status (rosca) de cogerenciamento](media/co-management-dashboard/Co-management-status-graph.PNG)

Selecione uma seção do grafo para exibir a lista de dispositivos para essa categoria.

![Lista de dispositivos com falha de registro](media/co-management-dashboard/Enrollment-Failure_Device-List.PNG)


### <a name="co-management-status-funnel"></a>Status de cogerenciamento (funil)

*Aplica-se à versão 1810 e posteriores*

Um gráfico de funil que mostra o número de dispositivos com os seguintes estados do processo de registro:  
- Dispositivos qualificados  
- Agendado  
- Registro iniciado  
- Inscrito  

![Bloco de status de cogerenciamento (funil)](media/co-management-dashboard/1358980-status-funnel.png)


### <a name="co-management-enrollment-status"></a>Status do registro de cogerenciamento

*Aplica-se à versão 1810 e posteriores*

Mostra a divisão de status do dispositivo nas seguintes categorias:
- Sucesso, ingressado no Azure AD híbrido  
- Sucesso, ingressado no Azure AD  
- Inscrição, ingressado no Azure AD híbrido  
- Falha, ingressado no Azure AD híbrido  
- Falha, ingressado no Azure AD  
- Entrada do usuário pendente  

Selecione um estado no bloco para detalhar uma lista de dispositivos nesse estado.  

![Bloco de status do registro de cogerenciamento](media/co-management-dashboard/1358980-enrollment-status.png)


### <a name="workload-transition"></a>Transição da carga de trabalho

*Aplica-se a todas as versões*

Exibe um gráfico de barras com o número de dispositivos transferidos para o Microsoft Intune para as cargas de trabalho disponíveis. 

A lista de cargas de trabalho varia de acordo com a versão do Configuration Manager. Para obter mais informações, veja [Cargas de trabalho podem ser transferidas para o Intune](/sccm/comanage/workloads).

Focalize uma seção do gráfico para mostrar o número de dispositivos que fizeram a transição para a carga de trabalho. 

![Gráfico de barras de transição de carga de trabalho](media/co-management-dashboard/Workload-Transition.PNG)


### <a name="enrollment-errors"></a>Erros de registro

*Aplica-se à versão 1810 e posteriores*

Esta tabela é uma lista de erros de registro de dispositivos. Esses erros podem vir do componente MDM no Windows, o núcleo do sistema operacional do Windows ou o cliente do Configuration Manager. 

Há centenas de possíveis erros. A tabela a seguir lista os erros mais comuns.
<!-- SCCMDocs issue 1064, BUG 3158555 -->

| Erro | Descrição |
|---------|---------|
| 2147549183 (0x8000FFFF) | O registro do MDM não foi configurado ainda no AD do Azure, ou o registro de URL não é esperado.<br><br>[Habilitar o registro automático do Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment) |
| 2149056536 (0x80180018)<br>MENROLL_E_USERLICENSE | Licença de usuário está no registro de bloqueio de estado inválido<br><br>[Atribuir licenças a usuários](https://docs.microsoft.com/intune/licenses-assign) |
| 2149056555 (0x8018002B)<br>MENROLL_E_MDM_NOT_CONFIGURED | Ao tentar automaticamente registrado no Intune, mas a configuração do AD do Azure totalmente não é aplicada. Esse problema deve ser transitório, como as tentativas de dispositivo após um curto período. |
| 2149056554 (0x‭8018002A‬)<br>&nbsp; | O usuário cancelou a operação<br><br>Se o registro do MDM exige autenticação multifator e o usuário não tiver conectado com um segundo fator com suporte, o Windows exibe uma notificação do sistema para o usuário se registre. Se o usuário não responder para notificação do sistema, esse erro ocorre. Esse problema deve ser transitório, como o Configuration Manager será tentar novamente e avisar o usuário. Os usuários devem usar a autenticação multifator quando eles entrarem no Windows. Também instruí-los esperassem esse comportamento e se for solicitado, execute a ação. | 
| 2149056533 (0x80180015)<br>MENROLL_E_NOTSUPPORTED | Gerenciamento de dispositivos móveis geralmente não é suportado | 
| 2149056514 (0x80180002)<br>MENROLL_E_DEVICE_AUTHENTICATION_ERROR | Falha ao autenticar o usuário do servidor<br><br> Não há nenhum token do Azure AD para o usuário. Verifique se que o usuário pode autenticar no Azure AD. |
| 2147942450 (0x‭80070032‬)<br>&nbsp; | Somente há suporte para o registro automático do MDM no Windows RS3 e posteriores.<br><br>Verifique se o dispositivo atende a [requisitos mínimos](/sccm/comanage/overview#windows-10) para o cogerenciamento. |
| 3400073293 | Resposta de conta de realm ADAL usuário desconhecida<br><br>Verifique a configuração do AD do Azure e certifique-se de que os usuários possam autenticar com êxito. | 
| 3399548929 | Precisa de entrada do usuário<br><br>Esse problema deve ser temporário. Ocorre quando o usuário rapidamente sai antes de ocorre a tarefa de inscrição. | 
| 3400073236 | Falha na solicitação de token de segurança ADAL.<br><br>Verifique a configuração do AD do Azure e certifique-se de que os usuários possam autenticar com êxito. |
| 2149122477 | Problema HTTP genérico |
| 3400073247 | A autenticação integrada do ADAL do Windows só tem suporte no fluxo federado<br><br>[Planejar sua implementação de junção do Azure Active Directory híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) | 
| 3399942148 | O servidor ou proxy não foi encontrado.<br><br>Esse problema deve ser transitório, quando o cliente não pode se comunicar com a nuvem. Se ele persistir, verifique se que o cliente tem conectividade consistente com o Azure. | 
| 2149056532 | Não há suporte para plataforma específica ou versão<br><br>Verifique se o dispositivo atende a [requisitos mínimos](/sccm/comanage/overview#windows-10) para o cogerenciamento. |
| 2147943568 | Elemento não encontrado<br><br>Esse problema deve ser temporário. Se ele persistir, entre em contato com o Microsoft Support. |
| 2192179208 | Não há recursos de memória estão disponíveis para processar este comando.<br><br>Esse problema deve ser temporário, ele deve ser resolvido sozinho quando o cliente tentará novamente. |
| 3399614467 | Falha de ADAL concessão de autorização para essa asserção<br><br>Verifique a configuração do AD do Azure e certifique-se de que os usuários possam autenticar com êxito. |
| 2149056517 | Falha genérica do servidor de gerenciamento, por exemplo, erro de acesso do banco de dados<br><br>Esse problema deve ser temporário. Se ele persistir, entre em contato com o Microsoft Support. |
| 2149134055 | Nome do WinHTTP não resolvido<br><br>O cliente não é possível resolver o nome do serviço. Verifique a configuração de DNS. | 
| 2149134050 | tempo limite da Internet<br><br>Esse problema deve ser transitório, quando o cliente não pode se comunicar com a nuvem. Se ele persistir, verifique se que o cliente tem conectividade consistente com o Azure. | 


Para obter mais informações, consulte [valores de erro de registro do MDM](https://docs.microsoft.com/windows/desktop/mdmreg/mdm-registration-constants).



## <a name="deployment-policies"></a>Políticas de implantação

duas políticas são criadas no nó **Implantações** do workspace **Monitoramento**. Uma política para o grupo piloto e outra para produção. Essas políticas relatam somente o número de dispositivos nos quais o Configuration Manager aplicou a política. Elas não consideram quantos dispositivos estão registrados no Intune, o que é um requisito para que os dispositivos possam ser cogerenciados.  



## <a name="wmi-device-data"></a>Dados de dispositivo do WMI

Consulta de **SMS_Client_ComanagementState** classe WMI. Você pode criar coleções personalizadas no Configuration Manager, que ajudam a determinar o status da implantação do cogerenciamento. Para obter mais informações sobre como criar coleções personalizadas, consulte [como criar coleções](/sccm/core/clients/manage/collections/create-collections). 

Os campos a seguir estão disponíveis na classe WMI:  

- **MachineId**: Uma ID de dispositivo exclusivo para o cliente do Configuration Manager  

- **MDMEnrolled**: especifica se o dispositivo é registrado no MDM  

- **Authority**: A autoridade para os quais o dispositivo está registrado  

- **ComgmtPolicyPresent**: especifica se a política de cogerenciamento do Configuration Manager existe no cliente. Se o valor de **MDMEnrolled** for **0**, o dispositivo não será cogerenciado independentemente da existência da política de cogerenciamento no cliente.  

Um dispositivo é cogerenciado quando os campos **MDMEnrolled** e **ComgmtPolicyPresent** têm o valor **1**.  
