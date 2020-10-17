---
title: Lync Server 2013：定义企业语音要求
description: Lync Server 2013：定义企业语音的要求。
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
ms.openlocfilehash: 77547262816f0ad29ae905ff22974d8f48c21b95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545388"
---
# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="03357-103">在 Lync Server 2013 中定义对企业语音的要求</span><span class="sxs-lookup"><span data-stu-id="03357-103">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03357-104">_**上次修改的主题：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="03357-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="03357-105">本主题概述了您需要对拓扑中的区域、网站和链接之间的注意事项以及在部署企业语音时这些网站的重要性。</span><span class="sxs-lookup"><span data-stu-id="03357-105">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="03357-106">有关帮助您做出这些决策的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 "高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) "。</span><span class="sxs-lookup"><span data-stu-id="03357-106">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="03357-107">站点和区域</span><span class="sxs-lookup"><span data-stu-id="03357-107">Sites and Regions</span></span>

<span data-ttu-id="03357-108">首先，确定您的拓扑中的网站，您将在其中部署企业语音和这些网站所属的网络区域。</span><span class="sxs-lookup"><span data-stu-id="03357-108">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="03357-109">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="03357-109">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="03357-110">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="03357-110">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="03357-111">确定在本地部署网关的位置，将在其中部署 Survivable 分支机构 (Sba) ，以及可以在本地或在中心站点) 将 SIP 中继 (到 Internet 电话服务提供程序 (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="03357-111">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="03357-112">站点之间的网络链路</span><span class="sxs-lookup"><span data-stu-id="03357-112">Network Links Between Sites</span></span>

<span data-ttu-id="03357-113">您还需要考虑您在中央站点与其分支站点之间的网络链接上所需的带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="03357-113">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="03357-114">如果您有或计划在站点之间部署弹性 WAN 链接，我们建议您在每个分支站点部署一个网关，以提供本地的直接向内拨号 () 在这些站点上的用户终止。</span><span class="sxs-lookup"><span data-stu-id="03357-114">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="03357-115">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="03357-115">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="03357-116">如果没有可恢复的 WAN 链路，请在分支站点上托管少于1000个用户，并且没有本地训练有素的 Lync Server 管理员，我们建议您在分支站点部署 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="03357-116">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="03357-117">如果你在分支站点上托管1000和5000用户，缺少弹性 WAN 连接，并且已培训的 Lync Server 管理员可用，我们建议您在分支站点上部署具有小型网关的 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="03357-117">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="03357-118">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="03357-118">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03357-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03357-119">See Also</span></span>


[<span data-ttu-id="03357-120">Lync Server 2013 中的高级企业语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="03357-120">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

