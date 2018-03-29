---
title: SQL 存储设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 若要编辑属性的 SQL Server 数据库，则必须更改 SQL Server 数据库实例。 不能使用编辑属性对话框中执行任务的存档服务器数据库从一台计算机移动到另一个。 此外，不能用于编辑属性对话框中更改的 SQL Server 实例承载中央管理存储。
ms.openlocfilehash: 2a1fc051e3dc848272a7cad539eaa749ff95d9b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑属性的 SQL Server 数据库，则必须更改 SQL Server 数据库实例。 不能使用**编辑属性**对话框中执行任务的存档服务器数据库从一台计算机移动到另一个。 此外，不能用于**编辑属性**对话框中更改的 SQL Server 实例承载中央管理存储。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑 SQL Server 数据库的属性

若要更改由中央管理存储任何数据库的 SQL Server 的实例，完成拓扑生成器中的以下步骤：
  
### <a name="to-modify-an-instance-of-sql-server"></a>若要修改的 SQL Server 实例

1. 选择在**SQL 存储**节点下，相应的数据库，然后单击**编辑属性**。
    
2. 在**编辑属性**对话框中，执行以下任一操作：
    
  - 若要使用默认的 SQL Server 实例，选择**默认实例**，然后单击**确定**。
    
  - 若要使用已命名的数据库实例，选择**命名实例**、 在文本框中，输入实例名称，然后单击**确定**。 应输入只有实例名称 (例如，ArchivingInstance)，并不是整个 SQL Server 路径。
    
当您在使用**编辑属性**对话框中时，拓扑生成器不会验证您输入的数据库实例是有效的实例。 例如，如果您无意中的 typeArchivingInstanec 作为实例名称，然后单击**确定**，拓扑生成器将接受该无效的实例。 发布此拓扑之前，您必须更正此错误： 如果找不到一个 SQL Server 实例，拓扑生成器不会为您创建该实例。
  

