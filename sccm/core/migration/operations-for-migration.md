---
title: Operações de migração
titleSuffix: Configuration Manager
description: Criar e executar trabalhos para migrar dados e clientes para o System Center Configuration Manager.
ms.date: 12/30/2016
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: c28e3492-851a-40fc-ba13-67ebc2d8b41a
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: b59ff47ace87e4c7e8a345402616de44342ea9c1
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56121406"
---
# <a name="operations-for-migrating-to-system-center-configuration-manager"></a>Operações de migração para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Para migração no System Center Configuration Manager, é possível migrar dados e clientes após coletar com êxito os dados do site de origem em uma hierarquia de origem com suporte. Use as informações nas seções a seguir para criar e executar trabalhos de migração para migrar dados e clientes e, em seguida, concluir o processo de migração.  

-   [Criar e editar trabalhos de migração](#Create_Edit_migration_Jobs)  

-   [Executar trabalhos de migração](#Run_Migration_Jobs)  

-   [Atualizar ou reatribuir um ponto de distribuição compartilhado](#BKMK_ProcUpgrdSS)  

-   [Monitorar a atividade de migração no workspace Migração](#Monitor_MIgration)  

-   [Migrar clientes](#BKMK_MigrateClients)  

-   [Concluir a migração](#Complete_Migration)  

##  <a name="Create_Edit_migration_Jobs"></a> Criar e editar trabalhos de migração  
 Use os procedimentos a seguir para criar trabalhos de migração de dados, editar a lista de exclusões de trabalhos de migração baseados em coleção, configurar pontos de distribuição compartilhados e editar agendamentos de trabalhos de migração.  

> [!NOTE]  
>  O procedimento a seguir usado para criar um trabalho de migração que migra por coleções aplica-se somente às hierarquias de origem que executam uma versão com suporte do Configuration Manager 2007. O tipo de trabalho de migração baseado em coleção não está disponível quando você migra de uma hierarquia de origem do System Center 2012 Configuration Manager ou do System Center Configuration Manager.  

#### <a name="create-a-migration-job-to-migrate-by-collections"></a>Criar um trabalho de migração para migrar por coleções  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Na guia **Início**, no grupo **Criar**, escolha **Criar Trabalho de Migração**.  

4.  Na página **Geral** do Assistente para Criar Trabalho de Migração, configure o seguinte e, em seguida, escolha **OK**:  

    -   Especifique um nome para o trabalho de migração.  

    -   Na lista suspensa **Tipo de Trabalho** , selecione **Migração da coleção**.  

5.  Na página **Selecionar Coleções**, configure o seguinte e, em seguida, escolha **Avançar**:  

    -   Selecione as coleções que você deseja migrar.  

    -   Se deseja migrar somente as coleções e não os objetos associados a elas, desmarque **Migrar objetos associados com as coleções especificadas**. Ao desmarcar essa opção, nenhum objeto associado será migrado nesse trabalho e você pode pular as etapas 6 e 7.  

6.  Na página **Selecionar Objetos**, desmarque os tipos de objeto ou objetos disponíveis específicos que você não deseja migrar. Por padrão, todos os tipos de objeto associado e objetos disponíveis são selecionados. Escolha **Próxima**.  

7.  Na página **Propriedade do Conteúdo**, atribua a propriedade de conteúdo de cada site de origem listado a um site na hierarquia de destino e, em seguida, escolha **Avançar**.  

8.  Na página **Escopo de Segurança**, selecione um ou mais escopos de segurança de administração baseada em funções para atribuir aos objetos a serem migrados nesse trabalho e, em seguida escolha **Avançar**.  

9. Na página **Limitação de Coleção**, configure uma coleção da hierarquia de destino para limitar o escopo de cada coleção listada e, em seguida, escolha **Avançar**. Se não houver coleções listadas, escolha **Avançar**.  

10. Na página **Substituição de Código do Site**, atribua um código do site da hierarquia de destino para substituir o código do site do Configuration Manager 2007 em cada coleção listada e, em seguida, escolha **Avançar**. Se não houver coleções listadas, escolha **Avançar**.  

11. Na página **Informações de Análise**, escolha **Salvar em Arquivo** para salvar as informações exibidas para visualizações futuras. Quando estiver pronto para continuar, escolha **Avançar**.  

12. Na página **Configurações**, defina quando o trabalho de migração será executado, escolha as configurações adicionais que você necessita para esse trabalho de migração e, em seguida escolha **Avançar**.  

13. Confirme as configurações e conclua o assistente.  

#### <a name="create-a-migration-job-to-migrate-by-objects"></a>Criar um trabalho de migração para migrar por objetos  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Na guia **Início**, no grupo **Criar**, escolha **Criar Trabalho de Migração**.  

4.  Na página **Geral** do Assistente para Criar Trabalho de Migração, configure o seguinte e, em seguida, escolha **Avançar**:  

    -   Especifique um nome para o trabalho de migração.  

    -   Na lista suspensa **Tipo de Trabalho** , selecione **Migração de objeto**.  

5.  Na página **Selecionar Objetos** , selecione os tipos de objeto que você deseja migrar. Por padrão, todos os objetos disponíveis estarão selecionados para cada tipo de objeto que você escolher.  

6.  Na página **Propriedade do Conteúdo**, atribua a propriedade de conteúdo de cada site de origem listado a um site na hierarquia de destino e, em seguida, escolha **Avançar**. Se não houver sites de origem listados, escolha **Avançar**.  

7.  Na página **Escopo de Segurança**, selecione um ou mais escopos de segurança de administração baseada em funções para atribuir aos objetos nesse trabalho de migração e, em seguida, escolha **Avançar**.  

8.  Na página **Informações de Análise**, escolha **Salvar em Arquivo** para salvar as informações exibidas para visualizações futuras. Quando estiver pronto para continuar, escolha **Avançar**.  

9. Na página **Configurações**, defina quando o trabalho de migração será executado e escolha as configurações adicionais que você necessita para esse trabalho de migração. Em seguida, escolha **Avançar**.  

10. Confirme as configurações e conclua o assistente.  

#### <a name="create-a-migration-job-to-migrate-changed-objects"></a>Criar um trabalho de migração para migrar objetos alterados  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Na guia **Início**, no grupo **Criar**, escolha **Criar Trabalho de Migração**.  

4.  Na página **Geral** do Assistente para Criar Trabalho de Migração, configure o seguinte e, em seguida, escolha **Avançar**:  

    -   Especifique um nome para o trabalho de migração.  

    -   Na lista suspensa **Tipo de Trabalho**, selecione **Objetos modificados após a migração**.  

5.  Na página **Selecionar Objetos** , selecione os tipos de objeto que você deseja migrar. Por padrão, todos os objetos disponíveis estarão selecionados para cada tipo de objeto que você escolher.  

6.  Na página **Propriedade do Conteúdo**, atribua a propriedade de conteúdo de cada site de origem listado a um site na hierarquia de destino e, em seguida, escolha **Avançar**. Se não houver sites de origem listados, escolha **Avançar**.  

7.  Na página **Escopo de Segurança**, selecione um ou mais escopos de segurança de administração baseada em funções para atribuir aos objetos nesse trabalho de migração e, em seguida, escolha **Avançar**.  

8.  Na página **Informações de Análise**, escolha **Salvar em Arquivo** para salvar as informações exibidas para visualizações futuras. Quando estiver pronto para continuar, escolha **Avançar**.  

9. Na página **Configurações**, defina quando o trabalho de migração será executado e escolha as configurações adicionais que você precisa para esse trabalho de migração. Ao contrário dos outros tipos de trabalho de migração, esse trabalho de migração deve substituir os objetos migrados anteriormente no banco de dados do System Center Configuration Manager. Escolha **Próxima**.  

10. Confirme as configurações e, em seguida, conclua o assistente.  

###  <a name="BKMK_Modify_Exclusion_List"></a> Modificar a lista de exclusões para migração  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, escolha **Migração** para obter acesso à lista de exclusões. É possível também acessar a lista de exclusão do nó **Hierarquia de Origem** ou **Trabalhos de Migração** .  

3.  Na guia **Início**, no grupo **Migração**, escolha **Editar Lista de Exclusões**.  

4.  Na caixa de diálogo **Editar Lista de Exclusões**, selecione o objeto excluído a ser removido da lista de exclusões e, em seguida, escolha **Remover**.  

5.  Escolha **OK** para salvar as alterações e concluir a edição. Para cancelar as alterações atuais e restaurar todos os objetos que foram removidos, escolha **Cancelar** e, em seguida, escolha **Não**. Isso cancelará a remoção dos objetos e fechará a caixa de diálogo **Editar Lista de Exclusões** .  

#### <a name="share-distribution-points-from-the-source-hierarchy"></a>Compartilhar os pontos de distribuição da hierarquia de origem  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração**, escolha **Hierarquia de Origem** e selecione o site de origem que você deseja configurar.  

3.  Na guia **Início**, no grupo **Site de Origem**, escolha **Configurar**.  

4.  Na caixa de diálogo **Credenciais do Site de Origem**, selecione **Habilitar o compartilhamento de ponto de distribuição para o servidor do site de origem** e, em seguida, escolha **OK**.  

5.  Após a conclusão da coleta de dados, escolha **Fechar**.  

#### <a name="change-the-schedule-of-a-migration-job"></a>Alterar o agendamento de um trabalho de migração  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Escolha o trabalho de migração que você deseja alterar. Na guia **Início**, no grupo **Propriedades**, clique em **Propriedades**.  

4.  Nas propriedades do trabalho de migração, selecione a guia **Configurações**, altere a hora de execução do trabalho de migração e, em seguida, escolha **OK**.  

##  <a name="Run_Migration_Jobs"></a> Executar trabalhos de migração  
 Use o procedimento a seguir para executar um trabalho de migração que ainda não foi iniciado.  


1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Escolha o trabalho de migração que você deseja executar. Na guia **Início**, no grupo **Trabalho de Migração**, escolha **Iniciar**.  

4.  Escolha **Sim** para iniciar o trabalho de migração.  

##  <a name="BKMK_ProcUpgrdSS"></a> Atualizar ou reatribuir um ponto de distribuição compartilhado  
 É possível atualizar um ponto de distribuição com suporte compartilhado de um site de origem do Configuration Manager 2007 (ou transferir um ponto de distribuição com suporte compartilhado de um site de origem do System Center Configuration Manager) para ser um ponto de distribuição na hierarquia de destino.  

> [!IMPORTANT]  
>  Para poder atualizar um ponto de distribuição secundário do Configuration Manager 2007, é necessário desinstalar o software cliente do Configuration Manager 2007 de um computador com ponto de distribuição secundário. Se o software cliente do Configuration Manager 2007 estiver instalado quando você tentar atualizar o ponto de distribuição, ocorrerá falha na atualização e o conteúdo anteriormente implantado no ponto de distribuição secundário será removido do computador.  

> [!CAUTION]  
>  Ao atualizar ou transferir um ponto de distribuição compartilhado, a função do sistema de sites do ponto de distribuição e o computador do sistema de sites serão removidos do site de origem e adicionados como um ponto de distribuição ao site na hierarquia de destino que você selecionar.  

#### <a name="upgrade-or-reassign-a-shared-distribution-point"></a>Atualizar ou reatribuir um ponto de distribuição compartilhado  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Hierarquia de Origem**.  

3.  Selecione o site que tem o ponto de distribuição que você deseja atualizar, escolha a guia **Pontos de Distribuição Compartilhados** e selecione o ponto de distribuição qualificado para ser atualizado ou transferido.  

4.  Na guia **Ponto de Distribuição**, no grupo **Ponto de Distribuição**, escolha **Transferir**.  

5.  Especifique as configurações no Assistente para Transferir Ponto de Distribuição Compartilhado como se você estivesse instalando um novo ponto de distribuição para a hierarquia de destino, com as seguintes adições:  

    -   Na página **Conversão de Conteúdo**, examine as diretrizes sobre o espaço necessário para converter o conteúdo existente. Em seguida, na página **Configurações de Unidade** do assistente, verifique se a unidade do computador do ponto de distribuição selecionado tem a quantidade necessária de espaço livre em disco.  

6.  Confirme as configurações e, em seguida, conclua o assistente.  

##  <a name="Monitor_MIgration"></a> Monitorar a atividade de migração no workspace Migração  
 Usar o console do Configuration Manager para monitorar a migração.  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Trabalhos de Migração**.  

3.  Escolha o trabalho de migração que você deseja monitorar.  

4.  Exiba os detalhes e o status do trabalho de migração selecionado nas guias **Resumo** e **Objetos no Trabalho**.  

##  <a name="BKMK_MigrateClients"></a> Migrar clientes  
 Após a migração de dados dos clientes entre hierarquias, mas antes de completar a migração, planeje a migração de clientes para a hierarquia de destino. A migração de clientes entre hierarquias envolve desinstalar o software cliente do Configuration Manager dos computadores atribuídos à hierarquia de origem e instalar o software cliente do Configuration Manager da hierarquia de destino. Ao instalar o cliente da hierarquia de destino, você também atribui o cliente a um site primário naquela hierarquia. Para saber mais sobre a migração de clientes, consulte [Planejando a estratégia de migração de cliente no System Center Configuration Manager](../../core/migration/planning-a-client-migration-strategy.md).  

##  <a name="Complete_Migration"></a> Concluir a migração  
 Use este procedimento para concluir a migração da hierarquia de origem.  

1.  No console do Configuration Manager, escolha **Administração**.  

2.  No workspace **Administração**, expanda **Migração** e, em seguida, escolha **Hierarquia de Origem**.  

3.  Para hierarquias de origem do Configuration Manager 2007, selecione um site de origem que esteja no nível inferior da hierarquia de origem. Para uma hierarquia de origem do System Center 2012 Configuration Manager ou do System Center Configuration Manager, selecione o sites de origem disponível.  

4.  Na guia **Início**, no grupo **Limpar**, escolha **Parar Coleta de Dados**.  

5.  Escolha **Sim** para confirmar a ação.  

6.  Para uma hierarquia de origem do Configuration Manager 2007, antes de continuar para a próxima etapa, repita as etapas 3, 4 e 5. Realize estas etapas em cada site na hierarquia, da parte inferior da hierarquia até a parte superior. Para uma hierarquia de origem do System Center 2012 Configuration Manager ou do System Center Configuration Manager, selecione a próxima etapa.  

7.  Na guia **Início**, no grupo **Limpar**, escolha **Limpar Dados de Migração**.  

8.  Na caixa de diálogo **Limpar Dados de Migração**, na lista suspensa **Hierarquia de origem**, selecione o código do site e o servidor do site no site de nível superior da hierarquia de origem e, em seguida, escolha **OK**.  

9. Escolha **Sim** para concluir o processo de migração para a hierarquia de origem.  
