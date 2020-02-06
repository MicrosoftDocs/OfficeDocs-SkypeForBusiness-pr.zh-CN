---
title: SQL 存储设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 若要编辑 SQL Server 数据库的属性，必须更改 SQL Server 数据库实例。 不能使用 "编辑属性" 对话框执行任务，例如将存档服务器数据库从一台计算机移动到另一台计算机。 此外，您不能使用 "编辑属性" 对话框更改承载中央管理存储的 SQL Server 实例。
ms.openlocfilehash: 654b1727badf9c0f08bcab9e181b301b72bd1299
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819194"
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑 SQL Server 数据库的属性，必须更改 SQL Server 数据库实例。 不能使用 "**编辑属性**" 对话框执行任务，例如将存档服务器数据库从一台计算机移动到另一台计算机。 此外，您不能使用 "**编辑属性**" 对话框更改承载中央管理存储的 SQL Server 实例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑 SQL Server 数据库的属性

若要更改除中央管理存储之外的任何数据库所使用的 SQL Server 实例，请在拓扑生成器中完成以下过程：
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改 SQL Server 实例

1. 在 " **SQL 存储**" 节点下选择相应的数据库，然后单击 "**编辑属性**"。
    
2. 在 "**编辑属性**" 对话框中，执行下列操作之一：
    
   - 若要使用默认的 SQL Server 实例，请选择 "**默认实例**"，然后单击 **"确定"**。
    
   - 若要使用命名的数据库实例，请选择 "**命名实例**"，在文本框中输入实例名称，然后单击 **"确定"**。 你应仅输入实例名称（例如，ArchivingInstance），而不是整个 SQL Server 路径。
    
在 "**编辑属性**" 对话框中工作时，拓扑生成器将不会验证您输入的数据库实例是否为有效的实例。 例如，如果不慎 typeArchivingInstanec 为实例名称，然后单击 **"确定**"，拓扑生成器将接受该无效实例。 必须更正此错误，然后才能发布此拓扑：如果找不到 SQL Server 实例，拓扑生成器将不会为你创建该实例。
  

