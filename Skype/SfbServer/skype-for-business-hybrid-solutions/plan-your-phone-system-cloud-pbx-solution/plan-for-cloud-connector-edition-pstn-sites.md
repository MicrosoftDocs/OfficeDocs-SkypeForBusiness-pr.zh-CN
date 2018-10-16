---
title: 规划云连接器版本 PSTN 网站
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 阅读本主题可了解如何规划云连接器 Edition PSTN 网站以确保高效且具有成本效益的呼叫路由。
ms.openlocfilehash: fa224bd4fa3dc1d0be5db8104e414f9a78d01b30
ms.sourcegitcommit: 58934985891818fa505ae742b1e750edccadd870
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "25576517"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="b5f64-103">规划云连接器版本 PSTN 网站</span><span class="sxs-lookup"><span data-stu-id="b5f64-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="b5f64-104">阅读本主题可了解如何规划云连接器 Edition PSTN 网站以确保高效且具有成本效益的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="b5f64-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="b5f64-105">本主题介绍需要了解的有关云连接器 Edition 和呼叫路由，以便您可以在规划云连接器 PSTN 网站。</span><span class="sxs-lookup"><span data-stu-id="b5f64-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="b5f64-106">PSTN 网站是云连接器 appliance，部署在相同的位置，并与常见连接到他们的 PSTN 网关的组合。</span><span class="sxs-lookup"><span data-stu-id="b5f64-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="b5f64-107">本主题重点介绍如何设置云连接器站点拓扑，以确保您云连接器的网站可以处理入站和出站路由分配给网站可能的方式大多数成本有效且高效的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b5f64-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="b5f64-108">有关云连接器以及在 PSTN 网站的好处的详细信息，请确保阅读[Plan for Business 云连接器 edition Skype](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f64-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="b5f64-109">云连接器 PSTN 网站和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="b5f64-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="b5f64-110">云连接器 PSTN 网站是创建以避免不必要的长途和间国家关税，并确保出站的紧急呼叫将路由至相应的中继拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="b5f64-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="b5f64-111">为了确保对呼叫（包括紧急服务呼叫）进行实惠且高效的路由，必须仔细规划 PSTN 网站以及如何向每个网站分配用户。</span><span class="sxs-lookup"><span data-stu-id="b5f64-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="b5f64-112">在规划云连接器时，告诉运营商你的办公室和用户所在位置以及 PSTN 中继端接运营商的位置，这一点至关重要。</span><span class="sxs-lookup"><span data-stu-id="b5f64-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="b5f64-113">您需要使用您的运营商，以确定如何紧急呼叫可以路由，然后使用这些信息来定义云连接器 PSTN 网站并为用户分配适当的网站。</span><span class="sxs-lookup"><span data-stu-id="b5f64-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="b5f64-114">例如，应该确保在分布了 PSTN 网站的数据中心处端接的中继配置为处理为该网站的用户分配的所有号码的入站和出站路由。</span><span class="sxs-lookup"><span data-stu-id="b5f64-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="b5f64-115">每个云连接器装置可以连接到多个 IP 网关、 IP Pbx 或会话边界控制器 (Sbc)。</span><span class="sxs-lookup"><span data-stu-id="b5f64-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="b5f64-116">网关和 Pbx 连接到电信中继 （PRI 或 SIP 中继），因为云连接器 appliance 逻辑连接到 PSTN 的入站和出站呼叫的中继。</span><span class="sxs-lookup"><span data-stu-id="b5f64-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="b5f64-117">具有云连接器和本地 PSTN 连接时，你将从你的本地运营商获取中继和相关电话号码。</span><span class="sxs-lookup"><span data-stu-id="b5f64-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="b5f64-118">如果你的企业是大型企业，你可能有多个运营商—尤其是当你的企业跨多个城市、省/市/自治区或国家/地区时。</span><span class="sxs-lookup"><span data-stu-id="b5f64-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="b5f64-119">由于你的运营商拥有电话号码，因此由该运营商负责处理紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5f64-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="b5f64-120">Skype 业务 online 同样，将网站中的所有云连接器装置，并将出站呼叫路由到位于同一站点的云连接器装置旋转逐个。</span><span class="sxs-lookup"><span data-stu-id="b5f64-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="b5f64-121">网站中的每个云连接器交叉连接到同一组 PSTN 中继（全网状）。</span><span class="sxs-lookup"><span data-stu-id="b5f64-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="b5f64-122">由于每个用户与云连接器 PSTN 站点相关联，因此任何出站呼叫从该用户 （普通或紧急） 将分配给用户与云连接器 appliance PSTN 网站中之一。</span><span class="sxs-lookup"><span data-stu-id="b5f64-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="b5f64-123">云连接器向其连接的 IP 网关、IP-PBX、SBC 或直接 PSTN 中继执行静态呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="b5f64-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="b5f64-124">云连接器还不能根据目标（成本最低的路由）或根据来源（静态或动态紧急呼叫）向中继执行动态路由。</span><span class="sxs-lookup"><span data-stu-id="b5f64-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="b5f64-125">由于入站呼叫只可能来自与号码关联的中继，因此入站呼叫不是问题。</span><span class="sxs-lookup"><span data-stu-id="b5f64-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="b5f64-126">出站呼叫，但是，可以转到任何云连接器装置网站中 （和按扩展名 PSTN 中继连接到该云连接器装置） 会导致不需要长途呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5f64-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="b5f64-127">此外，紧急呼叫将不经过如果在数据中心与不同区域代码或运营商拉伸云连接器 PSTN 网站。</span><span class="sxs-lookup"><span data-stu-id="b5f64-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="b5f64-128">示例</span><span class="sxs-lookup"><span data-stu-id="b5f64-128">An example</span></span>

<span data-ttu-id="b5f64-129">下面的示例演示如何组合到 PSTN 站点的中继以及如何将用户分配到网站。</span><span class="sxs-lookup"><span data-stu-id="b5f64-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="b5f64-130">对于 Contoso 公司，假设：</span><span class="sxs-lookup"><span data-stu-id="b5f64-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="b5f64-131">有四个用户：</span><span class="sxs-lookup"><span data-stu-id="b5f64-131">There are four users:</span></span> 
    
  - <span data-ttu-id="b5f64-132">华盛顿州雷德蒙德的用户 A（美国）</span><span class="sxs-lookup"><span data-stu-id="b5f64-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="b5f64-133">华盛顿州贝尔维尤的用户 B（美国）</span><span class="sxs-lookup"><span data-stu-id="b5f64-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="b5f64-134">华盛顿州桑塔利亚的用户 C（美国）</span><span class="sxs-lookup"><span data-stu-id="b5f64-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="b5f64-135">波特兰 OR （美国） 中的用户 D</span><span class="sxs-lookup"><span data-stu-id="b5f64-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="b5f64-136">运营商 A 提供电话号码和中继中：</span><span class="sxs-lookup"><span data-stu-id="b5f64-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="b5f64-137">雷德蒙德（区号 425）</span><span class="sxs-lookup"><span data-stu-id="b5f64-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="b5f64-138">贝尔维尤（区号 425）</span><span class="sxs-lookup"><span data-stu-id="b5f64-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="b5f64-139">桑塔利亚（区号 360）</span><span class="sxs-lookup"><span data-stu-id="b5f64-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="b5f64-140">B 的运营商提供的电话号码和中继中：</span><span class="sxs-lookup"><span data-stu-id="b5f64-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="b5f64-141">波特兰（区号 503）</span><span class="sxs-lookup"><span data-stu-id="b5f64-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="b5f64-142">用户 A 雷德蒙德 (数据中心 A) 中和贝尔维尤 (数据中心 B) 中的用户 B 都是在每个其他旁边市郊和相同区域代码 (425) 中，因为运营商 A 应该能够从用户 A 的 Redmond 贝尔维尤在中继上执行紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5f64-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="b5f64-143">因此，用户 A 和 B，贝尔维尤和雷德蒙德，云连接器中继可能可以在同一云连接器 PSTN 站点下图中所示。</span><span class="sxs-lookup"><span data-stu-id="b5f64-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="b5f64-144">一个办公地点的用户的紧急呼叫可以路由到其他办公地点的中继。</span><span class="sxs-lookup"><span data-stu-id="b5f64-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="b5f64-145">但是，您应，咨询您的运营商，这将工作。</span><span class="sxs-lookup"><span data-stu-id="b5f64-145">You should, however, check with your carrier that this will work.</span></span>
  
![支持的 SFB 与 MA 拓扑，仅限本地部署。](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="b5f64-147">另外看看以下示例：</span><span class="sxs-lookup"><span data-stu-id="b5f64-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="b5f64-148">桑塔利亚的用户 C（其号码由运营商 A 提供）与贝尔维尤和雷德蒙德 425 区号内的运营商 A 其他用户相距两个小时车程，且位于另一个区号 (360) 内。</span><span class="sxs-lookup"><span data-stu-id="b5f64-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="b5f64-149">因此，即使来电从运营商 A，很可能运营商的呼叫路由软件 Centralia 区号 360 中的可能会拒绝传入的紧急呼叫源自用户 B 贝尔维尤区号 425。</span><span class="sxs-lookup"><span data-stu-id="b5f64-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="b5f64-150">在这种情况下是关键运营商确认云连接器和其关联的中继 Centralia PSTN 网站中可以跨距离和区域代码处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5f64-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="b5f64-151">在波特兰 D 用户使用的许多和中继供稿运营商 B，因此它不太可能运营商 B 将的执行紧急呼叫从电话号码归运营商 a。使用户 D 和云连接器 appliance 关联的中继，在波特兰将必须位于不同的 PSTN 网站。</span><span class="sxs-lookup"><span data-stu-id="b5f64-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

