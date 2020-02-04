---
title: Lync Server 2013：规划呼叫寄存灾难恢复
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
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="762d1-102">在 Lync Server 2013 中规划呼叫寄存灾难恢复</span><span class="sxs-lookup"><span data-stu-id="762d1-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="762d1-103">_**主题上次修改时间：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="762d1-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="762d1-104">本部分介绍了一些方法，用于准备用于灾难恢复的呼叫寄存应用程序以及灾难恢复过程的一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="762d1-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="762d1-105">准备呼叫寄存灾难恢复</span><span class="sxs-lookup"><span data-stu-id="762d1-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="762d1-106">在准备和执行灾难恢复过程时，请牢记以下事项。</span><span class="sxs-lookup"><span data-stu-id="762d1-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="762d1-107">在执行容量规划时规划灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="762d1-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="762d1-108">对于灾难恢复容量，配对池中的每个池都应该能够处理两个池中的呼叫寄存服务的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="762d1-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="762d1-109">有关呼叫寄存容量规划的详细信息，请参阅[Lync Server 2013 中的呼叫寄存的容量规划](lync-server-2013-capacity-planning-for-call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="762d1-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="762d1-110">在灾难恢复期间，已被重定向到备份池的用户将使用在备份池中运行的呼叫驻留服务。</span><span class="sxs-lookup"><span data-stu-id="762d1-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="762d1-111">因此，在灾难恢复期间对呼叫寄存的支持需要在主池和备份池中部署和启用呼叫驻留应用程序。</span><span class="sxs-lookup"><span data-stu-id="762d1-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="762d1-112">对于驻留在该池中的用户，每个池必须具有有效的轨道编号范围，以便用于停车通话。</span><span class="sxs-lookup"><span data-stu-id="762d1-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="762d1-113">始终保留已为呼叫寄存上载的任何自定义音乐的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="762d1-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="762d1-114">这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到该池的文件已损坏、损坏或删除，将丢失这些文件。</span><span class="sxs-lookup"><span data-stu-id="762d1-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="762d1-115">呼叫寄存灾难恢复注意事项</span><span class="sxs-lookup"><span data-stu-id="762d1-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="762d1-116">每个池中只能定义一组通话寄存应用程序配置设置和一个自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="762d1-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="762d1-117">这些设置包括超时阈值、暂停的音乐、最大的呼叫装货尝试和超时 URI。</span><span class="sxs-lookup"><span data-stu-id="762d1-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="762d1-118">若要查看这些配置设置，请运行**CsCpsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="762d1-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="762d1-119">有关**CsCpsConfiguration** cmdlet 的详细信息，请参阅[CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="762d1-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="762d1-120">在灾难恢复期间，呼叫寄存使用备份池中的 "呼叫驻留" 应用程序，因此不会备份主池中的设置。</span><span class="sxs-lookup"><span data-stu-id="762d1-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="762d1-121">如果无法恢复主池，并且你部署新池以替换主池，则会丢失主池中的设置，你需要在新池中重新配置呼叫寄存设置和任何自定义的音乐保留音频文件。</span><span class="sxs-lookup"><span data-stu-id="762d1-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="762d1-122">如果你部署具有不同完全限定的域名（FQDN）的新池来替换主池，你需要将与主池相关联的所有呼叫寄存轨道范围重新分配给新池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="762d1-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="762d1-123">若要将轨道范围重新分配给新池，你可以使用 Lync Server 控制面板或**CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="762d1-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="762d1-124">有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="762d1-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

