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
ms.openlocfilehash: 65fbbf4db9e15eac2d29fcde6bd126355c794a95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="8dbc2-102">在 Lync Server 2013 中配置和监控备份服务</span><span class="sxs-lookup"><span data-stu-id="8dbc2-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dbc2-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8dbc2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8dbc2-104">您可以使用以下 Lync Server 命令行管理程序命令来配置和监控备份服务。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dbc2-105">默认情况下，RTCUniversalServerAdmins 组是唯一具有运行 <STRONG>Get-CsBackupServiceStatus</STRONG> 的权限的组。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="8dbc2-106">要使用此 cmdlet，请以该组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="8dbc2-107">或者，可通过使用 <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet 向其他组（如 CSAdministrator）授予对此命令的访问权。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="8dbc2-108">查看备份服务配置</span><span class="sxs-lookup"><span data-stu-id="8dbc2-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="8dbc2-109">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8dbc2-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="8dbc2-110">SyncInterval 的默认值为 2 分钟。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="8dbc2-111">设置备份服务同步间隔</span><span class="sxs-lookup"><span data-stu-id="8dbc2-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="8dbc2-112">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8dbc2-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="8dbc2-113">例如，下面将此间隔设置为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8dbc2-114">尽管可使用此 cmdlet 更改备份服务的默认同步间隔，但除非绝对有必要，否则您不应这样做，因为同步间隔对备份服务的性能和恢复点目标 (RPO) 有很大的影响。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="8dbc2-115">获取特殊池的备份服务状态</span><span class="sxs-lookup"><span data-stu-id="8dbc2-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="8dbc2-116">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8dbc2-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="8dbc2-117">备份服务的同步状态是从一个池 (P1) 到其备份池 (P2) 进行单向定义的。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="8dbc2-118">从 P1 到 P2 的同步状态与从 P2 到 P1 的同步状态不同。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="8dbc2-119">对于 P1 到 P2，如果在同步间隔内将 P1 中所做的所有更改完全复制到 P2，则备份服务将处于“稳定”状态。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="8dbc2-120">如果不再将更改从 P1 同步到 P2，则备份服务处于“最终”状态。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="8dbc2-121">这两个状态均指示执行 cmdlet 时备份服务的快照。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="8dbc2-122">它不表示返回的状态之后将继续保持下去。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="8dbc2-123">特别是，仅在执行 cmdlet 后 P1 未生成任何更改的情况下，才一直保持“最终”状态。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="8dbc2-124">当作为 <STRONG>Invoke-CsPoolfailover</STRONG> 执行逻辑的一部分将 P1 置于只读模式后，P1 到 P2 的同步失败时才会出现此种情况。</span><span class="sxs-lookup"><span data-stu-id="8dbc2-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="8dbc2-125">获取有关特定池的备份关系的信息</span><span class="sxs-lookup"><span data-stu-id="8dbc2-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="8dbc2-126">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8dbc2-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="8dbc2-127">强制备份服务同步</span><span class="sxs-lookup"><span data-stu-id="8dbc2-127">To force a Backup Service sync</span></span>

<span data-ttu-id="8dbc2-128">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8dbc2-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

