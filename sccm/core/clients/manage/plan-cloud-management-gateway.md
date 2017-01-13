---
title: Planejar o gateway de gerenciamento de nuvem | Microsoft Docs
description: 
ms.date: 11/22/2016
ms.prod: configuration-manager
ms.technology:
- configmgr-client
ms.assetid: 2dc8c9f1-4176-4e35-9794-f44b15f4e55f
author: nbigman
ms.author: nbigman
manager: angrobe
translationtype: Human Translation
ms.sourcegitcommit: 1f8fbd8a16548ab2c34f5d3dac2b439f3908cea9
ms.openlocfilehash: e6befef692518a5622250af1c71d517b435f9058

---

# <a name="plan-for-cloud-management-gateway-in-configuration-manager"></a>Planejar o gateway de gerenciamento de nuvem no Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

Começando da versão 1610, o gateway de gerenciamento de nuvem fornece uma maneira simples de gerenciar clientes do Configuration Manager na Internet. O serviço de gateway de gerenciamento de nuvem, que é implantado no Microsoft Azure e requer uma assinatura do Azure, conecta-se à sua infraestrutura do Configuration Manager local usando uma nova função chamada de ponto de conexão do gateway de gerenciamento de nuvem. Após ser completamente implantado e configurado, os clientes poderão acessar funções do sistema de sites do Configuration Manager locais independentemente de se eles estão conectados à rede privada interna ou na Internet.

Use o console do Configuration Manager para implantar o serviço no Azure, adicione a função de ponto de conexão do gateway de gerenciamento de nuvem e configure as funções do sistema de sites para permitir o tráfego do gateway de gerenciamento de nuvem. No momento, o gateway de gerenciamento de nuvem dá suporte apenas às funções de ponto de gerenciamento e de ponto de atualização de software.

Os certificados de cliente e os certificados SSL são necessários para autenticar computadores e criptografar comunicações entre diferentes camadas do serviço. Normalmente, os computadores cliente recebem um certificado do cliente por meio da aplicação de política de grupo. Para criptografar o tráfego entre clientes e o servidor do sistema de sites hospedando as funções, você precisa criar um certificado SSL personalizado por meio da AC. Além desses dois tipos de certificados, você também precisa configurar um certificado de gerenciamento no Azure que permita que o Configuration Manager implante o serviço de gateway de gerenciamento de nuvem.

## <a name="requirements-for-cloud-management-gateway"></a>Requisitos para o gateway de gerenciamento de nuvem

-   Computadores cliente e o servidor do sistema de sites que está executando o ponto de conexão do gateway de gerenciamento de nuvem.

-   Certificados SSL personalizados da AC interna – Usado para criptografar a comunicação de computadores cliente e autenticar a identidade do serviço de gateway de gerenciamento de nuvem.

-   Assinatura do Azure para serviços de nuvem.

-   Certificado de gerenciamento do Azure – usado para autenticar o Configuration Manager com o Azure.

## <a name="limitations-of-cloud-management-gateway"></a>Limitações do gateway de gerenciamento de nuvem

-   O gateway de gerenciamento de nuvem dá suporte apenas às funções de ponto de gerenciamento e de ponto de atualização de software.

-   No momento, os seguintes recursos não têm suporte no Configuration Manager para o gateway de gerenciamento de nuvem:

    -   Implantação e atualização do cliente usando o push do cliente

    -   Atribuição automática de site

    -   Políticas de usuário

    -   Catálogo de aplicativos (incluindo solicitações de aprovação de software)

    -   OSD (implantação de sistema operacional) completa

    -   Console do Configuration Manager

    -   Ferramentas remotas

    -   Site de relatórios

    -   Wake on LAN

    -   Clientes Mac, Linux e UNIX

    -   Azure Resource Manager

    -   Cache de pares

    -   Gerenciamento de dispositivo móvel local

## <a name="cost-of-cloud-management-gateway"></a>Custo do gateway de gerenciamento de nuvem

>[!IMPORTANT]
>As informações de custo fornecidas abaixo são apenas para fins de estimativa. Seu ambiente pode ter outras variáveis que afetam o custo geral do uso do gateway de gerenciamento de nuvem.

O gateway de gerenciamento de nuvem usa a seguinte funcionalidade do Microsoft Azure, que resulta em encargos para a conta de assinatura do Azure:

-   Máquina virtual

    -   O gateway de gerenciamento de nuvem atualmente requer uma máquina virtual Standard\_A2. Ao criar o serviço, você pode selecionar quantas VMs para dar suporte ao serviço (uma é o padrão).

    -   Apenas para fins de estimativa, estime que uma única máquina virtual Standard\_A2 do Azure pode dar suporte a aproximadamente 2.000 clientes baseados na Internet simultâneos.

    -   Consulte a [Calculadora de preços do Azure](https://azure.microsoft.com/en-us/pricing/calculator/) para ajudar a determinar os possíveis custos.

      >[!NOTE]
      >Os custos de máquina virtual variam de acordo com a região.

-   Transferência de dados de saída

    -   Há cobrança para dados saindo do serviço. Consulte os [Detalhes de preços de largura de banda do Azure](https://azure.microsoft.com/en-us/pricing/details/bandwidth/) para ajudar a determinar os possíveis custos.

    -   Apenas para fins de estimativa, estime aproximadamente 100 MB por cliente por mês para clientes baseados na Internet realizando atualizações de política a cada hora.

    >[!NOTE]
    > Executar outras ações com suporte por meio do gateway de gerenciamento de nuvem (por exemplo, implantar atualizações de software ou aplicativos) aumentará a quantidade de transferência de dados de saída do Azure.

-   Armazenamento de conteúdo

    -   Os clientes baseados na Internet gerenciados com o gateway de gerenciamento de nuvem obterão o conteúdo da atualização de software do Windows Update sem custo.

    -   Qualquer outro conteúdo necessário (por exemplo, aplicativos) deve ser distribuído para um ponto de distribuição baseado em nuvem. No momento, o gateway de gerenciamento de nuvem dá suporte apenas ao Ponto de Distribuição na Nuvem para enviar conteúdo para clientes.

    - Consulte o custo do uso de uma [distribuição baseada em nuvem](/sccm/core/plan-design/hierarchy/use-a-cloud-based-distribution-point#cost-of-using-cloud-based-distribution) para obter mais detalhes.

## <a name="next-steps"></a>Próximas etapas

[Configurar o gateway de gerenciamento de nuvem](setup-cloud-management-gateway.md)



<!--HONumber=Dec16_HO3-->

