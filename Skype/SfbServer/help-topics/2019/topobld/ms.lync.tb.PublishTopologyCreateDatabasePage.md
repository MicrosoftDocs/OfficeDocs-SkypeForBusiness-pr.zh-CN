---
title: 创建数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: 拓扑生成器提供了在 SQL Server 应用商店上安装数据库的方法。 使用拓扑生成器安装数据库时，应用程序读取拓扑中的信息，然后在指定的 SQL Server 计算机或 SQL Server 群集上安装所需的数据库。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定计算机上安装特定数据库，或者必须安装 collocated 数据库，则必须改为使用 Windows PowerShell 命令行接口和 CsDatabase cmdlet。
ms.openlocfilehash: b31d970338848a2fb39d3d41b1ecdcc550efe277
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795453"
---
# <a name="create-database"></a>创建数据库
 
拓扑生成器提供了在 SQL Server 应用商店上安装数据库的方法。 使用拓扑生成器安装数据库时，应用程序读取拓扑中的信息，然后在指定的 SQL Server 计算机或 SQL Server 群集上安装所需的数据库。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定计算机上安装特定数据库，或者必须安装 collocated 数据库，则必须改为使用 Windows PowerShell 命令行接口和[CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。
  
### <a name="creating-a-database"></a>创建数据库

1. 单击 "Skype for Business 服务器" 节点，然后单击 "**安装数据库**"。
    
2. 在 "**安装**数据库" 对话框中的 "**创建数据库**" 页面上，选择要在其中创建新数据库的 SQL Server 应用商店的完全限定的域名（FQDN）。
    
3. 单击“**高级**”。在“**选择数据库文件位置**”对话框中，选择下列选项之一：
    
   - **自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。
    
   - **使用 SQL Server 实例默认值**。 如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。 而是将日志和数据文件存储在 SQL Server 默认路径指定的位置（这些路径必须由 SQL Server 管理员配置为 "高级"）。 数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。
    
4. 单击“**确定**”。
    
5. 在“**创建数据库**”页上，单击“**下一步**”。
    
6. 在“**数据库创建已完成**”页上，单击“**完成**”。
    

