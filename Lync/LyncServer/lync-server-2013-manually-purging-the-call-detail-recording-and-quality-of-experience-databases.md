---
title: 手动清除呼叫详细记录和体验数据库的质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979f05441bfb62c8b79c604127e23fe7b7b4909f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="52520-102">在 Lync Server 2013 中手动清除 "呼叫详细信息记录" 和 "体验质量" 数据库</span><span class="sxs-lookup"><span data-stu-id="52520-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52520-103">_**主题上次修改时间:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="52520-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="52520-p101">管理员可将呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 数据库配置为自动从数据库中清除旧记录；当已对指定数据库（CDR 或 QoE）启用清除时以及数据库中有任何记录的期限长于指定的时间量时，就会出现上述情况。例如，在每天的 1:00 AM，管理员可能会配置系统，以便从 QoE 数据库中删除期限长于 60 天的 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="52520-p101">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="52520-106">除了自动清除外, 还添加了两个新 cmdlet--CsCdrDatabasePurge 和 CsQoEDatbasePurge--已添加到 Microsoft Lync Server 2013;这些 cmdlet 允许管理员随时手动清除 CDR 和 QoE 数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="52520-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="52520-107">例如，若要从 CDR 数据库中手动清除所有期限长于 10 天的记录，则可以使用类似于下面的命令：</span><span class="sxs-lookup"><span data-stu-id="52520-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="52520-108">在前面的命令中, 将从 atl-sql-001.litwareinc.com 上的监视数据库中删除呼叫详细记录和超过10天的诊断数据记录。</span><span class="sxs-lookup"><span data-stu-id="52520-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="52520-109">(呼叫详细记录是用户/会话报告。</span><span class="sxs-lookup"><span data-stu-id="52520-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="52520-110">诊断数据记录是由客户端应用程序 (如 Lync 2013) 上载的诊断日志。</span><span class="sxs-lookup"><span data-stu-id="52520-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="52520-111">如上所述，当运行 Invoke-CsCdrDatabasePurge cmdlet 时，您必须同时包含 PurgeCallDetaiDataOlderThanDays 和 PurgeDiagnosticDataOlderThanDays 参数。</span><span class="sxs-lookup"><span data-stu-id="52520-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="52520-112">但是，不一定要将这些参数设置为相同的值。</span><span class="sxs-lookup"><span data-stu-id="52520-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="52520-113">例如，可以清除所有期限长于 10 天的呼叫详细信息记录，同时将所有诊断数据记录保留在数据库中。</span><span class="sxs-lookup"><span data-stu-id="52520-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="52520-114">若要执行此操作, 请将 PurgeCallDetailDataOlderThanDays 设置为 10, 将 PurgeDiagnosticDataOlderThanDays 设置为0。</span><span class="sxs-lookup"><span data-stu-id="52520-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="52520-115">例如：</span><span class="sxs-lookup"><span data-stu-id="52520-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="52520-116">默认情况下，无论何时运行 Invoke-CsCdrDatabasePurge 时，您都将看到每个必须清除的数据库表都带有类似于下面内容的提示：</span><span class="sxs-lookup"><span data-stu-id="52520-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="52520-p105">您必须在数据库清除实际执行前键入 Y（表示“是”）或 A（表示“全部清除”）。如果您想要隐藏这些确认提示，则将以下参数添加到对 Invoke-CsCdrDatabasePurge 的调用的末尾：</span><span class="sxs-lookup"><span data-stu-id="52520-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="52520-119">例如：</span><span class="sxs-lookup"><span data-stu-id="52520-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="52520-120">如果这样做，则不会显示确认提示，且数据库清除将立即执行。</span><span class="sxs-lookup"><span data-stu-id="52520-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="52520-121">若要清除 QoE 数据库，请使用 Invoke-CsQoEDatabasePurge cmdlet 并指定要删除的记录的期限（以天为单位）：</span><span class="sxs-lookup"><span data-stu-id="52520-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

