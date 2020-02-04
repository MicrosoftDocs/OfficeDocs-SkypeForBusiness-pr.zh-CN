---
title: Lync Server 2013：定义 E9 的范围-1-1 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="52763-102">在 Lync Server 2013 中定义 E9 部署的范围</span><span class="sxs-lookup"><span data-stu-id="52763-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52763-103">_**主题上次修改时间：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="52763-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="52763-104">在将 Microsoft Lync Server 2013 配置为 E9-1 之前，你需要规划 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="52763-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="52763-105">要考虑的一些问题包括：</span><span class="sxs-lookup"><span data-stu-id="52763-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="52763-106">**贵组织关于 E9-1-1 的策略和法律义务是什么？**</span><span class="sxs-lookup"><span data-stu-id="52763-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="52763-107">E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。</span><span class="sxs-lookup"><span data-stu-id="52763-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="52763-108">您应咨询您的法律团队，了解在相关地区的您的 Lync Server 部署中可能会收取的义务。</span><span class="sxs-lookup"><span data-stu-id="52763-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="52763-109">**需要在企业内部的哪些区域启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="52763-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="52763-p103">可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。</span><span class="sxs-lookup"><span data-stu-id="52763-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="52763-112">**如何为分支站点部署 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="52763-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="52763-113">语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="52763-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="52763-114">如果您有集中式电子 9-1-1 SIP 中继并且发生 WAN 中断，则登录的客户可能无法从位置信息服务获取位置或连接到紧急服务服务提供商。</span><span class="sxs-lookup"><span data-stu-id="52763-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="52763-115">Lync 服务器提供了多个用于处理分支机构中的语音复原的策略，包括：具有弹性数据网络、在每个分支处部署 SIP 主干或在中断期间将紧急呼叫推送到本地网关。</span><span class="sxs-lookup"><span data-stu-id="52763-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="52763-116">有关详细信息，请参阅[在 Lync Server 2013 中规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="52763-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="52763-117">**是否为在网络外部工作的用户启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="52763-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="52763-118">自动位置获取仅适用于组织网络内的客户端，因此你的组织需要确定它是否支持 E9 从 Lync 客户端（非本地）拨打的 1-1。</span><span class="sxs-lookup"><span data-stu-id="52763-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="52763-119">例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？</span><span class="sxs-lookup"><span data-stu-id="52763-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="52763-120">如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="52763-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="52763-121">但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。</span><span class="sxs-lookup"><span data-stu-id="52763-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52763-122">通过使用 VPN 连接到组织网络的用户的 Lync 客户端可以获取内部 IP 地址信息，但由于这些地址不能用于标识用户的实际位置，因此必须将 VPN 子网排除在位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="52763-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="52763-123">**是否向美国之外的站点提供紧急呼叫路由？**</span><span class="sxs-lookup"><span data-stu-id="52763-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="52763-p106">您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="52763-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

