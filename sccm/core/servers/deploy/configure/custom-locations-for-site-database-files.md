---
title: Locais de arquivos de banco de dados personalizados
titleSuffix: Configuration Manager
description: Saiba como especificar locais personalizados para arquivos de banco de dados do SQL Server.
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.technology: configmgr-other
ms.topic: conceptual
ms.assetid: 500a9aa6-68aa-44eb-bf49-350c1314a697
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f094e2e6eab0067f51cb7fcd193a4acc914fc5c
ms.sourcegitcommit: 874d78f08714a509f61c52b154387268f5b73242
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56134945"
---
# <a name="custom-locations-for-system-center-configuration-manager-site-database-files"></a>Locais personalizados para os arquivos do banco de dados do site do System Center Configuration Manager

*Aplica-se a: System Center Configuration Manager (Branch Atual)*

 O System Center Configuration Manager dá suporte a locais personalizados para arquivos de banco de dados do SQL Server.  

> [!NOTE]  
>  A opção de especificar locais de arquivo não padrão não está disponível quando você usa um cluster do SQL Server.  

 **Durante a instalação** de um novo site primário ou site de administração central, você pode:  

-   **Especificar locais de arquivo não padrão para o banco de dados do site**: a instalação Configuration Manager cria o banco de dados do site usando esses locais.  

-   **Especificar o uso de um banco de dados do SQL Server criado previamente que usa locais de arquivo personalizados**:  a instalação do Configuration Manager usa esse banco de dados criado previamente e seus locais de arquivos pré-configurados.  

**Após a instalação** você pode alterar o local dos arquivos de banco de dados do site. Isso exige que você pare o site e edite o local do arquivo no SQL Server:  

-   No servidor do site do Configuration Manager pare o serviço **SMS_Executive**.  

-   Siga a documentação para a versão do SQL Server que você usa para orientá-lo sobre como mover um banco de dados de usuário. Por exemplo, se você usa o SQL Server 2014, consulte [Mover bancos de dados de usuário](https://technet.microsoft.com/library/ms345483\(v=sql.120\).aspx) no TechNet.  

-   Depois de completar a movimentação de arquivos de banco de dados, reinicie o serviço **SMS_Executive** no servidor de sites do Configuration Manager.  
