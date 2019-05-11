---
title: 配置和监控备份服务
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务 Server 命令行管理程序命令可用于配置和监控备份服务。
ms.openlocfilehash: aa6a1aca7e753877c15f64c3736a09ad9e2ca066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903149"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="8cb35-103">配置和监控业务服务器中 Skype 的备份服务</span><span class="sxs-lookup"><span data-stu-id="8cb35-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="8cb35-104">以下 Skype 业务 Server 命令行管理程序命令可用于配置和监控备份服务。</span><span class="sxs-lookup"><span data-stu-id="8cb35-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="8cb35-105">若要还原存储在前端池的文件存储中的会议信息，请参阅下面的[还原备份服务使用的会议内容](#restore-conference-contents-using-the-backup-service)，。</span><span class="sxs-lookup"><span data-stu-id="8cb35-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="8cb35-106">以 RTCUniversalServerAdmins 组是唯一具有默认情况下运行**Get-csbackupservicestatus**权限的组。</span><span class="sxs-lookup"><span data-stu-id="8cb35-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="8cb35-107">若要使用此 cmdlet，此组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="8cb35-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="8cb35-108">或者，您可以使用**Set-csbackupserviceconfiguration** cmdlet 授予到其他组 (例如，CSAdministrator) 访问此命令。</span><span class="sxs-lookup"><span data-stu-id="8cb35-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="8cb35-109">若要查看的备份服务配置</span><span class="sxs-lookup"><span data-stu-id="8cb35-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="8cb35-110">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb35-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="8cb35-111">SyncInterval 的默认值为两分钟。</span><span class="sxs-lookup"><span data-stu-id="8cb35-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="8cb35-112">若要设置的备份服务同步间隔</span><span class="sxs-lookup"><span data-stu-id="8cb35-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="8cb35-113">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb35-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="8cb35-114">例如，以下为 3 分钟设置的间隔。</span><span class="sxs-lookup"><span data-stu-id="8cb35-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="8cb35-115">尽管可以使用此 cmdlet 的备份服务更改默认同步时间间隔，不应执行以便除非绝对需要时，为同步间隔具有对备份服务性能和恢复点目标 (RPO) 很大的影响。</span><span class="sxs-lookup"><span data-stu-id="8cb35-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="8cb35-116">若要获取特定池的备份服务状态</span><span class="sxs-lookup"><span data-stu-id="8cb35-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="8cb35-117">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb35-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="8cb35-118">备份服务同步状态定义通信量从一个池 (P1) 到其备份池 (P2)。</span><span class="sxs-lookup"><span data-stu-id="8cb35-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="8cb35-119">从 P1 P2 到同步状态可以是不同于 p1 从 P2。</span><span class="sxs-lookup"><span data-stu-id="8cb35-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="8cb35-120">对于 P1 到 P2，备份服务位于"稳定"状态如果所有 P1 中所做的更改会完全都复制转移到 P2 内的同步间隔。</span><span class="sxs-lookup"><span data-stu-id="8cb35-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="8cb35-121">位于"最终"状态如果要从 P1 同步到 P2 没有更多更改。</span><span class="sxs-lookup"><span data-stu-id="8cb35-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="8cb35-122">两种状态指示在 cmdlet 执行的时间的备份服务的快照。</span><span class="sxs-lookup"><span data-stu-id="8cb35-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="8cb35-123">并不表示，按原样以后将保持返回的状态。</span><span class="sxs-lookup"><span data-stu-id="8cb35-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="8cb35-124">具体而言，将继续如果 P1 不会生成任何更改之后执行此 cmdlet 仅保留"最终"状态。</span><span class="sxs-lookup"><span data-stu-id="8cb35-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="8cb35-125">这是对于故障 P1 转移到 P2 之后 P1 **Invoke-cspoolfailover**执行逻辑的一部分置于只读模式,，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="8cb35-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="8cb35-126">若要获取特定池的备份关系的信息</span><span class="sxs-lookup"><span data-stu-id="8cb35-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="8cb35-127">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb35-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="8cb35-128">若要强制备份服务同步</span><span class="sxs-lookup"><span data-stu-id="8cb35-128">To force a Backup Service sync</span></span>

<span data-ttu-id="8cb35-129">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8cb35-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="8cb35-130">还原使用备份服务的会议内容</span><span class="sxs-lookup"><span data-stu-id="8cb35-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="8cb35-131">如果在前端池的文件存储中存储的会议信息变得不可用，以便在池上驻留的用户，您必须还原此信息保留其会议数据。</span><span class="sxs-lookup"><span data-stu-id="8cb35-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="8cb35-132">如果与另一个前端池配对中断会议数据的前端池时，您可以使用备份服务还原数据。</span><span class="sxs-lookup"><span data-stu-id="8cb35-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="8cb35-133">如果整个池已失败，并且您需要进行故障转移到备份池其用户，则还必须执行此任务。</span><span class="sxs-lookup"><span data-stu-id="8cb35-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="8cb35-134">当这些用户都到其原始池将故障转移后时，您必须使用此过程将其会议内容复制到其原始的池。</span><span class="sxs-lookup"><span data-stu-id="8cb35-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="8cb35-135">假定 Pool1 配备 Pool2，并在 Pool1 会议数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="8cb35-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="8cb35-136">可以使用以下 cmdlet 以调用备份服务，要恢复的内容：</span><span class="sxs-lookup"><span data-stu-id="8cb35-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="8cb35-137">还原会议内容可能需要一些时间，具体取决于其大小。</span><span class="sxs-lookup"><span data-stu-id="8cb35-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="8cb35-138">您可以使用以下 cmdlet 检查进程状态：</span><span class="sxs-lookup"><span data-stu-id="8cb35-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="8cb35-139">此 cmdlet 返回的数据会议模块的稳定状态的值时，此过程已完成。</span><span class="sxs-lookup"><span data-stu-id="8cb35-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
