---
title: "Migração completa | System Center Configuration Manager"
description: "Saiba como concluir a migração para uma hierarquia de destino do System Center Configuration Manager depois de uma hierarquia de origem não contiver dados."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-other
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f4854b50-2e8c-414c-a872-9579554dca98
caps.latest.revision: 5
caps.handback.revision: 0
author: Brenduns
ms.author: brenduns
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: 862a039ada302c9432fc86d68f5ba9aad360f69b


---
# <a name="planning-to-complete-migration-in-system-center-configuration-manager"></a>Planejamento da conclusão da migração no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Com o System Center Configuration Manager, quando a hierarquia de origem já não contiver mais dados que você queira migrar para a hierarquia de destino, você poderá concluir o processo de migração. A conclusão da migração inclui as seguintes etapas gerais:  

-   Verificar se os dados necessários foram migrados. Antes de concluir a migração de uma hierarquia de origem, verifique se todos os recursos de que você necessita foram migrados com êxito da hierarquia de origem para a hierarquia de destino. Isso pode incluir dados e clientes.  

-   Pare a coleta de dados dos sites de origem. Para concluir a migração de uma hierarquia de origem, primeiro você deverá parar a coleta de dados dos sites de origem.  

-   Limpar dados de migração. Depois de parar a coleta de dados de todos os sites de origem em uma hierarquia de origem, você poderá remover os dados sobre o processo de migração e sobre a hierarquia de origem do banco de dados da hierarquia de destino.  

-   Encerre a hierarquia de origem. Depois de concluir a migração de uma hierarquia de origem e essa hierarquia não contiver mais recursos que você gerencia, você poderá encerrar os sites na hierarquia de origem e remover de seu ambiente a infraestrutura relacionada. Para obter informações sobre como encerrar sites e hierarquias de origem, consulte a documentação dessa versão do Configuration Manager.  

Use as seguintes seções para ajudá-lo a planejar a conclusão da migração de uma hierarquia de origem, parando a coleta de dados e limpando os dados de migração:  

-   [Planejar a interrupção da coleta de dados](#Plan_to_Stop_Data_Gath)  

-   [Planejar a limpeza dos dados de migração](#Plan_to_clean_up)  

##  <a name="a-nameplantostopdatagatha-plan-to-stop-gathering-data"></a><a name="Plan_to_Stop_Data_Gath"></a> Planejar a interrupção da coleta de dados  
 Antes de concluir a migração e limpar os dados da migração, pare a coleta de dados de cada site de origem na hierarquia de origem. Para interromper a coleta de dados de cada site de origem, execute o comando **Parar Coleta de Dados** na parte inferior da camada dos sites de origem e repita o processo em cada site pai. O site de nível superior da hierarquia de origem deve ser o último site em que a coleta de dados seja interrompida. Você deve parar a coleta de dados em cada site filho para poder executar esse comando em um site pai. Normalmente, você interrompe a coleta de dados somente quando está pronto para concluir o processo de migração.  

 Depois de parar a coleta de dados de um local de origem, pontos de distribuição compartilhados daquele site não estarão mais disponíveis como locais de conteúdo para clientes na hierarquia de destino. Portanto, certifique-se que qualquer conteúdo migrado que os clientes precisem acessar na hierarquia de destino permaneça disponível, usando uma das seguintes opções:  

-   Na hierarquia de destino, distribua o conteúdo a pelo menos um ponto de distribuição.  

-   Antes de interromper a coleta de dados de um site de origem, atualize ou reatribua pontos de distribuição compartilhados que tenham o conteúdo necessário. Para obter informações sobre a atualização ou reatribuição dos pontos de distribuição compartilhados, consulte as seções que se aplicam no tópico [Planejando uma estratégia de migração de implantação de conteúdo no System Center Configuration Manager](../../core/migration/planning-a-content-deployment-migration-strategy.md).  

Depois de parar a coleta de dados de cada site de origem na hierarquia de origem, você poderá limpar os dados de migração. Até você limpar os dados de migração, cada tarefa de migração executada ou programada para ser executada permanecerá acessível no console do Configuration Manager.  

Para mais informações sobre sites de origem e coleta de dados, consulte [Planejando uma estratégia de hierarquia de origem no System Center Configuration Manager](../../core/migration/planning-a-source-hierarchy-strategy.md).  

##  <a name="a-nameplantocleanupa-plan-to-clean-up-migration-data"></a><a name="Plan_to_clean_up"></a> Planejar a limpeza dos dados de migração  
 A última etapa para se concluir a migração é limpar os dados de migração. É possível usar o comando **Limpar Dados de Migração** depois de interromper a coleta de dados de cada site de origem na hierarquia de origem. Essa ação opcional remove dados sobre a hierarquia de origem atual do banco de dados da hierarquia de destino.  

 Quando você limpa dados de migração, a maior parte dos dados é removida do banco de dados da hierarquia de destino. No entanto, detalhes sobre os objetos migrados são mantidos. Com esses detalhes, você pode usar o espaço de trabalho **Migração** para reconfigurar a hierarquia de origem que contém os dados que foram migrados para retomar a migração  daquela hierarquia de origem ou rever objetos ou a propriedade do site dos objetos migrados anteriormente.  



<!--HONumber=Nov16_HO1-->

