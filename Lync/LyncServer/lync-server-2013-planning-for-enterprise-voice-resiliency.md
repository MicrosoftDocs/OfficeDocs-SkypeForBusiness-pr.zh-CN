---
title: Lync Server 2013：规划企业语音恢复能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66bba2fe6f53198fcc1e1fc423423e02d46ac8b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="16265-102">在 Lync Server 2013 中规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="16265-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16265-103">_**主题上次修改时间:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="16265-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="16265-104">语音弹性指当托管 Lync Server 2013 的中心网站不可用时, 用户可以继续进行呼叫和接收呼叫的能力, 无论是通过广域网 (WAN) 故障还是其他原因。</span><span class="sxs-lookup"><span data-stu-id="16265-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="16265-105">如果中央站点发生故障，企业语音服务必须通过无缝故障转移至备份站点以保持不中断。</span><span class="sxs-lookup"><span data-stu-id="16265-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="16265-106">如果发生 WAN 故障，分支站点的呼叫必须重定向到本地 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="16265-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="16265-107">本节讨论了如何规划在中央站点或 WAN 发生故障时的语音恢复能力。</span><span class="sxs-lookup"><span data-stu-id="16265-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16265-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="16265-108">In This Section</span></span>

  - [<span data-ttu-id="16265-109">在 Lync Server 2013 中规划中央站点语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="16265-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="16265-110">在 Lync Server 2013 中规划分支站点语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="16265-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

