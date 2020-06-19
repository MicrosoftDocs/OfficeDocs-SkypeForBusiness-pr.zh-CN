---
title: 团队语音 Contoso 个案研究
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
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785975"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="deac6-103">Contoso 案例研究：电话系统</span><span class="sxs-lookup"><span data-stu-id="deac6-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="deac6-104">根据地理位置和其他因素，Contoso 拥有使用以下电话服务解决方案的办事处：</span><span class="sxs-lookup"><span data-stu-id="deac6-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="deac6-105">网站类型 A： Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="deac6-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="deac6-106">网站类型 B：传统的旧电话系统</span><span class="sxs-lookup"><span data-stu-id="deac6-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="deac6-107">网站类型 C： Skype for Business 企业语音和传统旧式电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="deac6-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="deac6-108">若要为整个组织实施 Microsoft Phone 系统解决方案，Contoso 必须确定 &mdash; 每个网站类型将 &mdash; 以下哪一种选项与电话系统一起使用才能连接到公共交换式电话网络（PSTN）：</span><span class="sxs-lookup"><span data-stu-id="deac6-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="deac6-109">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="deac6-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="deac6-110">通过直接路由使用自己的 PSTN 运营商的电话系统</span><span class="sxs-lookup"><span data-stu-id="deac6-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="deac6-111">通过直接路由将电话系统与呼叫计划和电话系统结合到自己的 PSTN 运营商</span><span class="sxs-lookup"><span data-stu-id="deac6-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="deac6-112">为了为其组织确定合适的解决方案，Contoso 使用[microsoft 电话服务解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)和[microsoft 团队中](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)的 Ignite 2019 会话通话。</span><span class="sxs-lookup"><span data-stu-id="deac6-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="deac6-113">网站类型 A： Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="deac6-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="deac6-114">Contoso Skype for business 企业语音已设置为中心和分支。</span><span class="sxs-lookup"><span data-stu-id="deac6-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="deac6-115">有一个中心位置，它在为国家/地区的 Skype for business Enterprise Voice 用户提供 PSTN 网关的区域中维护 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="deac6-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="deac6-116">这些卫星办公室通常没有自己的 Internet 出口。</span><span class="sxs-lookup"><span data-stu-id="deac6-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="deac6-117">这些用户的数字驻留在与现有 SBC 连接的 SIP 中继上。</span><span class="sxs-lookup"><span data-stu-id="deac6-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="deac6-118">为了确定已部署的 SBC 是否已针对直接路由和媒体绕过认证，Contoso 检查了[认证为直接路由的会话边框控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="deac6-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="deac6-119">用户的拨号习惯是使用扩展在旧式电话系统上拨出用户，即使用户有适用于对等音频的 Skype for Business 客户端也是如此。</span><span class="sxs-lookup"><span data-stu-id="deac6-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="deac6-120">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="deac6-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="deac6-121">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-121">Q.</span></span> <span data-ttu-id="deac6-122">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="deac6-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="deac6-123">答：</span><span class="sxs-lookup"><span data-stu-id="deac6-123">A.</span></span> <span data-ttu-id="deac6-124">否</span><span class="sxs-lookup"><span data-stu-id="deac6-124">No</span></span> 

- <span data-ttu-id="deac6-125">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-125">Q.</span></span> <span data-ttu-id="deac6-126">我们是否需要与第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="deac6-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="deac6-127">答：</span><span class="sxs-lookup"><span data-stu-id="deac6-127">A.</span></span> <span data-ttu-id="deac6-128">否</span><span class="sxs-lookup"><span data-stu-id="deac6-128">No</span></span> 

- <span data-ttu-id="deac6-129">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-129">Q.</span></span> <span data-ttu-id="deac6-130">我们是否需要保留当前的第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="deac6-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="deac6-131">答：是（管控国家），不</span><span class="sxs-lookup"><span data-stu-id="deac6-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="deac6-132">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-132">Q.</span></span> <span data-ttu-id="deac6-133">我们是否需要在部署 SBCs 上获得 ROI？</span><span class="sxs-lookup"><span data-stu-id="deac6-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="deac6-134">答：是和否</span><span class="sxs-lookup"><span data-stu-id="deac6-134">A. Yes and No</span></span>  

- <span data-ttu-id="deac6-135">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-135">Q.</span></span> <span data-ttu-id="deac6-136">此地区是否提供 Microsoft PSTN 呼叫计划？</span><span class="sxs-lookup"><span data-stu-id="deac6-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="deac6-137">答：是和否</span><span class="sxs-lookup"><span data-stu-id="deac6-137">A. Yes and No</span></span> 

<span data-ttu-id="deac6-138">根据问题的答案，Contoso 决定：</span><span class="sxs-lookup"><span data-stu-id="deac6-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="deac6-139">将位于 PSTN 呼叫计划的区域中的用户移动到使用呼叫计划的电话系统。</span><span class="sxs-lookup"><span data-stu-id="deac6-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="deac6-140">移动不在 PSTN 呼叫计划可用的区域中的用户、位于 SBCs 的 ROI 尚未满足的网站中的用户以及驻留在使用直接路由的电话系统所在国家/地区的用户。</span><span class="sxs-lookup"><span data-stu-id="deac6-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="deac6-141">下图显示了初始 Skype for Business 企业语音部署以及如何将此部署迁移到 Microsoft 通话计划和直接路由：</span><span class="sxs-lookup"><span data-stu-id="deac6-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![显示在状态之前和之后的图表](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="deac6-143">网站类型 B：传统的旧电话系统</span><span class="sxs-lookup"><span data-stu-id="deac6-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="deac6-144">Contoso 拥有许多利用旧式电话系统的办事处。</span><span class="sxs-lookup"><span data-stu-id="deac6-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="deac6-145">有一个具有 E 1.64 电话号码的用户子集，而其他用户仅有一个扩展名。</span><span class="sxs-lookup"><span data-stu-id="deac6-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="deac6-146">这些号码驻留在用于 PSTN 网关的 TDM 主干中。</span><span class="sxs-lookup"><span data-stu-id="deac6-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="deac6-147">站内拨号是通过在扩展的前面利用站点代码来确定呼叫路由的位置来配置的。</span><span class="sxs-lookup"><span data-stu-id="deac6-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="deac6-148">用户的拨号习惯是通过分机号码拨号。</span><span class="sxs-lookup"><span data-stu-id="deac6-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="deac6-149">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="deac6-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="deac6-150">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-150">Q.</span></span> <span data-ttu-id="deac6-151">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="deac6-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="deac6-152">答：</span><span class="sxs-lookup"><span data-stu-id="deac6-152">A.</span></span> <span data-ttu-id="deac6-153">否</span><span class="sxs-lookup"><span data-stu-id="deac6-153">No</span></span> 

- <span data-ttu-id="deac6-154">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-154">Q.</span></span> <span data-ttu-id="deac6-155">我们是否需要与第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="deac6-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="deac6-156">答：是</span><span class="sxs-lookup"><span data-stu-id="deac6-156">A. Yes</span></span>

- <span data-ttu-id="deac6-157">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-157">Q.</span></span> <span data-ttu-id="deac6-158">我们是否需要保留当前的第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="deac6-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="deac6-159">A. 否</span><span class="sxs-lookup"><span data-stu-id="deac6-159">A. No</span></span> 

- <span data-ttu-id="deac6-160">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-160">Q.</span></span> <span data-ttu-id="deac6-161">我们的地区是否提供 Microsoft PSTN 的呼叫计划？</span><span class="sxs-lookup"><span data-stu-id="deac6-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="deac6-162">答：是和否</span><span class="sxs-lookup"><span data-stu-id="deac6-162">A. Yes and No</span></span> 

<span data-ttu-id="deac6-163">根据问题的答案，Contoso 决定：</span><span class="sxs-lookup"><span data-stu-id="deac6-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="deac6-164">将位于 PSTN 呼叫计划的区域中的用户移动到使用呼叫计划的电话系统。</span><span class="sxs-lookup"><span data-stu-id="deac6-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="deac6-165">将没有位于 PSTN 呼叫计划的区域中的用户移动到使用直接路由的电话系统。</span><span class="sxs-lookup"><span data-stu-id="deac6-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="deac6-166">维护与业务关键模拟设备的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="deac6-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="deac6-167">下图显示了具有远程站点的原始旧系统部署以及使用本地媒体优化迁移到直接路由部署的步骤：</span><span class="sxs-lookup"><span data-stu-id="deac6-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="deac6-168">**原始旧部署**  
 ![显示在状态之前和之后的图表](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="deac6-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="deac6-169">**直接路由的部署**</span><span class="sxs-lookup"><span data-stu-id="deac6-169">**Deployment with Direct Routing**</span></span>

![显示在状态之前和之后的图表](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="deac6-171">网站类型 C： Skype for Business 企业语音和传统旧式电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="deac6-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="deac6-172">Contoso Skype for business 企业语音用户的号码驻留在来自运营商的 SBC 的 SIP 主干中。</span><span class="sxs-lookup"><span data-stu-id="deac6-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="deac6-173">传统电话系统的号码驻留在 TDM 主干网关。</span><span class="sxs-lookup"><span data-stu-id="deac6-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="deac6-174">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="deac6-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="deac6-175">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-175">Q.</span></span> <span data-ttu-id="deac6-176">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="deac6-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="deac6-177">答：</span><span class="sxs-lookup"><span data-stu-id="deac6-177">A.</span></span> <span data-ttu-id="deac6-178">否</span><span class="sxs-lookup"><span data-stu-id="deac6-178">No</span></span> 

- <span data-ttu-id="deac6-179">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-179">Q.</span></span> <span data-ttu-id="deac6-180">我们是否需要与第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="deac6-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="deac6-181">A. 否</span><span class="sxs-lookup"><span data-stu-id="deac6-181">A. No</span></span> 

- <span data-ttu-id="deac6-182">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-182">Q.</span></span> <span data-ttu-id="deac6-183">我们是否需要保留当前的第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="deac6-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="deac6-184">A. 否</span><span class="sxs-lookup"><span data-stu-id="deac6-184">A. No</span></span> 

- <span data-ttu-id="deac6-185">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-185">Q.</span></span> <span data-ttu-id="deac6-186">我们是否需要在部署 SBCs 上获得 ROI？</span><span class="sxs-lookup"><span data-stu-id="deac6-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="deac6-187">答：是和否</span><span class="sxs-lookup"><span data-stu-id="deac6-187">A. Yes and No</span></span>  

- <span data-ttu-id="deac6-188">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-188">Q.</span></span> <span data-ttu-id="deac6-189">此地区是否提供 Microsoft PSTN 呼叫计划？</span><span class="sxs-lookup"><span data-stu-id="deac6-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="deac6-190">A. 否</span><span class="sxs-lookup"><span data-stu-id="deac6-190">A. No</span></span> 

<span data-ttu-id="deac6-191">根据问题的答案，Contoso 决定以下事项：</span><span class="sxs-lookup"><span data-stu-id="deac6-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="deac6-192">对于将为其启用直接路由的传统电话用户，Contoso 将这些号码从 TDM 主干移植到了 SBC 的 SIP 主干，因为 SBC 经认证可直接路由。</span><span class="sxs-lookup"><span data-stu-id="deac6-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="deac6-193">若要支持移动到手机系统的用户的子集，并允许通过旧系统继续路由，则将旧电话系统设置为 SBC 的下一跃点。</span><span class="sxs-lookup"><span data-stu-id="deac6-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="deac6-194">此外，为了鼓励用户行为更改和删除在站点内部和站点内扩展拨号的相关性，Contoso 提供了用于所有内部通话的团队的指南。</span><span class="sxs-lookup"><span data-stu-id="deac6-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="deac6-195">下图显示了最初的 Skype for Business 企业语音和旧式电话系统部署以及使用直接路由迁移到混合部署的步骤：</span><span class="sxs-lookup"><span data-stu-id="deac6-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="deac6-196">**原始混合部署** 
 ![状态之前显示的图表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="deac6-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="deac6-197">**直接路由** 
 ![ 的混合部署状态之前显示的图表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="deac6-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="deac6-198">通话套餐</span><span class="sxs-lookup"><span data-stu-id="deac6-198">Calling Plans</span></span>

<span data-ttu-id="deac6-199">为了确定呼叫计划的配置要求，Contoso 已检查[通话计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="deac6-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="deac6-200">最终做出的决策：</span><span class="sxs-lookup"><span data-stu-id="deac6-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="deac6-201">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-201">Q.</span></span> <span data-ttu-id="deac6-202">我的用户是否需要国际通话？</span><span class="sxs-lookup"><span data-stu-id="deac6-202">Do my users need international calling?</span></span><br> <span data-ttu-id="deac6-203">答：是</span><span class="sxs-lookup"><span data-stu-id="deac6-203">A. Yes</span></span> 

- <span data-ttu-id="deac6-204">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-204">Q.</span></span> <span data-ttu-id="deac6-205">我的用户是否有直接向内拨电话号码？</span><span class="sxs-lookup"><span data-stu-id="deac6-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="deac6-206">。不是今天。</span><span class="sxs-lookup"><span data-stu-id="deac6-206">A. Not today.</span></span> <span data-ttu-id="deac6-207">所有启用的用户都将收到 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="deac6-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="deac6-208">问：</span><span class="sxs-lookup"><span data-stu-id="deac6-208">Q.</span></span> <span data-ttu-id="deac6-209">我是否希望屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="deac6-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="deac6-210">A. 用户的呼叫方 ID 将被屏蔽到 Contoso 的本地号码。</span><span class="sxs-lookup"><span data-stu-id="deac6-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="deac6-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="deac6-211">Direct Routing</span></span>

<span data-ttu-id="deac6-212">Contoso 参与了 Ignite，以保持最新的 Office 365 功能，包括可通过电话系统和直接路由使用的功能。</span><span class="sxs-lookup"><span data-stu-id="deac6-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="deac6-213">技术领导和架构师使用在 Ignite 2019 期间提供的指南确定其方向。</span><span class="sxs-lookup"><span data-stu-id="deac6-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="deac6-214">使用的关键会话：</span><span class="sxs-lookup"><span data-stu-id="deac6-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="deac6-215">通过 Microsoft 团队直接路由来规划成功</span><span class="sxs-lookup"><span data-stu-id="deac6-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="deac6-216">直接路由更新</span><span class="sxs-lookup"><span data-stu-id="deac6-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="deac6-217">配置</span><span class="sxs-lookup"><span data-stu-id="deac6-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="deac6-218">通话计划网站</span><span class="sxs-lookup"><span data-stu-id="deac6-218">Calling Plans sites</span></span>

<span data-ttu-id="deac6-219">要获取许可证并为用户分配电话号码，Contoso 按照[设置通话计划](set-up-calling-plans.md)中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="deac6-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="deac6-220">由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="deac6-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="deac6-221">若要了解如何使用 PowerShell 分配号码 &mdash; 以及其他设置， &mdash; Contoso 使用[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="deac6-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="deac6-222">直接路由网站</span><span class="sxs-lookup"><span data-stu-id="deac6-222">Direct Routing sites</span></span>

<span data-ttu-id="deac6-223">要将 Contoso 的本地电话基础结构连接到 Microsoft 团队，Contoso 管理员按照[配置直接路由](direct-routing-configure.md)和查看[microsoft 团队中的视频直接路由中](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="deac6-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="deac6-224">Contoso 还通过认证的 SBC 供应商引用直接路由部署文档。</span><span class="sxs-lookup"><span data-stu-id="deac6-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="deac6-225">在 SBC 和 Microsoft Phone 系统之间配置了直接路由后，Contoso 必须对该配置进行测试。</span><span class="sxs-lookup"><span data-stu-id="deac6-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="deac6-226">为此，Contoso 管理员使用在[Ignite 2019 的直接路由会话更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)中讨论的 SIP 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="deac6-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="deac6-227">SIP 测试客户端脚本和文档已从 PowerShell 脚本下载以测试直接路由会话边界控制器连接。</span><span class="sxs-lookup"><span data-stu-id="deac6-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="deac6-228">本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="deac6-228">Local Media Optimization</span></span>

<span data-ttu-id="deac6-229">Contoso 在全球不同地区看到了利用本地媒体优化的机会。</span><span class="sxs-lookup"><span data-stu-id="deac6-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="deac6-230">[用于直接路由的本地媒体优化](direct-routing-media-optimization.md)中介绍了 Contoso 支持的方案。</span><span class="sxs-lookup"><span data-stu-id="deac6-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="deac6-231">通过遵循 SBC 供应商和 Microsoft 的指南完成本地媒体优化的配置。</span><span class="sxs-lookup"><span data-stu-id="deac6-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="deac6-232">本地媒体优化的配置步骤包括：</span><span class="sxs-lookup"><span data-stu-id="deac6-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="deac6-233">配置用户和 SBC 网站</span><span class="sxs-lookup"><span data-stu-id="deac6-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="deac6-234">根据 SBC 供应商规范配置 SBC，</span><span class="sxs-lookup"><span data-stu-id="deac6-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="deac6-235">将外部受信任的 IP 地址添加到用于本地媒体优化的每个网站</span><span class="sxs-lookup"><span data-stu-id="deac6-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="deac6-236">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="deac6-236">Define the network topology</span></span> 

- <span data-ttu-id="deac6-237">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="deac6-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="deac6-238">确定模式：始终绕过或仅适用于本地用户</span><span class="sxs-lookup"><span data-stu-id="deac6-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="deac6-239">网络注意事项</span><span class="sxs-lookup"><span data-stu-id="deac6-239">Networking considerations</span></span>

<span data-ttu-id="deac6-240">Contoso 在启用电话系统后，有多个用户需要在多长时间内进行远程工作。</span><span class="sxs-lookup"><span data-stu-id="deac6-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="deac6-241">使用 VPN 访问特定的业务线应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="deac6-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="deac6-242">在使用 VPN 时，电话系统用户遇到通话质量下降。</span><span class="sxs-lookup"><span data-stu-id="deac6-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="deac6-243">为了解决质量问题，Contoso 实现了 VPN 拆分隧道，该隧道允许其 Office 365 通信在 Internet 上保持与内部应用的连接时通过 Internet。</span><span class="sxs-lookup"><span data-stu-id="deac6-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="deac6-244">若要实现 VPN 拆分隧道，Contoso 遵循[实现 Office 365 的 vpn 拆分隧道](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)的指南。</span><span class="sxs-lookup"><span data-stu-id="deac6-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





