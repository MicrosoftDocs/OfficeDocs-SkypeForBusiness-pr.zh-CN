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
description: 摘要： 了解如何手动清除 CDR 和 QoE 数据库 Skype 用于业务服务器 2015年的记录。
ms.openlocfilehash: 1451187112e636e58fbcd32061ce1e8bec1b7b9a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568530"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="b133e-103">手动清除 Skype for Business Server 2015 中的呼叫详细记录和用户体验质量数据库</span><span class="sxs-lookup"><span data-stu-id="b133e-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b133e-104">**摘要：** 了解如何手动清除 CDR 和 QoE 数据库 Skype 用于业务服务器 2015年的记录。</span><span class="sxs-lookup"><span data-stu-id="b133e-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b133e-p101">可以手动或自动清除 CDR 和 QoE 数据库的记录。清除记录非常重要，这样做数据不会变得过时或者需要从开始比较基准重置报告。</span><span class="sxs-lookup"><span data-stu-id="b133e-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="b133e-107">手动清除 CDR 和 QoE 数据库中的记录</span><span class="sxs-lookup"><span data-stu-id="b133e-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="b133e-p102">管理员可将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动从数据库中清除旧记录；当已对指定数据库（CDR 或 QoE）启用清除时以及数据库中有任何记录的期限长于指定的时间量时，就会出现上述情况。例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="b133e-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="b133e-110">除了自动清除，两个新 cmdlet 和 #x 2014;Invoke-cscdrdatabasepurge 和调用 CsQoEDatbasePurge 和 #x 2014;已添加到 Skype 的业务服务器 2015;这些 cmdlet，管理员可以随时从 CDR 和 QoE 数据库手动清除记录。</span><span class="sxs-lookup"><span data-stu-id="b133e-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server 2015; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="b133e-111">例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="b133e-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="b133e-112">上述命令中同时呼叫详细信息记录和诊断数据记录早于 10 天从 atl-sql-001.litwareinc.com 上的监控数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="b133e-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="b133e-113">（呼叫详细记录是用户/会话报告。</span><span class="sxs-lookup"><span data-stu-id="b133e-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="b133e-114">诊断数据记录是由客户端应用程序如 Skype 业务服务器 2015年上载诊断日志）。</span><span class="sxs-lookup"><span data-stu-id="b133e-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server 2015.)</span></span>
  
<span data-ttu-id="b133e-115">如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。</span><span class="sxs-lookup"><span data-stu-id="b133e-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="b133e-116">但是，不一定要将这些参数设置为相同的值。</span><span class="sxs-lookup"><span data-stu-id="b133e-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="b133e-117">例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。</span><span class="sxs-lookup"><span data-stu-id="b133e-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="b133e-118">为此，设置为 10，PurgeDiagnosticDataOlderThanDays 为 0 PurgeCallDetailDataOlderThanDays。</span><span class="sxs-lookup"><span data-stu-id="b133e-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="b133e-119">例如：</span><span class="sxs-lookup"><span data-stu-id="b133e-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="b133e-120">默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：</span><span class="sxs-lookup"><span data-stu-id="b133e-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="b133e-p106">您必须在数据库清除实际执行前键入 Y（表示“是”）或 A（表示“全部清除”）。如果您想要隐藏这些确认提示，则将以下参数添加到对 Invoke-CsCdrDatabasePurge 的调用的末尾：</span><span class="sxs-lookup"><span data-stu-id="b133e-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="b133e-123">例如：</span><span class="sxs-lookup"><span data-stu-id="b133e-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="b133e-124">如果这样做，则不会显示确认提示，且数据库清除将立即执行。</span><span class="sxs-lookup"><span data-stu-id="b133e-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="b133e-125">若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：</span><span class="sxs-lookup"><span data-stu-id="b133e-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


