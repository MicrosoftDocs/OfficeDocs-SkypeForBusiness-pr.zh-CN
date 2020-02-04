---
title: Lync Server 2013：配置和监控备份服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="4794e-102">在 Lync Server 2013 中配置和监控备份服务</span><span class="sxs-lookup"><span data-stu-id="4794e-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4794e-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4794e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4794e-104">你可以使用以下 Lync Server Management Shell 命令来配置和监视备份服务。</span><span class="sxs-lookup"><span data-stu-id="4794e-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4794e-105">RTCUniversalServerAdmins 组是唯一具有运行<STRONG>CsBackupServiceStatus</STRONG>默认权限的组。</span><span class="sxs-lookup"><span data-stu-id="4794e-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="4794e-106">若要使用此 cmdlet，请以该组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="4794e-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="4794e-107">或者，你可以使用<STRONG>CsBackupServiceConfiguration</STRONG> cmdlet 将对此命令的访问权限授予其他组（例如 CSAdministrator）。</span><span class="sxs-lookup"><span data-stu-id="4794e-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="4794e-108">查看备份服务配置</span><span class="sxs-lookup"><span data-stu-id="4794e-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="4794e-109">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4794e-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="4794e-110">SyncInterval 的默认值是2分钟。</span><span class="sxs-lookup"><span data-stu-id="4794e-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="4794e-111">设置备份服务同步间隔</span><span class="sxs-lookup"><span data-stu-id="4794e-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="4794e-112">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4794e-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="4794e-113">例如，下面的时间间隔设置为3分钟。</span><span class="sxs-lookup"><span data-stu-id="4794e-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4794e-114">虽然你可以使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对必要，否则不应执行此操作，因为同步间隔对备份服务性能和恢复点目标（RPO）有很高的影响。</span><span class="sxs-lookup"><span data-stu-id="4794e-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="4794e-115">获取特定池的备份服务状态</span><span class="sxs-lookup"><span data-stu-id="4794e-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="4794e-116">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4794e-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="4794e-117">备份服务同步状态是从池（P1） unidirectionally 到其备份池（P2）定义的。</span><span class="sxs-lookup"><span data-stu-id="4794e-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="4794e-118">从 P1 到 P2 的同步状态可能与从 P2 到 P1 的同步状态不同。</span><span class="sxs-lookup"><span data-stu-id="4794e-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="4794e-119">对于 P2 到 P2，如果在 P1 中进行的所有更改都在同步间隔内完全复制到 P2，则备份服务处于 "稳定" 状态。</span><span class="sxs-lookup"><span data-stu-id="4794e-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="4794e-120">如果没有其他更改要从 P1 同步到 P2，它将处于 "最终状态" 状态。</span><span class="sxs-lookup"><span data-stu-id="4794e-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="4794e-121">这两种状态表示执行 cmdlet 时备份服务的快照。</span><span class="sxs-lookup"><span data-stu-id="4794e-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="4794e-122">这并不意味着返回的状态将保持为后的状态。</span><span class="sxs-lookup"><span data-stu-id="4794e-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="4794e-123">特别是，仅当在执行 cmdlet 后 P1 不会生成任何更改时，"最终" 状态才会继续保持。</span><span class="sxs-lookup"><span data-stu-id="4794e-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="4794e-124">在将 p1 置于只读模式（作为<STRONG>CsPoolfailover</STRONG>执行逻辑的一部分）之后，p1 被置于只读模式下时，此情况为 true。</span><span class="sxs-lookup"><span data-stu-id="4794e-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="4794e-125">获取有关特定池的备份关系的信息</span><span class="sxs-lookup"><span data-stu-id="4794e-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="4794e-126">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4794e-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="4794e-127">强制备份服务同步</span><span class="sxs-lookup"><span data-stu-id="4794e-127">To force a Backup Service sync</span></span>

<span data-ttu-id="4794e-128">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4794e-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

