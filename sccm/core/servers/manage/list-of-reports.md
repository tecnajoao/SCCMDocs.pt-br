---
title: Lista de relatórios
titleSuffix: Configuration Manager
description: Veja uma lista de relatórios que são fornecidos com o Configuration Manager. Os relatórios aparecem em várias categorias.
ms.date: 11/27/2018
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: b7332ed3-8003-454b-bb12-1fdf8721425c
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35aff235d537efd738f29a0794f1fdb51a1fbb74
ms.sourcegitcommit: 0bf253085adeca0d9ea62d76497eb5ebf5ce89da
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57012506"
---
# <a name="list-of-reports-in-configuration-manager"></a>Lista de relatórios no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

O Configuration Manager fornece muitos relatórios internos que abrangem muitas das tarefas de relatório que você pode desejar realizar. Você também pode usar as instruções SQL nestes relatórios para ajudá-lo a escrever seus próprios relatórios.   

Os relatórios a seguir estão incluídos no Configuration Manager. Os relatórios aparecem em várias categorias.  



## <a name="administrative-security"></a>Segurança administrativa  

Os seis relatórios a seguir são listados na categoria **Segurança administrativa**.  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Log de atividade de administração**|Exibe um registro das alterações administrativas feitas para usuários administrativos, funções de segurança, escopos de segurança e coleções.|  
|**Atribuições de segurança de usuários administrativos**|Exibe os usuários administrativos, suas funções de segurança associadas e os escopos de segurança associados a cada função de segurança de cada usuário.|  
|**Objetos protegidos por um único escopo de segurança**|Exibe os objetos que um administrador atribuiu apenas ao escopo de segurança especificado. Esse relatório não exibe os objetos que um administrador associa a mais de um escopo de segurança.|  
|**Segurança para um objeto específico ou vários objetos do Configuration Manager**|Exibe os objetos protegíveis, os escopos de segurança associados aos objetos e quais usuários administrativos têm direitos aos objetos.|  
|**Resumo das funções de segurança**|Exibe as funções de segurança e os administradores do Configuration Manager associados a cada função.|  
|**Resumo dos escopos de segurança**|Exibe os escopos de segurança, os usuários administrativos do Configuration Manager e os grupos de segurança associados a cada escopo.|  



## <a name="alerts"></a>Alertas  

Os dois relatórios a seguir são listados na categoria **Alertas**.  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Scorecard de alerta**|Exibe um resumo de todos os alertas adiados que foram gerados entre as datas de início e de término especificadas.|  
|**Alertas Gerados com Mais Frequência**|Exibe um resumo dos alertas que foram gerados com mais frequência a partir da data de hoje até a data especificada para a área de recurso especificada.|  



## <a name="asset-intelligence"></a>Asset Intelligence  

Os 67 relatórios a seguir estão listados na categoria **Asset Intelligence**.  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Hardware 01A – Resumo dos computadores em uma coleção específica**|Exibe uma exibição de resumo do Asset Intelligence de computadores em uma coleção especificada.|  
|**Hardware 03A – Usuários primários de computador**|Exibe os usuários e a contagem de computadores em que eles são o usuário primário.|  
|**Hardware 03B – Computadores para um usuário de console primário específico**|Exibe todos os computadores dos quais um usuário especificado é o usuário primário do console.|  
|**Hardware 04A – Computadores com vários usuários (compartilhados)**|Exibe os computadores que não têm um usuário primário, pois nenhum usuário tem um tempo de logon conectado maior que 66%.|  
|**Hardware 05A – Usuários do console em um computador específico**|Exibe todos os usuários do console em um computador especificado.|  
|**Hardware 06A – Computadores para os quais não foi possível determinar os usuários do console**|Ajuda os usuários administrativos a identificar os computadores que precisam ter o registro em log de segurança ativado.|  
|**Hardware 07A – Dispositivos USB por fabricante**|Exibe os dispositivos USB, agrupados por fabricante.|  
|**Hardware 07B – Dispositivos USB por fabricante e descrição**|Exibe os dispositivos USB, agrupados por fabricante e descrição.|  
|**Hardware 07C – Computadores com um dispositivo USB específico**|Exibe todos os computadores com um dispositivo USB especificado.|  
|**Hardware 07D – Dispositivos USB em um computador específico**|Exibe todos os dispositivos USB em um computador especificado.|  
|**Hardware 08A – Hardware que não está pronto para uma atualização de software**|Exibe o hardware que não atende aos requisitos mínimos de hardware.|  
|**Hardware 09A – Pesquisar computadores**|Exibe um resumo dos computadores que correspondem a filtros de palavra-chave. Esses filtros são nome do computador, site do Configuration Manager, domínio, principal usuário do console, sistema operacional, fabricante ou modelo.|  
|**Hardware 10A – Computadores em uma coleção especificada que foi alterada durante um período especificado**|Exibe uma lista de computadores em uma coleção especificada em que uma classe de hardware foi alterada durante um período de tempo especificado.|  
|**Hardware 10B – Alterações em um computador especificado em um determinado período**|Exibe as classes que foram alteradas em um computador especificado em um período de tempo especificado.|  
|**Licença 01A – Razão de Licença por Volume da Microsoft para declarações de licença da Microsoft**|Exibe um inventário de todos os títulos de software da Microsoft disponíveis no programa de Licenciamento por Volume da Microsoft.|  
|**Licença 01B – Item de razão de Licença por Volume da Microsoft por canal de vendas**|Identifica e exibe o canal de vendas para o software de Licença por Volume da Microsoft inventariado.|  
|**Licença 01C – Computadores com um item de razão específico de Licença por Volume da Microsoft e canal de vendas**|Identifica e exibe os computadores que têm um item especificado de razão de Licença por Volume da Microsoft.|  
|**License 01D – Produtos de razão de Licença por Volume da Microsoft em um computador específico**|Identifica e exibe todos os itens de razão de Licença por Volume da Microsoft em um computador especificado.|  
|**Licença 02A – Contagem de licenças perto do vencimento por intervalos de tempo**|Exibe uma contagem de licenças perto do vencimento por um intervalo de tempo especificado. Os produtos exibidos têm suas licenças gerenciadas pelo serviço de licenciamento de software.|  
|**Licença 02B – Computadores com licenças perto do vencimento**|Exibe os computadores especificados com licenças perto do vencimento|  
|**Licença 02C – Informações de licença em um computador específico**|Exibe os produtos em um computador especificado que têm suas licenças gerenciadas pelo Serviço de Licenciamento de Software.|  
|**Licença 03A – Contagem de licenças por status de licença**|Exibe os produtos, por status de licença, que têm suas licenças gerenciadas pelo Serviço de Licenciamento de Software.|  
|**Licença 03B – Computadores com um status de licença específico**|Exibe os produtos com um status de licença especificado, cujas licenças são gerenciadas pelo Serviço de Licenciamento de Software.|  
|**Licença 04A – Contagem de produtos gerenciados pelo licenciamento de software**|Exibe uma contagem dos produtos que têm suas licenças gerenciadas pelo Serviço de Licenciamento de Software.|  
|**Licença 04B – Computadores com um Produto Específico Gerenciado por Serviço de Licenciamento de Software**|Exibe os computadores, gerenciados pelo Serviço de Licenciamento de Software, que inclui um produto especificado.|  
|**Licença 05A – Computadores que fornecem Serviço de Gerenciamento de Chaves**|Exibe os computadores que atuam como Servidores de Gerenciamento de Chaves.|  
|**Licença 06A – Contagens de processador de produtos licenciados por processador**|Exibe o número de processadores em computadores que usam os produtos da Microsoft que dão suporte ao licenciamento por processador.|  
|**Licença 06B – Computadores com um produto específico que dá suporte ao licenciamento por processador**|Exibe uma lista de computadores em que um produto da Microsoft especificado que dá suporte ao licenciamento por processador está instalado.|  
|**Licença 14A – Relatório de reconciliação de Licenciamento por Volume da Microsoft**|Exibe a reconciliação de licenças de software compradas por meio do Contrato de Licença por Volume da Microsoft e a contagem real de inventário.|  
|**Licença 14B – Lista de inventário de software da Microsoft não encontrado no MVLS**|Este relatório exibe os títulos de software da Microsoft em uso que não são encontrados no Contrato de Licença por Volume da Microsoft.|  
|**Licença 15A – Relatório de reconciliação de licença geral**|Exibe a reconciliação de licenças de software geral compradas e a contagem real de inventário.|  
|**Licença 15B – Relatório de reconciliação de licença geral por computador**|Exibe os computadores que instalaram o produto licenciado com uma versão especificada.|  
|**Software 01A – Resumo de software instalado em uma coleção específica**|Exibe um resumo do software instalado ordenado pelo número de instâncias encontradas no inventário.|  
|**Software 02A – Famílias de produtos para uma coleção específica**|Exibe as famílias de produtos e a contagem de software na família para uma coleção especificada.|  
|**Software 02B – Categorias de produtos para uma família de produtos específica**|Exibe as categorias de produtos em uma família de produto especificada e a contagem de software na categoria.|  
|**Software 02C – Software em uma família e categoria de produtos específicas**|Exibe todo o software que está na família e categoria de produtos especificadas.|  
|**Software 02D – Computadores com software específico instalado**|Exibe todos os computadores com o software especificado instalado.|  
|**Software 02E – Software instalado em um computador específico**|Exibe todo o software instalado em um computador especificado.|  
|**Software 03A – Software não categorizado**|Exibe o software que é categorizado como desconhecido ou sem nenhuma categorização.|  
|**Software 04A – Software configurado para execução automática nos computadores**|Exibe uma lista de software configurado para execução automática nos computadores.|  
|**Software 04B – Computadores com software específico configurado para execução automática**|Exibe todos os computadores com o software especificado configurado para execução automática.|  
|**Software 04C – Software configurado para execução automática em um computador específico**|Exibe o software instalado configurado para execução automática em um computador especificado.|  
|**Software 05A – Objetos Auxiliares de Navegador**|Exibe os objetos auxiliares de navegador instalados nos computadores em uma coleção especificada.|  
|**Software 05B – Computadores com um Objeto Auxiliar de Navegador específico**|Exibe todos os computadores com um objeto auxiliar de navegador especificado.|  
|**Software 05C – Objetos Auxiliares de Navegador em um computador específico**|Exibe todos os objetos auxiliares de navegador no computador especificado.|  
|**Software 06A – Pesquisar software instalado**|Esse relatório fornece um resumo do software instalado. Ele pesquisa com base nos seguintes critérios: nome do produto, distribuidor ou versão.|  
|**Software 06B – Software por nome do produto**|Exibe um resumo do software instalado com base em um nome de produto especificado.|  
|**Software 07A – Programas executáveis usados recentemente pela contagem de computadores**|Exibe os programas executáveis usados recentemente pelos usuários. Também inclui a contagem de computadores nos quais os usuários usaram o programa. A medição de software deve estar habilitada para este site para a exibição deste relatório.|  
|**Software 07B – Computadores que usaram recentemente um programa executável especificado**|Exibe os computadores nos quais os usuários usaram um programa executável especificado recentemente. Esse relatório exige a habilitação da configuração do cliente de medição de software.|  
|**Software 07C – Programas executáveis usados recentemente em um computador especificado**|Exibe os arquivos executáveis que os usuários usaram recentemente em um computador especificado. Esse relatório exige a habilitação da configuração do cliente de medição de software.|  
|**Software 08A – Programas executáveis usados recentemente pela contagem de usuários**|Exibe os programas executáveis usados recentemente pelos usuários. Também inclui uma contagem de usuários que usaram o programa mais recentemente. Esse relatório exige a habilitação da configuração do cliente de medição de software.|  
|**Software 08B – Usuários que usaram recentemente um programa executável especificado**|Exibe os usuários que mais usaram recentemente um programa executável especificado. Esse relatório exige a habilitação da configuração do cliente de medição de software.|  
|**Software 08C – Programas executáveis usados recentemente por um usuário especificado**|Exibe os programas executáveis que o usuário especificado usou recentemente. Esse relatório exige a habilitação da configuração do cliente de medição de software.|  
|**Software 09A – Software usado raramente**|Exibe os títulos de software que os usuários não usaram durante um período especificado.|  
|**Software 09B – Computadores com software usado raramente instalado**|Exibe os computadores com software instalado que os usuários não usaram por um período especificado. O período de tempo especificado se baseia no valor especificado no relatório “Software 09A - Software usado raramente”.|  
|**Software 10A – Títulos de software com vários rótulos personalizados específicos definidos**|Exibe os títulos de software com base na correspondência de todos os critérios de rótulo personalizado especificados. Até três rótulos personalizados podem ser selecionados para refinar a pesquisa de um título de software.|  
|**Software 10B – Computadores com um título de software com rótulo personalizado específico instalado**|Exibe todos os computadores nesta coleção que têm o título de software com rótulo personalizado especificado instalado.|  
|**Software 11A – Títulos de software com um rótulo personalizado específico definido**|Exibe os títulos de software com base na correspondência de pelo menos um dos critérios de rótulo personalizado especificados.|  
|**Software 12A – Títulos de software sem um rótulo personalizado**|Exibe todos os títulos de software que não têm um rótulo personalizado definido.|  
|**Software 14A – Pesquisar software habilitado para marca de identificação de software**|Exibe uma contagem de software instalado com uma marca de identificação de software habilitada.|  
|**Software 14B – Computadores com software habilitado para marca de identificação de software específico instalado**|Exibe todos os computadores que instalaram o software com uma marca de identificação de software especificado habilitada.|  
|**Software 14C – Software habilitado para marca de identificação de software instalado em um computador específico**|Exibe todo o software instalado com uma marca de identificação de software especificado habilitada em um computador especificado.|  
|**Ciclo de vida 01A: computadores com um produto de software específico**|Veja uma lista de computadores nos quais um produto especificado é detectado.|
|**Ciclo de vida 02A: lista de máquinas com produtos expirados na organização**|Veja os computadores que apresentam produtos expirados. Você pode filtrar este relatório pelo nome do produto.|
|**Ciclo de vida 03A: lista de produtos expirados encontrados na organização**|Veja detalhes de produtos em seu ambiente que apresentam datas de ciclo de vida expiradas.|
|**Ciclo de vida 04A: visão geral do ciclo de vida de produtos**|Veja uma lista de ciclos de vida de produtos. Filtre a lista por nome do produto e dias para expiração.|
|**Ciclo de vida 05A – painel de ciclo de vida do produto**|Começando na versão 1810, esse relatório inclui informações semelhantes às do painel no console.|



## <a name="client-push"></a>Push de cliente  

Os quatro relatórios a seguir são listados na categoria **Push de cliente**.  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Detalhes do status da instalação por push de cliente**|Exibe informações sobre o processo de instalação do cliente por push para todos os sites.|  
|**Detalhes do status de instalação por push do cliente para um site especificado**|Exibe informações sobre o processo de instalação do cliente por push para um site especificado.|  
|**Resumo do status da instalação por push do cliente**|Exibe uma exibição resumida do status de instalação do cliente por push para todos os sites.|  
|**Resumo do status da instalação por push do cliente para um site especificado**|Exibe uma exibição resumida do status de instalação do cliente por push para um site especificado.|  



## <a name="client-status"></a>Status do cliente  

Os sete relatórios a seguir são listados na categoria **Status do cliente**.  

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Detalhes da correção do cliente**|Exibe os detalhes das ações de correção do cliente para uma coleção especificada.|  
|**Resumo da correção do cliente**|Exibe um resumo das ações de correção do cliente para uma coleção especificada.|  
|**Histórico do status do cliente**|Exibe uma exibição histórica do status geral do cliente no site.|  
|**Resumo do status do cliente**|Exibe os resultados da verificação de cliente de clientes ativos para uma determinada coleção.|  
|**Hora do cliente para solicitar política**|Exibe o percentual de clientes que solicitaram a política, pelo menos, uma vez nos últimos 30 dias. Cada dia representa um percentual do total de clientes que solicitaram a política desde o primeiro dia do ciclo.|  
|**Detalhes de clientes com falha na verificação de cliente**|Exibe detalhes sobre os clientes com falha na verificação de cliente para uma coleção especificada.|  
|**Detalhes de clientes inativos**|Exibe uma lista detalhada de clientes inativos para uma determinada coleção.|  



## <a name="company-resource-access"></a>Acesso de recursos da empresa  

Os três relatórios a seguir são listados na categoria **Acesso aos recursos da empresa**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Histórico de emissão de certificado**|Exibe o histórico de certificados emitidos pelo ponto de registro de certificado para usuários e dispositivos do intervalo de datas especificado.|  
|**Lista de ativos por status de emissão de certificado**|Exibe os dispositivos ou usuários em um estado de emissão do certificado especificado após a avaliação de um perfil de certificado especificado.|  
|**Lista os ativos com certificados que estão se aproximando da expiração**|Exibe os dispositivos ou usuários com certificados que expiram na data especificada ou antes dela.|  



## <a name="compliance-and-settings-management"></a>Gerenciamento de conformidade e configurações  

Os 22 relatórios a seguir são listados na categoria **Gerenciamento de conformidade e configurações**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Histórico de conformidade de uma linha de base de configuração**|Exibe o histórico das alterações em conformidade de uma linha de base de configuração para o intervalo de datas especificado.|  
|**Histórico de conformidade de um item de configuração**|Exibe o histórico das alterações em conformidade de um item de configuração para o intervalo de datas especificado.|  
|**Conformidade de Acesso Condicional para Usuário**|Exibe a conformidade de acesso condicional detalhada para um usuário específico.|
|**Relatório de Conformidade de Acesso Condicional**|Um relatório de conformidade de acesso condicional para cada política de conformidade direcionada.|
|**Detalhes das regras compatíveis de itens de configuração em uma linha de base de configuração para um ativo**|Exibe informações sobre as regras avaliadas como em conformidade para um item de configuração especificado, para um dispositivo ou usuário especificado.|  
|**Detalhes das regras conflitantes dos itens de configuração em uma linha de base de configuração para um ativo**|Exibe informações sobre as regras em um item de configuração implantado que entram em conflito com outras regras. Inclua outras regras no mesmo item de configuração implantado ou outro.|  
|**Detalhes de erros de itens de configuração em uma linha de base de configuração para um ativo**|Exibe informações sobre os erros gerados por um item de configuração especificado para um dispositivo ou usuário especificado.|  
|**Detalhes de regras não compatíveis de itens de configuração em uma linha de base de configuração para um ativo**|Exibe informações sobre as regras que foram avaliadas como não compatíveis para um item de configuração especificado, para um dispositivo ou usuário especificado.|  
|**Detalhes das regras corrigidas de itens de configuração em uma linha de base de configuração para um ativo**|Exibe informações sobre as regras que foram corrigidas por um item de configuração especificado para um dispositivo ou usuário especificado.|  
|**Lista de ativos por estado de conformidade para uma linha de base de configuração**|Exibe os dispositivos ou usuários em um estado de conformidade especificado após a avaliação de uma linha de base de configuração especificada.|  
|**Lista de ativos por estado de conformidade para um item de configuração em uma linha de base de configuração**|Exibe os dispositivos ou usuários em um estado de conformidade especificado após a avaliação de um item de configuração especificado.|  
|**Lista de Aplicativos e Dispositivos não compatíveis com um usuário específico**|Exibe informações sobre usuários e dispositivos que têm aplicativos instalados que não estão em conformidade com uma política especificada.|  
|**Lista de regras conflitantes com uma regra especificada para um ativo**|Exibe uma lista de regras que entram em conflito com uma regra especificada para um item de configuração implantado.|  
|**Lista de ativos desconhecidos para uma linha de base de configuração**|Exibe uma lista de dispositivos ou usuários que ainda não relataram dados de conformidade para uma linha de base de configuração especificada.|  
|**Lista de ativos desconhecidos para um item de configuração**|Exibe uma lista de dispositivos ou usuários que ainda não relataram dados de conformidade para um item de configuração especificado.|  
|**Resumo de regras e erros de itens de configuração em uma linha de base de configuração para um ativo**|Exibe um resumo do estado de conformidade das regras e os erros de configuração para um item de configuração especificado. O item de configuração deve ser implantado em um dispositivo ou usuário.|  
|**Conformidade de resumo por linha de base de configuração**|Exibe um resumo da conformidade geral das linhas de base de configuração implantadas na hierarquia.|  
|**Conformidade de resumo por itens de configuração para uma linha de base de configuração**|Exibe um resumo da conformidade de itens de configuração em uma linha de base de configuração especificada.|  
|**Resumo da conformidade por políticas de configuração**|Exibe um resumo da conformidade das políticas de configuração.|  
|**Conformidade de resumo de uma linha de base de configuração para uma coleção**|Exibe um resumo da conformidade geral de uma linha de base de configuração especificada. O item de configuração deve ser implantado na coleção especificada.|  
|**Resumo de Usuários com Aplicativos Não Compatíveis**|Exibe informações sobre os usuários que têm aplicativos instalados que não estão em conformidade com uma política especificada.|  
|**Aceitação dos Termos e Condições**|Exibe itens de Termos e Condições e a versão aceita por usuário.|  



## <a name="data-warehouse"></a>Data warehouse  

Os sete relatórios a seguir estão listados na categoria **Data Warehouse**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Implantação do aplicativo**|Histórico: Exibe detalhes de implantação de aplicativo para um aplicativo e computador específicos.|
|**Endpoint Protection e Conformidade de Atualizações de Software**|Histórico: Exibe computadores com atualizações de software ausentes.|
|**Inventário geral de hardware**|Histórico: Exibe todo o inventário de hardware para um computador específico.|
|**Inventário geral de software**|Histórico: Exibe todo o inventário de software para um computador específico.|
|**Visão Geral de Integridade de Infraestrutura**|Histórico: Exibe uma visão geral da integridade da infraestrutura do seu Configuration Manager.|
|**Lista de Malwares Detectados**|Histórico: Exibe os malwares que foram detectados na sua organização.|
|**Resumo de distribuição de software**|Histórico: Um resumo da distribuição de software para um anúncio e computador específicos.|


## <a name="device-management"></a>Gerenciamento de dispositivo  

Os 37 relatórios a seguir são listados na categoria **Gerenciamento de dispositivos**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os dispositivos móveis de propriedade corporativa**|Exibe todos os dispositivos móveis de propriedade corporativa.|
|**Todos os clientes de dispositivo móvel**|Exibe informações sobre todos os clientes de dispositivos móveis. Os dispositivos gerenciados pelo conector do Exchange Server não são incluídos.|  
|**Problemas de certificado em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE e que não estão íntegros**|Exibe informações detalhadas sobre problemas de certificado em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Falha de implantação de cliente para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE**|Exibe informações detalhadas sobre falha de implantação para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Detalhes do status de implantação de cliente para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE**|Exibe informações sobre o status de dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Êxito de implantação do cliente para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE**|Exibe informações detalhadas sobre o êxito de implantação para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Problemas de comunicação em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE e que não estão íntegros**|Este relatório contém informações detalhadas sobre problemas de comunicação em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Status de conformidade da política de caixa de correio padrão do ActiveSync para os dispositivos móveis gerenciados pelo conector do Exchange Server**|Exibe um resumo do status da conformidade com a política de caixa de correio do Exchange ActiveSync padrão para os dispositivos móveis gerenciados pelo conector do Exchange Server.|  
|**Contagem de dispositivos móveis por configurações de exibição**|Este relatório exibe o número de dispositivos móveis por configurações de exibição.|  
|**Contagem de dispositivos móveis por sistema operacional**|Exibe o número de dispositivos móveis por sistema operacional.|  
|**Contagem de dispositivos móveis por memória de programa**|Exibe o número de dispositivos móveis por memória de programa.|  
|**Contagem de dispositivos móveis por configurações de memória de armazenamento**|Contagem de dispositivos móveis por configurações de memória de armazenamento|  
|**Informações de integridade para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE**|Exibe informações de integridade detalhadas para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Resumo de integridade para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE**|Exibe informações de integridade resumidas para dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Dispositivos móveis inativos gerenciados pelo conector do Exchange Server**|Exibe os dispositivos móveis gerenciados pelo conector do Exchange Server que não se conectaram a um Exchange Server em um número de dias especificado.|  
|**Lista de dispositivos por Estado de Acesso Condicional**|Exibe informações sobre a conformidade atual e o estado de acesso condicional de dispositivos. Você pode usar este relatório com políticas de acesso condicional. Esse relatório está disponível a partir versão 1602 do Configuration Manager.|  
|**Lista de dispositivos por estado de Atestado de Integridade**|Exibe uma lista de dispositivos com atributos relatados pelo Serviço de Atestado de Integridade|
|**Lista de Dispositivos registrados por usuário no Microsoft Intune**|Exibe todos os dispositivos que um usuário registrou no Microsoft Intune.|  
|**Lista de dispositivos em uma categoria de dispositivo específica**|Exibe informações de todos os dispositivos em uma categoria de dispositivo específica.|
|**Problemas de cliente local em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE e que não estão íntegros**|Este relatório contém informações detalhadas sobre problemas de cliente local em dispositivos móveis gerenciados pelo cliente do Configuration Manager para Windows CE.|  
|**Informações de cliente de dispositivo móvel**|Exibe informações sobre os dispositivos móveis que têm o cliente do Configuration Manager instalado. Você pode usar este relatório para verificar quais dispositivos móveis podem se comunicar com êxito com um ponto de gerenciamento.|  
|**Detalhes de conformidade de dispositivo móvel para o conector do Exchange Server**|Exibe os detalhes de conformidade do dispositivo móvel para uma política de caixa de correio do Exchange ActiveSync padrão configurada por meio do conector do Exchange Server.|  
|**Dispositivos móveis por sistema operacional**|Exibe os dispositivos móveis por sistema operacional.|  
|**Dispositivos móveis desbloqueados ou com raiz**|Exibe os dispositivos móveis com jailbroken ou com raiz.|  
|**Dispositivos móveis que estão sem gerenciamento porque estão inscritos mas não foram atribuídos a um site**|Exibe os dispositivos móveis que concluíram o registro no Configuration Manager e que têm um certificado, mas que não concluíram a atribuição de site.|  
|**Dispositivos móveis com uma quantidade específica de memória de programa livre**|Exibe todos os dispositivos móveis com sua quantidade especificada de memória de programa livre.|  
|**Dispositivos móveis com uma quantidade específica de memória de armazenamento removível livre**|Exibe todos os dispositivos móveis com a quantidade especificada de memória removível livre.|  
|**Dispositivos móveis com problemas de renovação de certificado**|Exibe os dispositivos móveis registrados que não renovaram seu certificado. Se você não renovar o certificado antes do período de expiração, os dispositivos móveis ficarão não gerenciados.|  
|**Dispositivos móveis com pouca memória de programa livre (menos do que o especificado em KB livre)**|Exibe os dispositivos móveis para os quais a memória de programa é menor do que um tamanho especificado em KB.|  
|**Dispositivos móveis com pouca memória de armazenamento removível livre (menos do que o especificado em KB livre)**|Exibe os dispositivos móveis para os quais a memória de armazenamento removível é menor do que um tamanho especificado em KB.|  
|**Número de dispositivos registrados por usuário no Microsoft Intune**|Exibe os usuários habilitados para a assinatura do Microsoft Intune. Também mostra o número total de dispositivos registrados para cada usuário.|  
|**Solicitação de desativação e apagamento pendente para dispositivos móveis**|Exibe as solicitações de apagamento pendentes para dispositivos móveis.|  
|**Dispositivos móveis inscritos recentemente e atribuídos**|Exibe os dispositivos móveis que concluíram com êxito a inscrição no Configuration Manager e a atribuição de site recentemente.|  
|**Dispositivos móveis recentemente apagados**|Exibe a lista de dispositivos móveis que foram apagados recentemente com êxito.|  
|**Resumo das configurações para dispositivos móveis gerenciados pelo conector do Exchange Server**|Exibe o número de dispositivos móveis que aplicam as configurações de cada política de caixa de correio do Exchange ActiveSync Padrão gerenciada pelo conector do Exchange Server.|  
|**Status Detalhado das Chaves de Sideload do Windows RT**|Exibe informações de status detalhadas de uma chave de sideload do Windows RT especificada.|  
|**Resumo das Chaves de Sideload do Windows RT**|Exibe o status das chaves de sideload do Windows RT.|  



## <a name="driver-management"></a>Gerenciamento de driver  

Os 13 relatórios a seguir são listados na categoria **Gerenciamento de drivers**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os drivers**|Exibe uma lista de todos os drivers.|  
|**Todos os drivers de uma plataforma específica**|Exibe todos os drivers de uma plataforma específica.|  
|**Todos os drivers em uma imagem de inicialização específica**|Exibe todos os drivers em uma imagem de inicialização especificada.|  
|**Todos os drivers em uma categoria específica**|Exibe todos os drivers em uma categoria especificada.|  
|**Todos os drivers em um pacote específico**|Exibe todos os drivers em um pacote especificado.|  
|**Categorias de um driver específico**|Exibe as categorias de um driver especificado.|  
|**Computadores que não instalaram drivers para uma coleção específica**|Exibe os computadores que não instalaram drivers para uma coleção especificada.|  
|**Relatório de correspondência de catálogo de driver para uma coleção específica**|Exibe o catálogo de drivers que correspondem ao relatório para uma coleção especificada.|  
|**Relatório de correspondência de catálogo de driver para um computador específico**|Exibe o catálogo de drivers que correspondem ao relatório para um computador especificado.|  
|**Relatório de correspondência de catálogo de driver para um dispositivo específico em um computador específico**|Exibe o catálogo de drivers que correspondem ao relatório para um dispositivo especificado em um computador especificado.|  
|**Relatório de correspondência de catálogo de driver para computadores em uma coleção específica com um dispositivo específico**|Exibe o catálogo de drivers que correspondem ao relatório para computadores em uma coleção especificada com um dispositivo especificado.|  
|**Drivers que não foram instalados em um computador específico**|Exibe os drivers que não foram instalados em um computador especificado.|  
|**Plataformas com suporte para um Driver específico**|Exibe as plataformas com suporte de um driver especificado.|  



## <a name="endpoint-protection"></a>Endpoint Protection  

Os seis relatórios a seguir são listados na categoria **Endpoint Protection**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Relatório de atividade antimalware**|Exibe uma visão geral da atividade de antimalware.|  
|**Status e histórico geral antimalware**|Exibe o histórico e status geral de antimalware.|  
|**Detalhes de malware do computador**|Exibe detalhes sobre um computador especificado e a lista de malware encontrado nele.|  
|**Computadores infectados**|Exibe uma lista de computadores com uma ameaça especificada detectada.|  
|**Usuários principais por ameaças**|Exibe a lista de usuários com o maior número de ameaças detectadas.|  
|**Lista de ameaças do usuário**|Exibe a lista de ameaças encontradas para uma conta de usuário especificada.|  



## <a name="hardware---cd-rom"></a>Hardware – CD-ROM  

Os quatro relatórios a seguir são listados na categoria **Hardware – CD-ROM**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Informações de CD-ROM para um computador específico**|Exibe informações sobre as unidades de CD-ROM em um computador especificado.|  
|**Computadores para um fabricante de CD-ROM específico**|Exibe uma lista de computadores que contêm uma unidade de CD-ROM produzida por um fabricante específico.|  
|**Contar unidades de CD-ROM por fabricante**|Exibe o número de unidades de CD-ROM inventariadas por fabricante.|  
|**Histórico – Histórico de CD-ROM para um computador específico**|Exibe o histórico de inventário das unidades de CD-ROM em um computador especificado.|  



## <a name="hardware---disk"></a>Hardware – Disco  

Os oito relatórios a seguir são listados na categoria **Hardware – Disco**. 

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores com um tamanho de disco rígido específico**|Exibe uma lista de computadores com discos rígidos de um tamanho especificado.|  
|**Computadores com pouco espaço livre em disco (menos do que o % livre especificado)**|Exibe uma lista de computadores em uma coleção especificada que têm menos do que o espaço livre em disco especificado.|  
|**Computadores com pouco espaço livre em disco (menos do que o especificado em MB livres)**|Exibe uma lista de computadores e discos que não têm espaço suficiente. A quantidade de espaço livre para a verificação é especificada em MB.|  
|**Contar configurações de disco físico**|Exibe o número de discos rígidos inventariados por capacidade de disco.|  
|**Informações de disco para um computador específico – Discos lógicos**|Exibe informações de resumo sobre os discos lógicos em um computador especificado.|  
|**Informações de disco para um computador específico – Partições**|Exibe informações de resumo sobre as partições de disco em um computador especificado.|  
|**Informações de disco para um computador específico – Discos físicos**|Exibe informações de resumo sobre os discos físicos em um computador especificado.|  
|**Histórico – Histórico do espaço em disco lógico para um computador específico**|Exibe o histórico de inventário de unidades de disco lógico em um computador especificado.|  



## <a name="hardware---general"></a>Hardware – Geral  

Os cinco relatórios a seguir são listados na categoria **Hardware – Geral**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Informações de um computador específico**|Exibe informações de resumo de um computador especificado.|  
|**Computadores em um grupo de trabalho ou domínio específico**|Exibe uma lista de computadores em um grupo de trabalho ou domínio especificado.|  
|**Classes de inventário atribuídas a uma coleção específica**|Exibe as classes de inventário atribuídas a uma coleção especificada.|  
|**Classes de inventário habilitadas em um computador específico**|Exibe as classes de inventário habilitadas em um computador especificado.|  
|**Informações do dispositivo do Windows AutoPilot**|Exibe as informações do dispositivo de cliente necessárias para o registro do Windows AutoPilot.|



## <a name="hardware---memory"></a>Hardware – Memória  

Os cinco relatórios a seguir são listados na categoria **Hardware – Memória**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores em que a memória física foi alterada**|Exibe uma lista de computadores em que a quantidade de RAM foi alterada desde o último ciclo de inventário.|  
|**Computadores com uma quantidade específica de memória**|Exibe uma lista de computadores que têm uma quantidade especificada de RAM (Memória Física Total arredondada para a MB mais próxima).|  
|**Computadores com pouca memória (menos ou o mesmo que o especificado em MB)**|Exibe uma lista de computadores com memória insuficiente. A quantidade de memória para a verificação é especificada em MB.|  
|**Contar configurações de memória**|Exibe o número de computadores inventariados por quantidade de RAM.|  
|**Informações de memória para um computador específico**|Exibe informações de resumo sobre a memória em um computador especificado.|  



## <a name="hardware---modem"></a>Hardware – Modem  

Os três relatórios a seguir são listados na categoria **Hardware – Modem**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores para um fabricante de modem específico**|Exibe uma lista de computadores que contêm um modem produzido por um fabricante especificado.|  
|**Contar modems por fabricante**|Exibe o número de modems inventariados para cada fabricante de modem.|  
|**Informações de modem para um computador específico**|Exibe informações de resumo sobre o modem em um computador especificado.|  



## <a name="hardware---network-adapter"></a>Hardware – adaptador de rede  

Os três relatórios a seguir são listados na categoria **Hardware – Adaptador de rede**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores com um adaptador de rede específico**|Exibe uma lista de computadores que contêm um adaptador de rede especificado.|  
|**Contar adaptadores de rede por tipo**|Exibe o número de placas de adaptadores de rede inventariadas de cada tipo.|  
|**Informações de adaptador de rede para um computador específico**|Exibe informações sobre os adaptadores de rede instalados em um computador especificado.|  



## <a name="hardware---processor"></a>Hardware – Processador  

Os cinco relatórios a seguir são listados na categoria **Hardware – Processador**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores para uma velocidade de processador especificada**|Exibe uma lista de computadores que contêm um processador de uma velocidade especificada.|  
|**Computadores com processadores rápidos (velocidade de clock igual ou maior que a especificada)**|Exibe uma lista de computadores que têm processadores com uma velocidade mais rápida do que a velocidade especificada.|  
|**Computadores com processadores lentos (velocidade de clock igual ou menor que a especificada)**|Exibe uma lista de computadores com processadores que são executados em uma velocidade de clock especificada ou em uma velocidade de clock mais lenta do que a especificada.|  
|**Contar velocidades de processador**|Exibe o número de computadores inventariados por velocidade do processador.|  
|**Informações de processador para um computador específico**|Exibe informações sobre os processadores instalados em um computador especificado.|  



## <a name="hardware---scsi"></a>Hardware – SCSI  

Os cinco relatórios a seguir são listados na categoria **Hardware – SCSI**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores com um tipo de placa SCSI específico**|Exibe uma lista de computadores que contêm uma placa SCSI especificada instalada.|  
|**Contar tipos de placa SCSI**|Exibe o número de placas SCSI inventariadas por tipo de placa.|  
|**Informações de placa SCSI para um computador específico**|Exibe informações sobre as placas SCSI instaladas em um computador especificado.|  



## <a name="hardware---security"></a>Hardware – Segurança

O relatório a seguir está listado na categoria **Hardware – Segurança**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Detalhes de estados de firmware em dispositivos**|Exibe os detalhes dos estados da UEFI, do SecureBoot e do TPM. **Observação**: Este relatório não está na versão 1810.<!--SCCMDocs issue #1189-->|  



## <a name="hardware---sound-card"></a>Hardware – placa de som  

Os três relatórios a seguir são listados na categoria **Hardware – SCSI**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores com uma placa de som específica**|Exibe uma lista de computadores que contêm uma placa de som especificada.|  
|**Contar placas de som**|Exibe o número de computadores inventariados por cada tipo de placa de som.|  
|**Informações de placa de som para um computador específico**|Exibe informações de resumo sobre as placas de som em um computador especificado.|  



## <a name="hardware---video-card"></a>Hardware – placa de vídeo  

Os três relatórios a seguir são listados na categoria **Hardware – Placa de vídeo**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores com uma placa de vídeo específica**|Exibe uma lista de computadores que contêm uma placa de vídeo especificada.|  
|**Contar placas de vídeo por tipo**|Exibe uma lista de todas as placas de vídeo instaladas nos computadores. Também mostra o número de cada tipo de placa de vídeo.|  
|**Informações de placa de vídeo para um computador específico**|Exibe informações de resumo sobre as placas de vídeo instaladas em um computador especificado.|  



## <a name="migration"></a>Migração  

Os cinco relatórios a seguir são listados na categoria **Migração**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Clientes na lista de exclusões**|Exibe os clientes excluídos da migração.|  
|**Dependência em uma coleção do Configuration Manager**|Exibe os objetos que dependem de uma coleção da hierarquia de origem.|  
|**Propriedades do trabalho de migração**|Este relatório mostra o conteúdo do trabalho de migração especificado.|  
|**Trabalhos de migração**|Este relatório mostra a lista de trabalhos de migração.|  
|**Objetos que não foram migrados**|Exibe uma lista de objetos que falharam em migrar durante a última tentativa.|  



## <a name="network"></a>Rede  

Os seis relatórios a seguir são listados na categoria **Rede**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Contar endereços IP por sub-rede**|Exibe o número de endereços IP inventariados para cada sub-rede IP.|  
|**IP – Todas as sub-redes por máscara de sub-rede**|Exibe uma lista de sub-redes IP e máscaras de sub-rede.|  
|**IP – Computadores em uma sub-rede específica**|Exibe uma lista de computadores e informações de IP para uma sub-rede IP especificada.|  
|**IP – Informações para um computador específico**|Exibe informações de resumo sobre IP em um computador especificado.|  
|**IP – Informações para um endereço IP específico**|Exibe informações de resumo sobre um endereço IP especificado.|  
|**MAC – Computadores para um endereço MAC específico**|Exibe o nome do computador e o endereço IP dos computadores que têm o endereço MAC especificado.|  



## <a name="operating-system"></a>Sistema operacional  

Os dez relatórios a seguir são listados na categoria **Sistema operacional**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Histórico de versão do sistema operacional do computador**|Exibe o histórico de inventário do sistema operacional em um computador especificado.|  
|**Computadores com um sistema operacional específico**|Exibe os computadores com um sistema operacional especificado.|  
|**Computadores com um sistema operacional e um service pack específicos**|Exibe os computadores com um sistema operacional e service pack especificados.|  
|**Contar versões de sistema operacional**|Exibe o número de computadores inventariados por sistema operacional.|  
|**Contar sistemas operacionais e service packs**|Exibe o número de computadores inventariados por sistema operacional e combinações de service pack.|  
|**Serviços – Computadores executando um serviço específico**|Exibe uma lista de computadores que executam um serviço especificado.|  
|**Serviços – Computadores executando o Servidor de Acesso Remoto**|Exibe uma lista de computadores que executam o Servidor de Acesso Remoto.|  
|**Serviços – Informações de serviços para um computador específico**|Exibe informações de resumo sobre os serviços em um computador especificado.|  
|**Detalhes do Serviço do Windows 10 para uma coleção específica**|Exibe informações gerais sobre o serviço do Windows 10 para uma coleção específica.|
|**Computadores com Windows Server**|Exibe uma lista de computadores que executam sistemas operacionais Windows Server.|  


## <a name="power-management"></a>Gerenciamento de Energia  

Os 18 relatórios a seguir são listados na categoria **Gerenciamento de energia**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Gerenciamento de energia – Atividade do computador**|Exibe um grafo mostrando a atividade do monitor, computador e usuário para uma coleção específica em um período especificado.|  
|**Gerenciamento de energia – Atividade do computador por computador**|Exibe um grafo mostrando a atividade do monitor, computador e usuário para um computador especificado em uma data especificada.|  
|**Gerenciamento de energia – Detalhes da atividade do computador**|Exibe uma lista dos recursos de suspensão e ativação de computadores na coleção especificada em uma data e hora especificadas.|  
|**Gerenciamento de energia – Detalhes do computador**|Exibe informações detalhadas sobre as funcionalidades de energia, configurações de energia e planos de energia aplicados a um computador especificado.|  
|**Gerenciamento de energia – O computador não está relatando detalhes**|Exibe uma lista de computadores que não relataram nenhuma atividade de energia em uma data e hora especificadas.|  
|**Gerenciamento de energia – Computadores excluídos**|Exibe uma lista de computadores excluídos do plano de energia.|  
|**Gerenciamento de energia – Computadores com vários planos de energia**|Exibe uma lista de computadores que têm várias configurações de energia conflitantes aplicadas.|  
|**Gerenciamento de energia – Consumo de energia**|Exibe o consumo de energia mensal total (em kWh) para uma coleção especificada em um período de tempo especificado.|  
|**Gerenciamento de energia – Consumo de energia por dia**|Exibe o consumo de energia total (em kWh) para uma coleção especificada nos últimos 31 dias.|  
|**Gerenciamento de energia – Custo de energia**|Exibe o custo de consumo de energia mensal total para uma coleção especificada em um período de tempo especificado.|  
|**Gerenciamento de energia – Custo de energia por dia**|Exibe o custo de consumo de energia total para uma coleção especificada nos últimos 31 dias.|  
|**Gerenciamento de energia – Impacto ambiental**|Exibe um gráfico mostrando as emissões de dióxido de carbono (CO2) geradas por uma coleção especificada em um período de tempo especificado.|  
|**Gerenciamento de energia – Impacto ambiental por dia**|Exibe um gráfico mostrando as emissões de CO2 geradas por uma coleção especificada nos últimos 31 dias.|  
|**Gerenciamento de energia – Detalhes do computador com insônia**|Exibe informações detalhadas sobre computadores que não foram suspensos ou que não hibernaram em um período de tempo especificado.|  
|**Gerenciamento de energia – Relatório de insônia**|Exibe uma lista das causas comuns que impediram que os computadores entrassem em suspensão ou hibernação. Também mostra o número de computadores afetados por cada causa em um período especificado.|  
|**Gerenciamento de energia – Recursos de energia**|Exibe os recursos de gerenciamento de energia de computadores na coleção especificada.|  
|**Gerenciamento de energia – Configurações de energia**|Exibe uma lista agregada de configurações de energia usadas por computadores em uma coleção especificada.|  
|**Gerenciamento de energia – Detalhes de configurações de energia**|Usado para exibir mais informações sobre os computadores que foram especificados no relatório **Gerenciamento de energia – Configurações de energia**.|  



## <a name="replication-traffic"></a>Tráfego de replicação  

Os dez relatórios a seguir são listados na categoria **Tráfego de replicação**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Tráfego de Replicação de Dados Globais por Link (gráfico de linhas)**|Exibe o tráfego total de replicação de dados globais em um link especificado para um número de dias especificado.|  
|**Tráfego de Replicação de Dados Globais por Link (gráfico de pizza)**|Exibe o tráfego total de replicação de dados globais em um link especificado para um número de dias especificado.|  
|**Tráfego de Replicação de Hierarquia por Link**|Exibe o tráfego de replicação total para cada link na hierarquia em um número de dias especificado.|  
|**Tráfego dos Dez Principais Grupos de Replicação de Hierarquia por Link (gráfico de pizza)**|Exibe o tráfego de replicação dos dez principais grupos de replicação em toda a hierarquia identificada pelo link.|  
|**Tráfego de Replicação do Link**|Exibe o tráfego de replicação total para todos os dados em um número de dias especificado.|  
|**Tráfego do grupo de replicação por link**|Exibe o tráfego de rede do grupo de replicação em um link de replicação de banco de dados especificado em um número de dias especificado.|  
|**Tráfego de Replicação de Dados de Site por Link (gráfico de linhas)**|Exibe o tráfego total de replicação de dados do site em um link especificado para um número de dias especificado.|  
|**Tráfego de Replicação de Dados de Site por Link (gráfico de pizza)**|Exibe o tráfego total de replicação de dados do site em um link especificado para um número de dias especificado.|  
|**Tráfego de Replicação de Hierarquia Total (gráfico de linhas)**|Exibe a replicação de dados globais e do site de agregação de hierarquia para cada direção de cada link para um número de dias especificado.|  
|**Tráfego de Replicação de Hierarquia Total (gráfico de pizza)**|Exibe a replicação de dados globais e do site de agregação de hierarquia para cada direção de cada link para um número de dias especificado.|  



## <a name="site---client-information"></a>Site – informações do cliente  

Os 19 relatórios a seguir são listados na categoria **Site – Informações do cliente**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Relatório de status detalhado de atribuição do cliente**|Exibe informações detalhadas sobre o status de atribuição do cliente.|  
|**Detalhes de falha na atribuição do cliente**|Exibe informações detalhadas sobre falhas de atribuição do cliente.|  
|**Detalhes do status de atribuição do cliente**|Exibe informações de visão geral sobre o status de atribuição do cliente.|  
|**Detalhes de êxito de atribuição do cliente**|Exibe informações detalhadas sobre clientes atribuídos com êxito.|  
|**Relatório de falha de implantação do cliente**|Exibe informações detalhadas para clientes com falha na implantação.|  
|**Detalhes do status de implantação cliente**|Exibe informações de resumo do status das instalações de cliente.|  
|**Relatório de êxito de implantação cliente**|Exibe informações detalhadas para clientes com êxito na implantação.|  
|**Clientes sem capacidade de comunicação HTTPS**|Exibe informações detalhadas sobre cada cliente que executa a HTTPS Communication Readiness Tool e relata sua falta de capacidade de se comunicar por HTTPS.|  
|**Computadores atribuídos, mas não instalados para um determinado site**|Exibe uma lista de computadores atribuídos a um site especificado, mas que não estão relatando para esse site.|  
|**Computadores com uma versão cliente do Configuration Manager específica**|Exibe uma lista de computadores que estão executando uma versão especificada do software cliente do Configuration Manager.|  
|**Contagem de clientes e protocolo usado para comunicação**|Exibe um resumo dos métodos de comunicação usado pelos clientes (HTTP ou HTTPS).|  
|**Contagem de clientes atribuídos e instalados para cada site**|Exibe o número de computadores atribuídos e instalados para cada site. Os clientes com uma localização de rede associada a vários sites serão contados somente como instalados se eles estiverem relatando a esse site.|  
|**Contagem de clientes capazes de comunicação HTTPS**|Exibe informações detalhadas sobre cada cliente que executa a HTTPS Communication Readiness Tool e relata sua capacidade ou falta de capacidade de se comunicar por HTTPS.|  
|**Contagem de clientes para cada site**|Exibe o número de clientes do Configuration Manager instalados por código do site.|  
|**Contagem de clientes do Configuration Manager por versões do cliente**|Exibe o número de computadores descobertos pela versão do cliente do Configuration Manager.|  
|**Detalhes do problema relatados para um ponto de status de fallback para uma coleção especificada**|Exibe informações detalhadas sobre os problemas relatados pelos clientes em uma coleção especificada. Esses clientes precisam ter um ponto de status de fallback atribuído.|  
|**Detalhes dos problemas relatados para o ponto de status de fallback para um site especificado**|Exibe informações detalhadas sobre os problemas relatados pelos clientes em um site especificado. Esses clientes precisam ter um ponto de status de fallback atribuído.|  
|**Resumo dos problemas relatados ao ponto de status de fallback**|Exibe informações sobre todos os problemas relatados pelos clientes. Esses clientes precisam ter um ponto de status de fallback atribuído.|  
|**Resumo dos problemas relatados para o ponto de status de fallback para uma coleção específica**|Exibe informações de resumo sobre os problemas relatados pelos clientes em uma coleção especificada. Esses clientes precisam ter um ponto de status de fallback atribuído.|  



## <a name="site---discovery-and-inventory-information"></a>Site – informações de descoberta e inventário  

Os dez relatórios a seguir são listados na categoria **Site – Informações de descoberta e inventário**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Clientes que não relataram recentemente (em um número de dias especificado)**|Exibe uma lista de clientes que não relataram dados de descoberta, inventário de hardware ou inventário de software em um número de dias especificado.|  
|**Computadores descobertos por um site específico**|Exibe uma lista de todos os computadores descobertos pelo site especificado. Também mostra a data da descoberta mais recente.|  
|**Computadores descobertos recentemente pelo método de descoberta**|Exibe uma lista dos computadores descobertos pelo site no número especificado de dias. Também lista os agentes que os descobriram. Se vários agentes descobriram um computador, ele poderá ser exibido mais de uma vez na lista.|  
|**Computadores não descobertos recentemente (em um número especificado de dias)**|Exibe uma lista dos computadores que o site não descobriu recentemente. Também mostra o número de dias desde que o site descobriu o computador.|  
|**Computadores não inventariados recentemente (em um número especificado de dias)**|Exibe uma lista dos computadores que o site não inventariado recentemente. Também mostra as últimas vezes que o cliente inventariou o computador.|  
|**Computadores que podem compartilhar o mesmo identificador exclusivo do Configuration Manager**|Exibe uma lista de computadores que tiveram seus nomes alterados. Uma alteração no nome é um possível sintoma de que um computador compartilha um Identificador Exclusivo do Configuration Manager com outro computador.|  
|**Computadores com endereços MAC duplicados**|Exibe os computadores que compartilham um endereço MAC.|  
|**Contar computadores em domínios de recursos ou grupos de trabalho**|Exibe o número de computadores em cada domínio de recurso ou grupo de trabalho.|  
|**Informações de descoberta para um computador específico**|Exibe uma lista de agentes e sites que descobriram um computador especificado.|  
|**Datas de inventário para um computador específico**|Exibe a data e hora da última execução do inventário em um computador especificado.|  



## <a name="site---general"></a>Site – Geral  

Os três relatórios a seguir são listados na categoria **Site – Geral**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores em um site específico**|Exibe uma lista de computadores cliente em um site especificado.|  
|**Status do site para a hierarquia**|Exibe a lista de sites na hierarquia com a versão do site e informações de status do site.|  
|**Status da atualização do Configuration Manager na hierarquia**|Exibe informações sobre as atualizações do site do Configuration Manager para a hierarquia.|  



## <a name="site---server-information"></a>Site – informações do servidor  

O relatório a seguir é listado na categoria **Site – Informações do servidor**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Funções do sistema de sites e servidores do sistema de sites para um site específico**|Exibe uma lista de servidor do sistema de sites e suas funções do sistema de sites para um site especificado.|  



## <a name="software---companies-and-products"></a>Software – empresas e produtos  

Os 15 relatórios a seguir são listados na categoria **Software – Empresas e produtos**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os produtos inventariados para uma empresa de software específica**|Exibe uma lista dos produtos e versões de software inventariados de uma empresa de software especificada.|  
|**Todas as empresas de software**|Exibe uma lista de todas as empresas que fabricam software inventariado.|  
|**Todos os aplicativos do Windows**|Exibe um resumo dos aplicativos do Windows instalados. Ele pesquisa usando os seguintes critérios: nome do aplicativo, arquitetura ou distribuidor.|  
|**Computadores com um produto específico**|Exibe uma lista dos computadores nos quais um produto especificado é inventariado e as versões desse produto.|  
|**Computadores com um nome e versão de produto específicos**|Exibe uma lista dos computadores nos quais uma versão especificada de um produto é inventariada.|  
|**Computadores com software específico registrado em Adicionar ou Remover Programas**|Exibe um resumo de todos os computadores com software especificado registrado em Adicionar ou Remover Programas ou Programas e Recursos.|  
|**Contar todos os produtos e versões inventariados**|Exibe uma lista de produtos e versões de software inventariados e o número de computadores em que cada um está instalado.|  
|**Contagem de produtos inventariados e versões de um produto específico**|Exibe uma lista das versões inventariadas de um produto especificado e o número de computadores em que cada um está instalado.|  
|**Contagem de todas as instâncias de software registradas com Adicionar ou Remover Programas**|Exibe um resumo de todas as instâncias de software instaladas e registradas com Adicionar ou Remover Programas ou Programas e Recursos em computadores na coleção especificada.|  
|**Contagem de instâncias de software específico registradas com Adicionar ou Remover Programas**|Exibe uma contagem de instâncias de pacotes de software especificados instalados e registrados com Adicionar ou Remover Programas ou Programas e Recursos.|  
|**Contagens de Navegador padrão**|Mostra a contagem de clientes com um navegador da Web específico como o padrão do Windows. <br>Use a seguinte referência para BrowserProgIDs comuns:<br> - AppXq0fevzme2pys62n3e0fbqa7peapykr8v: Microsoft Edge<br> - IE.HTTP: Microsoft Internet Explorer<br> - ChromeHTML: Google Chrome <br> - OperaStable: Software Opera<br> - FirefoxURL-308046B0AF4A39CB: Mozilla Firefox <br> – Desconhecido: o sistema operacional do cliente não dá suporte à consulta, a consulta não foi executada ou um usuário não fez logon|
|**Instalações dos aplicativos do Windows especificados**|Este relatório lista todos os computadores com um aplicativo do Windows especificado.|  
|**Produtos em um computador específico**|Exibe um resumo dos produtos de software inventariados e seus fabricantes em um computador especificado.|  
|**Software registrado em Adicionar ou Remover Programas em um computador específico**|Exibe um resumo do software instalado em um computador especificado que é registrado em Adicionar ou Remover Programas ou Programas e Recursos.|  
|**Aplicativos Windows instalados para o usuário especificado**|Exibe todos os aplicativos do Windows instalados para o usuário especificado|  



## <a name="software---files"></a>Software – Arquivos  

Os cinco relatórios a seguir são listados na categoria **Software – Arquivos**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os arquivos inventariados para um produto específico**|Exiba um resumo dos arquivos inventariados associados a um produto de software especificado.|  
|**Todos os arquivos inventariados em um computador específico**|Exiba um resumo de todos os arquivos inventariados em um computador especificado.|  
|**Comparar inventário de software em dois computadores**|Exibe as diferenças entre os inventários de software relatados para dois computadores especificados.|  
|**Computadores com um arquivo específico**|Exibe uma lista de computadores que coletaram inventário de software para um nome de arquivo especificado. Se um computador contiver várias cópias do arquivo, ele poderá ser exibido mais de uma vez na lista.|  
|**Contagem de computadores com um nome de arquivo específico**|Exibe o número de computadores que coletaram o inventário de software para um arquivo especificado.|  



## <a name="software-distribution---application-monitoring"></a>Distribuição de software – monitoramento de aplicativos  

Os dez relatórios a seguir são listados na categoria **Distribuição de software – Monitoramento de aplicativos**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as implantações de aplicativo (avançadas)**|Exibe informações de resumo detalhadas de todas as implantações de aplicativo.|  
|**Todas as implantações de aplicativo (básico)**|Exibe informações de resumo de todas as implantações de aplicativo.|  
|**Conformidade de aplicativo**|Exibe as informações de conformidade do aplicativo especificado na coleção especificada.|  
|**Implantações de aplicativos por ativo**|Exibe os aplicativos implantados em um dispositivo ou usuário especificado.|  
|**Erros de infraestrutura de aplicativos**|Exibe os erros de infraestrutura do aplicativo. Esses erros incluem problemas da infraestrutura interna ou erros resultantes de regras de requisitos inválidas.|  
|**Status detalhado do uso do aplicativo**|Exibe detalhes de uso de aplicativos instalados.|  
|**Status do resumo de uso do aplicativo**|Exibe um resumo de uso dos aplicativos instalados.|  
|**Aplicativos iOS com implantações com falha (aplicativo já instalado)**|Exibe informações de conformidade para o aplicativo iOS selecionado. Implante esse aplicativo como um 'Pacote do aplicativo para iOS da App Store', que você associou também a uma política de gerenciamento de aplicativo móvel. Esse relatório é usado para exibir usuários e dispositivos para os quais o aplicativo falhou ao ser instalado por ter sido já instalado manualmente pelo usuário.|  
|**Implantações de sequência de tarefas que contêm aplicativo**|Exibe as implantações de sequência de tarefas que instalam um aplicativo especificado.|  
|**Solicitações de usuário para aplicativo do Android**|Exibe os usuários que solicitaram a instalação de um aplicativo do Android.|  



## <a name="software-distribution---collections"></a>Distribuição de software – coleções  

Os três relatórios a seguir são listados na categoria **Distribuição de Software – Coleções**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as coleções**|Exibe todas as coleções na hierarquia.|  
|**Todos os recursos em uma coleção específica**|Exibe todos os recursos em uma coleção especificada.|  
|**Janelas de manutenção disponíveis para um cliente especificado**|Exibe todas as janelas de manutenção aplicáveis ao cliente especificado.|  



## <a name="software-distribution---content"></a>Distribuição de software – conteúdo  

Os 16 relatórios a seguir são listados na categoria **Distribuição de software – Conteúdo**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as distribuições de conteúdo ativas**|Exibe todos os pontos de distribuição nos quais o conteúdo está sendo atualmente instalado ou removido.|  
|**Todo o conteúdo**|Exibe todos os aplicativos e pacotes em um site.|  
|**Todo o conteúdo em um ponto de distribuição específico**|Exibe todo o conteúdo atualmente instalado em um ponto de distribuição especificado.|  
|**Todos os pontos de distribuição**|Exibe informações sobre os pontos de distribuição para cada site.|  
|**Todas as mensagens de status de um pacote específico em um ponto de distribuição específico**|Exibe todas as mensagens de status de um pacote especificado em um ponto de distribuição especificado.|  
|**Status de distribuição de conteúdo do aplicativo**|Exibe informações sobre o status de distribuição de conteúdo do aplicativo.|  
|**Aplicativos direcionados ao grupo de pontos de distribuição**|Exibe informações sobre o conteúdo do aplicativo que foi implantado em um grupo de pontos de distribuição especificado.|  
|**Aplicativos fora de sincronização em um grupo de pontos de distribuição especificado**|Exibe os aplicativos para os quais os arquivos de conteúdo associados não foram atualizados com a versão mais recente em um grupo de pontos de distribuição especificado.|  
|**Grupo de pontos de distribuição**|Exibe informações sobre um grupo de pontos de distribuição especificado.|  
|**Resumo do uso do ponto de distribuição**|Exibe o resumo de uso de ponto de distribuição para cada ponto de distribuição.|  
|**Status de distribuição do pacote especificado**|Exibe o status de distribuição para o conteúdo de pacote especificado em cada ponto de distribuição.|  
|**Pacotes direcionados a um grupo de pontos de distribuição**|Exibe informações sobre os pacotes destinados a um grupo de pontos de distribuição especificado.|  
|**Pacotes fora de sincronização em um grupo de pontos de distribuição especificado**|Exibe os pacotes para os quais os arquivos de conteúdo associados não foram atualizados com a versão mais recente em um grupo de pontos de distribuição especificado.|  
|**Rejeição de conteúdo de origem do cache par**|Exibe o número de rejeições de origem de cache par por grupo de limites.|
|**Rejeição de conteúdo de origem do cache par por condição**|Exibe as origens de cache par que rejeitaram fornecer o conteúdo de acordo com uma condição.|
|**Detalhes da rejeição de conteúdo de origem do cache par**|Exibe o nome do conteúdo rejeitado por uma origem par.|



## <a name="software-distribution---package-and-program-deployment"></a>Distribuição de software – implantação de pacote e programa 

Os cinco relatórios a seguir são listados na categoria **Distribuição de software – Implantação de pacote e programa**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as implantações de um pacote e programa especificados**|Exibe informações sobre todas as implantações de um pacote e programa especificado.|  
|**Todas as implantações de pacote e programa**|Exibe todas as implantações de pacote e programa neste site.|  
|**Todas as implantações do pacote e do programa para uma coleção especificada**|Exibe todas as implantações de pacote e programa em uma coleção especificada.|  
|**Todas as implantações do pacote e do programa de um computador especificado**|Exibe todas as implantações de pacote e programa que se aplicam a um computador especificado.|  
|**Todas as implantações do pacote e do programa para um usuário especificado**|Exibe todas as implantações de pacote e programa em um usuário especificado.|  



## <a name="software-distribution---package-and-program-deployment-status"></a>Distribuição de software – status de implantação de pacote e programa  

Os cinco relatórios a seguir são listados na categoria **Distribuição de software – Status de implantação de pacote e programa**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as implantações de pacote de recursos do sistema e programa com status**|Exibe todas as implantações de pacote e programa para o site com um status de resumo de cada implantação.|  
|**Todos os recursos de sistema para uma implantação de pacote e programa especificada em um determinado estado**|Exibe uma lista de recursos que estão em um estado especificado para uma implantação de pacote e programa especificada.|  
|**Gráfico – Status de conclusão da implantação de pacote e programa por hora**|Exibe o percentual de computadores que instalaram o pacote com êxito. A lista é organizada a cada hora desde que um administrador cria a implantação do pacote e do programa. Ele pode ser usado para rastrear o tempo médio para uma implantação de pacote e programa.|  
|**Status da implantação de pacote e programa para um cliente e implantação especificados**|Exibe as mensagens de status relatadas para um computador especificado e a implantação de pacote e programa.|  
|**Status de uma implantação de pacote e programa especificada**|Exibe o resumo do status de uma implantação de pacote e programa especificada.|  



## <a name="software-metering"></a>Medição de software  

Os 13 relatórios a seguir são listados na categoria **Medição de software**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as regras de medição de software aplicadas ao site**|Exibe uma lista de todas as regras de medição de software no site.|  
|**Computadores que têm um programa medido instalado, mas não executaram o programa desde uma data especificada**|Exibe todos os computadores com o aplicativo limitado especificado, mas cujo programa nenhum usuário executou desde a data especificada.|  
|**Computadores que executaram um programa de software medido específico**|Exibe uma lista de computadores que executaram programas que correspondem à regra de medição de software especificada no mês e ano especificados.|  
|**Uso simultâneo de todos os programas de software medidos**|Exibe o número máximo de usuários que executaram simultaneamente cada programa de software medido durante o mês e ano especificados.|  
|**Análise de tendência de uso simultâneo de um programa de software medido especificado**|Exibe o número máximo de usuários que executaram simultaneamente o programa de software medido especificado durante cada mês do ano passado.|  
|**Instalar a base para todos os programas de software medidos**|Exibe o número de computadores que contêm programas de software medidos instalados, conforme relatado pelo inventário de software. Esse relatório exige que o computador colete o inventário de software.|  
|**Progresso do resumo da medição de software**|Exibe a hora em que os dados de medição resumidos mais recentemente foram processados no servidor do site. Os relatórios de medição de software refletem somente os dados de medição processados antes dessas datas.|  
|**Resumo de uso de hora do dia para um programa de software medido específico**|Exibe o número médio de usos de um programa específico nos últimos 90 dias, dividido por dia e hora.|  
|**Uso total para todos os programas de software medidos**|Exibe o número de usuários que executaram programas no mês e ano especificados e que correspondem a cada regra de medição de software. Essas regras destinam-se ao software instalado localmente ou ao uso dos Serviços de Terminal.|  
|**Uso total para todos os programas de software medidos em Windows Terminal Servers**|Exibe o número de usuários que executaram programas que correspondem a cada regra de medição de software usando os Serviços de Terminal no mês e ano especificados.|  
|**Análise de tendência de uso total para um programa de software medido específico**|Exibe o número de usuários que executaram programas durante cada mês do ano passado e que correspondem à regra de medição de software especificada. Essas regras destinam-se ao software instalado localmente ou ao uso dos Serviços de Terminal.|  
|**Análise de tendência de uso total de um programa de software medido específico em Windows Terminal Servers**|Exibe o número de usuários que executaram programas durante cada mês do ano passado e que correspondem à regra de medição de software especificada. Essas regras referem-se ao uso dos Serviços de Terminal.|  
|**Usuários que executaram um programa de software medido específico**|Exibe uma lista de usuários que executaram programas no mês e ano especificados e que correspondem à regra de medição de software especificada.|  



## <a name="software-updates---a-compliance"></a>Atualizações de software – conformidade A  

Os oito relatórios a seguir são listados na categoria **Atualizações de software – Conformidade A**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Conformidade 1 – Conformidade geral**|Exibe os dados de conformidade geral de um grupo de atualização de software.|  
|**Conformidade 2 – Atualização de software específica**|Exibe os dados de conformidade para uma atualização de software especificada.|  
|**Conformidade 3 – Grupo de atualização (por atualização)**|Exibe os dados de conformidade das atualizações de software definidas em um grupo de atualização de software.|  
|**Conformidade 4 – Atualizações por fornecedor, mês e ano**|Exibe os dados de conformidade para atualizações de software liberadas por um fornecedor durante um mês e ano especificados.|  
|**Conformidade 5 – Computador específico**|Este relatório retorna os dados de conformidade de atualização de software para um computador especificado. Para limitar a quantidade de informações retornadas, é possível especificar a classificação da atualização de fornecedor e software.|  
|**Conformidade 6 – Estados de atualização de software específicos (secundários)**|Exibe a contagem e o percentual de computadores em cada estado de conformidade para a atualização de software especificada.|  
|**Conformidade 7 – Computadores em um estado de conformidade específico para um grupo de atualizações (secundários)**|Exibe todos os computadores em uma coleção que têm um estado de conformidade geral especificado em relação a um grupo de atualização de software.|  
|**Conformidade 8 – Computadores em um estado de conformidade específico para uma atualização (secundários)**|Exibe todos os computadores em uma coleção que têm um estado de conformidade especificado para uma atualização de software.|  
|**Conformidade 9 – integridade e conformidade gerais**|Exibe os dados gerais de integridade e conformidade de um grupo de atualização de software. (começando na versão 1806)| 


## <a name="software-updates---b-deployment-management"></a>Atualizações de software – gerenciamento de implantação B  

Os oito relatórios a seguir são listados na categoria **Atualizações de software – Gerenciamento de implantação B**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Gerenciamento 1 – Implantações de um grupo de atualização**|Exibe todas as implantações que incluem todas as atualizações de software definidas em um grupo de atualização de software especificado.|  
|**Gerenciamento 2 – Atualizações necessárias, mas não implantadas**|Exibe todas as atualizações de software específicas ao fornecedor que os clientes detectam como obrigatórias, mas que um administrador não implantou em uma coleção especificada.|  
|**Gerenciamento 3 – Atualizações em uma implantação**|Exibe as atualizações de software contidas em uma implantação especificada.|  
|**Gerenciamento 4 – Implantações destinadas a uma coleção**|Exibe todas as implantações de atualização de software destinadas a uma coleção especificada.|  
|**Gerenciamento 5 – Implantações destinadas a um computador**|Exibe todas as implantações de atualização de software implantadas em um computador especificado.|  
|**Gerenciamento 6 – Implantações que contêm uma atualização específica**|Exibe todas as implantações que incluem uma atualização de software especificada e a coleção de destino associada para a implantação.|  
|**Gerenciamento 7 – Atualizações em uma implantação com conteúdo ausente**|Exibe as atualizações de software em uma implantação especificada que não têm todo o conteúdo associado recuperado. Esse estado impede que os clientes instalem a atualização, o que impede que a implantação atinja 100% de conformidade.|  
|**Gerenciamento 8 – Computadores com conteúdo ausente (secundário)**|Exibe todos os computadores que exigem a atualização de software especificada, mas cujo conteúdo associado ainda não foi distribuído para um ponto de distribuição.|  



## <a name="software-updates---c-deployment-states"></a>Atualizações de software – estados de implantação C  

Os seis relatórios a seguir são listados na categoria **Atualizações de software – Estados de implantação C**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Estados 1 – Estados de imposição para uma implantação**|Exibe os estados de imposição de uma implantação de atualização de software especificada, que geralmente é a segunda fase da avaliação de uma implantação.|  
|**Estados 2 – Estados de avaliação para uma implantação**|Exibe o estado de avaliação para uma implantação de atualização de software especificada, que geralmente é a primeira fase da avaliação de uma implantação.|  
|**Estados 3 – Estados para uma implantação e computador**|Exibe os estados de todas as atualizações de software na implantação especificada para um computador especificado.|  
|**Estados 4 – Computadores em um estado específico para uma implantação (secundários)**|Exibe todos os computadores em um estado especificado para uma implantação de atualização de software.|  
|**Estados 5 – Estados para uma atualização em uma implantação (secundários)**|Exibe um resumo dos estados de uma atualização de software especificada definidos como destino por uma implantação especificada.|  
|**Estados 6 – Computadores em um estado de imposição específico para uma atualização (secundários)**|Exibe todos os computadores em um estado de imposição especificado para uma atualização de software especificada.|  



## <a name="software-updates---d-scan"></a>Atualizações de software – verificação D  

Os quatro relatórios a seguir são listados na categoria **Atualizações de software – Verificação D**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Verificação 1 – Estados da última verificação por coleção**|Especifique uma coleção para exibir a contagem de computadores em cada estado de verificação de conformidade. Os clientes retornam o estado durante a última verificação de conformidade.|  
|**Verificação 2 – Estados da última verificação por site**|Especifique um site para exibir a contagem de computadores em cada estado de verificação de conformidade. Os clientes retornam o estado durante a última verificação de conformidade.|  
|**Verificação 3 – Clientes de uma coleção que relataram um estado específico (secundários)**|Exibe todos os computadores de uma coleção especificada e um estado de verificação de conformidade especificado durante sua última verificação de conformidade.|  
|**Verificação 4 – Clientes de um site que relataram um estado específico (secundários)**|Especifique um site para exibir todos os computadores com um estado de verificação de conformidade especificado. Os clientes retornam o estado durante sua última verificação de conformidade.|  



## <a name="software-updates---e-troubleshooting"></a>Atualizações de software – solução de problemas E  

Os quatro relatórios a seguir são listados na categoria **Atualizações de software – Solução de problemas E**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Solução de problemas 1 – Erros de verificação**|Exibe os erros de verificação no site e uma contagem de computadores que apresentaram cada erro.|  
|**Solução de problemas 2 – Erros de implantação**|Exibe os erros de implantação no site e uma contagem de computadores que apresentaram cada erro.|  
|**Solução de problemas 3 – Computadores que apresentaram falha com um erro de verificação específico (secundários)**|Exibe uma lista dos computadores que falharam em uma verificação devido a um erro especificado.|  
|**Solução de problemas 4 – Computadores que apresentaram falha com um erro de implantação específico (secundários)**|Exibe uma lista dos computadores nos quais ocorreu uma falha na implantação de atualização devido a um erro especificado.|  



## <a name="state-migration"></a>Migração de estado  

Os três relatórios a seguir são listados na categoria **Migração de estado**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Informações de migração de estado para um computador de origem específico**|Exibe informações de migração de estado de um computador especificado.|  
|**Informações de migração de estado para um ponto de migração de estado específico**|Exibe informações de migração de estado de um ponto de migração de estado especificado.|  
|**Pontos de migração de estado para um site específico**|Exibe os pontos de migração de estado de um site especificado.|  



## <a name="status-messages"></a>Mensagens de status  

Os 12 relatórios a seguir são listados na categoria **Mensagens de status**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as mensagens para uma ID de mensagem específica**|Exibe uma lista de mensagens de status que têm uma ID de mensagem especificada.|  
|**Clientes que relatam erros nas últimas 12 horas para um site específico**|Exibe uma lista de computadores e componentes que relataram erros nas últimas 12 horas e o número de erros relatados.|  
|**Mensagens de componente nas últimas 12 horas**|Exibe uma lista de mensagens do componente das últimas 12 horas para um código do site, computador e componente especificados.|  
|**Mensagens de componente na última hora**|Exibe uma lista das mensagens de status criadas na última hora por um componente especificado em um computador especificado e em um site especificado.|  
|**Contar mensagens de componente na última hora de um site específico**|Exibe o número de mensagens de status por componente e severidade relatados na última hora em um site especificado.|  
|**Contar erros nas últimas 12 horas**|Exibe o número de mensagens de status de erro de componente de servidor nas últimas 12 horas.|  
|**Erros fatais (por componente)**|Exibe uma lista de computadores que relataram erros fatais por componente.|  
|**Erros fatais (por nome do computador)**|Exibe uma lista dos computadores que relataram erros fatais por nome do computador.|  
|**Últimas 1.000 mensagens para um computador específico (Erros e Avisos)**|Exibe um resumo das últimas 1.000 mensagens de status de erro e aviso de componente para um computador especificado.|  
|**Últimas 1.000 mensagens para um computador específico (Erros, Avisos e Informações)**|Exibe um resumo das últimas 1.000 mensagens de status de erro, aviso e informativo de componente para um computador especificado.|  
|**Últimas 1.000 mensagens para um computador específico (Erros)**|Exibe um resumo das últimas 1.000 mensagens de status de erro de componente de servidor para um computador especificado.|  
|**Últimas 1.000 mensagens para um componente de servidor específico**|Exibe um resumo das 1.000 mensagens de status mais recentes para um componente de servidor especificado.|  



## <a name="status-messages---audit"></a>Mensagens de status – auditoria  

Os três relatórios a seguir são listados na categoria **Mensagens de status – Auditoria**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todas as mensagens de auditoria para um usuário específico**|Exibe um resumo de todas as mensagens de status de auditoria para um usuário especificado. As mensagens de auditoria descrevem as ações realizadas no console do Configuration Manager que adicionam, modificam ou excluem objetos no Configuration Manager.|  
|**Controle remoto – Todos os computadores controlados por controle remoto por um usuário específico**|Exibe um resumo das mensagens de status que indicam o controle remoto de computadores cliente por um usuário especificado.|  
|**Controle remoto – Todas as informações de controle remoto**|Exibe um resumo das mensagens de status relacionadas ao controle remoto de computadores cliente.|  



## <a name="task-sequence---deployment-status"></a>Sequência de tarefas – status da implantação  

Os 11 relatórios a seguir são listados na categoria **Sequência de tarefas – Status de implantação**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os recursos do sistema de uma implantação de sequência de tarefas em um estado específico**|Exibe uma lista dos computadores de destino para a implantação de sequência de tarefas especificada em um estado de implantação especificado.|  
|**Todos os recursos de sistema para uma implantação de sequência de tarefas que está em um estado específico e que está disponível para computadores desconhecidos**|Exibe uma lista dos computadores de destino para a implantação de sequência de tarefas especificada no estado de implantação especificado.|  
|**Contagem dos recursos de sistema que têm implantações de sequência de tarefas atribuídas mas ainda não executadas**|Exibe o número de computadores que aceitaram sequências de tarefas, mas que não executaram a sequência de tarefas.|  
|**Histórico de uma implantação de sequência de tarefas em um computador**|Exibe o status de cada etapa da implantação de sequência de tarefas especificada no computador de destino especificado. Se nenhum registro for retornado, a sequência de tarefas não foi iniciada no computador.|  
|**Lista de computadores que excederam um período de tempo específico para executar uma implantação de sequência de tarefas**|Exibe a lista de computadores de destino que excederam o período de tempo especificado para executar uma sequência de tarefas.|  
|**Tempo de execução para uma implantação de sequência de tarefas específica em um computador de destino específico**|Exibe o tempo total necessário para concluir com êxito uma sequência de tarefas especificada em um computador especificado.|  
|**Tempo de execução para cada etapa de uma implantação de sequência de tarefas em um computador de destino específico**|Exibe o tempo necessário para concluir cada etapa da implantação de sequência de tarefas especificada no computador de destino especificado.|  
|**Status de uma implantação de sequência de tarefas específica para um computador específico**|Exibe o resumo do status de uma implantação de sequência de tarefas especificada em um computador especificado.|  
|**Status de uma implantação de sequência de tarefas em um computador de destino desconhecido**|Exibe o status da implantação de sequência de tarefas especificada no computador de destino desconhecido especificado.|  
|**Resumo do status de uma implantação de sequência de tarefas específica**|Exibe um resumo do status de todos os recursos que foram definidos como destino por uma implantação.|  
|**Resumo do status de uma implantação de sequência de tarefas específica disponível para computadores desconhecidos**|Exibe o resumo do status de todos os recursos direcionados pela implantação especificada disponíveis para uma coleção que contém computadores desconhecidos.|  



## <a name="task-sequence---deployments"></a>Sequência de tarefas – implantações  

Os 11 relatórios a seguir são listados na categoria **Sequência de tarefas – Implantações**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os recursos do sistema atualmente em um grupo ou fase específica de uma implantação específica de sequência de tarefas**|Exibe uma lista de computadores que estão sendo atualmente executados em um grupo ou fase especificada de uma implantação de sequência de tarefas especificada.|  
|**Todos os recursos do sistema em que uma implantação de sequência de tarefas falhou em um grupo ou fase específica**|Exibe uma lista de computadores que falharam em um grupo/fase especificada da implantação de sequência de tarefas especificada.|  
|**Todas as implantações de sequência de tarefas**|Exibe detalhes de todas as implantações de sequência de tarefas iniciadas no site atual.|  
|**Todas as implantações de sequência de tarefas disponíveis para computadores desconhecidos**|Exibe os detalhes de todas as implantações de sequência de tarefas iniciadas no site e implantadas em coleções que contêm computadores desconhecidos.|  
|**Contagem de falhas em cada fase ou grupo de uma sequência de tarefas específica**|Exibe o número de falhas em cada fase ou grupo da sequência de tarefas especificada.|  
|**Contagem de falhas em cada fase ou grupo de uma implantação de sequência de tarefas específica**|Exibe o número de falhas em cada fase ou grupo da implantação de sequência de tarefas especificada.|  
|**Status de implantação de todas as implantações de sequência de tarefas**|Exibe o progresso geral de todas as implantações de sequência de tarefas.|  
|**Progresso de uma sequência de tarefas em execução**|Exibe o progresso da sequência de tarefas especificada.|  
|**Progresso de uma implantação de sequência de tarefas em execução**|Exibe as informações de resumo para a implantação de sequência de tarefas especificada.|  
|**Progresso de todas as implantações para uma sequência de tarefas específicas**|Exibe o progresso de todas as implantações da sequência de tarefas especificada.|  
|**Relatório de resumo para uma implantação de sequência de tarefas**|Exibe as informações de resumo para a implantação de sequência de tarefas especificada.|  



## <a name="task-sequence---progress"></a>Sequência de tarefas – progresso  

Os cinco relatórios a seguir são listados na categoria **Sequência de tarefas – Progresso**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Gráfico – Progresso semanal de uma sequência de tarefas**|Exibe o progresso semanal de uma sequência de tarefas, a partir da data de implantação.|  
|**Progresso de uma sequência de tarefas**|Exibe o progresso da sequência de tarefas especificada.|  
|**Progresso de todas as sequências de tarefas**|Exibe um resumo do progresso de todas as sequências de tarefas.|  
|**Progresso de sequências de tarefas para implantações de sistema operacional**|Exibe o progresso de todas as sequências de tarefas que implantam sistemas operacionais.|  
|**Status de todos os computadores desconhecidos**|Exibe uma lista de computadores que eram desconhecidos no momento em que executaram uma implantação de sequência de tarefas e indica se agora são computadores conhecidos.|  



## <a name="task-sequences---references"></a>Sequências de tarefas – referências  

O relatório a seguir é listado na categoria **Sequências de tarefas – Referências**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Conteúdo referenciado por uma sequência de tarefas específica**|Exibe o conteúdo referenciado por uma sequência de tarefas especificada.|  



<!--
## Upgrade Assessment  
The following 11 reports are listed under the **Upgrade Assessment** category.

|Report name|Description|  
|-----------------|-----------------|  
|**Application status for a specific computer**|Displays the compatibility of applications that are installed on a computer for a specified operating system.|  
|**Application status for computers in a specific collection**|Displays the overall status for computers in a collection to let you assess them for upgrade to a specified operating system based on the applications on each computer. Use this report to determine which computers have compatible applications before you deploy an operating system.|  
|**Application status summary**|Displays a summary of the application status for a specified operating system. Use this report to determine application compatibility before you deploy an operating system.|  
|**Computers with a specific application installed**|Displays computers with a specified application installed.|  
|**Computers with a specific hardware device**|Displays computers that have a specific hardware device.|  
|**Hardware device status for a specific computer**|Displays the compatibility status of hardware devices for a specified operating system that are found on a specified computer.|  
|**Hardware device status for computers in a specific collection**|Displays the overall status for hardware devices for a specified operating system for computers in a specified collection. Use this report to determine hardware compatibility before you deploy an operating system.|  
|**Hardware device status summary**|Displays a summary of hardware device status for a specified operating system. You can use this report to determine hardware device compatibility before you deploy an operating system.|  
|**Operating system hardware requirements**|Displays the minimum and recommended hardware criteria for operating systems.|  
|**Operating system requirement status for computers in a specific collection**|Displays the status of operating system requirements for the specified operating system for computers in a specified collection. Use this report to determine if a computer meets the specified operating system requirements for CPU processor speed, memory size, and hard disk space.|  
|**Upgrade assessment summary**|Displays the upgrade assessment summary. You can use this report to assess the overall status for upgrade compatibility.|  
-->



## <a name="user---device-affinity"></a>Usuário – afinidade do dispositivo  

Os dois relatórios a seguir são listados na categoria **Usuário – Afinidade de dispositivo**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Associações de afinidade de dispositivo de usuário pendentes por coleção**|Este relatório mostra todas as atribuições de afinidade de dispositivo de usuário pendentes com base nos dados de uso, para membros de uma coleção.|  
|**Associações de afinidade de dispositivo de usuário por coleção**|Exibe todas as associações de dispositivo do usuário para a coleção especificada e agrupa os resultados por tipo de coleção (por exemplo, usuário ou dispositivo).|  



## <a name="user-data-and-profiles-health"></a>Dados do usuário e integridade de perfis  

Os quatro relatórios a seguir são listados na categoria **Integridade de dados e perfis do usuário**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Relatório de integridade de Redirecionamento de Pasta – Detalhes**|Exibe os detalhes do estado de integridade para redirecionamento de pasta para cada uma das pastas redirecionadas de determinado usuário.|  
|**Relatório de Integridade de Perfis do Usuário de Roaming – Detalhes**|Exibe os detalhes do estado de integridade do perfil de usuário móvel de um usuário especificado.|  
|**Relatório de integridade de dados e perfis do usuário – Detalhes**|Exibe os detalhes do erro ou do aviso de redirecionamento de pasta ou de perfis de usuário móveis. Esse relatório é o destino de detalhes do relatório de resumo.|  
|**Relatório de integridade de dados e perfis do usuário – Resumo**|Exibe o resumo dos estados de integridade para redirecionamento de pasta e perfis de usuário móvel.|  



## <a name="users"></a>Usuários  

Os três relatórios a seguir são listados na categoria **Usuários**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Computadores para um nome de usuário específico**|Exibe uma lista de computadores que foram usados por um usuário especificado.|  
|**Contar usuários por domínio**|Exibe o número de usuários em cada domínio.|  
|**Usuários em um domínio específico**|Exibe uma lista de usuários e seus computadores em um domínio especificado.|  



## <a name="virtual-applications"></a>Aplicativos virtuais  

Os sete relatórios a seguir são listados na categoria **Aplicativos virtuais**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Resultados do Ambiente Virtual do App-V**|Exibe informações sobre um ambiente virtual especificado em um estado especificado para uma coleção especificada.|  
|**Resultados do Ambiente Virtual do App-V para o Ativo**|Exibe informações sobre um ambiente virtual especificado para um ativo especificado. Também mostra os tipos de implantação para o ambiente virtual especificado.|  
|**Status do Ambiente Virtual do App-V**|Exibe as informações de conformidade de um ambiente virtual especificado para uma coleção especificada.|  
|**Computadores com um aplicativo virtual específico**|Exibe um resumo de computadores que contêm o atalho de aplicativos do App-V especificado, criado pelo Sequenciador de Gerenciamento de Virtualização de Aplicativo.|  
|**Computadores com um pacote de aplicativos virtuais específico**|Exibe um resumo dos computadores que contêm o pacote de aplicativos do App-V especificado.|  
|**Contagem de todas as instâncias de pacotes de aplicativos virtuais**|Exiba uma contagem de pacotes de aplicativos do App-V detectados.|  
|**Contagem de todas as instâncias de aplicativos virtuais**|Exiba uma contagem de aplicativos do App-V detectados.|  



## <a name="volume-purchase-programs---apple"></a>Programas de compra por volume – Apple

O relatório a seguir está listado na categoria **Programas de Compra por Volume – Apple**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Aplicativos do Apple Volume Purchase Program para iOS com contagens de licença**|Exibe todos os aplicativos iPhone, iPad e iPod touch licenciados por meio do Apple Volume Purchase Program. Esse relatório inclui também o total de licenças adquiridas e as licenças consumidas por aplicativo.|  



## <a name="vulnerability-assessment"></a>Avaliação de vulnerabilidade

O relatório a seguir está listado na categoria **Avaliação de Vulnerabilidade**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Relatório Geral de Avaliação de Vulnerabilidade**|Identifica as vulnerabilidades de segurança, administrativas e de conformidade de um computador específico|  



## <a name="wake-on-lan"></a>Wake On LAN  

Os sete relatórios a seguir são listados na categoria **Wake On LAN**.

|Nome do relatório|Descrição|  
|-----------------|-----------------|  
|**Todos os computadores destinados à atividade de Wake On LAN**|Especifique o tipo de implantação para exibir uma lista de computadores direcionados para a atividade de Wake On LAN.|  
|**Todos os objetos com atividade de ativação pendente**|Exibe os objetos que estão agendados para ativação.|  
|**Todos os sites habilitados para Wake On LAN**|Exibe uma lista de todos os sites na hierarquia que estão habilitados para Wake On LAN.|  
|**Erros recebidos durante o envio de pacotes de ativação por um período definido**|Exibe os erros recebidos durante o envio de pacotes de ativação aos computadores por um período definido.|  
|**Histórico de atividades de Wake On LAN**|Exibe um histórico da atividade de ativação ocorrida desde um determinado período.|  
|**Detalhes do Estado da Implantação do Proxy de Ativação**|Exibe informações sobre o status da implantação do Proxy de ativação para cada dispositivo em uma coleção especificada.|  
|**Resumo do estado da implantação do proxy de ativação**|Exibe um resumo do status da implantação do proxy de ativação para uma coleção especificada.|  
