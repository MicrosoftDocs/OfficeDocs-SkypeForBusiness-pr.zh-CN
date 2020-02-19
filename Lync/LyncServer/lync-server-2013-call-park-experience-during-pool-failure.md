---
title: Lync Server 2013：池故障期间的呼叫寄存体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61913ba4ccee86047bbed4d6454988d37081f5a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="a10a6-102">池故障期间 Lync Server 2013 中的呼叫寄存体验</span><span class="sxs-lookup"><span data-stu-id="a10a6-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a10a6-103">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="a10a6-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="a10a6-104">当前端池因计划外事件而不可用时，将断开已暂停但尚未检索的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="a10a6-105">在至备份池的故障转移期间，用户将重定向至备份池，并将处于恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="a10a6-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="a10a6-106">在恢复能力模式下，用户无法寄存呼叫，但可保持呼叫并转接呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="a10a6-107">故障转移完成后，可再次正常寄存并取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="a10a6-108">在故障回复期间，用户在脱离恢复能力模式之前，无法寄存呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="a10a6-109">在灾难恢复过程中，作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中部署的呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="a10a6-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="a10a6-110">因此，重定向到备份池的用户将使用为备份池中的呼叫寄存应用程序配置的呼叫寄存设置。</span><span class="sxs-lookup"><span data-stu-id="a10a6-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="a10a6-111">下表总结了灾难恢复阶段的呼叫寄存体验。</span><span class="sxs-lookup"><span data-stu-id="a10a6-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="a10a6-112">灾难恢复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="a10a6-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a10a6-113">呼叫状态</span><span class="sxs-lookup"><span data-stu-id="a10a6-113">Call state</span></span></th>
<th><span data-ttu-id="a10a6-114">中断出现时间</span><span class="sxs-lookup"><span data-stu-id="a10a6-114">When outage occurs</span></span></th>
<th><span data-ttu-id="a10a6-115">故障转移期间</span><span class="sxs-lookup"><span data-stu-id="a10a6-115">During failover</span></span></th>
<th><span data-ttu-id="a10a6-116">故障回复期间</span><span class="sxs-lookup"><span data-stu-id="a10a6-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a10a6-117">尚未寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="a10a6-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="a10a6-118">呼叫仍处于连接状态，但无法寄存。</span><span class="sxs-lookup"><span data-stu-id="a10a6-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a10a6-119">故障转移期间，用户处于恢复能力模式，无法寄存呼叫，但可保持呼叫并进行转接。</span><span class="sxs-lookup"><span data-stu-id="a10a6-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="a10a6-120">故障转移完成后，可寄存并取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="a10a6-121">故障回复期间，用户处于恢复能力模式，无法寄存呼叫，但可保持呼叫并进行转接。</span><span class="sxs-lookup"><span data-stu-id="a10a6-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="a10a6-122">故障回复完成后，可寄存并取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a10a6-123">呼叫已寄存，但尚未取回</span><span class="sxs-lookup"><span data-stu-id="a10a6-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="a10a6-124">将断开呼叫。</span><span class="sxs-lookup"><span data-stu-id="a10a6-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="a10a6-125">无呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="a10a6-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="a10a6-126">呼叫仍处于寄存状态。</span><span class="sxs-lookup"><span data-stu-id="a10a6-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a10a6-127">已取回的寄存呼叫</span><span class="sxs-lookup"><span data-stu-id="a10a6-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="a10a6-128">呼叫仍处于连接状态。</span><span class="sxs-lookup"><span data-stu-id="a10a6-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="a10a6-129">呼叫仍处于连接状态。</span><span class="sxs-lookup"><span data-stu-id="a10a6-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="a10a6-130">呼叫仍处于连接状态。</span><span class="sxs-lookup"><span data-stu-id="a10a6-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

