---
title: Lync Server 2013：定义企业语音要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a222a-102">在 Lync Server 2013 中定义企业语音要求</span><span class="sxs-lookup"><span data-stu-id="a222a-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a222a-103">_**主题上次修改时间：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="a222a-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="a222a-104">本主题概述了在你的拓扑中对网站之间的区域、网站和链接以及这些内容在你部署企业语音时的重要因素。</span><span class="sxs-lookup"><span data-stu-id="a222a-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a222a-105">有关有助于做出这些决策的详细信息，请参阅规划文档中[Lync Server 2013 中的高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)。</span><span class="sxs-lookup"><span data-stu-id="a222a-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="a222a-106">网站和区域</span><span class="sxs-lookup"><span data-stu-id="a222a-106">Sites and Regions</span></span>

<span data-ttu-id="a222a-107">首先，确定你的拓扑中的网站，你将在这些网站中部署企业语音和这些网站所属的网络区域。</span><span class="sxs-lookup"><span data-stu-id="a222a-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="a222a-108">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="a222a-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="a222a-109">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="a222a-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="a222a-110">确定本地部署网关的位置（将部署 Survivable 分支装置（SBAs）），以及你可以在哪里将 SIP 中继（本地或中央网站）配置为 Internet 电话服务提供商（ITSP）。</span><span class="sxs-lookup"><span data-stu-id="a222a-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="a222a-111">网站之间的网络链接</span><span class="sxs-lookup"><span data-stu-id="a222a-111">Network Links Between Sites</span></span>

<span data-ttu-id="a222a-112">您还需要考虑您的中心站点与其分支站点之间网络链接所期望的带宽使用情况。</span><span class="sxs-lookup"><span data-stu-id="a222a-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="a222a-113">如果你拥有或计划在网站之间部署弹性 WAN 链接，我们建议你在每个分支站点上部署网关，以便为用户在这些网站上提供本地直接向内拨号（已）终止。</span><span class="sxs-lookup"><span data-stu-id="a222a-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="a222a-114">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="a222a-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="a222a-115">如果您没有弹性 WAN 链接，在您的分支站点上托管的用户少于1000个用户，并且没有本地训练有素的 Lync 服务器管理员可用，我们建议您在分支站点部署 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="a222a-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="a222a-116">如果你在分支站点上的1000和5000用户之间托管，缺少弹性 WAN 连接，并且有经过培训的 Lync 服务器管理员可用，我们建议你在分支站点上使用小型网关部署 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="a222a-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="a222a-117">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="a222a-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a222a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a222a-118">See Also</span></span>


[<span data-ttu-id="a222a-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a222a-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

