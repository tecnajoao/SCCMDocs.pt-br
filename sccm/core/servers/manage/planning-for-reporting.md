---
title: Planejamento para emissão de relatórios
titleSuffix: Configuration Manager
description: Dos detalhes da instalação à segurança e largura de banda de rede, é importante planejar os relatórios no Configuration Manager.
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: ff920c84-d5c8-458c-b67f-bc7219b05690
author: aczechowski
manager: dougeby
ms.author: aaroncz
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9920b8b16f076fe9f0ebf807f4231e262fcabf33
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56123147"
---
# <a name="planning-for-reporting-in-system-center-configuration-manager"></a>Planejamento para emissão de relatórios no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Os relatórios no System Center Configuration Manager fornecem um conjunto de ferramentas e recursos que ajudam a usar as funcionalidades de relatórios avançadas do SQL Server Reporting Services. Use as seções a seguir para ajudá-lo a planejar os relatórios no Configuration Manager.  

##  <a name="BKMK_InstallReportingServicesPoint"></a> Determinar onde instalar o ponto do Reporting Services  
 Quando você executa relatórios do Configuration Manager em um site, eles têm acesso às informações no banco de dados do site ao qual estão conectados. Use as seções a seguir para ajudá-lo a determinar onde instalar o ponto do Reporting Services e qual fonte de dados usar.  

> [!NOTE]  
>  Para obter mais informações sobre o planejamento de sistemas de sites no Configuration Manager, consulte [Add site system roles (Adicionar funções do sistema de sites)](../deploy/configure/add-site-system-roles.md).  

###  <a name="BKMK_SupportedSiteServers"></a> Servidores de sistema de site com suporte  
 Você pode instalar o ponto do Reporting Services em um site de administração central, em sites primários, em diversos sistemas de site em um site e em outros sites na hierarquia. Não há suporte para o ponto do Reporting Services em sites secundários. O primeiro ponto do Reporting Services em um site é configurado como o servidor de relatório padrão. É possível adicionar mais pontos do Reporting Services em um site, mas o servidor de relatório padrão em cada site é usado ativamente para relatórios do Configuration Manager. É possível instalar o ponto do Reporting Services no servidor de site ou em um sistema de site remoto. No entanto, como uma prática recomendada por motivos de desempenho, use o Reporting Services em um servidor de sistema de site remoto.  

###  <a name="BKMK_DataReplication"></a> Considerações sobre a replicação de dados  
 O Configuration Manager classifica os dados replicados como dados globais ou do site. Os dados globais referem-se a objetos criados pelos usuários administrativos e replicados a todos os sites por meio da hierarquia, enquanto os sites secundários recebem somente um subconjunto de dados globais. Exemplos de dados globais incluem implantações e atualizações de software, coleções, e escopos de segurança de administração baseada em funções. Os dados de site referem-se a informações operacionais criadas pelos sites primários do Configuration Manager e pelos clientes que relatam aos sites primários. Os dados do site replicam para o site de administração central, mas não para outros sites primários. Dados de inventário de hardware, mensagens de status, alertas e resultados de coleções baseadas em consulta são exemplos de dados do site. Os dados de site são visíveis somente no site de administração central e no site primário de onde os dados são originários.  

 Considere os fatores a seguir para ajudá-lo a determinar onde instalar seus pontos do Reporting Services:  

-   Um ponto do Reporting Services com o banco de dados do site de administração central como sua fonte de dados de relatório tem acesso a todos os dados globais e do site na hierarquia do Configuration Manager. Se você precisar de relatórios que contenham dados de site para diversos sites em uma hierarquia, instale o ponto do Reporting Services em um sistema de sites no site de administração central e use o banco de dados deste como fonte de dados de relatório.  

-   Um ponto do Reporting Services com o banco de dados do site primário filho como sua fonte de dados de relatório possui acesso aos dados globais e de site somente do site primário local e de quaisquer sites secundários filho. Os dados do site para outros sites primários na hierarquia do Configuration Manager não são replicados para o site primário. Portanto, o ponto do Reporting Services não pode acessá-los. Se você precisa de relatórios que contenham dados do site de um site primário específico ou dados globais, mas não deseja que o usuário do relatório tenha acesso aos dados do site por meio de outros sites primários, instale um ponto do Reporting Services em um sistema de sites no site primário e use o banco de dados do site primário como fonte de dados de relatório.  

###  <a name="BKMK_NetworkBandwidth"></a> Considerações sobre a largura de banda da rede  
 Os servidores do sistema de site no mesmo site se comunicam entre si usando protocolo SMB, HTTP ou HTTPS, dependendo de como você configurou o site. Como essas comunicações não são gerenciadas e podem ocorrer a qualquer momento sem o controle da largura de banda da rede, examine a largura de banda da rede disponível antes de instalar a função do ponto do Reporting Services em um sistema de site.  

> [!NOTE]  
>  Para obter mais informações sobre o planejamento de sistemas de sites, consulte [Add site system roles (Adicionar funções do sistema de sites)](../deploy/configure/add-site-system-roles.md).  

##  <a name="BKMK_RoleBaseAdministration"></a> Planejamento para administração baseada em funções para relatórios  
 A segurança para relatórios é muito parecida com a de outros objetos no Configuration Manager, em que é possível atribuir funções de segurança e permissões a usuários administrativos. Os usuários administrativos podem executar e modificar somente os relatórios para os quais têm direitos de segurança apropriados. Para executar relatórios no console do Configuration Manager, é necessário ter direito de **Leitura** para a permissão do **Site** e as permissões configuradas para objetos específicos.  

 No entanto, diferentes de outros objetos no Configuration Manager, os direitos de segurança que você define para usuários administrativos no console do Configuration Manager também devem ser configurados no Reporting Services. Quando você configura os direitos de segurança no console do Configuration Manager, o ponto do Reporting Services se conecta ao Reporting Services e define as permissões apropriadas para relatórios. Por exemplo, a função de segurança do **Gerenciador de Atualização de Software** possui as permissões de **Executar Relatório** e **Modificar Relatório** associadas a ele. Usuários administrativos que são atribuídos somente à função de **Gerenciador de Atualização de Software** podem executar e modificar relatórios apenas para atualizações de software. Relatórios para outros objetos não são exibidos no console do Configuration Manager. A exceção a isso é que alguns relatórios não estão associados a objetos protegíveis específicos do Configuration Manager. Para esses relatórios, o usuário administrativo deve ter o direito de **Leitura** para a permissão do **Site** de executar os relatórios e o direito de **Modificar** para a permissão do **Site** de modificar os relatórios.  

 Os relatórios agora são totalmente habilitados para administração baseada em função. Os dados para todos os relatórios incluídos com o Configuration Manager são filtrados com base nas permissões do usuário administrativo que executa o relatório. Usuários administrativos com funções específicas só podem visualizar informações definidas para suas funções.  

 Para obter mais informações sobre direitos de segurança para relatórios, consulte [Configure reporting (Configurar relatórios)](configuring-reporting.md).  

 Para obter mais informações sobre administração baseada em funções no Configuration Manager, consulte [Configure role-based administration (Configurar administração baseada em funções)](../deploy/configure/configure-role-based-administration.md).  

## <a name="next-steps"></a>Próximas etapas  
 Use os tópicos adicionais a seguir para ajudá-lo a planejar os relatórios no Configuration Manager:  

-   [Pré-requisitos para relatórios no System Center Configuration Manager](../../../core/servers/manage/prerequisites-for-reporting.md)  
-   [Melhores práticas para relatórios no System Center Configuration Manager](../../../core/servers/manage/best-practices-for-reporting.md)  
