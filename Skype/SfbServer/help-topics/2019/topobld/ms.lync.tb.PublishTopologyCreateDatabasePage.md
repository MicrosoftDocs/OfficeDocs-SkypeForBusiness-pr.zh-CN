---
title: 创建数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: 拓扑生成器提供一种方法在 SQL Server 存储上安装数据库。 使用拓扑生成器安装数据库时，应用程序从拓扑中读取信息，然后将所需的数据库安装在指定的 SQL Server 计算机或 SQL Server 群集。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果您需要在特定计算机上，安装特定数据库，或者必须安装并置的数据库，您必须改为使用 Windows PowerShell 命令行界面和的 Install-csdatabase cmdlet。
ms.openlocfilehash: 0929c87381fb6535d076161a301a662a15452024
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878674"
---
# <a name="create-database"></a>创建数据库
 
拓扑生成器提供一种方法在 SQL Server 存储上安装数据库。 使用拓扑生成器安装数据库时，应用程序从拓扑中读取信息，然后将所需的数据库安装在指定的 SQL Server 计算机或 SQL Server 群集。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果您需要在特定计算机上，安装特定数据库，或者必须安装并置的数据库，您必须改为使用 Windows PowerShell 命令行界面和的[Install-csdatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。
  
### <a name="creating-a-database"></a>创建数据库

1. 单击 Skype 业务服务器节点，然后单击**安装数据库**。
    
2. 在**安装数据库**对话框中，在**创建数据库**页上，选择新数据库要创建的 SQL Server 存储的完全限定的域名 (FQDN)。
    
3. 单击“**高级**”。在“**选择数据库文件位置**”对话框中，选择下列选项之一：
    
   - **自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。
    
   - **使用 SQL Server 实例默认值**。 如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。 而是日志和数据文件存储在 SQL Server 默认路径 （这些路径必须配置中的 SQL Server 管理员高级） 指定的位置。 数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。
    
4. 单击“**确定**”。
    
5. 在“**创建数据库**”页上，单击“**下一步**”。
    
6. 在“**数据库创建已完成**”页上，单击“**完成**”。
    

