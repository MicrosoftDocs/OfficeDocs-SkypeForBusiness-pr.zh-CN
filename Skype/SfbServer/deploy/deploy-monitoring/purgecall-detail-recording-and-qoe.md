---
title: 在 Skype for Business Server 中手动清除呼叫详细信息记录和用户体验质量数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 摘要：了解如何手动清除 Skype for Business Server 使用的 CDR 和 QoE 数据库中的记录。
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802142"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>在 Skype for Business Server 中手动清除呼叫详细信息记录和用户体验质量数据库
 
**摘要：** 了解如何手动清除 Skype for Business Server 使用的 CDR 和 QoE 数据库中的记录。
  
CDR 和 QoE 数据库可以手动或自动清除记录。 清除记录非常重要，这样数据不会过时或需要从起始基线重置报告。
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>手动清除 CDR 和 QoE 数据库中的记录

管理员可以将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动清除数据库中的旧记录;如果为指定的数据库 (CDR 或 QoE) 启用了清除，并且数据库中存在超过指定时间的任何记录，则会出现此情况。 例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。
  
除了该自动清除之外，Skype for Business Server &#x2014; Invoke-CsCdrDatabasePurge了两Invoke-CsQoEDatbasePurge &#x2014; cmdlet 和 cmdlet;这些 cmdlet 允许管理员随时手动清除 CDR 和 QoE 数据库中的记录。 例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

在上一个命令中，呼叫详细信息记录和超过 10 天的诊断数据记录都将从 atl-sql-001.litwareinc.com。  (呼叫详细信息记录是用户/会话报告。 诊断数据记录是由客户端应用程序（如 Skype for Business Server.) 
  
如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。 但是，不一定要将这些参数设置为相同的值。 例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。 为此，将 PurgeCallDetailDataOlderThanDays 设置为 10，将 PurgeDiagnosticDataOlderThanDays 设置为 0。 例如：
  
```powershell
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
  
```powershell
-Confirm:$False
```

例如：
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

如果这样做，则不会显示确认提示，且数据库清除将立即执行。
  
若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


