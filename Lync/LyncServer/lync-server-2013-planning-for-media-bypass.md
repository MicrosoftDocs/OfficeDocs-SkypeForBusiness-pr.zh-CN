---
title: Lync Server 2013：规划媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0471e-102">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="0471e-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0471e-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0471e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0471e-104">媒体绕过指信号遍历中介服务器的呼叫可以从媒体路径中删除中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0471e-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="0471e-105">媒体旁路功能可通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高语音质量。</span><span class="sxs-lookup"><span data-stu-id="0471e-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="0471e-106">可伸缩性得到改进，因为消除绕过通话的媒体处理会减少中介服务器上的负载。</span><span class="sxs-lookup"><span data-stu-id="0471e-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="0471e-107">负载的减少使中介服务器控制多个网关的能力有所补充。</span><span class="sxs-lookup"><span data-stu-id="0471e-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="0471e-108">如果没有中介服务器的分支站点通过受限制带宽的一个或多个 WAN 链接连接到中心站点，则媒体绕过会允许来自分支站点的客户端的媒体直接流向本地网关，而不首先必须跨 WAN 链接流过中央站点的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0471e-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="0471e-109">通过从媒体处理中免除中介服务器，媒体绕过可能还会减少企业语音基础结构所需的中介服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="0471e-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="0471e-110">下图显示了具有和没有媒体旁路功能的拓扑中的基本媒体和信号路径。</span><span class="sxs-lookup"><span data-stu-id="0471e-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="0471e-111">**具有和没有媒体旁路功能的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="0471e-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="0471e-112">![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")</span><span class="sxs-lookup"><span data-stu-id="0471e-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="0471e-113">一般而言，应尽可能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="0471e-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0471e-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="0471e-114">In This Section</span></span>

  - [<span data-ttu-id="0471e-115">Lync Server 2013 中绕过媒体的概述</span><span class="sxs-lookup"><span data-stu-id="0471e-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="0471e-116">Lync Server 2013 中的媒体绕过模式</span><span class="sxs-lookup"><span data-stu-id="0471e-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="0471e-117">Lync Server 2013 中的媒体绕过和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="0471e-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="0471e-118">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="0471e-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0471e-119">相关部分</span><span class="sxs-lookup"><span data-stu-id="0471e-119">Related Sections</span></span>

[<span data-ttu-id="0471e-120">在 Lync Server 2013 中部署高级企业语音功能</span><span class="sxs-lookup"><span data-stu-id="0471e-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0471e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0471e-121">See Also</span></span>


[<span data-ttu-id="0471e-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0471e-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="0471e-123">Lync Server 2013 中的全局媒体绕过选项</span><span class="sxs-lookup"><span data-stu-id="0471e-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

