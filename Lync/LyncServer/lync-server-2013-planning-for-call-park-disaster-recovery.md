---
title: Lync Server 2013：规划呼叫寄存灾难恢复
description: Lync Server 2013：规划呼叫寄存灾难恢复。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554278"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="005f4-103">在 Lync Server 2013 中规划呼叫寄存灾难恢复</span><span class="sxs-lookup"><span data-stu-id="005f4-103">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="005f4-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="005f4-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="005f4-105">本节介绍一些为灾难恢复准备呼叫寄存应用程序以及灾难恢复过程的一些注意事项的方法。</span><span class="sxs-lookup"><span data-stu-id="005f4-105">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="005f4-106">为呼叫寄存灾难恢复做准备</span><span class="sxs-lookup"><span data-stu-id="005f4-106">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="005f4-107">准备和执行灾难恢复过程时牢记以下事项。</span><span class="sxs-lookup"><span data-stu-id="005f4-107">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="005f4-108">执行容量规划时，规划灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="005f4-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="005f4-109">对于灾难恢复容量，配对池中的每个池都应能够处理两个池中的呼叫寄存服务的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="005f4-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="005f4-110">有关呼叫寄存容量规划的详细信息，请参阅 [Lync Server 2013 中的呼叫寄存的容量规划](lync-server-2013-capacity-planning-for-call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="005f4-110">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="005f4-111">灾难恢复期间，作为故障转移过程之一重定向至备份池的用户将使用在备份池中运行的呼叫寄存服务。</span><span class="sxs-lookup"><span data-stu-id="005f4-111">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="005f4-112">因此，在灾难恢复过程中对呼叫寄存的支持要求在主池和备份池中部署和启用呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="005f4-112">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="005f4-113">每个池针对驻留在该池中的用户数必须具有有效范围的用于寄存呼叫的通道号。</span><span class="sxs-lookup"><span data-stu-id="005f4-113">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="005f4-114">始终保留已为呼叫寄存上载的任何自定义音乐保留的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="005f4-114">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="005f4-115">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，则这些文件将丢失。</span><span class="sxs-lookup"><span data-stu-id="005f4-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="005f4-116">呼叫寄存灾难恢复注意事项</span><span class="sxs-lookup"><span data-stu-id="005f4-116">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="005f4-117">您可以为每个池仅定义一组呼叫寄存应用程序配置设置和一个自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="005f4-117">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="005f4-118">这些设置包括超时阈值、保持音乐、最大呼叫应答尝试数和超时 URI。</span><span class="sxs-lookup"><span data-stu-id="005f4-118">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="005f4-119">要查看这些配置设置，请运行 **Get-CsCpsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005f4-119">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="005f4-120">有关 **CsCpsConfiguration** cmdlet 的详细信息，请参阅 [CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="005f4-120">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="005f4-121">在灾难恢复过程中，呼叫寄存将使用备份池中的呼叫寄存应用程序，因此不会备份主池中的设置。</span><span class="sxs-lookup"><span data-stu-id="005f4-121">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="005f4-122">如果无法恢复主池并部署新池以替换主池，则将丢失主池的设置，并且需要在新池中重新配置呼叫寄存设置和任何自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="005f4-122">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="005f4-123">如果使用其他完全限定的域名部署新池 (FQDN) 替换主池，则需要将与主池关联的所有呼叫寄存轨道范围重新分配给新池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="005f4-123">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="005f4-124">若要将轨道范围重新分配给新池，可以使用 Lync Server 控制面板或 **CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="005f4-124">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="005f4-125">有关 **CsCallParkOrbit** cmdlet 的详细信息，请参阅 [CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="005f4-125">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

