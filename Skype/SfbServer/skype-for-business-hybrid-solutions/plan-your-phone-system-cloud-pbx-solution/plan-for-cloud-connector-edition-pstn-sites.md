---
title: 规划云连接器版本 PSTN 网站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 阅读本主题, 了解如何规划你的云连接器版本 PSTN 网站, 以确保有效且经济高效的呼叫路由。
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287032"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="f4539-103">规划云连接器版本 PSTN 网站</span><span class="sxs-lookup"><span data-stu-id="f4539-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="f4539-104">阅读本主题, 了解如何规划你的云连接器版本 PSTN 网站, 以确保有效且经济高效的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="f4539-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="f4539-105">本主题介绍了你需要了解的有关云连接器版本和呼叫路由的内容, 以便你可以规划你的云连接器 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="f4539-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="f4539-106">PSTN 站点是云连接器装置的组合, 可在同一位置部署, 并与公用 PSTN 网关连接。</span><span class="sxs-lookup"><span data-stu-id="f4539-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="f4539-107">本主题重点介绍如何设置你的云连接器网站拓扑, 以确保你的云连接器网站能够以最经济高效且有效的方式处理分配给网站的所有用户的入站和出站路由。</span><span class="sxs-lookup"><span data-stu-id="f4539-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="f4539-108">有关云连接器和 PSTN 网站优点的详细信息, 请务必阅读[Skype for Business 云连接器版的计划](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="f4539-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="f4539-109">云连接器 PSTN 网站和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="f4539-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="f4539-110">云连接器 PSTN 站点是创建的拓扑结构, 用于防止不必要的长途和国内费率, 并确保将出站紧急呼叫路由到相应的主干。</span><span class="sxs-lookup"><span data-stu-id="f4539-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="f4539-111">为了确保对呼叫（包括紧急服务呼叫）进行实惠且高效的路由，必须仔细规划 PSTN 站点以及如何向每个站点分配用户。</span><span class="sxs-lookup"><span data-stu-id="f4539-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="f4539-112">作为云连接器规划的一部分, 您必须与运营商联系, 了解您的办事处和用户所在的位置, 以及 PSTN 中继从运营商处终止。</span><span class="sxs-lookup"><span data-stu-id="f4539-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="f4539-113">您需要使用您的运营商来确定如何传送紧急电话, 然后使用该信息定义云连接器 PSTN 站点并将用户分配给相应的站点。</span><span class="sxs-lookup"><span data-stu-id="f4539-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="f4539-114">例如，应该确保在分布了 PSTN 站点的数据中心处端接的中继配置为处理为该站点的用户分配的所有号码的入站和出站路由。</span><span class="sxs-lookup"><span data-stu-id="f4539-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="f4539-115">每个云连接器设备都可以连接到多个 IP 网关、IP Pbx 或会话边界控制器 (SBCs)。</span><span class="sxs-lookup"><span data-stu-id="f4539-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="f4539-116">由于网关和 Pbx 连接到电信中继 (PRI 或 SIP 中继), 因此云连接器装置在逻辑上连接到 PSTN 中继进行入站和出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4539-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="f4539-117">通过云连接器和本地 PSTN 连接, 你可以获取来自本地运营商的主干和关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f4539-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="f4539-118">如果你的企业是大型企业，你可能有多个运营商—尤其是当你的企业跨多个城市、省/市/自治区或国家/地区时。</span><span class="sxs-lookup"><span data-stu-id="f4539-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="f4539-119">由于你的运营商拥有电话号码，因此由该运营商负责处理紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4539-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="f4539-120">Skype for Business Online 同等地对待网站中的所有云连接器装置, 并将按循环方式将出站呼叫路由到同一站点中的云连接器装置。</span><span class="sxs-lookup"><span data-stu-id="f4539-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="f4539-121">网站中的每个云连接器都与同一组 PSTN 中继 (完全网状) 交叉连接。</span><span class="sxs-lookup"><span data-stu-id="f4539-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="f4539-122">由于每个用户都与一个云连接器 PSTN 站点关联, 因此来自该用户的任何出站呼叫 (普通或紧急) 都将分配给与该用户相关联的 PSTN 站点中的某个云连接器装置。</span><span class="sxs-lookup"><span data-stu-id="f4539-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="f4539-123">云连接器执行静态呼叫路由到其连接的 IP 网关、IP-Pbx、SBCs 或直接 PSTN 中继。</span><span class="sxs-lookup"><span data-stu-id="f4539-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="f4539-124">云连接器尚未支持基于目标 (最小成本路由) 或基于原始 (静态或动态紧急呼叫) 的中继的动态路由。</span><span class="sxs-lookup"><span data-stu-id="f4539-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="f4539-125">由于入站呼叫只可能来自与号码关联的中继，因此入站呼叫不是问题。</span><span class="sxs-lookup"><span data-stu-id="f4539-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="f4539-126">但是, 出站呼叫可以转到网站中的任何云连接器装置 (以及通过连接到该云接口装置的 PSTN 中继), 这可能会导致不需要长途通话。</span><span class="sxs-lookup"><span data-stu-id="f4539-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="f4539-127">此外, 如果云连接器 PSTN 站点通过不同的地区代码或运营商跨数据中心延伸, 则紧急呼叫将不会经历。</span><span class="sxs-lookup"><span data-stu-id="f4539-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="f4539-128">示例</span><span class="sxs-lookup"><span data-stu-id="f4539-128">An example</span></span>

<span data-ttu-id="f4539-129">以下示例显示了如何将中继分组到 PSTN 网站以及如何将用户分配给网站。</span><span class="sxs-lookup"><span data-stu-id="f4539-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="f4539-130">对于 Contoso 公司，假设：</span><span class="sxs-lookup"><span data-stu-id="f4539-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="f4539-131">有四个用户：</span><span class="sxs-lookup"><span data-stu-id="f4539-131">There are four users:</span></span> 
    
  - <span data-ttu-id="f4539-132">华盛顿州雷德蒙德的用户 A（美国）</span><span class="sxs-lookup"><span data-stu-id="f4539-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="f4539-133">华盛顿州贝尔维尤的用户 B（美国）</span><span class="sxs-lookup"><span data-stu-id="f4539-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="f4539-134">华盛顿州桑塔利亚的用户 C（美国）</span><span class="sxs-lookup"><span data-stu-id="f4539-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="f4539-135">上海或 (美国) 的用户 D</span><span class="sxs-lookup"><span data-stu-id="f4539-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="f4539-136">运营商 A 在以下设备中提供电话号码和中继:</span><span class="sxs-lookup"><span data-stu-id="f4539-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="f4539-137">雷德蒙德（区号 425）</span><span class="sxs-lookup"><span data-stu-id="f4539-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="f4539-138">贝尔维尤（区号 425）</span><span class="sxs-lookup"><span data-stu-id="f4539-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="f4539-139">桑塔利亚（区号 360）</span><span class="sxs-lookup"><span data-stu-id="f4539-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="f4539-140">运营商 B 在以下设备中提供电话号码和中继:</span><span class="sxs-lookup"><span data-stu-id="f4539-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="f4539-141">波特兰（区号 503）</span><span class="sxs-lookup"><span data-stu-id="f4539-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="f4539-142">由于 Redmond (数据中心 A) 中的用户 A 和邯郸中的用户 B (数据中心 B) 分别在 suburbs 中, 并且在同一区号 (425) 中, 运营商 A 应该能够在邯郸的主干中的用户 A 处进行紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4539-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="f4539-143">因此, 邯郸和 Redmond 的用户 A 和 B 以及云连接器中继可能位于同一个云连接器 PSTN 站点中, 如下图所示。</span><span class="sxs-lookup"><span data-stu-id="f4539-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="f4539-144">一个办公地点的用户的紧急呼叫可以路由到其他办公地点的中继。</span><span class="sxs-lookup"><span data-stu-id="f4539-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="f4539-145">但是, 你应该与运营商联系, 确保这一点将起作用。</span><span class="sxs-lookup"><span data-stu-id="f4539-145">You should, however, check with your carrier that this will work.</span></span>
  
![支持的 SFB 与 MA 拓扑，仅限本地部署。](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="f4539-147">另外看看以下示例：</span><span class="sxs-lookup"><span data-stu-id="f4539-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="f4539-148">桑塔利亚的用户 C（其号码由运营商 A 提供）与贝尔维尤和雷德蒙德 425 区号内的运营商 A 其他用户相距两个小时车程，且位于另一个区号 (360) 内。</span><span class="sxs-lookup"><span data-stu-id="f4539-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="f4539-149">因此, 即使呼叫来自承运人 A, Centralia 区号360中的载波呼叫路由软件也可能会拒绝来自邯郸区域代码425中的用户 B 的传入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4539-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="f4539-150">在这种情况下, 运营商务必确认 Centralia PSTN 站点中的云连接器及其关联的中继可以跨距离和区号处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4539-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="f4539-151">工作中的用户 D 使用由运营商 B 提供的号码和干线, 因此, 运营商 B 对运营商 B 所拥有的电话号码的紧急呼叫几乎不太可能。因此, 中继中的用户 D 和云连接器装置以及相关的将必须位于另一个 PSTN 站点中。</span><span class="sxs-lookup"><span data-stu-id="f4539-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

