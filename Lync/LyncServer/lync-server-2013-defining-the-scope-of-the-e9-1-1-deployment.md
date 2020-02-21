---
title: Lync Server 2013：定义 E9-1-1 部署的范围
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
ms.openlocfilehash: ed4a5fb3e34192aab9c94d72a3bc79b733828e3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="7e2ec-102">在 Lync Server 2013 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="7e2ec-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e2ec-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7e2ec-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7e2ec-104">在为 E9-1-1 配置 Microsoft Lync Server 2013 之前，需要规划 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="7e2ec-105">要考虑的一些问题包括：</span><span class="sxs-lookup"><span data-stu-id="7e2ec-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="7e2ec-106">**贵组织关于 E9-1-1 的策略和法律义务是什么？**</span><span class="sxs-lookup"><span data-stu-id="7e2ec-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="7e2ec-107">E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="7e2ec-108">应咨询你的法律团队，以了解可能适用于你的相关地理位置的 Lync Server 部署的义务。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="7e2ec-109">**需要在企业内部的哪些区域启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="7e2ec-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="7e2ec-p103">可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="7e2ec-112">**如何为分支站点部署 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="7e2ec-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="7e2ec-113">语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="7e2ec-114">如果您有集中化的电子 9-1-1 SIP 中继，并且发生 WAN 中断，则登录的客户端可能无法从位置信息服务获取位置或连接到紧急服务服务提供商。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="7e2ec-115">Lync Server 提供了几种用于在分支机构中处理语音弹性的策略，包括：具有可恢复的数据网络、在每个分支中部署 SIP 中继或在中断期间将紧急呼叫推送到本地网关。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="7e2ec-116">有关详细信息，请参阅[Lync Server 2013 中的规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="7e2ec-117">**是否为在网络外部工作的用户启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="7e2ec-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="7e2ec-p105">自动位置获取仅适用于位于组织网络内部的客户端，因此您的组织需要决定是否支持从外部 Lync 客户端进行的 E9-1-1 呼叫。例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e2ec-122">使用 VPN 连接到组织网络的用户的 Lync 客户端可以选取内部 IP 地址信息，但由于这些地址不能用于标识用户的实际位置，因此必须将 VPN 子网排除在位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="7e2ec-123">**是否向美国之外的站点提供紧急呼叫路由？**</span><span class="sxs-lookup"><span data-stu-id="7e2ec-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="7e2ec-p106">您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="7e2ec-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

