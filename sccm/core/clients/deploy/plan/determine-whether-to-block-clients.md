---
title: Bloqueando clientes | System Center Configuration Manager
description: "Bloqueie o acesso do cliente à segurança do sistema usando o System Center Configuration Manager."
ms.custom: na
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.reviewer: na
ms.suite: na
ms.technology:
- configmgr-client
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 54ef5fbb-521d-4ca5-a1c5-61e6f538d71e
caps.latest.revision: 8
author: Mtillman
ms.author: mtillman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1134bb2f04152288e72d40b1b1083f415cb4e900
ms.openlocfilehash: bbb541d62c0d8f6d7deb602aaf962e81d4e2b13a


---
# <a name="determine-whether-to-block-clients-in-system-center-configuration-manager"></a>Determinar o bloqueio de clientes no System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Se um computador cliente ou dispositivo móvel cliente não for mais confiável, você poderá bloquear o cliente no console do System Center 2012 Configuration Manager. Clientes bloqueados são rejeitados pela infraestrutura do Configuration Manager para que não possam se comunicar com os sistemas de sites para baixar política, carregar dados de inventário ou enviar mensagens de estado ou status.  

 Você deve bloquear e desbloquear um cliente de seu site registrado, em vez de um site secundário ou um site de administração central.  

> [!IMPORTANT]  
>  O bloqueio no Configuration Manager pode ajudar a proteger o site do Configuration Manager; contudo, não confie nesse recurso para proteger o site contra computadores ou dispositivos móveis não confiáveis, caso você permita que clientes se comuniquem com sistemas de sites usando HTTP, pois um cliente bloqueado poderia reingressar no site com um certificado autoassinado e uma ID de hardware novos. Em vez disso, use o recurso de bloqueio para bloquear a mídia de inicialização perdida ou comprometida usada para implantar sistemas operacionais e quando o sistemas de sites aceitar conexões de cliente HTTPS.  

 Clientes que acessam o site usando o certificado de proxy de ISV não podem ser bloqueados. Para obter mais informações sobre os certificados de proxy de ISV, consulte o SDK (Software Development Kit) do System Center Configuration Manager.  

 Se seus sistemas de site aceitam conexões de cliente HTTPS e sua PKI (infraestrutura de chave pública) oferece suporte para uma CRL (lista de certificados revogados), sempre considere a revogação de certificado como a principal linha de defesa contra certificados potencialmente comprometidos. O bloqueio de clientes no Configuration Manager oferece uma segunda linha de defesa para proteger sua hierarquia.  

##  <a name="a-namebkmkblockvscrla-considerations-for-blocking-clients"></a><a name="BKMK_Block_vs_CRL"></a> Considerações para bloqueio de clientes  

-   Essa opção está disponível para conexões de cliente HTTP e HTTPS, mas possui segurança limitada quando clientes se conectam a sistemas de sites usando HTTP.  

-   Usuários administrativos do Configuration Manager têm autoridade para bloquear um cliente, e a ação é realizada no console do Configuration Manager.  

-   A comunicação do cliente é rejeitada somente da hierarquia do Configuration Manager.  

    > [!NOTE]  
    >  O mesmo cliente pode se registrar com uma hierarquia do Configuration Manager diferente.  

-   O cliente é bloqueado imediatamente do site do Configuration Manager.  

-   Ajuda a proteger os sistemas de site contra computadores e dispositivos móveis potencialmente comprometidos.  

## <a name="considerations-for-using-certificate-revocation"></a>Considerações para usar revogação de certificado  

-   Essa opção estará disponível para conexões de cliente HTTPS Windows se a infraestrutura de chave pública for compatível com a CRL (lista de certificados revogados).  

     Clientes Mac sempre executam a verificação de CRL e essa funcionalidade não pode ser desabilitada.  

     Embora clientes de dispositivo móvel não utilizem listas de certificados revogados para verificar os certificados dos sistemas de site, seus certificados podem ser revogados e verificados pelo Configuration Manager.  

-   Os administradores de infraestrutura de chave pública têm autoridade para revogar um certificado, e a ação é realizada fora do console do Configuration Manager.  

-   A comunicação do cliente poderá ser rejeitada de qualquer computador ou dispositivo móvel que requerer esse certificado de cliente.  

-   Provavelmente haverá um atraso entre a revogação de um certificado e o download, pelos sistemas de site, da CRL (lista de certificados revogados) modificada.  

-   Para muitas implantações de PKI, esse atraso pode ser de um dia ou mais. Por exemplo, nos Serviços de Certificados do Active Directory, o período de expiração padrão é de uma semana para uma CRL completa, e de um dia para uma CRL delta.  

-   Ajuda a proteger os sistemas de site e clientes contra computadores e dispositivos móveis potencialmente comprometidos.  

    > [!NOTE]  
    >  Você pode proteger ainda mais os sistemas de site que executam o IIS por meio de clientes desconhecidos configurando uma CTL (lista de certificados confiáveis) no IIS.  



<!--HONumber=Nov16_HO1-->

