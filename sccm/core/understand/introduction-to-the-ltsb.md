---
title: Introdução ao Branch de Manutenção em Longo Prazo
titleSuffix: Configuration Manager
description: Saiba mais sobre o Branch de Manutenção em Longo Prazo do System Center Configuration Manager.
ms.date: 05/01/2017
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 694bc29f-a7fd-4e06-815a-1a9c5e9ac563
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: f714be298c244b86178780138f5a700c89ae2a76
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56128976"
---
# <a name="introduction-to-the-long-term-servicing-branch-of-system-center-configuration-manager"></a>Introdução ao Branch de Manutenção em Longo Prazo do System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (branch de manutenção em longo prazo)*

O LTSB (Branch de Manutenção em Longo Prazo) do System Center Configuration Manager é uma ramificação distinta do Configuration Manager que foi projetado como uma opção de instalação disponível para todos os clientes. No entanto, é a única opção para clientes que descontinuam seus direitos de assinatura do Software Assurance (SA) ou equivalente para o Configuration Manager.


Com base no Configuration Manager versão 1606, o LTSB tem menos funcionalidades quando comparado com o Branch Atual do Configuration Manager.

 > [!TIP]   
 > Se estava procurando informações sobre os canais do **Windows Server**, confira o artigo [Windows Server 2016 new Current Branch for Business servicing option]( https://blogs.technet.microsoft.com/windowsserver/2016/07/12/windows-server-2016-new-current-branch-for-business-servicing-option/) (Nova opção de manutenção do Branch Atual para Negócios do Windows Server 2016).

## <a name="features-that-are-not-available-in-the-ltsb-of-configuration-manager"></a>Recursos que não estão disponíveis no LTSB do Configuration Manager
O Branch Atual do Configuration Manager oferece suporte à seguinte funcionalidade que não está disponível quando você usa o LTSB:

-   Atualizações no console que adicionam novos recursos e aprimoramentos.
-   Suporte para sistemas operacionais recém-lançados para uso como clientes e servidores de site.
-   Use uma assinatura do Microsoft Intune para oferecer suporte a:
    -   Intune em uma configuração de MDM (Gerenciamento de Dispositivo Móvel) híbrido
    -   MDM local
-   O Painel de Serviço e os Planos de Serviço do Windows 10, incluem suporte às versões do CB (Branch Atual) e do CBB (Branch Atual para Negócios) do Windows 10.  
-   Suporte para versões futuras do Windows Server e do Windows 10 LTSB
-   Asset Intelligence
-   Pontos de distribuição baseados em nuvem
-   Exchange Online como um Exchange Connector    

Embora o suporte para esses recursos não esteja disponível no LTSB, alguns recursos permanecem visíveis no console do Configuration Manager, mas não podem ser selecionados ou usados.


## <a name="find-documentation-for-the-ltsb"></a>Localizar a documentação para o LTSB
O LTSB tem base na versão 1606 do Branch Atual. Para ver a documentação do produto, use a [documentação do Branch Atual](https://docs.microsoft.com/sccm/), com restrições e limitações específicas ao LTSB. Essas restrições e limitações são identificadas nos seguintes tópicos online:

- [Introdução ao Branch de Manutenção em Longo Prazo](introduction-to-the-ltsb.md): (este tópico)
- [Instalar o Branch de Manutenção de Longo Prazo](install-the-ltsb.md)
- [Atualizar o Branch de Manutenção em Longo Prazo para o Branch Atual](convert-to-current-branch.md)
- [Configurações com suporte para o Branch de Manutenção em Longo Prazo](supported-configurations-for-ltsb.md)
- [Gerenciar o Branch de Manutenção de Longo Prazo do Configuration Manager](manage-the-ltsb.md)

Quando você consultar a documentação do Branch Atual para o LTSB, os detalhes que se aplicam à versão 1606 também se aplicarão ao LTSB. O LTSB não dá suporte para recursos ou detalhes introduzidos na versão 1610 ou posterior.


## <a name="licensing-overview-for-the-ltsb"></a>Visão geral do licenciamento para o LTSB   
Os clientes com SA (Software Assurance) ativo para as licenças do System Center Configuration Manager ou com direitos de assinatura equivalentes a partir de 1º de outubro de 2016 têm direito de usar a versão 1606, de outubro de 2016, do System Center Configuration Manager. Clientes que adquiriram direitos do System Center Configuration Manager em ou após 1º de outubro de 2016 encontrarão duas opções licenciadas durante a instalação: Branch Atual e LTSB (Branch de Manutenção de Longo Prazo).

Clientes que têm direitos perpétuos do System Center Configuration Manager ou que permitirem que o SA ou a assinatura expire após 1º de outubro podem instalar a versão do LTSB do System Center Configuration Manager que for atual no momento em que a licença expirar.

[Os termos e condições completos dos produtos que você compra por meio dos programas de licenciamento por volume da Microsoft podem ser encontrados aqui](http://go.microsoft.com/fwlink/?LinkId=800052).

Para saber mais sobre licenciamento para branches do Configuration Manager, confira [Licenciamento e branches do System Center Configuration Manager](learn-more-editions.md).

## <a name="next-steps"></a>Próximas etapas

Se você decidir que o Configuration Manager LTSB é o branch correto para seu ambiente, [instale um novo site do LTSB](/sccm/core/understand/install-the-ltsb#install-a-new-site) como parte de uma nova hierarquia, ou [atualize um site e hierarquia do System Center 2012 Configuration Manager](/sccm/core/understand/install-the-ltsb#upgrade-from-system-center-2012-configuration-manager).

Se você não tiver a mídia de instalação, veja [Documentação do System Center 2016](https://technet.microsoft.com/system-center-docs/system-center) para obter informações sobre como obter System Center 2016, que inclui a mídia que você pode usar para instalar o System Center Configuration Manager LTSB.  
