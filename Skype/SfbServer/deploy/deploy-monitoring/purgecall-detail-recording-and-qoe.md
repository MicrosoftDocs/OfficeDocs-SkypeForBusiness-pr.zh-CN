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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="ab0ec-103">在 Skype for Business Server 中手动清除呼叫详细信息记录和用户体验质量数据库</span><span class="sxs-lookup"><span data-stu-id="ab0ec-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="ab0ec-104">**摘要：** 了解如何手动清除 Skype for Business Server 使用的 CDR 和 QoE 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="ab0ec-105">CDR 和 QoE 数据库可以手动或自动清除记录。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="ab0ec-106">清除记录非常重要，这样数据不会过时或需要从起始基线重置报告。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="ab0ec-107">手动清除 CDR 和 QoE 数据库中的记录</span><span class="sxs-lookup"><span data-stu-id="ab0ec-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="ab0ec-108">管理员可以将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动清除数据库中的旧记录;如果为指定的数据库 (CDR 或 QoE) 启用了清除，并且数据库中存在超过指定时间的任何记录，则会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="ab0ec-109">例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="ab0ec-110">除了该自动清除之外，Skype for Business Server &#x2014; Invoke-CsCdrDatabasePurge了两Invoke-CsQoEDatbasePurge &#x2014; cmdlet 和 cmdlet;这些 cmdlet 允许管理员随时手动清除 CDR 和 QoE 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="ab0ec-111">例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="ab0ec-112">在上一个命令中，呼叫详细信息记录和超过 10 天的诊断数据记录都将从 atl-sql-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="ab0ec-113"> (呼叫详细信息记录是用户/会话报告。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="ab0ec-114">诊断数据记录是由客户端应用程序（如 Skype for Business Server.) </span><span class="sxs-lookup"><span data-stu-id="ab0ec-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="ab0ec-115">如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="ab0ec-116">但是，不一定要将这些参数设置为相同的值。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="ab0ec-117">例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="ab0ec-118">为此，将 PurgeCallDetailDataOlderThanDays 设置为 10，将 PurgeDiagnosticDataOlderThanDays 设置为 0。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="ab0ec-119">例如：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="ab0ec-120">默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="ab0ec-p106">您必须在数据库清除实际执行前键入 Y（表示“是”）或 A（表示“全部清除”）。如果您想要隐藏这些确认提示，则将以下参数添加到对 Invoke-CsCdrDatabasePurge 的调用的末尾：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="ab0ec-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="ab0ec-124">如果这样做，则不会显示确认提示，且数据库清除将立即执行。</span><span class="sxs-lookup"><span data-stu-id="ab0ec-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="ab0ec-125">若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：</span><span class="sxs-lookup"><span data-stu-id="ab0ec-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


