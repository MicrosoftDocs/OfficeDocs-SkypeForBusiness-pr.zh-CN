---
title: Teams 语音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 针对多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101028"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="7e33a-103">Contoso 案例研究：电话系统</span><span class="sxs-lookup"><span data-stu-id="7e33a-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="7e33a-104">根据地理位置和其他因素，Contoso 设有办公室，其电话解决方案如下：</span><span class="sxs-lookup"><span data-stu-id="7e33a-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="7e33a-105">站点类型 A：Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="7e33a-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="7e33a-106">站点类型 B：传统传统电话系统</span><span class="sxs-lookup"><span data-stu-id="7e33a-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="7e33a-107">站点类型 C：Skype for Business 企业语音传统传统电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="7e33a-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="7e33a-108">若要为整个组织实施 Microsoft Phone System 解决方案，Contoso 必须针对每种网站类型确定以下哪些选项用于电话系统以连接到公共电话交换网 &mdash; &mdash; (PSTN) ：</span><span class="sxs-lookup"><span data-stu-id="7e33a-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="7e33a-109">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="7e33a-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="7e33a-110">通过直接路由使用自己的 PSTN 运营商的电话系统</span><span class="sxs-lookup"><span data-stu-id="7e33a-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="7e33a-111">通过直接路由将电话系统与呼叫计划和电话系统与自己的 PSTN 运营商结合使用</span><span class="sxs-lookup"><span data-stu-id="7e33a-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="7e33a-112">为了确定适合其组织的解决方案，Contoso 在 [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) Teams 中使用了 Microsoft 电话解决方案和 Ignite 2019 [会话呼叫](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="7e33a-113">站点类型 A：Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="7e33a-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="7e33a-114">Contoso Skype for Business 企业语音已设置为中心和分支。</span><span class="sxs-lookup"><span data-stu-id="7e33a-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="7e33a-115">在提供 Skype for Business PSTN 连接的区域中，有一个中心位置维护 PSTN 网关，企业语音用户。</span><span class="sxs-lookup"><span data-stu-id="7e33a-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="7e33a-116">通常，这些卫星办事处没有其自己的 Internet 出口。</span><span class="sxs-lookup"><span data-stu-id="7e33a-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="7e33a-117">这些用户的数字驻留在连接到现有 SBC 的 SIP 中继上。</span><span class="sxs-lookup"><span data-stu-id="7e33a-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="7e33a-118">为了确定已部署的 SBC 是否通过了直接路由和媒体旁路的认证，Contoso 检查了通过直接路由 认证的会话 [边界控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="7e33a-119">用户的拨号习惯是使用分机拨打旧电话系统上的用户，即使该用户有可用于对等音频的 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="7e33a-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="7e33a-120">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="7e33a-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="7e33a-121">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-121">Q.</span></span> <span data-ttu-id="7e33a-122">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="7e33a-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="7e33a-123">答：</span><span class="sxs-lookup"><span data-stu-id="7e33a-123">A.</span></span> <span data-ttu-id="7e33a-124">否</span><span class="sxs-lookup"><span data-stu-id="7e33a-124">No</span></span> 

- <span data-ttu-id="7e33a-125">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-125">Q.</span></span> <span data-ttu-id="7e33a-126">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="7e33a-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="7e33a-127">答：</span><span class="sxs-lookup"><span data-stu-id="7e33a-127">A.</span></span> <span data-ttu-id="7e33a-128">否</span><span class="sxs-lookup"><span data-stu-id="7e33a-128">No</span></span> 

- <span data-ttu-id="7e33a-129">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-129">Q.</span></span> <span data-ttu-id="7e33a-130">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="7e33a-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="7e33a-131">答：是 (国家/地区) 和否</span><span class="sxs-lookup"><span data-stu-id="7e33a-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="7e33a-132">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-132">Q.</span></span> <span data-ttu-id="7e33a-133">是否需要部署 SDC 的 ROI？</span><span class="sxs-lookup"><span data-stu-id="7e33a-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="7e33a-134">答：是和否</span><span class="sxs-lookup"><span data-stu-id="7e33a-134">A. Yes and No</span></span>  

- <span data-ttu-id="7e33a-135">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-135">Q.</span></span> <span data-ttu-id="7e33a-136">Microsoft PSTN 呼叫计划是否在此区域可用？</span><span class="sxs-lookup"><span data-stu-id="7e33a-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="7e33a-137">答：是和否</span><span class="sxs-lookup"><span data-stu-id="7e33a-137">A. Yes and No</span></span> 

<span data-ttu-id="7e33a-138">Contoso 根据其问题的答案决定：</span><span class="sxs-lookup"><span data-stu-id="7e33a-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="7e33a-139">移动位于 PSTN 呼叫计划可用于具有呼叫计划的电话系统的区域的用户。</span><span class="sxs-lookup"><span data-stu-id="7e33a-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="7e33a-140">将不在提供 PSTN 呼叫计划的区域的用户、位于尚未满足 SBC ROI 的网站中的用户，以及居住在具有电话法规的国家/地区且具有直接路由的电话系统的用户移动。</span><span class="sxs-lookup"><span data-stu-id="7e33a-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="7e33a-141">下图显示了初始 Skype for Business 企业语音部署，以及此部署如何迁移到 Microsoft 呼叫计划和直接路由：</span><span class="sxs-lookup"><span data-stu-id="7e33a-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![显示状态之前和之后](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="7e33a-143">站点类型 B：传统传统电话系统</span><span class="sxs-lookup"><span data-stu-id="7e33a-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="7e33a-144">Contoso 有许多办公室利用旧式电话系统。</span><span class="sxs-lookup"><span data-stu-id="7e33a-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="7e33a-145">有一部分用户拥有 E1.64 电话号码，而其他用户只有分机号。</span><span class="sxs-lookup"><span data-stu-id="7e33a-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="7e33a-146">这些号码驻留在到 PSTN 网关的 TDM 中继上。</span><span class="sxs-lookup"><span data-stu-id="7e33a-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="7e33a-147">通过利用扩展前面的站点代码来确定呼叫的路由位置，配置了站点内拨号。</span><span class="sxs-lookup"><span data-stu-id="7e33a-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="7e33a-148">用户的拨号习惯是按分机进行拨号。</span><span class="sxs-lookup"><span data-stu-id="7e33a-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="7e33a-149">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="7e33a-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="7e33a-150">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-150">Q.</span></span> <span data-ttu-id="7e33a-151">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="7e33a-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="7e33a-152">答：</span><span class="sxs-lookup"><span data-stu-id="7e33a-152">A.</span></span> <span data-ttu-id="7e33a-153">否</span><span class="sxs-lookup"><span data-stu-id="7e33a-153">No</span></span> 

- <span data-ttu-id="7e33a-154">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-154">Q.</span></span> <span data-ttu-id="7e33a-155">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="7e33a-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="7e33a-156">答：是的</span><span class="sxs-lookup"><span data-stu-id="7e33a-156">A. Yes</span></span>

- <span data-ttu-id="7e33a-157">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-157">Q.</span></span> <span data-ttu-id="7e33a-158">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="7e33a-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="7e33a-159">答：不</span><span class="sxs-lookup"><span data-stu-id="7e33a-159">A. No</span></span> 

- <span data-ttu-id="7e33a-160">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-160">Q.</span></span> <span data-ttu-id="7e33a-161">Microsoft PSTN 的呼叫计划是否在我们的区域可用？</span><span class="sxs-lookup"><span data-stu-id="7e33a-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="7e33a-162">答：是和否</span><span class="sxs-lookup"><span data-stu-id="7e33a-162">A. Yes and No</span></span> 

<span data-ttu-id="7e33a-163">Contoso 根据其问题的答案决定：</span><span class="sxs-lookup"><span data-stu-id="7e33a-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="7e33a-164">移动位于 PSTN 呼叫计划可用于具有呼叫计划的电话系统的区域的用户。</span><span class="sxs-lookup"><span data-stu-id="7e33a-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="7e33a-165">移动未位于 PSTN 呼叫计划可用于具有直接路由的电话系统的区域的用户。</span><span class="sxs-lookup"><span data-stu-id="7e33a-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="7e33a-166">保持与业务关键型模拟设备的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="7e33a-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="7e33a-167">下图显示了使用远程站点的原始旧系统部署，以及使用本地媒体优化迁移到直接路由部署：</span><span class="sxs-lookup"><span data-stu-id="7e33a-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="7e33a-168">**原始旧版部署**  
 ![显示状态之前和之后](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="7e33a-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="7e33a-169">**使用直接路由进行部署**</span><span class="sxs-lookup"><span data-stu-id="7e33a-169">**Deployment with Direct Routing**</span></span>

![显示状态之前和之后](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="7e33a-171">站点类型 C：Skype for Business 企业语音传统旧电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="7e33a-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="7e33a-172">Contoso Skype for Business 企业语音用户号码位于运营商发至 SBC 的 SIP 中继上。</span><span class="sxs-lookup"><span data-stu-id="7e33a-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="7e33a-173">传统电话系统的数字驻留在到 PSTN 网关的 TDM 中继上。</span><span class="sxs-lookup"><span data-stu-id="7e33a-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="7e33a-174">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="7e33a-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="7e33a-175">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-175">Q.</span></span> <span data-ttu-id="7e33a-176">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="7e33a-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="7e33a-177">答：</span><span class="sxs-lookup"><span data-stu-id="7e33a-177">A.</span></span> <span data-ttu-id="7e33a-178">否</span><span class="sxs-lookup"><span data-stu-id="7e33a-178">No</span></span> 

- <span data-ttu-id="7e33a-179">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-179">Q.</span></span> <span data-ttu-id="7e33a-180">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="7e33a-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="7e33a-181">答：不</span><span class="sxs-lookup"><span data-stu-id="7e33a-181">A. No</span></span> 

- <span data-ttu-id="7e33a-182">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-182">Q.</span></span> <span data-ttu-id="7e33a-183">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="7e33a-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="7e33a-184">答：不</span><span class="sxs-lookup"><span data-stu-id="7e33a-184">A. No</span></span> 

- <span data-ttu-id="7e33a-185">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-185">Q.</span></span> <span data-ttu-id="7e33a-186">是否需要部署 SDC 的 ROI？</span><span class="sxs-lookup"><span data-stu-id="7e33a-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="7e33a-187">答：是和否</span><span class="sxs-lookup"><span data-stu-id="7e33a-187">A. Yes and No</span></span>  

- <span data-ttu-id="7e33a-188">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-188">Q.</span></span> <span data-ttu-id="7e33a-189">Microsoft 的 PSTN 呼叫计划是否在此区域可用？</span><span class="sxs-lookup"><span data-stu-id="7e33a-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="7e33a-190">答：不</span><span class="sxs-lookup"><span data-stu-id="7e33a-190">A. No</span></span> 

<span data-ttu-id="7e33a-191">Contoso 根据其问题的答案决定以下事项：</span><span class="sxs-lookup"><span data-stu-id="7e33a-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="7e33a-192">对于将启用直接路由的旧式电话用户，Contoso 将 TDM 中继中的号码移植到 SBC 的 SIP 中继，因为 SBC 已通过直接路由认证。</span><span class="sxs-lookup"><span data-stu-id="7e33a-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="7e33a-193">为了支持一部分用户迁移到电话系统并允许通过旧系统持续路由，旧式电话系统已设置为 SBC 的下一跃点。</span><span class="sxs-lookup"><span data-stu-id="7e33a-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="7e33a-194">此外，为了鼓励用户行为更改并删除对站点内部和内部分机拨号的依赖，Contoso 提供了使用 Teams 进行所有内部呼叫的指导。</span><span class="sxs-lookup"><span data-stu-id="7e33a-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="7e33a-195">下图显示了原始 Skype for Business 企业语音旧电话系统部署以及使用直接路由迁移到混合部署：</span><span class="sxs-lookup"><span data-stu-id="7e33a-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="7e33a-196">**原始混合部署** 
 ![显示状态前的图表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="7e33a-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="7e33a-197">**使用直接路由的混合部署** 
 ![显示状态前的图表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="7e33a-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="7e33a-198">通话套餐</span><span class="sxs-lookup"><span data-stu-id="7e33a-198">Calling Plans</span></span>

<span data-ttu-id="7e33a-199">为了确定调用计划的配置要求，Contoso 查看了调用 [计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="7e33a-200">做出以下决策：</span><span class="sxs-lookup"><span data-stu-id="7e33a-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="7e33a-201">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-201">Q.</span></span> <span data-ttu-id="7e33a-202">我的用户是否需要国际呼叫？</span><span class="sxs-lookup"><span data-stu-id="7e33a-202">Do my users need international calling?</span></span><br> <span data-ttu-id="7e33a-203">答：是的</span><span class="sxs-lookup"><span data-stu-id="7e33a-203">A. Yes</span></span> 

- <span data-ttu-id="7e33a-204">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-204">Q.</span></span> <span data-ttu-id="7e33a-205">我的用户是否都有直接向内 DID 电话号码？</span><span class="sxs-lookup"><span data-stu-id="7e33a-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="7e33a-206">答：今天不能。</span><span class="sxs-lookup"><span data-stu-id="7e33a-206">A. Not today.</span></span> <span data-ttu-id="7e33a-207">启用的所有用户都将收到 DID。</span><span class="sxs-lookup"><span data-stu-id="7e33a-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="7e33a-208">问：</span><span class="sxs-lookup"><span data-stu-id="7e33a-208">Q.</span></span> <span data-ttu-id="7e33a-209">是否要屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="7e33a-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="7e33a-210">答：用户的来电显示将被屏蔽为 Contoso 的本地号码。</span><span class="sxs-lookup"><span data-stu-id="7e33a-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="7e33a-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="7e33a-211">Direct Routing</span></span>

<span data-ttu-id="7e33a-212">Contoso 参加 Ignite，随时了解 Office 365 功能，包括电话系统和直接路由功能。</span><span class="sxs-lookup"><span data-stu-id="7e33a-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="7e33a-213">技术领导和架构师使用 Ignite 2019 期间提供的指南来确定方向。</span><span class="sxs-lookup"><span data-stu-id="7e33a-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="7e33a-214">使用的关键会话：</span><span class="sxs-lookup"><span data-stu-id="7e33a-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="7e33a-215">规划 Microsoft Teams 直接路由的成功</span><span class="sxs-lookup"><span data-stu-id="7e33a-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="7e33a-216">直接路由的更新</span><span class="sxs-lookup"><span data-stu-id="7e33a-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="7e33a-217">配置</span><span class="sxs-lookup"><span data-stu-id="7e33a-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="7e33a-218">呼叫计划网站</span><span class="sxs-lookup"><span data-stu-id="7e33a-218">Calling Plans sites</span></span>

<span data-ttu-id="7e33a-219">为了获取许可证并将电话号码分配给用户，Contoso 按照设置 [呼叫计划 中的步骤操作](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="7e33a-220">由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="7e33a-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="7e33a-221">若要了解如何使用 PowerShell 和其他设置分配数字 &mdash; &mdash; ，Contoso 使用了 Teams [PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="7e33a-222">直接路由站点</span><span class="sxs-lookup"><span data-stu-id="7e33a-222">Direct Routing sites</span></span>

<span data-ttu-id="7e33a-223">为了将 Contoso 本地电话基础结构连接到 Microsoft Teams，Contoso 的管理员遵循配置直接路由中的[](direct-routing-configure.md)步骤，并查看了 Microsoft [Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)中的直接路由视频，获得指导。</span><span class="sxs-lookup"><span data-stu-id="7e33a-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="7e33a-224">Contoso 还参考了经过认证的 SBC 供应商提供的直接路由部署文档。</span><span class="sxs-lookup"><span data-stu-id="7e33a-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="7e33a-225">在 SBC 和 Microsoft Phone System 之间配置直接路由后，Contoso 必须测试配置。</span><span class="sxs-lookup"><span data-stu-id="7e33a-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="7e33a-226">为此，Contoso 管理员使用了 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)的直接路由更新会话中讨论的 SIP 测试器客户端。</span><span class="sxs-lookup"><span data-stu-id="7e33a-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="7e33a-227">SIP 测试器客户端脚本和文档从 PowerShell 脚本下载，用于测试直接路由会话边界控制器连接。</span><span class="sxs-lookup"><span data-stu-id="7e33a-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="7e33a-228">本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="7e33a-228">Local Media Optimization</span></span>

<span data-ttu-id="7e33a-229">Contoso 看到了在全球不同区域利用本地媒体优化的机会。</span><span class="sxs-lookup"><span data-stu-id="7e33a-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="7e33a-230">Contoso 支持的方案在直接路由的本地 [媒体优化中进行了介绍](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="7e33a-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="7e33a-231">根据 SBC 供应商和 Microsoft 的指导完成本地媒体优化的配置。</span><span class="sxs-lookup"><span data-stu-id="7e33a-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="7e33a-232">本地媒体优化的配置步骤包括：</span><span class="sxs-lookup"><span data-stu-id="7e33a-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="7e33a-233">配置用户和 SBC 站点</span><span class="sxs-lookup"><span data-stu-id="7e33a-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="7e33a-234">根据 SBC 供应商规范配置 SBC，</span><span class="sxs-lookup"><span data-stu-id="7e33a-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="7e33a-235">将外部受信任的 IP 地址添加到用于本地媒体优化的每个站点</span><span class="sxs-lookup"><span data-stu-id="7e33a-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="7e33a-236">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="7e33a-236">Define the network topology</span></span> 

- <span data-ttu-id="7e33a-237">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="7e33a-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="7e33a-238">确定模式："始终绕过"或"仅针对本地用户"</span><span class="sxs-lookup"><span data-stu-id="7e33a-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="7e33a-239">网络注意事项</span><span class="sxs-lookup"><span data-stu-id="7e33a-239">Networking considerations</span></span>

<span data-ttu-id="7e33a-240">Contoso 有一些用户在启用电话系统后需要长时间远程工作。</span><span class="sxs-lookup"><span data-stu-id="7e33a-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="7e33a-241">用户使用 VPN 访问某些业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e33a-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="7e33a-242">在 VPN 上，电话系统用户遇到呼叫质量下降的情况。</span><span class="sxs-lookup"><span data-stu-id="7e33a-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="7e33a-243">为了解决质量问题，Contoso 实施了 VPN 拆分隧道，允许其 Office 365 流量遍历 Internet，同时与内部应用的连接仍位于 VPN 上。</span><span class="sxs-lookup"><span data-stu-id="7e33a-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="7e33a-244">为了实施 VPN 拆分隧道，Contoso 遵循为 [Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel)实现 VPN 拆分隧道中的指南。</span><span class="sxs-lookup"><span data-stu-id="7e33a-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

