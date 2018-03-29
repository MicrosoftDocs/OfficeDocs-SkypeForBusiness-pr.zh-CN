---
title: 手动清除 Skype for Business Server 2015 中的呼叫详细记录和用户体验质量数据库
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 摘要： 了解如何手动清除 CDR 和使用 Skype 业务服务器 2015年 QoE 数据库中的记录。
ms.openlocfilehash: 805bf72b3d4846bb00d3c3772b033242976cd7c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a>手动清除 Skype for Business Server 2015 中的呼叫详细记录和用户体验质量数据库
 
**摘要：**了解如何手动清除 CDR 和使用 Skype 业务服务器 2015年 QoE 数据库中的记录。
  
可以手动或自动清除 CDR 和 QoE 数据库的记录。清除记录非常重要，这样做数据不会变得过时或者需要从开始比较基准重置报告。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>手动清除 CDR 和 QoE 数据库中的记录

管理员可将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动从数据库中清除旧记录；当已对指定数据库（CDR 或 QoE）启用清除时以及数据库中有任何记录的期限长于指定的时间量时，就会出现上述情况。例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。
  
除了自动清除，两个新的 cmdlet 和 #x 2014;调用 CsCdrDatabasePurge 并调用 CsQoEDatbasePurge & #x 2014;已添加到 Skype 的业务服务器 2015;这些 cmdlet 允许管理员手动从 CDR 和 QoE 数据库清除记录，在任何时候。 例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

在上述命令中都可以调用详细记录和诊断数据记录之前 10 天从 atl 的 sql 001.litwareinc.com 上的监视数据库中删除。（呼叫详细记录了用户/会话报告。 诊断数据记录是诊断日志上载的客户端应用程序，如 Skype 的业务服务器 2015年）。
  
如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。 但是，不一定要将这些参数设置为相同的值。 例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。 为此，请设置为 10，PurgeDiagnosticDataOlderThanDays 为 0 PurgeCallDetailDataOlderThanDays。 例如：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：
  
```
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
```

您必须在数据库清除实际执行前键入 Y（表示“是”）或 A（表示“全部清除”）。如果您想要隐藏这些确认提示，则将以下参数添加到对 Invoke-CsCdrDatabasePurge 的调用的末尾：
  
```
-Confirm:$False
```

例如：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

如果这样做，则不会显示确认提示，且数据库清除将立即执行。
  
若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


