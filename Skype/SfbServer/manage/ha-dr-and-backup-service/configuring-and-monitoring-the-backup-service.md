---
title: 配置和监控备份服务
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 可以使用 Skype for Business Server 命令行管理程序命令配置和监视备份服务。
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817192"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="3c7b4-103">在 Skype for Business Server 中配置和监视备份服务</span><span class="sxs-lookup"><span data-stu-id="3c7b4-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="3c7b4-104">可以使用以下 Skype for Business Server 命令行管理程序命令配置和监视备份服务。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="3c7b4-105">若要还原存储在前端池的文件存储中的会议信息，请参阅下面的"使用备份服务[](#restore-conference-contents-using-the-backup-service)还原会议内容"。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="3c7b4-106">默认情况下，RTCUniversalServerAdmins 组是唯一具有运行 **Get-CsBackupServiceStatus** 的权限的组。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="3c7b4-107">要使用此 cmdlet，请以该组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="3c7b4-108">或者，可通过使用 **Set-CsBackupServiceConfiguration** cmdlet 向其他组（如 CSAdministrator）授予对此命令的访问权。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="3c7b4-109">查看备份服务配置</span><span class="sxs-lookup"><span data-stu-id="3c7b4-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="3c7b4-110">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="3c7b4-111">SyncInterval 的默认值为 2 分钟。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="3c7b4-112">设置备份服务同步间隔</span><span class="sxs-lookup"><span data-stu-id="3c7b4-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="3c7b4-113">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="3c7b4-114">例如，下面将此间隔设置为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="3c7b4-115">尽管可使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对有必要，否则您不应这样做，因为同步间隔对备份服务的性能和恢复点目标 (RPO) 有很大的影响。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="3c7b4-116">获取特殊池的备份服务状态</span><span class="sxs-lookup"><span data-stu-id="3c7b4-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="3c7b4-117">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="3c7b4-118">备份服务的同步状态是从一个池 (P1) 到其备份池 (P2) 进行单向定义的。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="3c7b4-119">从 P1 到 P2 的同步状态与从 P2 到 P1 的同步状态不同。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="3c7b4-120">对于 P1 到 P2，如果在同步间隔内将 P1 中所做的所有更改完全复制到 P2，则备份服务将处于“稳定”状态。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="3c7b4-121">如果不再将更改从 P1 同步到 P2，则备份服务处于“最终”状态。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="3c7b4-122">这两个状态均指示执行 cmdlet 时备份服务的快照。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="3c7b4-123">它不表示返回的状态之后将继续保持下去。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="3c7b4-124">特别是，仅在执行 cmdlet 后 P1 未生成任何更改的情况下，才一直保持“最终”状态。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="3c7b4-125">当作为 **Invoke-CsPoolfailover** 执行逻辑的一部分将 P1 置于只读模式后，P1 到 P2 的同步失败时才会出现此种情况。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="3c7b4-126">获取有关特定池的备份关系的信息</span><span class="sxs-lookup"><span data-stu-id="3c7b4-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="3c7b4-127">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="3c7b4-128">强制备份服务同步</span><span class="sxs-lookup"><span data-stu-id="3c7b4-128">To force a Backup Service sync</span></span>

<span data-ttu-id="3c7b4-129">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="3c7b4-130">使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="3c7b4-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="3c7b4-131">如果存储在前端池的文件存储中的会议信息变得不可用，则必须还原此信息，以便池中的用户保留其会议数据。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="3c7b4-132">如果丢失会议数据的前端池与另一个前端池配对，您可以使用备份服务还原数据。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="3c7b4-p105">此外，如果整个池已失败并且您必须将其用户故障转移到备份池，则也必须执行此任务。在将这些用户故障转移回其原始池时，您也必须使用此过程将其会议内容复制回其原始池。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="3c7b4-135">假定将 Pool1 与 Pool2 配对且 Pool1 中的会议数据已丢失。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="3c7b4-136">可以使用以下 cmdlet 调用备份服务来还原内容：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="3c7b4-p107">还原会议内容可能需要一些时间，具体取决于该内容的大小。您可以使用以下 cmdlet 检查过程状态：</span><span class="sxs-lookup"><span data-stu-id="3c7b4-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="3c7b4-139">当此 cmdlet 为数据会议模块返回值“稳定状态”时，表示此过程已完成。</span><span class="sxs-lookup"><span data-stu-id="3c7b4-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
