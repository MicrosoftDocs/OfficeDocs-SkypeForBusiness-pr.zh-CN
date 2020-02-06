---
title: 配置和监控备份服务
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以使用 Skype for Business Server Management Shell 命令来配置和监视备份服务。
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818213"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="87c3f-103">在 Skype for Business 服务器中配置和监视备份服务</span><span class="sxs-lookup"><span data-stu-id="87c3f-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="87c3f-104">你可以使用以下 Skype for Business 服务器管理外壳命令来配置和监视备份服务。</span><span class="sxs-lookup"><span data-stu-id="87c3f-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="87c3f-105">若要还原存储在前端池的文件存储中的会议信息，请参阅下面[的使用备份服务还原会议内容](#restore-conference-contents-using-the-backup-service)。</span><span class="sxs-lookup"><span data-stu-id="87c3f-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="87c3f-106">RTCUniversalServerAdmins 组是唯一具有运行**CsBackupServiceStatus**默认权限的组。</span><span class="sxs-lookup"><span data-stu-id="87c3f-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="87c3f-107">若要使用此 cmdlet，请以该组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="87c3f-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="87c3f-108">或者，你可以使用**CsBackupServiceConfiguration** cmdlet 将对此命令的访问权限授予其他组（例如 CSAdministrator）。</span><span class="sxs-lookup"><span data-stu-id="87c3f-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="87c3f-109">查看备份服务配置</span><span class="sxs-lookup"><span data-stu-id="87c3f-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="87c3f-110">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87c3f-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="87c3f-111">SyncInterval 的默认值是2分钟。</span><span class="sxs-lookup"><span data-stu-id="87c3f-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="87c3f-112">设置备份服务同步间隔</span><span class="sxs-lookup"><span data-stu-id="87c3f-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="87c3f-113">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87c3f-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="87c3f-114">例如，下面的时间间隔设置为3分钟。</span><span class="sxs-lookup"><span data-stu-id="87c3f-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="87c3f-115">虽然你可以使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对必要，否则不应执行此操作，因为同步间隔对备份服务性能和恢复点目标（RPO）有很高的影响。</span><span class="sxs-lookup"><span data-stu-id="87c3f-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="87c3f-116">获取特定池的备份服务状态</span><span class="sxs-lookup"><span data-stu-id="87c3f-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="87c3f-117">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87c3f-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="87c3f-118">备份服务同步状态是从池（P1） unidirectionally 到其备份池（P2）定义的。</span><span class="sxs-lookup"><span data-stu-id="87c3f-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="87c3f-119">从 P1 到 P2 的同步状态可能与从 P2 到 P1 的同步状态不同。</span><span class="sxs-lookup"><span data-stu-id="87c3f-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="87c3f-120">对于 P2 到 P2，如果在 P1 中进行的所有更改都在同步间隔内完全复制到 P2，则备份服务处于 "稳定" 状态。</span><span class="sxs-lookup"><span data-stu-id="87c3f-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="87c3f-121">如果没有其他更改要从 P1 同步到 P2，它将处于 "最终状态" 状态。</span><span class="sxs-lookup"><span data-stu-id="87c3f-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="87c3f-122">这两种状态表示执行 cmdlet 时备份服务的快照。</span><span class="sxs-lookup"><span data-stu-id="87c3f-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="87c3f-123">这并不意味着返回的状态将保持为后的状态。</span><span class="sxs-lookup"><span data-stu-id="87c3f-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="87c3f-124">特别是，仅当在执行 cmdlet 后 P1 不会生成任何更改时，"最终" 状态才会继续保持。</span><span class="sxs-lookup"><span data-stu-id="87c3f-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="87c3f-125">在将 p1 置于只读模式（作为**CsPoolfailover**执行逻辑的一部分）之后，p1 被置于只读模式下时，此情况为 true。</span><span class="sxs-lookup"><span data-stu-id="87c3f-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="87c3f-126">获取有关特定池的备份关系的信息</span><span class="sxs-lookup"><span data-stu-id="87c3f-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="87c3f-127">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87c3f-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="87c3f-128">强制备份服务同步</span><span class="sxs-lookup"><span data-stu-id="87c3f-128">To force a Backup Service sync</span></span>

<span data-ttu-id="87c3f-129">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="87c3f-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="87c3f-130">使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="87c3f-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="87c3f-131">如果在前端池的文件存储中存储的会议信息不可用，则必须还原此信息，以便驻留在该池中的用户保留其会议数据。</span><span class="sxs-lookup"><span data-stu-id="87c3f-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="87c3f-132">如果已丢失会议数据的前端池与另一个前端池配对，则可以使用备份服务还原数据。</span><span class="sxs-lookup"><span data-stu-id="87c3f-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="87c3f-133">如果整个池出现故障，并且你必须将其用户故障转移到备份池，还必须执行此任务。</span><span class="sxs-lookup"><span data-stu-id="87c3f-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="87c3f-134">当这些用户故障恢复到其原始池时，必须使用此过程将其会议内容复制回其原始池。</span><span class="sxs-lookup"><span data-stu-id="87c3f-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="87c3f-135">假设 Pool1 与 Pool2 配对，并且 Pool1 中的会议数据丢失。</span><span class="sxs-lookup"><span data-stu-id="87c3f-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="87c3f-136">你可以使用以下 cmdlet 调用备份服务来还原内容：</span><span class="sxs-lookup"><span data-stu-id="87c3f-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="87c3f-137">还原会议内容可能需要一些时间，具体取决于它们的大小。</span><span class="sxs-lookup"><span data-stu-id="87c3f-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="87c3f-138">你可以使用以下 cmdlet 检查进程状态：</span><span class="sxs-lookup"><span data-stu-id="87c3f-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="87c3f-139">当此 cmdlet 为数据会议模块返回稳定状态的值时，将执行此过程。</span><span class="sxs-lookup"><span data-stu-id="87c3f-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
