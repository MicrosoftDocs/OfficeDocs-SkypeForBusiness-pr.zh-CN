---
title: 创建数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 拓扑生成器提供了一种在数据库存储中安装SQL Server的方法。 当您使用拓扑生成器安装数据库时，应用程序会从拓扑中读取信息，然后在指定的 SQL Server 或 SQL Server 群集中安装所需数据库。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定的计算机上安装特定数据库，或者必须安装并排的数据库，则必须使用 Windows PowerShell 命令行接口和 Install-CsDatabase cmdlet。
ms.openlocfilehash: b8c4cc75104093b868d40be18a540eea4019a0b7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619888"
---
# <a name="create-database"></a>创建数据库
 
拓扑生成器提供了一种在数据库存储中安装SQL Server的方法。 当您使用拓扑生成器安装数据库时，应用程序会从拓扑中读取信息，然后在指定的 SQL Server 或 SQL Server 群集中安装所需数据库。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定的计算机上安装特定数据库，或者必须安装并排的数据库，则必须改为使用 Windows PowerShell 命令行接口和[Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。
  
### <a name="creating-a-database"></a>创建数据库

1. 单击"Skype for Business Server 2015"节点，然后单击"**安装数据库"。**
    
2. 在"**安装** 数据库"对话框中的"创建数据库"页上，选择要创建新数据库的 SQL Server 存储的完全限定域名 (FQDN) FQDN。
    
3. 单击“高级”。在“选择数据库文件位置”对话框中，选择下列选项之一：
    
   - **自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。
    
   - **使用 SQL Server 实例默认值**。 如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。 日志和数据文件将存储在由 SQL Server 默认路径（SQL Server 管理员必须提前配置好这些路径）指定的位置。 数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。
    
4. 单击“确定”。
    
5. 在“创建数据库”页上，单击“下一步”。
    
6. 在“数据库创建已完成”页上，单击“完成”。
