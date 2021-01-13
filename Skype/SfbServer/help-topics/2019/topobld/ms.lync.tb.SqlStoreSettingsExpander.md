---
title: SQL 存储设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑数据库SQL Server，必须更改SQL Server实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用"编辑属性"对话框更改承载中央管理存储SQL Server实例。
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805512"
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑数据库SQL Server，必须更改SQL Server实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用"编辑属性"对话框更改承载中央管理存储SQL Server实例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑数据库SQL Server属性

若要更改由中央SQL Server存储外的任何数据库使用的数据库的实例，请完成拓扑生成器中的以下过程：
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改实例SQL Server

1. 在“SQL 存储”节点下选择相应的数据库，然后单击“编辑属性”。
    
2. 在“编辑属性”对话框中，执行下列操作之一：
    
   - 若要使用默认SQL Server实例，请选择 **"默认实例**"，然后单击"**确定"。**
    
   - 要使用命名数据库实例，请选择 **“命名实例”**，在文本框中输入实例名称，然后单击 **“确定”**。 应仅输入实例名称 (例如 ArchivingInstance) ，而不是整个SQL Server路径。
    
当您在"编辑属性"对话框中操作时，拓扑生成器不会验证您输入的数据库实例是否有效。 例如，如果无意中键入ArchivingInstanec 作为实例名称，然后单击"确定"，拓扑生成器将接受该无效实例。 在发布此拓扑之前，必须更正此错误：如果找不到SQL Server实例，拓扑生成器将不会创建该实例。
  

