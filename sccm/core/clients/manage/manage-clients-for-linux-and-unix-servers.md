---
title: Gerenciar clientes do Linux e UNIX | System Center Configuration Manager
description: Gerencie clientes em servidores Linux e UNIX no System Center Configuration Manager.
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-client
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 948664f2-239d-47a8-92fc-f8efeebd5796
caps.latest.revision: 7
caps.handback.revision: 0
author: Mtillman
ms.author: mtillman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: d10b6876058d19d3a9a750a59267913d15793574


---
# <a name="how-to-manage-clients-for-linux-and-unix-servers-in-system-center-configuration-manager"></a>Como gerenciar clientes para servidores Linux e UNIX no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Ao gerenciar servidores Linux e UNIX com o System Center Configuration Manager, você pode configurar coleções, janelas de manutenção e configurações do cliente para ajudar a gerenciar os servidores. Além disso, embora o cliente do Configuration Manager para Linux e UNIX não tenha uma interface do usuário, você pode forçar o cliente a pesquisar manualmente a política do cliente.

##  <a name="a-namebkmkcollectionsforlnua-collections-of-linux-and-unix-servers"></a><a name="BKMK_CollectionsforLnU"></a> Coleções de servidores Linux e UNIX  
 Você usa coleções para gerenciar grupos de servidores Linux e UNIX da mesma maneira que usa coleções para gerenciar outros tipos de clientes. As coleções podem ser coleções de associação direta ou coleções baseadas em consulta que identificam os sistemas operacionais cliente, as configurações de hardware ou outros detalhes sobre o cliente que são armazenados no banco de dados do site. Por exemplo, você pode usar coleções que incluem servidores Linux e UNIX para gerenciar o seguinte:  

-   Configurações do cliente  

-   Implantações de software  

-   Impor janelas de manutenção  

 Para poder identificar um cliente Linux ou UNIX pelo seu sistema operacional ou sua distribuição, é necessário coletar com êxito o inventário de hardware do cliente. Para obter informações sobre a coleta de inventário de hardware, consulte [Inventário de hardware para Linux e UNIX no System Center Configuration Manager](../../../core/clients/manage/inventory/hardware-inventory-for-linux-and-unix.md).  

 As configurações padrão do cliente para inventário de hardware incluem informações sobre o sistema operacional de um computador cliente. Você pode usar a propriedade **Legenda** da classe **Sistema Operacional** para identificar o sistema operacional de um servidor Linux ou UNIX.  

 Você pode exibir detalhes sobre os computadores que executam o cliente do Configuration Manager para Linux e UNIX no nó Dispositivos do espaço de trabalho Ativos e Conformidade no console do Configuration Manager. No espaço de trabalho Ativos e Conformidade do console do Configuration Manager, é possível exibir o nome do sistema operacional de cada computador na coluna **Sistema Operacional**.  

 Por padrão, os servidores Linux e UNIX são membros da coleção **Todos os Sistemas** . É recomendável que você compile coleções personalizadas que incluam somente servidores Linux e UNIX, ou um subconjunto deles. Isso permite que você gerencie operações como implantação de software ou atribuição de configurações do cliente a grupos de computadores aplicáveis. Por exemplo, se você implantar o software de computadores RHEL6 x64 em uma coleção que contém computadores com Windows e Linux, o status da implantação mostrará êxito parcial. Em vez disso, ao implantar o software em uma coleção que contém apenas computadores RHEL6 x64, é possível usar mensagens de status e relatórios para identificar com precisão o sucesso da implantação.  

 Ao compilar uma coleção personalizada para servidores Linux e UNIX, inclua consultas de regra de associação que incluem o atributo Caption para o atributo Operating System. Para obter informações sobre a criação de coleções, consulte [Como criar coleções no System Center Configuration Manager](../../../core/clients/manage/collections/create-collections.md).  

##  <a name="a-namebkmkmaintenancewindowsforlnua-maintenance-windows-for-linux-and-unix-servers"></a><a name="BKMK_MaintenanceWindowsforLnU"></a> Janelas de manutenção para servidores Linux e UNIX  
 O cliente do Configuration Manager para servidores Linux e UNIX dá suporte ao uso de janelas de manutenção. Esse suporte não foi alterado desde o suporte para clientes baseados em Windows.  

 Para obter mais informações sobre como usar janelas de manutenção, consulte [Como usar janelas de manutenção no System Center Configuration Manager](../../../core/clients/manage/collections/use-maintenance-windows.md).  

##  <a name="a-namebkmkclientsettingsforlnua-client-settings-for-linux-and-unix-servers"></a><a name="BKMK_ClientSettingsforLnU"></a> Configurações de cliente para servidores Linux e UNIX  
 Você pode definir configurações do cliente que se aplicam a servidores Linux e UNIX da mesma forma que você define configurações para outros clientes.  

 Por padrão, as **Configurações Padrão do Agente Cliente** se aplicam a servidores Linux e UNIX. Você também pode criar configurações personalizadas do cliente e implantá-las em coleções que contêm sistemas operacionais clientes específicos ou uma combinação de sistemas operacionais cliente.  

 Não há outras configurações do cliente que se aplicam somente aos clientes Linux e UNIX. No entanto, há configurações padrão do cliente que não se aplicam aos clientes Linux e UNIX. O cliente para Linux e UNIX só aplica configurações de funcionalidade às quais ele dá suporte, e quaisquer configurações de funcionalidade sem suporte serão ignoradas.  

 Por exemplo, você cria uma configuração personalizada de dispositivo do cliente que especifica um agendamento de inventário de hardware e depois a atribui a uma coleção que inclui computadores com Linux. O resultado é que o agendamento de inventário de hardware é imposto nos servidores Linux e UNIX. Em seguida, você cria uma configuração personalizada do dispositivo de cliente que habilita e define as configurações de controle remoto e as atribui à mesma coleção. O resultado é que as configurações de controle remoto são ignoradas pelos servidores Linux e UNIX. Isso ocorre porque o cliente para o Linux e UNIX não dá suporte ao controle remoto no Configuration Manager.  

 Para obter informações sobre configurações de cliente, consulte [Como definir as configurações do cliente no System Center Configuration Manager](../../../core/clients/deploy/configure-client-settings.md).  

##  <a name="a-namebkmkpolicyforlnua-computer-policy-for-linux-and-unix-servers"></a><a name="BKMK_PolicyforLnU"></a> Política de computador para servidores Linux e UNIX  
 O cliente do Configuration Manager para servidores Linux e UNIX sonda periodicamente seu site em relação à política de computador para saber mais sobre as configurações solicitadas e para verificar se há implantações.  

 Você também pode forçar o cliente em um servidor Linux ou UNIX a sondar imediatamente a política do computador. Para sondar imediatamente, use as credenciais de **raiz** no servidor para executar o seguinte comando: **/opt/microsoft/configmgr/bin/ccmexec -rs policy**  

 Os detalhes sobre a pesquisa de política de computador são inseridos no arquivo de log do cliente compartilhado, **scxcm.log**.  

> [!NOTE]  
>  O cliente do Configuration Manager para Linux e UNIX nunca solicita nem processa a política de usuário.  

##  <a name="a-namebkmkmanagelinuxcertsa-how-to-manage-certificates-on-the-client-for-linux-and-unix"></a><a name="BKMK_ManageLinuxCerts"></a> Como gerenciar certificados no cliente para Linux e UNIX  
 Depois de instalar o cliente para Linux e UNIX, você pode usar a ferramenta **certutil** para atualizar o cliente com um novo certificado PKI e importar uma nova CRL (lista de Certificados Revogados). Quando você instala o cliente para Linux e UNIX, essa ferramenta é colocada no seguinte local: **/opt/microsoft/configmgr/bin/certutil**  

 Para gerenciar certificados, em cada cliente execute certutil com uma das seguintes opções:  

|Opção|Mais informações|  
|------------|----------------------|  
|importPFX|Use esta opção para especificar um certificado para substituir o certificado que está sendo usado atualmente por um cliente.<br /><br /> Quando você usa o **-importPFX**, também é necessário usar o parâmetro **–password** da linha de comando para fornecer a senha associada ao arquivo PKCS#12.<br /><br /> Use **-rootcerts** para especificar requisitos de certificado raiz adicionais.<br /><br /> Exemplo: **certutil -importPFX &lt;Caminho para o certificado PKCS#12> -password &lt;Senha do certificado\> [-rootcerts &lt;lista de certificados separados por vírgula>]**|  
|-importsitecert|Use esta opção para atualizar o certificado de assinatura de servidor do site localizado no servidor de gerenciamento.<br /><br /> Exemplo: **certutil -importsitecert &lt;Caminho para o certificado DER\>**|  
|-importcrl|Use esta opção para atualizar a CRL no cliente com um ou mais caminhos de arquivo da CRL.<br /><br /> Exemplo: **certutil -importcrl &lt;caminhos de arquivos CRL separados por vírgula\>**|  



<!--HONumber=Nov16_HO1-->

