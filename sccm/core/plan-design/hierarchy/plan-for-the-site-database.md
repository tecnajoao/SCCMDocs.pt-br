---
title: Planejar o banco de dados do site
titleSuffix: Configuration Manager
description: Considere o banco de dados do site e a função do servidor de banco de dados do site ao planejar sua hierarquia do System Center Configuration Manager.
ms.date: 03/08/2018
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 104fb4cc-6e83-40a3-8e6b-ac909fb9ec7d
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c9134fa0bbabf5425ce17d21b143d71437aea36
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56136374"
---
# <a name="plan-for-the-site-database-for-system-center-configuration-manager"></a>Planejar o banco de dados do site para o System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

O servidor de banco de dados do site é um computador que executa uma versão com suporte do Microsoft SQL Server. O SQL Server é usado para armazenar informações para sites do Configuration Manager. Cada site em uma hierarquia do Configuration Manager contém um banco de dados e um servidor de site que são atribuídos à função de servidor de banco de dados do site.  

-   Para sites da administração central e sites primários, você pode instalar o SQL Server no servidor do site ou em um computador que não seja o servidor do site.  

-   Para sites secundários, você pode usar o SQL Server Express em vez de uma instalação completa do SQL Server. O servidor de banco de dados deve, no entanto, ser executado no servidor do site secundário.  

-  Para o uso de um Grupo de Disponibilidade do SQL, o Modelo de Recuperação de Banco de Dados deve ser definido como COMPLETO  

-  Para o uso de um Grupo de Disponibilidade que não seja do SQL, o Modelo de Recuperação de Banco de Dados deve ser definido como SIMPLES  

Mais informações sobre os modos de recuperação do SQL podem ser encontradas em [Modelos de recuperação (SQL Server)](https://docs.microsoft.com/sql/relational-databases/backup-restore/recovery-models-sql-server).

As seguintes configurações do SQL Server podem ser usadas para hospedar o banco de dados do site:  

-   A instância padrão do SQL Server  

-   Uma instância nomeada em um único computador com o SQL Server  

-   Uma instância nomeada em uma instância clusterizada do SQL Server  

-   Um grupo de disponibilidade AlwaysOn do SQL Server (a partir da versão 1602 do System Center Configuration Manager)


Para hospedar o banco de dados do site, o SQL Server deve atender aos requisitos detalhados na seção [Suporte a versões do SQL Server para o System Center Configuration Manager](../../../core/plan-design/configs/support-for-sql-server-versions.md).  



## <a name="remote-database-server-location-considerations"></a>Considerações do local do servidor de banco de dados remoto  

Se você usar um computador servidor remoto de banco de dados, certifique-se de que a conexão de rede é uma intervenção de alta disponibilidade e conexão de rede grande de largura de banda. O servidor do site e algumas funções do sistema de sites devem se comunicar constantemente com o servidor remoto que hospeda o banco de dados do site.

-   A quantidade de largura de banda necessária para a comunicação com o servidor de banco de dados depende de uma combinação de muitas configurações diferentes de site e cliente. Portanto, a largura de banda real necessária não pode ser prevista adequadamente.  

-   Cada computador que executa o Provedor de SMS e que se conecta ao banco de dados do site aumenta os requisitos de largura de banda da rede.  

-   O computador que executa o SQL Server deve estar localizado em um domínio com uma relação de confiança bidirecional com o servidor do site e todos os computadores que executam o Provedor de SMS.  

-   Não é possível usar um SQL Server clusterizado para o servidor do banco de dados do site quando o banco de dados do site está colocalizado com o servidor do site.  


Normalmente, um servidor de sistema de sites dá suporte a funções de sistema de sites de um único site do Configuration Manager. Você pode, no entanto, usar diferentes instâncias do SQL Server, em servidores clusterizados e não clusterizados executando o SQL Server, para hospedar um banco de dados de diferentes sites do Configuration Manager. Para dar suporte a bancos de dados de diferentes sites, é necessário configurar cada instância do SQL Server para usar portas de comunicação exclusivas.  
