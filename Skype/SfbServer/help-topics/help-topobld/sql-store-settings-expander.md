---
title: SQL 存储设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 若要编辑的 SQL Server 数据库的属性，则必须更改 SQL Server 数据库实例。 不能使用编辑属性对话框中执行任务，例如将存档服务器数据库从一台计算机移动到另一个。 此外，您不能使用编辑属性对话框来更改 SQL Server 实例承载中央管理存储。
ms.openlocfilehash: 66f75ba3aa92530f983f3415d690b0eb0ae1ed15
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971993"
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑的 SQL Server 数据库的属性，则必须更改 SQL Server 数据库实例。 不能使用**编辑属性**对话框中执行任务，例如将存档服务器数据库从一台计算机移动到另一个。 此外，您不能使用**编辑属性**对话框来更改 SQL Server 实例承载中央管理存储。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑 SQL Server 数据库的属性

若要更改除中央管理存储之外的任何数据库使用的 SQL Server 实例，完成以下过程在拓扑生成器中：
  
### <a name="to-modify-an-instance-of-sql-server"></a>若要修改的 SQL Server 实例

1. 选择**SQL 存储**节点中，在相应的数据库，然后单击**编辑属性**。
    
2. 在**编辑属性**对话框中，执行以下任一操作：
    
  - 若要使用默认 SQL Server 实例，选择**默认实例**，然后单击**确定**。
    
  - 若要使用的命名的数据库实例，选择**命名实例**，在文本框中，输入实例名称，然后单击**确定**。 您应输入仅实例名称 (例如，ArchivingInstance)，并且不是整个 SQL Server 路径。
    
当您正在在**编辑属性**对话框中时，则拓扑生成器不会验证您输入的数据库实例有效实例。 例如，如果您不小心 typeArchivingInstanec 作为实例名称，然后单击**确定**拓扑生成器将接受该无效的实例。 您可以发布该拓扑之前，您必须更正此错误： 找不到 SQL Server 实例，如果拓扑生成器不会为您创建的实例。
  

