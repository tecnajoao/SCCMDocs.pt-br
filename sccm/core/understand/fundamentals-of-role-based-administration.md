---
title: Fundamentos da administração baseada em funções
titleSuffix: Configuration Manager
description: Use a administração baseada em funções para controlar o acesso administrativo ao Configuration Manager e aos objetos gerenciados.
ms.date: 1/3/2017
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 0a2d6c3f-a4e4-4c19-b087-3caada480de9
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d5da8213f3e0b0f53961b74e11d6f27662ee340
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56119986"
---
# <a name="fundamentals-of-role-based-administration-for-system-center-configuration-manager"></a>Fundamentos de administração baseada em funções para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Com o System Center Configuration Manager, você usa administração baseada em funções para proteger o acesso necessário para administrar o Configuration Manager. Você também protege o acesso aos objetos que você gerencia, como coleções, implantações e sites. Depois de entender os conceitos apresentados neste tópico, você poderá [Configurar administração baseada em funções para o System Center Configuration Manager](../../core/servers/deploy/configure/configure-role-based-administration.md).  

 O modelo de administração baseada em funções define e gerencia configurações de acesso de segurança de toda a hierarquia para todos os sites e configurações de sites usando o seguinte:  

- *Funções de segurança* são atribuídas a usuários administrativos para fornecer a esses usuários (ou grupos de usuários) permissões para objetos diferentes do Configuration Manager. Por exemplo, permissões para criar ou alterar as configurações de cliente.  

- *Escopos de segurança* são usados para agrupar instâncias específicas de objetos pelas quais um usuário administrativo é responsável por gerenciar, como um aplicativo que instala o Microsoft Office 2010.  

- *Coleções* são usadas para especificar grupos de recursos de usuários e de dispositivos que o usuário administrativo pode gerenciar.  

  Com a combinação de funções de segurança, escopos de segurança e coleções, você segrega as atribuições administrativas que atendem aos requisitos da sua organização. Usadas em conjunto, elas definem o escopo administrativo de um usuário, que é o que esse usuário poderá exibir e gerenciar na sua implantação do Configuration Manager.  

## <a name="benefits-of-role-based-administration"></a>Benefícios da administração baseada em funções  

-   Os sites não são usados como limites administrativos.  

-   Você cria usuários administrativos para uma hierarquia e somente precisa atribuir segurança a eles uma vez.  

-   Todas as atribuições de segurança são replicadas e estão disponíveis em toda a hierarquia.  

-   Há funções de segurança internas que são usadas para atribuir as tarefas administrativas típicas. Criar suas próprias funções de segurança personalizadas para oferecer suporte às necessidades específicas do seu negócio.  

-   Os usuários administrativos veem apenas os objetos que eles têm permissões para gerenciar.  

-   Você pode auditar ações de segurança administrativa.  

Ao projetar e implementar a segurança administrativa para o Configuration Manager, use o seguinte para criar um *escopo administrativo* para um usuário administrativo:  

-   [Funções de segurança](#bkmk_Planroles)  

-   [Coleções](#bkmk_planCol)  

-   [Escopos de segurança](#bkmk_PlanScope)  


 O escopo administrativo controla os objetos que um usuário administrativo exibe no console do Configuration Manager e controla as permissões que um usuário tem nesses objetos. Configurações de administração baseadas em funções replicam em cada site na hierarquia como dados globais e, em seguida, são aplicadas a todas as conexões administrativas.  

> [!IMPORTANT]  
>  Atrasos de replicação entre sites podem impedir que um site receba alterações para a administração baseada em funções. Para obter informações sobre como monitorar a replicação de banco de dados entre sites, consulte o tópico [Transferências de dados entre sites no System Center Configuration Manager](../../core/servers/manage/data-transfers-between-sites.md).  

##  <a name="bkmk_Planroles"></a> Funções de segurança  
 Use as funções de segurança para conceder permissões de segurança a usuários administrativos. Funções de segurança são grupos de permissões de segurança atribuídas a usuários administrativos para que eles executem suas tarefas administrativas. Essas permissões de segurança definem as ações administrativas que um usuário administrativo pode executar e as permissões concedidas a tipos de objetos particulares. Como uma prática recomendada de segurança, atribua as funções de segurança que fornecem o mínimo de permissões.  

 O Configuration Manager tem diversas funções de segurança internas para suporte de agrupamentos típicos de tarefas administrativas, e é possível criar suas próprias funções de segurança personalizadas para oferecer suporte a seus requisitos específicos de negócios. Exemplos de funções de segurança interna:  

-   *Administrador Completo* concede todas as permissões no Configuration Manager.  

-   O *Gerenciador de Ativos* concede permissões para gerenciar o Ponto de sincronização do Asset Intelligence, as classes de relatórios do Asset Intelligence, o inventário de software, o inventário de hardware e as regras de medição.  

-   *Gerenciador de Atualização de Software* concede permissões para definir e implantar atualizações de software. Usuários administrativos associados a essa função podem criar coleções, grupos de atualização de software, implantações e modelos.  

> [!TIP]  
>  Você pode exibir a lista de funções de segurança internas e funções de segurança personalizadas que você cria, incluindo suas descrições, no console do Configuration Manager. Para exibir as funções, no workspace **Administração**, expanda **Segurança** e, em seguida, selecione **Funções de Segurança**.  

 Cada função de segurança tem as permissões específicas para diferentes tipos de objeto. Por exemplo, a função de segurança *Autor de Aplicativos* tem as seguintes permissões para aplicativos: Aprovar, Criar, Excluir, Modificar, Modificar Pasta, Mover Objeto, Ler, Executar Relatório e Definir Escopo de Segurança.

 Você não pode alterar as permissões das funções de segurança internas, mas pode copiar a função, fazer alterações e então salvar essas alterações como uma nova função de segurança personalizada. Também é possível importar funções de segurança que você exportou de outra hierarquia, por exemplo, de uma rede de teste. Examine as funções de segurança e suas permissões para determinar se você usará as funções de segurança internas ou precisará criar suas próprias funções de segurança personalizadas.  

 ### <a name="to-help-you-plan-for-security-roles"></a>Para ajudá-lo a planejar as funções de segurança  

1.  Identificar as tarefas que os usuários administrativos executam no Configuration Manager. Essas tarefas podem estar relacionadas a um ou mais grupos de tarefas de gerenciamento, como implantação de aplicativos e pacotes, implantação de sistemas operacionais e configurações para conformidade, configuração de sites e segurança, auditoria, controle de computadores remotamente e coleta de dados de inventário.  

2.  Mapear essas tarefas administrativas a uma ou mais funções de segurança internas.  

3.  Se algum dos usuários administrativos executar as tarefas de diversas funções de segurança, atribua-as a esses usuários administrativos em vez de criar uma nova função de segurança que combine as tarefas.  

4.  Se as tarefas identificadas não mapearem para as funções de segurança internas, crie e teste novas funções de segurança.  

Para obter informações sobre como criar e configurar funções de segurança para administração baseada em funções, consulte [Criar funções de segurança personalizadas](../../core/servers/deploy/configure/configure-role-based-administration.md#BKMK_CreateSecRole) e [Configurar funções de segurança](../../core/servers/deploy/configure/configure-role-based-administration.md#BKMK_ConfigSecRole) no tópico [Configurar administração baseada em funções para o System Center Configuration Manager](../../core/servers/deploy/configure/configure-role-based-administration.md).  

##  <a name="bkmk_planCol"></a> Coleções  
 Coleções especificam os recursos de usuário e computador que um usuário administrativo pode exibir ou gerenciar. Por exemplo, para usuários administrativos implantarem aplicativos ou executarem controle remoto, eles devem ser atribuídos a uma função de segurança que conceda acesso a uma coleção que contenha esses recursos. Você pode selecionar coleções de usuários ou dispositivos.  

 Para obter mais informações sobre coleções, consulte [Introdução a coleções no System Center Configuration Manager](../../core/clients/manage/collections/introduction-to-collections.md).  

 Para configurar administração baseada em funções, verifique se você precisa criar novas coleções por algum dos seguintes motivos:  

-   Organização funcional. Por exemplo, separar as coleções de servidores e estações de trabalho.  

-   Alinhamento geográfico. Por exemplo, separar as coleções para América do Norte e Europa.  

-   Requisitos de segurança e processos de negócios. Por exemplo, separar coleções para computadores de teste e de produção.  

-   Alinhamento da organização. Por exemplo, separar as coleções para cada unidade de negócios.  

Para obter informações sobre como configurar coleções para administração baseada em funções, consulte [Configurar coleções para gerenciar a segurança](../../core/servers/deploy/configure/configure-role-based-administration.md#BKMK_ConfigColl) no tópico [Configurar administração baseada em funções para o System Center Configuration Manager](../../core/servers/deploy/configure/configure-role-based-administration.md).  

##  <a name="bkmk_PlanScope"></a> Escopos de segurança  
 Use escopos de segurança para fornecer aos usuários administrativos acesso a objetos protegidos. Um escopo de segurança é um conjunto nomeado de objetos protegíveis que são atribuídos a usuários administradores como um grupo. Todos os objetos protegíveis devem ser atribuídos a um ou mais escopos de segurança. O Configuration Manager tem dois escopos de segurança internos:  

-   O escopo de segurança interno *Todos* concede acesso a todos os escopos. Você não pode atribuir objetos a este escopo de segurança.  

-   O escopo de segurança interno *Padrão* é usado para todos os objetos, por padrão. Ao instalar primeiro o Configuration Manager, todos os objetos são atribuídos a esse escopo de segurança.  

Se deseja restringir os objetos que os usuários administrativos podem ver e gerenciar, você deve criar e usar seus próprios escopos de segurança personalizados. Escopos de segurança não oferecem suporte a uma estrutura hierárquica e não podem ser aninhados. Escopos de segurança podem conter um ou mais tipos de objeto, que incluem o seguinte:  

-   Inscrições de alertas  

-   Aplicativos  

-   Imagens de inicialização  

-   Grupos de limites  

-   Itens de configuração  

-   Configurações personalizadas do cliente  

-   Pontos de distribuição e grupos de ponto de distribuição  

-   Pacotes de driver  

-   Condições globais  

-   Trabalhos de migração  

-   Imagens do sistema operacional  

-   Pacotes de instalação do sistema operacional  

-   Pacotes  

-   Consultas  

-   Sites  

-   Regras de medição de software  

-   Grupos de atualização de software  

-   Pacotes de atualizações de software  

-   Pacotes de sequência de tarefas  

-   Pacotes e itens de configuração de dispositivo do Windows CE  

Há também alguns objetos que não podem ser incluídos em escopos de segurança porque eles são usados somente pelas funções de segurança. O acesso administrativo a esses objetos não pode ser limitado a um subconjunto dos objetos disponíveis. Por exemplo, você pode ter um usuário administrativo que cria grupos de limites que são usados para um site específico. Como esse objeto de limite não suporta escopos de segurança, não é possível atribuir a esse usuário um escopo de segurança que forneça acesso somente aos limites que podem ser associados a esse site. Como o objeto de limite não pode estar associado a um escopo de segurança, quando você atribui uma função de segurança que inclui acesso a objetos de limite a um usuário, este pode acessar cada limite na hierarquia.  

Objetos que não são limitados por escopos de segurança incluem o seguinte:  

-   Florestas do Active Directory  

-   Usuários administrativos  

-   Alertas  

-   Políticas de antimalware  

-   Limites  

-   Associações de computador  

-   Configurações de cliente padrão  

-   Modelos de implantação  

-   Drivers de dispositivo  

-   Conector do Exchange Server  

-   Mapeamentos site a site da migração  

-   Perfis de registro do dispositivo móvel  

-   Funções de segurança  

-   Escopos de segurança  

-   Endereços de sites  

-   Funções do sistema de site  

-   Títulos de software  

-   Atualizações de software  

-   Mensagens de status  

-   Afinidades de dispositivo de usuário  

Crie escopos de segurança quando precisar limitar o acesso ao separar instâncias de objetos. Por exemplo:  

-   Você possui um grupo de usuários administrativos que devem ser capazes de ver aplicativos de produção e não aplicativos de teste. Crie um escopo de segurança para aplicativos de produção e outro para os aplicativos de teste.  

-   Diferentes usuários administrativos necessitam de acesso distinto para algumas instâncias de um tipo de objeto. Por exemplo, um grupo de usuários administrativos requer permissão de Leitura para grupos de atualização de software específicos e outro grupo de usuários administrativos requer permissões de Modificar e Excluir para outros grupos de atualização de software. Crie escopos de segurança diferentes para esses grupos de atualização de software.  

Para obter informações sobre como configurar escopos de segurança para administração baseada em funções, consulte [Configurar escopos de segurança para um objeto](../../core/servers/deploy/configure/configure-role-based-administration.md#BKMK_ConfigSecScope) no tópico [Configurar administração baseada em funções para o System Center Configuration Manager](../../core/servers/deploy/configure/configure-role-based-administration.md).  
