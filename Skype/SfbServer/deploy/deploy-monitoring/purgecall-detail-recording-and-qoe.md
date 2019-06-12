---
title: 在 Skype for Business 服务器中手动清除呼叫详细信息录制和体验数据库的质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '摘要: 了解如何从 CDR 和 Skype for Business Server 使用的 QoE 数据库中手动清除记录。'
ms.openlocfilehash: c995611704c2fed04461da0b311e8a4141fc4908
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282327"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>在 Skype for Business 服务器中手动清除呼叫详细信息录制和体验数据库的质量
 
**摘要:** 了解如何从供 Skype for Business Server 使用的 CDR 和 QoE 数据库中手动清除记录。
  
可以手动或自动清除 CDR 和 QoE 数据库的记录。清除记录非常重要，这样做数据不会变得过时或者需要从开始比较基准重置报告。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>手动清除 CDR 和 QoE 数据库中的记录

管理员可将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动从数据库中清除旧记录；当已对指定数据库（CDR 或 QoE）启用清除时以及数据库中有任何记录的期限长于指定的时间量时，就会出现上述情况。例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。
  
除了自动清除外, 还添加了两个新 cmdlet &#x2014; CsCdrDatabasePurge 和 Invoke CsQoEDatbasePurge &#x2014; 已添加到 Skype for Business 服务器;这些 cmdlet 允许管理员随时手动清除 CDR 和 QoE 数据库中的记录。 例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

在前面的命令中, 将从 atl-sql-001.litwareinc.com 上的监视数据库中删除呼叫详细记录和超过10天的诊断数据记录。 (呼叫详细记录是用户/会话报告。 诊断数据记录是由客户端应用程序 (如 Skype for Business 服务器) 上载的诊断日志。
  
如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。 但是，不一定要将这些参数设置为相同的值。 例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。 若要执行此操作, 请将 PurgeCallDetailDataOlderThanDays 设置为 10, 将 PurgeDiagnosticDataOlderThanDays 设置为0。 例如：
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

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


