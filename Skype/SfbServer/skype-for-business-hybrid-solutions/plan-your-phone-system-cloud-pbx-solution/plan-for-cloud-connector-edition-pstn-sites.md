---
title: 云连接器版本 PSTN 站点规划
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 阅读本主题，了解如何规划云连接器版本 PSTN 站点以确保有效且经济高效的呼叫路由。
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096226"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="aa4ed-103">云连接器版本 PSTN 站点规划</span><span class="sxs-lookup"><span data-stu-id="aa4ed-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="aa4ed-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="aa4ed-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="aa4ed-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="aa4ed-106">阅读本主题，了解如何规划云连接器版本 PSTN 站点以确保有效且经济高效的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="aa4ed-107">本主题介绍你需要了解的云连接器版本和呼叫路由，以便你可以规划云连接器 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="aa4ed-108">PSTN 站点是云连接器设备的组合，部署在同一位置，并连接了常见的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="aa4ed-109">本主题重点介绍如何设置云连接器站点拓扑，以确保云连接器站点可以尽可能经济高效的方式为分配到站点的所有用户处理入站和出站路由。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="aa4ed-110">有关云连接器和 PSTN 站点优势的信息，请务必阅读 Plan for [Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="aa4ed-111">云连接器 PSTN 站点和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="aa4ed-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="aa4ed-112">云连接器 PSTN 站点是一种拓扑结构，用于防止不必要的长途和国家/地区间通信，并确保出站紧急呼叫路由到相应的中继。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="aa4ed-113">为了确保呼叫（包括紧急服务的呼叫）的成本高效路由，您必须仔细规划 PSTN 站点以及如何将用户分配给每个站点。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="aa4ed-114">作为规划云连接器的一部分，有必要与运营商就你的办公室和用户所在的位置以及 PSTN 中继从运营商处终止的位置交谈。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="aa4ed-115">你需要与运营商合作以确定如何路由紧急呼叫，然后使用该信息定义云连接器 PSTN 站点并将用户分配给相应的站点。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="aa4ed-116">例如，应确保终止于 PSTN 站点拉伸的数据中心的中继配置为处理分配给该站点上用户的所有号码的入站和出站路由。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="aa4ed-117">每个云连接器设备都可以连接到 SDC 或 SDC (多个 IP 网关、IP PBX 或) 。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="aa4ed-118">由于网关和 PBX 连接到 telco 中继 (PRI 或 SIP 中继) ，因此云连接器设备在逻辑上连接到 PSTN 中继进行入站和出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="aa4ed-119">通过云连接器和本地 PSTN 连接，你可以从本地运营商获取中继和相关电话号码。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="aa4ed-120">如果你的企业是大型企业，你可能拥有多个运营商，尤其是在你的企业跨越多个城市、州或国家/地区时。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="aa4ed-121">由于运营商拥有电话号码，因此运营商负责处理紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="aa4ed-122">Skype for Business Online 同等对待站点内的所有云连接器设备，并旋转将出站呼叫路由到同一站点中的云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="aa4ed-123">站点中的每个云连接器都交叉连接到同一组 PSTN 中继 (完全网格化) 。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="aa4ed-124">由于每个用户都与云连接器 PSTN 站点关联，因此来自该用户 (正常或紧急) 的任何出站呼叫都将分配给与该用户关联的 PSTN 站点中的云连接器设备之一。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="aa4ed-125">云连接器将静态呼叫路由到其连接的 IP 网关、IP-PBX、SDC 或直接 PSTN 中继。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="aa4ed-126">云连接器尚不能够基于目标 (（成本最低路由) 或基于源 (静态或动态紧急呼叫) ） 进行动态路由。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="aa4ed-127">入站呼叫不是问题，因为呼叫只能来自与号码关联的中继。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="aa4ed-128">但是，出站呼叫可以转到站点 (并扩展连接到该云连接器设备的 PSTN 中继) 这可能会导致不需要的长途呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="aa4ed-129">此外，如果云连接器 PSTN 站点扩展到具有不同区号或运营商的数据中心，紧急呼叫将不会通过。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="aa4ed-130">示例</span><span class="sxs-lookup"><span data-stu-id="aa4ed-130">An example</span></span>

<span data-ttu-id="aa4ed-131">以下示例演示如何将中继分组到 PSTN 站点以及如何向这些站点分配用户。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="aa4ed-132">对于 Contoso 公司，假定以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa4ed-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="aa4ed-133">有四个用户：</span><span class="sxs-lookup"><span data-stu-id="aa4ed-133">There are four users:</span></span> 
    
  - <span data-ttu-id="aa4ed-134">美国雷德蒙德州 (A) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="aa4ed-135">美国雷德维尤州 (B) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="aa4ed-136">位于华盛顿州中部的用户 C (USA) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="aa4ed-137">波特兰或美国波特兰 (D) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="aa4ed-138">运营商 A 在：</span><span class="sxs-lookup"><span data-stu-id="aa4ed-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="aa4ed-139">Redmond (区号 425) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="aa4ed-140">Bellevue (区号 425) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="aa4ed-141">Centralia (区号 360) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="aa4ed-142">运营商 B 在：</span><span class="sxs-lookup"><span data-stu-id="aa4ed-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="aa4ed-143">波特兰 (区号 503) </span><span class="sxs-lookup"><span data-stu-id="aa4ed-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="aa4ed-144">由于雷德蒙德 (数据中心 A 的用户 A) 和 Bellevue (数据中心 B) 中的用户 B 彼此并位于同一区号 (425) 中，运营商 A 应该能够在 Bellevue 的中继上从 Redmond 的用户 A 拨打紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="aa4ed-145">因此，用户 A 和 B 以及 Bellevue 和 Redmond 的云连接器中继可能在同一云连接器 PSTN 站点中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="aa4ed-146">可以将来自一个办公室用户的紧急呼叫路由到另一个办公室的中继。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="aa4ed-147">但是，你应该与运营商核实这是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-147">You should, however, check with your carrier that this will work.</span></span>
  
![如何设置 PSTN 站点](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="aa4ed-149">还请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="aa4ed-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="aa4ed-150">Centralia 的用户 C（其号码由运营商 A 提供）需要两个小时的时间，并且位于其他运营商 A 用户（位于 Bellevue 和 Redmond 425 区号中）的 2 小时驱动器之外，位于不同的区号 (360) 中。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="aa4ed-151">因此，即使呼叫来自运营商 A，Centralia 区号 360 中的运营商的呼叫路由软件也可能拒绝来自 Bellevue 区号 425 中的用户 B 的传入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="aa4ed-152">在这种情况下，运营商确认 Centralia PSTN 站点中的云连接器及其关联中继可以处理跨距离和区号的呼叫至关重要。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="aa4ed-153">波特兰的用户 D 使用运营商 B 提供的号码和中继，因此运营商 B 从运营商 A 拥有的电话号码接听紧急呼叫的可能性很小。因此，波特兰的用户 D 和云连接器设备以及关联的中继必须位于不同的 PSTN 站点中。</span><span class="sxs-lookup"><span data-stu-id="aa4ed-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
