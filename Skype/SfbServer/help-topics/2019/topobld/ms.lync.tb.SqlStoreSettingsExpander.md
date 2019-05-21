---
title: SQL 存储设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑 SQL Server 数据库的属性, 必须更改 SQL Server 数据库实例。 不能使用 "编辑属性" 对话框执行任务, 例如将存档服务器数据库从一台计算机移动到另一台计算机。 此外, 您不能使用 "编辑属性" 对话框更改承载中央管理存储的 SQL Server 实例。
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303016"
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑 SQL Server 数据库的属性, 必须更改 SQL Server 数据库实例。 不能使用 "**编辑属性**" 对话框执行任务, 例如将存档服务器数据库从一台计算机移动到另一台计算机。 此外, 您不能使用 "**编辑属性**" 对话框更改承载中央管理存储的 SQL Server 实例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑 SQL Server 数据库的属性

若要更改除中央管理存储之外的任何数据库所使用的 SQL Server 实例, 请在拓扑生成器中完成以下过程:
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改 SQL Server 实例

1. 在 " **SQL 存储**" 节点下选择相应的数据库, 然后单击 "**编辑属性**"。
    
2. 在 "**编辑属性**" 对话框中, 执行下列操作之一:
    
   - 若要使用默认的 SQL Server 实例, 请选择 "**默认实例**", 然后单击 **"确定"**。
    
   - 若要使用命名的数据库实例, 请选择 "**命名实例**", 在文本框中输入实例名称, 然后单击 **"确定"**。 你应仅输入实例名称 (例如, ArchivingInstance), 而不是整个 SQL Server 路径。
    
在 "**编辑属性**" 对话框中工作时, 拓扑生成器将不会验证您输入的数据库实例是否为有效的实例。 例如, 如果不慎 typeArchivingInstanec 为实例名称, 然后单击 **"确定**", 拓扑生成器将接受该无效实例。 必须更正此错误, 然后才能发布此拓扑: 如果找不到 SQL Server 实例, 拓扑生成器将不会为你创建该实例。
  

