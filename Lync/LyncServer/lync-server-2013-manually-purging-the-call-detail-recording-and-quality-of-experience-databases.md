---
title: 手动清除呼叫详细信息记录和用户体验质量数据库
TOCTitle: 手动清除呼叫详细信息记录和用户体验质量数据库
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204812(v=OCS.15)
ms:contentKeyID: 49312524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 手动清除呼叫详细信息记录和用户体验质量数据库

 

_**上一次修改主题：** 2014-07-07_

如上一节中所述，管理员可将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动从数据库中清除旧记录；当已对指定数据库（CDR 或 QoE）启用清除时以及数据库中有任何记录的期限长于指定的时间量时，就会出现上述情况。例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。

除该自动清除之外，Microsoft Lync Server 2013 中还增加了两个新的 cmdlet - Invoke-CsCdrDatabasePurge 和 Invoke-CsQoEDatbasePurge；这些 cmdlet 允许管理员随时从 CDR 和 QoE 数据库中手动清除记录。例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

在上述命令中，期限长于 10 天的呼叫详细信息记录和诊断数据记录都将从 atl-sql-001.litwareinc.com 上的监视数据库中删除。（呼叫详细信息记录是用户/会话报告。诊断数据记录是由客户端应用程序（如 Lync 2013）上载的诊断日志。）

如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。但是，不一定要将这些参数设置为相同的值。例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。若要执行该操作，请将 PurgeCallDetailDataOlderThanDays 设置为 10，并将 PurgeDiagnosticDataOlderThanDays 设置为 0。例如：

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

您必须在数据库清除实际执行前键入 Y（表示“是”）或 A（表示“全部清除”）。如果您想要隐藏这些确认提示，则将以下参数添加到对 Invoke-CsCdrDatabasePurge 的调用的末尾：

    -Confirm:$False

例如：

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

如果这样做，则不会显示确认提示，且数据库清除将立即执行。

若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

