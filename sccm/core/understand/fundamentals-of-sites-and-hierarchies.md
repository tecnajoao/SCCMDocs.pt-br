---
title: Conceitos básico de sites e hierarquias
titleSuffix: Configuration Manager
description: Obtenha as informações de conceitos básicos sobre os sites e hierarquias do System Center Configuration Manager.
ms.date: 12/30/2016
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 4db1e15f-e832-4cf9-be33-d3971e635a55
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00465c431ded49c3833b19a3efd1da05ad1c388d
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56124629"
---
# <a name="fundamentals-of-sites-and-hierarchies-for-system-center-configuration-manager"></a>Conceitos básicos de sites e hierarquias do System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Uma implantação do System Center Configuration Manager deve ser instalada em um domínio do Active Directory. A base desta implantação inclui um ou mais sites do Configuration Manager que formam uma hierarquia de sites. De um único site para uma hierarquia com vários sites, o tipo e o local dos sites instalados fornecem a capacidade de escalar verticalmente (expandir) sua implantação quando necessário, bem como fornecer serviços a usuários e dispositivos gerenciados.

## <a name="hierarchies-of-sites"></a>Hierarquias de sites
Quando você instala o System Center Configuration Manager pela primeira vez, o primeiro site do Configuration Manager instalado determina o escopo da hierarquia. O primeiro site do Configuration Manager é a base da qual você gerenciará dispositivos e usuários em sua empresa. Esse primeiro site deve ser um site de administração central ou um site primário autônomo.  

 Um *site de administração central* é adequado para implantações de grande escala, fornece um ponto central de administração e fornece a flexibilidade para dar suporte a dispositivos distribuídos em uma infraestrutura de rede global. Depois de instalar um site de administração central, é necessário instalar um ou mais sites primários como sites filho. Essa configuração é necessária porque um site de administração central não oferece suporte direto ao gerenciamento de dispositivos, que é a função de um site primário. Um site de administração central dá suporte a diversos sites primários filho. Os sites primários filho são usados para gerenciar diretamente os dispositivos e controlar a largura de banda da rede quando os dispositivos gerenciados estão em diferentes localizações geográficas.  

 Um *site primário autônomo* é adequado para implantações menores, podendo ser usado para gerenciar dispositivos sem ter que instalar sites adicionais. Embora um site primário autônomo possa limitar o tamanho da sua implantação, ele dá suporte a um cenário para posterior expansão da hierarquia através da instalação de um novo site de administração central. Com esse cenário de expansão de site, o site primário autônomo se torna um site primário filho e então, você pode instalar sites primários filho adicionais abaixo do novo site de administração central. Dessa forma, é possível expandir a implantação inicial para o futuro crescimento de sua empresa.  

> [!TIP]  
>  Um site primário autônomo e um site primário filho são na realidade do mesmo tipo: um site primário. A diferença no nome se baseia na relação de hierarquia que é criada quando você também usa um site de administração central. Essa relação de hierarquia também pode limitar a instalação de certas funções do sistema de sites que estendem a funcionalidade Configuration Manager. Essa limitação de funções ocorre porque determinadas funções do sistema de sites só podem ser instaladas no site de nível superior da hierarquia: um site de administração central ou um site primário autônomo.  

 Depois de instalar seu primeiro site, você poderá instalar sites adicionais. Se seu primeiro site foi um site de administração central, você poderá instalar um ou mais sites primários filho. Depois de instalar um site primário (autônomo ou primário filho), você pode instalar um ou mais sites secundários.  

 Um *site secundário* só pode ser instalado como um site filho abaixo de um site primário. Esse tipo de site estende o alcance de um site primário para gerenciamento de dispositivos em locais que têm uma conexão de rede lenta com o site primário. Embora o site secundário estenda o site primário, o site primário gerencia todos os clientes. O site secundário fornece suporte para dispositivos no local remoto. Ele oferece suporte através da compactação e gerenciamento da transferência de informações na rede que você envia (implanta) para clientes e que os clientes enviam de volta para o site.  

 Os diagramas a seguir mostram alguns exemplos de designs de site.  

 ![Exemplos de hierarquia](media/Hierarchy_examples.png)  

 Para mais informações, consulte os seguintes tópicos:  

-   [Introduction to System Center Configuration Manager](../../core/understand/introduction.md)  

-   [Criar uma hierarquia de sites para o System Center Configuration Manager](../../core/plan-design/hierarchy/design-a-hierarchy-of-sites.md)  

-   [Instalar sites do System Center Configuration Manager](/sccm/core/servers/deploy/install/installing-sites)  

## <a name="site-system-servers-and-site-system-roles"></a>Servidores do sistema de site e funções do sistema de site  
 Cada site do Configuration Manager instala *funções do sistema de sites* que dão suporte às operações de gerenciamento. As funções a seguir são instaladas por padrão quando você instala um site:

-   A função de servidor de site é atribuída ao computador no qual você instala o site.

-   A função de servidor de banco de dados do site é atribuída ao SQL Server que hospeda o banco de dados do site.

Outras funções do sistema de sites são opcionais e são usadas somente quando você quer usar a funcionalidade que esteja ativa em uma função do sistema de sites. Qualquer computador que hospede uma função do sistema de sites é conhecido como servidor do sistema de sites.  

 Para uma implantação menor do Configuration Manager, inicialmente, você pode executar todas as funções do sistema de sites diretamente no computador do servidor do site. Depois, conforme o ambiente gerenciado e as necessidades aumentam, é possível instalar servidores adicionais do sistema de sites para hospedar mais funções do sistema de sites, a fim de aprimorar a eficiência do site no fornecimento de serviços a mais dispositivos.  

 Para obter informações sobre como planejar diferentes funções do sistema de sites, consulte [Funções do sistema de sites](../../core/plan-design/hierarchy/plan-for-site-system-servers-and-site-system-roles.md#bkmk_planroles) em [Planejar servidores de sistema de sites e funções de sistema de sites no System Center Configuration Manager](../../core/plan-design/hierarchy/plan-for-site-system-servers-and-site-system-roles.md).

## <a name="publishing-site-information-to-active-directory-domain-services"></a>Publicando informações de sites nos Serviços de Domínio Active Directory  
 Para simplificar o gerenciamento do Configuration Manager, é possível estender o esquema do Active Directory para dar suporte aos detalhes usados pelo Configuration Manager e, assim, os sites publicam suas principais informações no AD DS (Active Directory Domain Services). Então, os computadores que você deseja gerenciar podem recuperar com segurança informações relacionadas ao site da fonte confiável do AD DS. As informações que os clientes podem recuperar identificam sites disponíveis, servidores do sistema de sites e os serviços que esses servidores do sistema de sites fornecem.  

 *A extensão do esquema do Active Directory* é feita apenas uma vez para cada floresta e pode ser feita antes ou depois da instalação do Configuration Manager.   Quando você estende o esquema, é necessário criar um novo contêiner do Active Directory chamado System Management em cada domínio. O contêiner contém um site do Configuration Manager para publicar dados para serem localizados por clientes. Para obter mais informações, consulte [Preparar o Active Directory para publicação de sites](../../core/plan-design/network/extend-the-active-directory-schema.md).  

 *A publicação de dados do site* aprimora a segurança da hierarquia do Configuration Manager e reduz a sobrecarga administrativa, mas não é obrigatória para funcionalidades básicas do Configuration Manager.  
