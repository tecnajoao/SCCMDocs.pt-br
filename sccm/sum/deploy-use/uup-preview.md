---
title: Versão prévia do UUP
titleSuffix: Configuration Manager
description: Instruções para a versão prévia da integração deUUP
ms.date: 12/21/2018
ms.prod: configuration-manager
ms.technology: configmgr-sum
ms.topic: conceptual
ms.assetid: 0b0da585-0096-410b-8035-6b7a312f37f5
author: aczechowski
ms.author: aaroncz
manager: dougeby
robots: noindex,nofollow
ms.openlocfilehash: d2aac5945d4b7678acf78d215c557a34aaef9c72
ms.sourcegitcommit: f5fa9e657350ceb963a7928497d2adca9caef3d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2018
ms.locfileid: "53748550"
---
# <a name="uup-private-preview-instructions"></a>Instruções para a versão prévia privada do UUP

> [!Note]  
> Essa informação está relacionada a uma versão prévia do recurso, a qual pode ser substancialmente modificada antes de seu lançamento comercial. A Microsoft não oferece garantias, expressas ou implícitas, quanto às informações fornecidas aqui.  

## <a name="benefits"></a>Benefícios

### <a name="feature-updates"></a>Atualizações de recursos

As atualizações de recurso com UUP são projetadas para minimizar vários problemas que os clientes têm com manutenção nos dias de hoje. Experimente as atualizações de recurso de UUP, incluindo:

- Atualizar direto para o nível de conformidade de segurança mais recente, você não precisa instalar atualizações de segurança imediatamente após a atualização para estar em conformidade. A cada mês, uma nova atualização de recurso será publicada para incluir a atualização de segurança cumulativa mais recente. Você não precisará baixar novamente ou distribuir a maior parte do conteúdo de atualização de recurso a cada mês, apenas o componente de atualização de segurança, que também é compartilhado com a atualização cumulativa.

- Todos os FODs e pacotes de idioma devem ser preservados e não são perdidos durante o processo de atualização.

- As atualizações de recurso com UUP dão suporte a arquivos de instalação expressa, permitindo que os clientes reduzam a quantidade de conteúdo que cada cliente deve baixar.

### <a name="cumulative-updates"></a>Atualizações cumulativas

As atualizações cumulativas com UUP permitem que o conteúdo para FODs e pacotes de idiomas sejam distribuídos offline, permitindo que os usuários finais os adquiram sob demanda, sem necessidade de acessar a Internet nem de esforços de preparo entediantes por parte dos administradores.



## <a name="set-up-instructions"></a>Instruções de configuração

### <a name="1-send-your-wsus-id-to-your-uup-preview-contact-at-microsoft"></a>1. Enviar sua ID do WSUS para seu contato de versão prévia do UUP na Microsoft

Para participar da versão prévia privada do UUP, você deve compartilhar sua ID do WSUS com a Microsoft para que possamos incluir seu ambiente na lista de permissões para a versão prévia. Sem essa ID, não será possível ver todas as atualizações de UUP até a versão prévia tornar-se pública.

Para recuperar sua ID do WSUS:

```PowerShell
$server = Get-WsusServer
$config = $server.GetConfiguration()
$config.ServerId
```

### <a name="2-upgrade-configmgr-to-a-supported-version"></a>2. Atualizar o ConfigMgr para uma versão compatível

Se você estiver sincronizando arquivos de instalação expressa em seu ambiente, o ConfigMgr 1810 (os builds GA, anel Modo Rápido e TAP são todos aceitáveis) será necessário para ambientes de produção ou então a Technical Preview 1812 para ambientes de Technical Preview.

Se você não estiver sincronizando arquivos de instalação expressa em seu ambiente, o hotfix de UUP do ConfigMgr 1810, além do 1810 GA, será necessário para ambientes de produção ou a Technical Preview 1812 para ambientes de Technical Preview.


#### <a name="configmgr-1810-uup-hotfix-kb4482615-from-1810-ga-slow-ring"></a>Hotfix do UUP 1810 do ConfigMgr (KB4482615) do 1810 GA (anel Modo Lento)
Se você estiver atualmente no ConfigMgr 1810 GA (anel Modo Lento), você precisará atualizar o ConfigMgr para o pacote cumulativo de atualizações do UUP.

1. Aplique o "Hotfix (KB4482615) do Configuration Manager 1810" (GUI do pacote 86450B7D-3574-4CF7-8B11-486A2C1F62A6) – esse hotfix permitirá UUP para cenários não expressos.  

    1. Baixar o hotfix do Centro de Download da Microsoft (o link será fornecido após ser publicado)  

    2. Depois de baixar esse hotfix, confira a seguinte página da Web do Microsoft Docs para obter instruções de instalação: [Usar a ferramenta de registro de atualização para importar hotfixes](/sccm/core/servers/manage/use-the-update-registration-tool-to-import-hotfixes)  

    3. Para obter informações sobre como baixar arquivos de Suporte da Microsoft, clique no número do artigo a seguir para exibir o artigo na Base de Dados de Conhecimento Microsoft: [Como obter os arquivos de Suporte da Microsoft dos serviços online](https://support.microsoft.com/help/119591/how-to-obtain-microsoft-support-files-from-online-services)  

2. Após a atualização para o hotfix UUP, atualize os clientes do ConfigMgr de modo a corresponder. Todos os clientes aos quais que você direcionar atualizações de UUP precisam ser atualizados para evitar **baixar desnecessariamente cerca de 6 GB** de conteúdo não utilizado para o cliente.

#### <a name="configmgr-1810-uup-hotfix-kb4482615-from-1810-fast-ring"></a>Hotfix do UUP 1810 do ConfigMgr (KB4482615) do 1810 anel Modo Rápido
Se você estiver atualmente em um ConfigMgr 1810 anel Modo Rápido, será necessário atualizar do ConfigMgr com duas atualizações de manutenção, mas adie a implantação de atualizações do cliente até você ter feito ambos, de modo que você só precise atualizar os clientes uma vez.

1. Um hotfix para acumular até o GA 1810 estará disponível para você em breve (previsão para o início de janeiro), aguarde até ver a atualização aparecer em Atualizações e Manutenção.  

2. Atualização (somente servidores do site, não clientes) para "Configuration Manager 1810 Hotfix (KB4479288)" (GUID do pacote 930FA45E-530F-4B08-B1BF-DE3F5267B03C)  

3. Atualize para o "Hotfix (KB4482615) do Configuration Manager 1810" (GUID do pacote 86450B7D-3574-4CF7-8B11-486A2C1F62A6) – esse hotfix habilitará UUP para cenários não expressos.  

    1. Baixar o hotfix do Centro de Download da Microsoft (o link será fornecido após ser publicado)  

    2. Depois de baixar esse hotfix, confira a seguinte página da Web do Microsoft Docs para obter instruções de instalação: [Usar a ferramenta de registro de atualização para importar hotfixes](/sccm/core/servers/manage/use-the-update-registration-tool-to-import-hotfixes)  

    3. Para obter informações sobre como baixar arquivos de Suporte da Microsoft, clique no número do artigo a seguir para exibir o artigo na Base de Dados de Conhecimento Microsoft: [Como obter os arquivos de Suporte da Microsoft dos serviços online](https://support.microsoft.com/help/119591/how-to-obtain-microsoft-support-files-from-online-services)  

4. Após a atualização para o hotfix UUP, atualize os clientes do ConfigMgr de modo a corresponder. Todos os clientes aos quais que você direcionar atualizações de UUP precisam ser atualizados para evitar **baixar desnecessariamente cerca de 6 GB** de conteúdo não utilizado para o cliente.

#### <a name="1812-technical-preview"></a>Technical Preview 1812
O Technical Preview 1812, em cenários UUP compatíveis, é equivalente ao Hotfix do UUP do ConfigMgr 1810 (KB4482615).

A única observação é que a atualização de cliente do Technical Preview 1812 é interrompida de TP 1810.1 ou TP 1811. Para contornar esse problema, você precisará desinstalar clientes TP 1810.1 e TP 1811 e, em seguida, instalar o cliente TP 1812 corretamente. Todos os clientes aos quais que você direcionar atualizações de UUP precisam estar no Technical Preview 1812 (ou posterior) para evitar **baixar desnecessariamente cerca de 6 GB** de conteúdo não utilizado para o cliente.


### <a name="3-update-windows-clients-to-supported-versions"></a>3. Atualizar clientes do Windows para as versões compatíveis

#### <a name="for-express-installation-file-sync"></a>Para sincronização de arquivos de instalação expressa
Para conteúdo expresso, as versões compatíveis do Windows incluem:

- **Windows 10 versão 1709** com [KB4338825](https://support.microsoft.com/help/4338825) (atualização de segurança cumulativa de julho de 2017) ou posterior  

- **Windows 10 versão 1803** com [KB4284835](https://support.microsoft.com/help/4284835) (atualização de segurança cumulativa de junho de 2017) ou posterior  

- **Windows 10 versão 1809** com atualização cumulativa que não é de segurança de janeiro (ou a posterior atualização de segurança cumulativa de fevereiro) ou posterior

#### <a name="for-non-express-installation-file-sync"></a>Para sincronização de arquivos de instalação não expressa
Para conteúdo não expresso, um patch adicional precisa ser aplicado. Esse caminho se tornou disponível em um formato não cumulativo no catálogo de 12/20 e estará disponível no formato normal cumulativo no final de janeiro.

**Windows 10 versão 1709** e **Windows 10 versão 1803** com uma das seguintes opções:
- Dezembro-janeiro: Os clientes precisam ter um nível base de atualização cumulativa mais a atualização não cumulativa  
    - Atualização cumulativa  
        - 1709: [KB4338825](https://support.microsoft.com/help/4338825) (atualização de segurança cumulativa de julho de 2017) até atualização de segurança cumulativa de janeiro de 2019, inclusive  
        - 1803: [KB4284835](https://support.microsoft.com/help/4284835) (atualização de segurança cumulativa de junho de 2017) até atualização de segurança cumulativa de janeiro de 2019, inclusive  
    - Atualização não cumulativa: Esta atualização só está disponível no catálogo e não sincroniza diretamente para o WSUS. Para importar a atualização para o seu ambiente a fim de implantá-la, confira [Importar atualizações do catálogo do Microsoft Update](/sccm/sum/get-started/synchronize-software-updates#import-updates-from-the-microsoft-update-catalog).  
        - 1709: [KB4483530](https://support.microsoft.com/help/4483530)  
        - 1803: [KB4483541](https://support.microsoft.com/help/4483541)  
- Fevereiro e depois: Para atualização cumulativa, apenas a ainda não lançada atualização cumulativa que não é de segurança de janeiro (ou a posterior atualização de segurança cumulativa de fevereiro) ou posterior   

**Windows 10 versão 1809** com atualização cumulativa que não é de segurança de janeiro (ou a posterior atualização de segurança cumulativa de fevereiro) ou posterior


### <a name="4-enable-express-installation-on-clients-in-client-settings"></a>4. Habilitar a instalação expressa nos clientes nas configurações do cliente

A configuração para habilitar a instalação expressa do cliente precisa ser definida para atualizações de UUP, independentemente de o conteúdo expresso ser sincronizado ou não. Com essa configuração, o ConfigMgr pode permitir que o WUA determine o conteúdo necessário a baixar para os clientes, em vez de fazer com que o ConfigMgr baixe todo o conteúdo associado à atualização de UUP. Essa configuração é necessária mesmo para cenários não expressos, pois há conteúdo opcional de FOD e de pacote de idiomas, resultando em uma quantidade não significativa de dados extra que não são necessários para todos os clientes associados à atualização.

Habilitar essa configuração não afetará os downloads de conteúdo do servidor, somente os comportamentos de download do cliente. É importante que você tenha o ConfigMgr e as versões de cliente do Windows articuladas acima antes de habilitar essa configuração se ela ainda não foi habilitada, pois essas versões corrigem alguns problemas de compatibilidade com a aprovação de atualizações diretamente no WSUS, além de habilitarem o ConfigMgr a usar esse canal para atualizações de UUP, mesmo se o conteúdo expresso não estiver sincronizado.

Para habilitar a instalação expressa nos clientes:

1. No console do Configuration Manager, vá até **Administração** \ **Configurações do Cliente**  

2. Abra as propriedades das Configurações do Cliente que você deseja usar ou crie um novo para implantar conforme apropriado.  

3. No grupo **Atualizações de Software**, defina **Habilitar a instalação de arquivos de instalação expressos em clientes** para **Sim**

![Realçando a configuração do cliente no grupo de Atualizações de Software](../media/uup-preview-client-settings.png)


### <a name="5-make-sure-your-adrs-are-set-as-desired"></a>5. Verifique se as ADRs estão definidas conforme desejado 

Antes de habilitar a sincronização de atualizações de UUP, considere suas ADRs e qualquer outra infraestrutura de atualização que você tem em vigor. Se você não quiser que essas atualizações sejam implantadas automaticamente como parte de suas ADRs e planos de manutenção existentes, não deixe de atualizar suas ADRs para filtrá-las. Confira [Como localizar atualizações de UUP sincronizadas](#how-to-find-synced-uup-updates). Planos de serviço existentes implantarão não UPP somente por padrão, mas você pode atualizá-los para alterar esse comportamento.

Considere também se essas atualizações afetarão qualquer um dos seus relatórios de conformidade ou outras infraestruturas apenas sincronizando-os e faça quaisquer modificações desejadas com antecedência. Por exemplo, se você medir a conformidade para todos os produtos, você verá agora ambas a atualização do Windows 10 cumulativa UPP e a não UPP como em conformidade ou sem conformidade, o que causará, portanto, uma distorção em seus números.



## <a name="enable-uup-and-start-testing"></a>Habilitar UUP e começar a testar

### <a name="select-products-and-classifications-to-sync"></a>Selecionar os produtos e classificações a sincronizar

Depois que você está pronto para começar a sincronizar atualizações de UUP e experimentá-las, bem como recebeu uma comunicação da Microsoft informando que habilitamos o seu WSUS para ver o piloto, habilite os novos produtos.

1. [Sincronizar Atualizações de Software](/sccm/sum/get-started/synchronize-software-updates) para permitir que os novos produtos sejam populados  

2. No console do Configuration Manager, acesse **Administração** \ **Configuração do Site** \ **Sites**  

3. Selecione o seu site de nível mais alto (autoridades de certificação ou autônomo primário)  

4. Abra **Configurar Componentes do Site** \ **Ponto de Atualização do Software**  

5. Na guia **Produtos**, depois que o servidor do WSUS é adicionado à versão prévia, dois novos produtos deverão aparecer. Esses produtos contêm a conteúdo da versão prévia de UUP.  

    - **Piloto do Windows 10 UUP**: Atualizações de UUP da estação de trabalho do Windows  
    - **Windows Server 2016 UUP**: Atualizações do Windows Server UUP  

6. Na guia **Classificações**, não deixe de selecionar:  

    - **Atualizações de Segurança**: Para ver as Atualizações Cumulativas do UUP  
    - **Atualizações**: Para ver as Atualizações de Recurso do UUP  

7. Sincronizar atualizações de software para ver as novas atualizações de UUP


### <a name="how-to-find-synced-uup-updates"></a>Como encontrar atualizações de UUP sincronizadas

Depois de ter sincronizado atualizações de UUP em seu ambiente, você desejará encontrá-las para que sejam testadas. Há duas maneiras fáceis de encontrar as atualizações de versão prévia dentro do console do Configuration Manager.

- Como essas atualizações de versão prévia estão em produtos separados, você sempre pode usar o produto para filtrar ou encontrar essas atualizações. O filtro de produto foi adicionado a Planos de Manutenção para que você possa selecionar se deseja implantar as atualizações de recurso UUP ou não UUP.  

- Há uma nova coluna opcional **Marca**, nos nós **Todas as Atualizações de Software** e **Todas as Atualizações do Windows 10** da biblioteca de Software, bem como um filtro em ADRs. Esse campo é definido como **UUP** para atualizações de UUP e em branco para atualizações não UUP.  


### <a name="updates-available-during-preview"></a>Atualizações disponíveis durante a versão prévia

- Atualizações Cumulativas do Windows 10 1709
    - Atualização de segurança de dezembro (11/12)
    - Atualização de segurança de janeiro (8/1)
    - Atualização não de segurança de janeiro (15/1)
    - Atualização de segurança de fevereiro (12/2)  

- Atualizações Cumulativas do Windows 10 1803
    - Atualização de segurança de dezembro (11/12)
    - Atualização de segurança de janeiro (8/1)
    - Atualização não de segurança de janeiro (15/1)
    - Atualização de segurança de fevereiro (12/2)  

- Atualizações Cumulativas do Windows 10 1809
    - Atualização de segurança de fevereiro (12/2)  

- Atualizações de Recursos do Windows 10 1803 (de 1709 a 1803)   
    - Conformidade de atualizações de segurança de dezembro (11/12)
    - Conformidade de atualizações de segurança de janeiro (8/1)
    - Conformidade de atualizações de segurança de fevereiro (12/2)  

- Atualizações de Recursos do Windows 10 1809 (de 1709 a 1803)
    - Conformidade de atualizações de segurança de dezembro (11/12)
    - Conformidade de atualizações de segurança de janeiro (8/1)
    - Conformidade de atualizações de segurança de fevereiro (12/2)  

Se necessário, a atualização de segurança de março e outras futuras continuarão a ser publicadas em todas essas áreas enquanto o UUP ainda estiver em versão prévia (pública ou privada). Depois de concluirmos a versão prévia, somente as Atualizações Cumulativas do Windows 10 versão 1809 e Atualizações de Recurso (do Windows 10 versão 1803 em diante) serão compatíveis em produção.


### <a name="scenarios-to-try"></a>Cenários para experimentar

#### <a name="feature-updates"></a>Atualizações de recursos
- Atualizar diretamente para o nível de conformidade de segurança de sua escolha  

- Atualizar com FODs e pacotes de idiomas instalados antes da atualização, eles são preservados durante a atualização  

- Opcionalmente, habilite a sincronização de arquivos de instalação expressa para atualizações de recursos para reduzir a quantidade de conteúdo que cada cliente deve baixar.  

    > [!Note]  
    > Esse benefício do cliente ocorre às custas de maior download de servidor e a distribuição, como é o caso para arquivos de instalação expressa para atualizações cumulativas.  

#### <a name="cumulative-updates"></a>Atualizações cumulativas
Durante a versão prévia, mantenha os clientes em conformidade usando a atualização do tipo de UUP para várias atualizações consecutivas, a fim de conhecer continuamente as expectativas.

#### <a name="content"></a>Conteúdo
A primeira atualização para cada combinação de versão principal (1709, 1803, 1809), arquitetura e idioma parecerá grande em número de arquivos e espaço em disco, quando comparada com o que você teria visto anteriormente nas atualizações não UUP. Este conteúdo extra é principalmente para todos os pacotes de idiomas e de FOD para as atualizações cumulativas. Para atualizações de recurso, especialmente se a expressa está habilitada, há conteúdo adicional que é grande para essa primeira atualização. 

No entanto, as atualizações subsequentes (as atualizações cumulativas e as atualizações de recurso mensal em níveis mais altos de conformidade), a quantidade de conteúdo novo que precisa ser baixado e distribuído será muito menor, já que todo o conteúdo de pacote de idiomas e de FOD é compartilhado de forma inteligente entre as atualizações, em vez de baixado novamente ou redistribuído. Durante a versão prévia, em 1709 e 1803, esse download mensal será aproximadamente equivalente ao tamanho das atualizações cumulativas que você vê em cenários não UUP. No entanto, na 1809, a história fica muito melhor, pois o download incremental da atualização cumulativa é muito menor de mês a mês. 

Quando você vê o conteúdo total baixado e distribuído em um período de 12 meses para não expressa, a 1803 sem UUP deve ser aproximadamente equivalente à 1809 com UUP e, depois desse ponto de virada, o conteúdo total baixado e distribuído em todo o tempo de vida da versão é menor na 1809 com UUP. Para a expressa, o ponto de virada é mais cedo do que com a 1809, pois a expressa é somente para atualizações de recursos não cumulativas e, portanto, o custo da expressa para conteúdo do servidor de grande porte é apenas uma vez por versão, em vez de mensal.

#### <a name="supported-content-channels"></a>Canais de conteúdo compatíveis
Para a versão prévia, teste com o que você usa em seus ambientes empresariais reais. O UUP dará suporte a todos os canais de conteúdo, incluindo:
- Otimização de Entrega do Windows
- Cache par do Configuration Manager
- Windows BranchCache
- Implantar sem baixar para o servidor (sem pacote de implantação) para baixar diretamente do MU (cujo uso recomenda-se que seja feito conjuntamente com o uso do DO)
- Provedores terceiros de conteúdo alternativo

Para obter mais informações, confira [Otimizar a entrega de atualização do Windows 10](/sccm/sum/deploy-use/optimize-windows-10-update-delivery).