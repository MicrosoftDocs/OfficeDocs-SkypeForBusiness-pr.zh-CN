---
title: 创建数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 拓扑生成器使您能够在 SQL Server 存储安装数据库。 使用拓扑生成器安装数据库时，应用程序从拓扑结构中读取信息，然后将所需的数据库安装在指定的 SQL Server 的计算机或群集 SQL Server 上。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果您需要在特定计算机上安装特定的数据库或您必须安装一个按顺序排列的数据库，则必须使用 Windows PowerShell 命令行界面和安装 CsDatabase cmdlet。
ms.openlocfilehash: 9bee333e0b56a6eeb8f4363e6657be2fabfa1ace
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-database"></a>创建数据库
 
拓扑生成器使您能够在 SQL Server 存储安装数据库。 使用拓扑生成器安装数据库时，应用程序从拓扑结构中读取信息，然后将所需的数据库安装在指定的 SQL Server 的计算机或群集 SQL Server 上。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果您需要在特定计算机上安装特定的数据库或您必须安装一个按顺序排列的数据库，则必须使用 Windows PowerShell 命令行界面和[安装 CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。
  
### <a name="creating-a-database"></a>创建数据库

1. 单击 Skype 业务服务器 2015年节点，然后单击**安装数据库**。
    
2. 在**安装数据库**对话框中的**创建数据库**页上，选择新的数据库将创建对 SQL Server 存储完全限定的域名 (FQDN)。
    
3. 单击“**高级**”。在“**选择数据库文件位置**”对话框中，选择下列选项之一：
    
  - **自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。
    
  - **使用 SQL Server 实例默认值**。 如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。 相反，日志和数据文件存储在 SQL Server 默认路径 （这些路径必须配置 SQL Server 管理员高级） 由指定的位置。 数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。
    
4. 单击“**确定**”。
    
5. 在“**创建数据库**”页上，单击“**下一步**”。
    
6. 在“**数据库创建已完成**”页上，单击“**完成**”。
    

