---
title: SQL 存储设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑数据库SQL Server，必须更改SQL Server数据库实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用"编辑属性"对话框更改承载中央SQL Server存储的组的实例。
ms.openlocfilehash: f77eeb2f397b02231b7d1b004c243f218967c040
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864099"
---
# <a name="sql-store-settings-expander"></a>SQL 存储设置扩展器
 
若要编辑数据库SQL Server，必须更改SQL Server数据库实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用"**编辑属性"** 对话框更改承载中央管理存储SQL Server服务器的实例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>编辑数据库SQL Server属性

若要更改中央SQL Server数据库（中央管理存储）使用的数据库的实例，请完成拓扑生成器中的以下过程：
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改应用程序SQL Server

1. 在“SQL 存储”节点下选择相应的数据库，然后单击“编辑属性”。
    
2. 在“编辑属性”对话框中，执行下列操作之一：
    
   - 若要使用默认实例 **SQL Server，请选择"默认实例**"，然后单击"确定 **"。**
    
   - 要使用命名数据库实例，请选择 **“命名实例”**，在文本框中输入实例名称，然后单击 **“确定”**。 只应输入实例名称 (例如 ArchivingInstance) ，而不是整个SQL Server路径。
    
当您在"编辑属性"对话框中操作时，拓扑生成器不会验证您输入的数据库实例是有效的实例。 例如，如果您无意中键入ArchivingInstanec 作为实例名称，然后单击"确定"，拓扑生成器将接受该无效实例。 在发布此拓扑之前，必须更正此错误：如果找不到SQL Server实例，拓扑生成器将不会创建该实例。
  

