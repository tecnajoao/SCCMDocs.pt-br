---
title: Qual branch devo usar | System Center Configuration Manager
description: "Aprenda as diferenças entre os branches do System Center Configuration Manager disponíveis."
ms.custom: na
ms.date: 10/12/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a3be4f8f-3d44-4e3c-9fa1-e85f30a36e72
caps.latest.revision: 0
author: Brenduns
ms.author: brenduns
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: bbaaf9ed876f7693ea831be7c787dba904197a62
ms.openlocfilehash: 3957e854e980246c410f7de27caed9d66fc4829f


---
# <a name="which-branch-of-configuration-manager-should-i-use"></a>Qual branch do Configuration Manager devo usar?

*Aplica-se a: System Center Configuration Manager (Branch Atual), (Branch de Manutenção em Longo Prazo), (Technical Preview)*


Desde outubro de 2016, há três branches do System Center Configuration Manager disponíveis. Use este tópico para ajudá-lo a escolher o branch correto para você.

## <a name="current-branch-of-system-center-configuration-manager"></a>Branch atual do System Center Configuration Manager
Essa é um branch licenciado para uso em um ambiente de produção em que você deseja a opção de ter os recursos e funcionalidades mais recentes. Esse é o branch que você deve usar quando tiver um dos seguintes: System Center Datacenter, System Center Standard, System Center Configuration Manager ou direitos de assinatura equivalentes.  Para mais informações sobre as opções de licenciamento e Software Assurance, confira [Licensing and branches for System Center Configuration Manager](learn-more-editions.md) (Licenciamento e branches do System Center Configuration Manager).


>  [!TIP]
> O Branch Atual também pode ser instalado como uma edição de avaliação que não requer uma licença. A edição de avaliação pode ser usada por 180 dias e dá suporte à atualização para uma edição licenciada do Branch Atual.

O Branch Atual é atualizado várias vezes ao ano com novos recursos. Cada versão de atualização tem suporte para um (1) ano após seu lançamento. Você deve atualizar para uma versão mais recente do Branch Atual na data da validade ou antes da validade desse período de um ano. As atualizações para as versões mais novas estão disponíveis como atualizações no console.

Para instalar o Branch Atual como um novo site ou como uma atualização do *System Center 2012 Configuration Manager with Service Pack 2* ou *System Center 2012 R2 Configuration Manager with Service Pack 1*, use a [mídia de linha de base](/sccm/core/servers/manage/updates#baseline-and-update-versions) do System Center Configuration Manager fornecida como um DVD com o System Center 2016 ou que está disponível como parte da versão autônoma do System Center Configuration Manager. O acesso a esta mídia depende de como o System Center Configuration Manager foi licenciado.

Você também pode usar a mídia de linha de base para instalar um novo site de uma edição de avaliação do Branch Atual. Se você deseja instalar apenas uma edição de avaliação, pode obter o software do site do [Centro de Avaliação do TechNet](https://www.microsoft.com/evalcenter/evaluate-system-center-configuration-manager-and-endpoint-protection).

>  [!NOTE]
> Você usa a mídia de linha de base para instalar sites para uma nova hierarquia do Configuration Manager. Se você instalou uma versão de linha de base como a versão 1511 anteriormente, use as atualizações no console para atualizar seus sites para uma nova versão, como a 1606.
>
> Sites que são atualizados usando atualizações no console resultam em um site igual ao novo site instalado usando a mídia de linha de base.
>
> Para mais informações, confira [Updates for System Center Configuration Manager](/sccm/core/servers/manage/updates) (Atualizações para o System Center Configuration Manager).

**Recursos do Branch Atual:**
- Recebe [atualizações no console](/sccm/core/servers/manage/install-in-console-updates) que disponibilizam novos recursos para uso.
- Recebe atualizações no console que fornecem correções de segurança e qualidade para os recursos existentes.
- Dá suporte a atualizações fora da banda quando necessário. Confira [Usar a ferramenta de registro de atualização](/sccm/core/servers/manage/use-the-update-registration-tool-to-import-hotfixes) ou [Usar o instalador do hotfix](/sccm/core/servers/manage/use-the-hotfix-installer-to-install-updates).
- Pode interoperar com o Microsoft Intune e outros serviços baseados em nuvem e infraestrutura.
- Dá suporte à [migração de dados](/sccm/core/migration/migrate-data-between-hierarchies) de e para outras instalações do Configuration Manager.
- Dá suporte à atualização de versões anteriores do Configuration Manager.
- Dá suporte à instalação como uma instalação de avaliação, por meio da qual você pode atualizar para uma instalação totalmente licenciada posteriormente.

A versão inicial do Branch Atual foi a versão 1511. Atualizações subsequentes incluem as versões 1602, 1606 e assim por diante. Cada versão permanece no suporte por um ano e a Microsoft recomenda que você atualize para a versão mais nova logo após seu lançamento. Você pode esperar por até um ano antes de atualizar para uma versão mais nova e também pode ignorar uma atualização para instalar a versão mais nova disponível. Como cada versão é cumulativa, se você pular uma atualização e instalar a versão mais recente, ainda terá acesso a todos os recursos e aprimoramentos de versões anteriores.

Para mais informações, confira [Support for Current Branch versions](/sccm/core/servers/manage/current-branch-versions-supported) (Suporte para versões do Branch Atual).

**Opções de atualização:**
- Com o Software Assurance, você pode instalar atualizações no console para versões do Branch Atual.  
- Não há nenhuma opção para converter o Branch Atual em um Technical Preview. Os Technical Previews são instalações separadas que não exigem uma licença.
- Não há nenhuma opção para converter seu Branch Atual para o LTSB (Branch de Manutenção em Longo Prazo). Você deve desinstalar o Branch Atual e, em seguida, desinstalar o LTSB como uma nova instalação.

##  <a name="long-term-servicing-branch-ltsb-of-system-center-configuration"></a>O LTSB (Branch de Manutenção em Longo Prazo) do System Center Configuration
Esse é um branch licenciado para uso na produção para clientes do Configuration Manager que estão usando o Branch Atual e que permitiram que o SA (Software Assurance) do Configuration Manager ou seus direitos de assinatura equivalentes expirassem após 1º de outubro de 2016.  Para informações sobre as opções de licenciamento e Software Assurance, confira [Licensing and branches for System Center Configuration Manager](learn-more-editions.md) (Licenciamento e branches do System Center Configuration Manager).

O LTSB não recebe atualizações no console que oferecem novas funcionalidades ou atualiza funcionalidades existentes. No entanto, correções de segurança críticas são fornecidas.

Para instalar o LTSB como um novo site ou uma atualização do site do Configuration Manager 2012 com suporte, use a [mídia de linha de base](/sccm/core/servers/manage/updates#baseline-and-update-versions) da versão 1606 obtida como um DVD com a versão do System Center 2016 ou System Center Configuration Manager (Branch Atual e Branch de Manutenção em Longo Prazo 1606). Você pode usar a mídia de linha de base para instalar um novo site que executa a versão 1606 do Branch Atual ou um novo site que executa o Branch de Manutenção em Longo Prazo.

> [!TIP]  
> Para saber sobre o System Center 2016, confira a [documentação do System Center 2016](https://technet.microsoft.com/system-center-docs/System-Center-2016). Esta documentação também identifica como obter o System Center 2016, que exige um contrato de licença da Microsoft ou direitos semelhantes.  Você também pode obter uma Avaliação do System Center 2016 do [Centro de Avaliação do TechNet](https://www.microsoft.com/evalcenter/evaluate-system-center-technical-preview).

**Recursos do LTSB:**
-   Recebe atualizações no console que fornecem correções de segurança críticas.
- Fornece uma opção de instalação quando o contrato de SA ou direitos equivalentes para o Configuration Manager tiverem expirado.
- Dá suporte à atualização (conversão) para o Branch Atual quando você tem um contrato de SA atual ou direitos equivalentes para o Configuration Manager.

**Limitações:**  
O LTSB se baseia na versão 1606 do Branch Atual e tem as seguintes limitações:
- O LTSB tem suporte por 10 anos de atualizações de segurança críticas após sua disponibilidade geral (outubro de 2016), após o qual o suporte para esse branch expira.  Para mais informações sobre o ciclo de vida de suporte, confira [Política de Ciclo de Vida da Microsoft](https://support.microsoft.com/en-us/lifecycle).
- Dá suporte a uma lista de definições limitada dos sistemas operacionais do servidor e do cliente e tecnologias relacionadas, como as versões do SQL Server.  Para mais informações sobre o que tem suporte com esse branch, confira [Configurações com suporte para o Branch de Manutenção em Longo Prazo](supported-configurations-for-ltsb.md).
- Não recebe atualizações para novos recursos.
- Não dá suporte à adição de uma Assinatura do Microsoft Intune, o que impede o uso do:
  - Intune em uma configuração de MDM híbrida
 - MDM local
-   Não dá suporte ao uso do Painel de Serviço do Windows 10, Planos de Serviço e não dá suporte ao CB (Branch Atual) e ao CBB (Branch Atual para Negócios) do Windows 10
- Não dá suporte a versões futuras do Windows 10 LTSB e do Windows Server
-   Não há suporte para o Asset Intelligence
-   Não há suporte para pontos de distribuição baseados em nuvem
-   O Suporte para o Exchange Online não tem suporte como um Exchange Connector
-   Não dá suporte a nenhum recurso de pré-lançamento



**Opções de atualização:**
- Você pode converter sua instalação LTSB para uma instalação de Branch Atual. A conversão para o Branch Atual tem suporte antes ou depois do suporte ao LTSB expirar.

  Para converter, você deve ter um contrato de Software Assurance ativo com a Microsoft.  Para mais informações, consulte os links a seguir:
  - [Atualizar o Branch de Manutenção em Longo Prazo para o Branch Atual](convert-to-current-branch.md)
  - [Licenciamento e branches do System Center Configuration Manager](learn-more-editions.md)
  - [Baseline and update versions](/sccm/core/servers/manage/updates#baseline-and-update-versions) (Versões de linha de base e atualização) em [Updates for Configuration Manager](/sccm/core/servers/manage/updates) (Atualizações para o Configuration Manager)
- Não há nenhuma opção para converter o LTSB em um Technical Preview. Os Technical Previews são instalações separadas que não exigem uma licença.
-   Você não pode atualizar uma edição de avaliação do Branch Atual para uma instalação do LTSB.


## <a name="technical-preview-for-system-center-configuration-manager"></a>Visualização técnica do System Center Configuration Manager
O Technical Preview é para uso em um ambiente de laboratório em que você deseja conhecer e testar os recursos mais recentes sendo desenvolvidos para o Configuration Manager. O Technical Preview não tem suporte em um ambiente de produção e não requer que você tenha um contrato de licença do Software Assurance.

Para instalar um novo site que executa o Technical Preview, use a [mídia de linha de base do System Center Configuration Manager Technical Preview](/sccm/core/get-started/technical-preview#install-and-update-the-technical-preview) mais recente. Depois de instalar o Technical Preview, há novas versões disponíveis como atualizações no console todo mês.

**Recursos do Technical Preview:**
-  Com base nas versões de linha de base recente do Branch Atual.
-  Recebe atualizações no console que atualizam sua instalação para a versão mais recente de Technical Preview.
-  Inclui novos recursos que estão sendo desenvolvidos e para os quais nossos desenvolvedores gostariam de receber seus comentários.
-  Recebe atualizações que se aplicam apenas ao branch de Technical Preview.

**Limitações:**
-  [O suporte é limitado](/sccm/core/get-started/technical-preview#requirements-and-limitatins-for-the-techincal-preview), incluindo apenas um único site primário e até 10 clientes.  
-  Não pode ser atualizada para o Branch Atual ou o LTSB.
-  Não dá suporte ao uso da migração para importar ou exportar dados para outra instalação do Configuration Manager.
-  Não dá suporte à atualização de versões anteriores do Configuration Manager.
-  Não dá suporte à instalação como uma instalação de avaliação.

Recursos que são introduzidos pela primeira vez em um Technical Preview geralmente são adicionados ao Branch Atual em uma atualização posterior.  Cada nova versão da Technical Preview inclui os recursos dos technical previews anteriores, mesmo após esses recursos terem sido adicionados ao Branch Atual.

Para mais informações, confira [Technical Preview do System Center Configuration Manager](/sccm/core/get-started/technical-preview).

**Opções de atualização:**
-   Você pode instalar qualquer atualização no console para uma nova versão de Technical Preview.
-   Não há nenhuma opção de converter um Technical Preview para o Branch Atual ou LTSB.



<!--HONumber=Nov16_HO1-->

