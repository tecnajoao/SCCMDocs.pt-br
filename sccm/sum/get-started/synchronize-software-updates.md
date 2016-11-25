---

title: "Gerenciar sincronização de atualizações de software | Configuration Manager"
description: "Use estas etapas para agendar a sincronização de atualizações de software, iniciar a sincronização de atualizações de software manualmente e monitorar a sincronização de atualizações de software."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 10/06/2016
ms.topic: article
ms.prod: configuration-manager
ms.service: 
ms.technology:
- configmgr-sum
ms.assetid: ea8698c4-9df5-4cf5-8b62-ab93115b4769
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: a720a38962aee33f0d6a7c9ca447dd98d7e0c24e



---

#  <a name="a-namebkmksumsynca-synchronize-software-updates"></a><a name="BKMK_SUMSync"></a> Sincronizar atualizações de software

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

 A sincronização de atualização de software no Configuration Manager é o processo de recuperação de metadados de atualização de software que atendem aos critérios configurados. Isso inclui produtos específicos, classificações e idiomas. Normalmente, o ponto de atualização de software no site de administração central ou em um site primário autônomo recupera os metadados do Microsoft Update. Em seguida, o site de nível superior enviará uma solicitação de sincronização para outros sites. Quando um site recebe a solicitação de sincronização proveniente do site pai, o ponto de atualização de software recupera os metadados das atualizações de software e sua [origem de sincronização](../plan-design/plan-for-software-updates.md#BKMK_SyncSource) upstream. Para obter mais informações sobre a sincronização de atualização de software, consulte [Software updates synchronization (Sincronização de atualizações de software)](../understand/software-updates-introduction.md#BKMK_Synchronization).

Configure a sincronização de atualização de software para ser executada em um agendamento nas propriedades do ponto de atualização de software no site de nível superior. Após configurar o agendamento de sincronização você, geralmente, não irá alterar o agendamento como parte das operações normais. No entanto, você pode iniciar manualmente a sincronização de atualização de software quando for necessário.

  > [!NOTE]  
  >  Os pontos de atualização de software devem ser conectados à sua origem de sincronização upstream para sincronizar atualizações de software. Quando o ponto de atualização de software está desconectado de sua origem de sincronização upstream, você pode usar o método de exportar e importar para sincronizar as atualizações de software. Para obter mais informações, consulte [Synchronize software updates from a disconnected software update point](synchronize-software-updates-disconnected.md) (Sincronizar atualizações de software de um ponto de atualização de software desconectado).  

## <a name="schedule-software-updates-synchronization"></a>Agendar a sincronização de atualizações de software
Quando você configura um agendamento para a sincronização de atualizações de software, o ponto de atualização de software de nível de site inicia a sincronização com o Microsoft Update na data e hora agendadas. O agendamento personalizado permite que você sincronize as atualizações de software em uma data e hora em que as demandas do servidor do WSUS, servidor do site e a rede estão baixas. Por exemplo, é possível definir o agendamento para que as atualizações de software sejam sincronizadas toda semana às 2h. Durante a sincronização agendada, todas as alterações aos metadados de atualizações de software desde a última sincronização agendada são inseridas no banco de dados do site. Isso inclui novos metadados de atualizações de software ou metadados que foram modificados, removidos ou agora vencidos.

Use os procedimentos a seguir no site de nível superior para agendar a sincronização de atualizações de software.  

#### <a name="to-schedule-software-updates-synchronization"></a>Para agendar a sincronização de atualizações de software  

  1.  No console do Configuration Manager, clique em **Administração**.  

  2.  No espaço de trabalho Administração, expanda **Configuração do Site**e clique em **Sites**.  

  3.  No painel de resultados, clique no site de administração central ou no site primário autônomo.  

  4.  Na guia **Início** , no grupo **Configurações** , clique em **Configurar Componentes do Site**e clique em **Ponto de Atualização de Software**.  

  5.  Na caixa de diálogo Propriedades do Componente de Ponto de Atualização de Software, selecione **Habilitar sincronização em um agendamento**e especifique o agendamento de sincronização.  

## <a name="manually-start-software-updates-synchronization"></a>Iniciar manualmente a sincronização de atualizações de software
Também é possível iniciar manualmente a sincronização de atualizações de software no site de nível superior no console do Configuration Manager no nó **Todas as atualizações de software** no espaço de trabalho **Biblioteca de Software**.  

Use os procedimentos a seguir no site de nível superior para iniciar manualmente a sincronização de atualizações de software.  

#### <a name="to-manually-start-software-updates-synchronization"></a>Para iniciar manualmente a sincronização de atualizações de software  

  1.  No console do Configuration Manager conectado ao site de administração central ou ao site primário autônomo, clique em **Biblioteca de Software**.  

  2.  No espaço de trabalho Biblioteca de Software, expanda **Atualizações de Software** e clique em **Todas as Atualizações de Software** ou **Grupos de Atualização de Software**.  

  3.  Na guia **Início** , no grupo **Criar** , clique em **Sincronizar Atualizações de Software**. Na caixa de diálogo, clique em **Sim** para confirmar que deseja iniciar o processo de sincronização.  

   Iniciado o processo de sincronização no ponto de atualização de software, é possível monitorar o processo de sincronização no console do Configuration Manager para todos os pontos de atualização de software em sua hierarquia. Use o procedimento a seguir para monitorar o processo de sincronização de atualizações de software.  


## <a name="monitor-software-updates-synchronization"></a>Monitorar a sincronização de atualizações de software
Após iniciar o processo de sincronização, será possível usar o console do Configuration Manager para monitorar o processo para todos os pontos de atualização de software da hierarquia. Use o procedimento a seguir para monitorar o processo de sincronização de atualização de software. Para obter mais informações sobre como monitorar as atualização de software, incluindo o processo de sincronização, consulte [Monitor software updates (Monitorar atualizações de software)](../deploy-use/monitor-software-updates.md).

#### <a name="to-monitor-the-software-updates-synchronization-process"></a>Para monitorar o processo de sincronização de atualizações de software  

  1.  No console do Configuration Manager, clique em **Monitoramento**.  

  2.  No espaço de trabalho **Monitoramento** , clique em **Status da Sincronização do Ponto de Atualização do Software**.  

    Os pontos de atualização de software na sua hierarquia do Configuration Manager são exibidos no painel de resultados. Nessa exibição, você pode monitorar o status de sincronização de todos os pontos de atualização de software. Quando desejar obter informações mais detalhadas sobre o processo de sincronização, você pode examinar o arquivo wsyncmgr.log, localizado em <*ConfigMgrInstallationPath*>\Logs em cada servidor do site.  

## <a name="next-steps"></a>Próximas etapas
Depois de sincronizar as atualizações de software pela primeira vez ou depois que houver novas classificações ou produtos disponíveis, você deverá [configurar as novas classificações e produtos](configure-classifications-and-products.md) para sincronizar atualizações de software com os novos critérios.

Depois de sincronizar as atualizações de software com os critérios de que você precisa, [gerencie as configurações para atualizações de software](manage-settings-for-software-updates.md).  



<!--HONumber=Nov16_HO1-->

