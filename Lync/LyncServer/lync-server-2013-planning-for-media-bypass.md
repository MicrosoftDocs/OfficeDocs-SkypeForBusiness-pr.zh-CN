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
ms.openlocfilehash: 659333b98aed7e21ca806a93969a3b9f8bbe3e9e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9ab97-102">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="9ab97-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ab97-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9ab97-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9ab97-104">媒体旁路功能是指在可能的情况下，从信号遍历中介服务器的呼叫的媒体路径中删除中介服务器。</span><span class="sxs-lookup"><span data-stu-id="9ab97-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="9ab97-105">媒体旁路功能可通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高语音质量。</span><span class="sxs-lookup"><span data-stu-id="9ab97-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="9ab97-106">由于绕过的呼叫无需媒体处理操作，这可减少中介服务器上的负载，从而提高可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="9ab97-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="9ab97-107">这种负载降低补充了中介服务器控制多个网关的能力。</span><span class="sxs-lookup"><span data-stu-id="9ab97-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="9ab97-108">如果没有中介服务器的分支站点通过受限制带宽的一个或多个 WAN 链路连接到中央站点，则媒体旁路降低了带宽需求，因为允许来自分支站点的客户端的媒体直接流向本地网关，而不首先必须跨 WAN 链路传递到位于中央站点的中介服务器和背面。</span><span class="sxs-lookup"><span data-stu-id="9ab97-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="9ab97-109">通过从媒体处理中免除中介服务器，媒体旁路也可能会减少企业语音基础结构所需的中介服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="9ab97-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="9ab97-110">下图显示了具有和没有媒体旁路功能的拓扑中的基本媒体和信号路径。</span><span class="sxs-lookup"><span data-stu-id="9ab97-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="9ab97-111">**具有和没有媒体旁路功能的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="9ab97-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="9ab97-112">![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")</span><span class="sxs-lookup"><span data-stu-id="9ab97-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="9ab97-113">一般而言，应尽可能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="9ab97-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9ab97-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="9ab97-114">In This Section</span></span>

  - [<span data-ttu-id="9ab97-115">Lync Server 2013 中的媒体旁路概述</span><span class="sxs-lookup"><span data-stu-id="9ab97-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="9ab97-116">Lync Server 2013 中的媒体旁路模式</span><span class="sxs-lookup"><span data-stu-id="9ab97-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="9ab97-117">Lync Server 2013 中的媒体旁路和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="9ab97-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="9ab97-118">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="9ab97-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9ab97-119">相关部分</span><span class="sxs-lookup"><span data-stu-id="9ab97-119">Related Sections</span></span>

[<span data-ttu-id="9ab97-120">在 Lync Server 2013 中部署高级企业语音功能</span><span class="sxs-lookup"><span data-stu-id="9ab97-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ab97-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ab97-121">See Also</span></span>


[<span data-ttu-id="9ab97-122">在 Lync Server 2013 中配置具有媒体旁路功能的中继</span><span class="sxs-lookup"><span data-stu-id="9ab97-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="9ab97-123">Lync Server 2013 中的全局媒体旁路选项</span><span class="sxs-lookup"><span data-stu-id="9ab97-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

