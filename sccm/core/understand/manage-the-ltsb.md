---
title: Gerenciar o LTSB | Microsoft Docs
description: "Gerenciamento de diferenças para o LTSB do System Center Configuration Manager."
ms.custom: na
ms.date: 05/01/2017
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8da2887a-fd8e-438c-b926-849c121f7fdf
caps.latest.revision: 0
author: Brenduns
ms.author: brenduns
manager: angrobe
ms.translationtype: Human Translation
ms.sourcegitcommit: 31819a1df4e63e1114682490a9b3c3b4e5c99cfa
ms.openlocfilehash: 9c6f349ead906532a7a58df74609de976769e251
ms.contentlocale: pt-br
ms.lasthandoff: 05/17/2017


---
# <a name="manage-the-long-term-servicing-branch-of-configuration-manager"></a>Gerenciar o Branch de Manutenção de Longo Prazo do Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch de Manutenção em Longo Prazo)*

Quando você usa o LTSB (Branch de Manutenção de Longo Prazo) do System Center Configuration Manager, as informações a seguir podem ajudar você a compreender as alterações importantes que afetam a maneira como você gerencia sua infraestrutura.

Como o LTSB é equivalente à versão 1606 do Branch Atual (com algumas exceções, como a integração do Intune e os recursos relacionados à nuvem), a maioria das tarefas de planejamento, implantação, configuração e gerenciamento diário são as mesmas.

Por exemplo, o LTSB dá suporte ao mesmo número de sites, tipos de site, clientes e infraestrutura geral que o Branch Atual. Portanto, você pode usar as diretrizes encontradas nos tópicos sobre design e planejamento de hierarquia e site para o Branch Atual. Da mesma forma, para recursos com o LTSB com suporte dos dois branches, como Atualizações de Software ou Implantação de Sistema Operacional, use as diretrizes encontradas nas seções da documentação do Branch Atual com as advertências sobre não ter acesso às alterações de recurso introduzidas após a versão 1606 do Branch Atual.

As seções a seguir fornecem informações sobre gerenciar tarefas que não são semelhantes.

## <a name="updates-and-servicing"></a>Atualizações e serviços
Somente as atualizações de segurança críticas são disponibilizadas como atualizações no console no LTSB.  

As informações sobre as atualizações regulares para as versões subsequentes do Branch Atual estão visíveis nesse console, mas não estão disponíveis no LTSB. Elas não são baixadas e não podem ser instaladas.

Para dar suporte às atualizações no console para as correções de segurança críticas, um site do LTSB requer o uso do [ponto de conexão de serviço](/sccm/core/servers/deploy/configure/about-the-service-connection-point). É possível configurar essa função de sistema de sites no modo offline ou online, como é feito para o Branch Atual. O LTSB coleta e envia os mesmos dados de telemetria e uso que o Branch Atual.

O LTSB dá suporte ao uso da ferramenta de Registro de Atualização e Instalador de Hotfix, como documentado para o Branch Atual.

Para obter informações gerais sobre atualizações e manutenção, confira [Updates for System Center Configuration Manager](/sccm/core/servers/manage/updates) (Atualizações para o System Center Configuration Manager).


## <a name="changes-for-site-expansion-and-the-cdlatest-folder"></a>Alterações para a expansão de site e para a pasta CD.Latest
Quando você executa o LTSB e está expandindo um site primário autônomo instalando um novo site de administração central, deve usar a Instalação e os arquivos de origem da mídia de linha de base da versão 1606. Para o Branch Atual, você executa a Instalação e usa os arquivos de origem da pasta CD.Latest.

Embora você não execute a Instalação para a expansão do site da pasta CD.Latest, você continua a usar a pasta CD.Latest para a recuperação de site e para instalar um novo site primário filho quando seu primeiro site do LTSB era um site de administração central.

Para saber mais sobre expansão do site, confira [Expandir um site primário autônomo](/sccm/core/servers/deploy/install/use-the-setup-wizard-to-install-sites#expand-a-stand-alone-primary-site). Para mais informações sobre a pasta CD.Latest, confira [The CD.Latest folder](/sccm/core/servers/manage/the-cd.latest-folder) (A pasta CD.Latest).


## <a name="recovery"></a>Recuperação
Quando você recupera um site, é necessário restaurar o site ou o banco de dados do site para seu branch original. Não é possível recuperar um banco de dados do site do Branch Atual para uma instalação do LTSB ou vice-versa.
