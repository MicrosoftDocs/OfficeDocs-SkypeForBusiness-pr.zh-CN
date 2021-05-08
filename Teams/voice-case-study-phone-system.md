---
title: Teams Contoso 案例研究
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
description: Teams多语言公司语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101028"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="373c6-103">Contoso 案例研究：电话系统</span><span class="sxs-lookup"><span data-stu-id="373c6-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="373c6-104">根据地理位置和其他因素，Contoso 设有办公室，其电话解决方案如下：</span><span class="sxs-lookup"><span data-stu-id="373c6-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="373c6-105">网站类型 A：Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="373c6-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="373c6-106">站点类型 B：传统传统电话系统</span><span class="sxs-lookup"><span data-stu-id="373c6-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="373c6-107">站点类型 C：Skype for Business 企业语音传统旧电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="373c6-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="373c6-108">若要为Microsoft 电话组织实施 Microsoft 电话 系统解决方案，Contoso 必须确定将以下哪些选项用于每个网站类型电话系统以连接到公共电话交换网 &mdash; &mdash; (PSTN) ：</span><span class="sxs-lookup"><span data-stu-id="373c6-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="373c6-109">电话系统套餐</span><span class="sxs-lookup"><span data-stu-id="373c6-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="373c6-110">电话系统直接路由与自己的 PSTN 运营商联系</span><span class="sxs-lookup"><span data-stu-id="373c6-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="373c6-111">将电话系统与呼叫计划结合使用，电话系统直接路由与自己的 PSTN 运营商联系</span><span class="sxs-lookup"><span data-stu-id="373c6-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="373c6-112">为了确定适合其组织的解决方案，Contoso 使用[Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)电话解决方案和 Ignite 2019 会话呼叫在[Microsoft Teams。](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="373c6-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="373c6-113">网站类型 A：Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="373c6-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="373c6-114">Contoso Skype for Business 企业语音已设置为中心和分支。</span><span class="sxs-lookup"><span data-stu-id="373c6-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="373c6-115">有一个中心位置维护了 PSTN 网关，该区域为国家/地区的用户Skype for Business 企业语音 PSTN。</span><span class="sxs-lookup"><span data-stu-id="373c6-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="373c6-116">通常，这些卫星办事处没有其自己的 Internet 出口。</span><span class="sxs-lookup"><span data-stu-id="373c6-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="373c6-117">这些用户的数字驻留在连接到现有 SBC 的 SIP 中继上。</span><span class="sxs-lookup"><span data-stu-id="373c6-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="373c6-118">为了确定已部署的 SBC 是否通过了直接路由和媒体旁路的认证，Contoso 检查了通过直接路由 认证的会话 [边界控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="373c6-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="373c6-119">用户的拨号习惯是使用分机拨打旧电话系统上的用户，即使该用户有可用于对等音频的 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="373c6-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="373c6-120">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="373c6-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="373c6-121">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-121">Q.</span></span> <span data-ttu-id="373c6-122">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="373c6-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="373c6-123">答：</span><span class="sxs-lookup"><span data-stu-id="373c6-123">A.</span></span> <span data-ttu-id="373c6-124">不支持</span><span class="sxs-lookup"><span data-stu-id="373c6-124">No</span></span> 

- <span data-ttu-id="373c6-125">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-125">Q.</span></span> <span data-ttu-id="373c6-126">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="373c6-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="373c6-127">答：</span><span class="sxs-lookup"><span data-stu-id="373c6-127">A.</span></span> <span data-ttu-id="373c6-128">不支持</span><span class="sxs-lookup"><span data-stu-id="373c6-128">No</span></span> 

- <span data-ttu-id="373c6-129">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-129">Q.</span></span> <span data-ttu-id="373c6-130">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="373c6-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="373c6-131">答：是 (国家/地区) 和否</span><span class="sxs-lookup"><span data-stu-id="373c6-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="373c6-132">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-132">Q.</span></span> <span data-ttu-id="373c6-133">是否需要部署 SDC 的 ROI？</span><span class="sxs-lookup"><span data-stu-id="373c6-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="373c6-134">答：是和否</span><span class="sxs-lookup"><span data-stu-id="373c6-134">A. Yes and No</span></span>  

- <span data-ttu-id="373c6-135">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-135">Q.</span></span> <span data-ttu-id="373c6-136">Microsoft PSTN 呼叫计划是否在此区域可用？</span><span class="sxs-lookup"><span data-stu-id="373c6-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="373c6-137">答：是和否</span><span class="sxs-lookup"><span data-stu-id="373c6-137">A. Yes and No</span></span> 

<span data-ttu-id="373c6-138">Contoso 根据其问题的答案决定：</span><span class="sxs-lookup"><span data-stu-id="373c6-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="373c6-139">移动位于 PSTN 呼叫计划可用于使用呼叫计划电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="373c6-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="373c6-140">移动不在 PSTN 呼叫计划可用的区域的用户、位于尚未满足 SDC ROI 的网站中的用户，以及居住在具有电话法规的国家/地区且使用直接路由电话系统的用户。</span><span class="sxs-lookup"><span data-stu-id="373c6-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="373c6-141">下图显示了初始部署Skype for Business 企业语音以及此部署如何迁移到 Microsoft 呼叫计划和直接路由：</span><span class="sxs-lookup"><span data-stu-id="373c6-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![显示状态之前和之后](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="373c6-143">站点类型 B：传统传统电话系统</span><span class="sxs-lookup"><span data-stu-id="373c6-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="373c6-144">Contoso 有许多办公室利用旧式电话系统。</span><span class="sxs-lookup"><span data-stu-id="373c6-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="373c6-145">有一部分用户拥有 E1.64 电话号码，而其他用户只有分机号。</span><span class="sxs-lookup"><span data-stu-id="373c6-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="373c6-146">这些号码驻留在到 PSTN 网关的 TDM 中继上。</span><span class="sxs-lookup"><span data-stu-id="373c6-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="373c6-147">通过利用扩展前面的站点代码来确定呼叫的路由位置，配置了站点内拨号。</span><span class="sxs-lookup"><span data-stu-id="373c6-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="373c6-148">用户的拨号习惯是按分机进行拨号。</span><span class="sxs-lookup"><span data-stu-id="373c6-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="373c6-149">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="373c6-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="373c6-150">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-150">Q.</span></span> <span data-ttu-id="373c6-151">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="373c6-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="373c6-152">答：</span><span class="sxs-lookup"><span data-stu-id="373c6-152">A.</span></span> <span data-ttu-id="373c6-153">不支持</span><span class="sxs-lookup"><span data-stu-id="373c6-153">No</span></span> 

- <span data-ttu-id="373c6-154">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-154">Q.</span></span> <span data-ttu-id="373c6-155">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="373c6-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="373c6-156">答：是的</span><span class="sxs-lookup"><span data-stu-id="373c6-156">A. Yes</span></span>

- <span data-ttu-id="373c6-157">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-157">Q.</span></span> <span data-ttu-id="373c6-158">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="373c6-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="373c6-159">答：不</span><span class="sxs-lookup"><span data-stu-id="373c6-159">A. No</span></span> 

- <span data-ttu-id="373c6-160">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-160">Q.</span></span> <span data-ttu-id="373c6-161">Microsoft PSTN 的呼叫计划是否在我们的区域可用？</span><span class="sxs-lookup"><span data-stu-id="373c6-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="373c6-162">答：是和否</span><span class="sxs-lookup"><span data-stu-id="373c6-162">A. Yes and No</span></span> 

<span data-ttu-id="373c6-163">Contoso 根据其问题的答案决定：</span><span class="sxs-lookup"><span data-stu-id="373c6-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="373c6-164">移动位于 PSTN 呼叫计划可用于使用呼叫计划电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="373c6-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="373c6-165">移动未位于 PSTN 呼叫计划可用于使用直接路由电话系统的用户。</span><span class="sxs-lookup"><span data-stu-id="373c6-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="373c6-166">保持与业务关键型模拟设备的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="373c6-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="373c6-167">下图显示了使用远程站点的原始旧系统部署，以及使用本地媒体优化迁移到直接路由部署：</span><span class="sxs-lookup"><span data-stu-id="373c6-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="373c6-168">**原始旧版部署**  
 ![显示状态之前和之后](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="373c6-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="373c6-169">**使用直接路由进行部署**</span><span class="sxs-lookup"><span data-stu-id="373c6-169">**Deployment with Direct Routing**</span></span>

![显示状态之前和之后](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="373c6-171">站点类型 C：Skype for Business 企业语音传统旧电话系统的组合</span><span class="sxs-lookup"><span data-stu-id="373c6-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="373c6-172">Contoso Skype for Business 企业语音用户号码位于运营商发自 SBC 的 SIP 中继上。</span><span class="sxs-lookup"><span data-stu-id="373c6-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="373c6-173">传统电话系统的数字驻留在到 PSTN 网关的 TDM 中继上。</span><span class="sxs-lookup"><span data-stu-id="373c6-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="373c6-174">Contoso 基于以下问题做出决策：</span><span class="sxs-lookup"><span data-stu-id="373c6-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="373c6-175">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-175">Q.</span></span> <span data-ttu-id="373c6-176">我们是否需要保留本地部署提供的功能？</span><span class="sxs-lookup"><span data-stu-id="373c6-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="373c6-177">答：</span><span class="sxs-lookup"><span data-stu-id="373c6-177">A.</span></span> <span data-ttu-id="373c6-178">不支持</span><span class="sxs-lookup"><span data-stu-id="373c6-178">No</span></span> 

- <span data-ttu-id="373c6-179">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-179">Q.</span></span> <span data-ttu-id="373c6-180">我们是否需要和第三方 PBX 系统和其他电话设备互操作？</span><span class="sxs-lookup"><span data-stu-id="373c6-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="373c6-181">答：不</span><span class="sxs-lookup"><span data-stu-id="373c6-181">A. No</span></span> 

- <span data-ttu-id="373c6-182">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-182">Q.</span></span> <span data-ttu-id="373c6-183">我们是否需要保留当前第三方运营商？</span><span class="sxs-lookup"><span data-stu-id="373c6-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="373c6-184">答：不</span><span class="sxs-lookup"><span data-stu-id="373c6-184">A. No</span></span> 

- <span data-ttu-id="373c6-185">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-185">Q.</span></span> <span data-ttu-id="373c6-186">是否需要部署 SDC 的 ROI？</span><span class="sxs-lookup"><span data-stu-id="373c6-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="373c6-187">答：是和否</span><span class="sxs-lookup"><span data-stu-id="373c6-187">A. Yes and No</span></span>  

- <span data-ttu-id="373c6-188">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-188">Q.</span></span> <span data-ttu-id="373c6-189">Microsoft 的 PSTN 呼叫计划是否在此区域可用？</span><span class="sxs-lookup"><span data-stu-id="373c6-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="373c6-190">答：不</span><span class="sxs-lookup"><span data-stu-id="373c6-190">A. No</span></span> 

<span data-ttu-id="373c6-191">Contoso 根据其问题的答案决定以下事项：</span><span class="sxs-lookup"><span data-stu-id="373c6-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="373c6-192">对于将启用直接路由的旧式电话用户，Contoso 将 TDM 中继中的号码移植到 SBC 的 SIP 中继，因为 SBC 已通过直接路由认证。</span><span class="sxs-lookup"><span data-stu-id="373c6-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="373c6-193">为了支持一部分用户迁移到 电话系统并允许通过旧系统持续路由，旧式电话系统已设置为 SBC 的下一跃点。</span><span class="sxs-lookup"><span data-stu-id="373c6-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="373c6-194">此外，为了鼓励用户行为更改并删除对站点内和内部分机拨号的依赖，Contoso 提供了在所有内部呼叫Teams使用通知。</span><span class="sxs-lookup"><span data-stu-id="373c6-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="373c6-195">下图显示了原始Skype for Business 企业语音旧电话系统部署以及使用直接路由迁移到混合部署：</span><span class="sxs-lookup"><span data-stu-id="373c6-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="373c6-196">**原始混合部署** 
 ![显示状态前的图表](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="373c6-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="373c6-197">**使用直接路由的混合部署** 
 ![显示状态前的图表](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="373c6-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="373c6-198">通话套餐</span><span class="sxs-lookup"><span data-stu-id="373c6-198">Calling Plans</span></span>

<span data-ttu-id="373c6-199">为了确定调用计划的配置要求，Contoso 查看了调用 [计划核心部署决策](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="373c6-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="373c6-200">做出以下决策：</span><span class="sxs-lookup"><span data-stu-id="373c6-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="373c6-201">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-201">Q.</span></span> <span data-ttu-id="373c6-202">我的用户是否需要国际呼叫？</span><span class="sxs-lookup"><span data-stu-id="373c6-202">Do my users need international calling?</span></span><br> <span data-ttu-id="373c6-203">答：是的</span><span class="sxs-lookup"><span data-stu-id="373c6-203">A. Yes</span></span> 

- <span data-ttu-id="373c6-204">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-204">Q.</span></span> <span data-ttu-id="373c6-205">我的用户是否都有直接向内 DID 电话号码？</span><span class="sxs-lookup"><span data-stu-id="373c6-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="373c6-206">答：今天不能。</span><span class="sxs-lookup"><span data-stu-id="373c6-206">A. Not today.</span></span> <span data-ttu-id="373c6-207">启用的所有用户都将收到 DID。</span><span class="sxs-lookup"><span data-stu-id="373c6-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="373c6-208">问：</span><span class="sxs-lookup"><span data-stu-id="373c6-208">Q.</span></span> <span data-ttu-id="373c6-209">是否要屏蔽或禁用来电显示？</span><span class="sxs-lookup"><span data-stu-id="373c6-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="373c6-210">答：用户的来电显示将被屏蔽为 Contoso 的本地号码。</span><span class="sxs-lookup"><span data-stu-id="373c6-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="373c6-211">直接路由</span><span class="sxs-lookup"><span data-stu-id="373c6-211">Direct Routing</span></span>

<span data-ttu-id="373c6-212">Contoso 参加 Ignite，随时了解Office 365功能，包括可用于电话和直接路由的功能。</span><span class="sxs-lookup"><span data-stu-id="373c6-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="373c6-213">技术领导和架构师使用 Ignite 2019 期间提供的指南来确定方向。</span><span class="sxs-lookup"><span data-stu-id="373c6-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="373c6-214">使用的关键会话：</span><span class="sxs-lookup"><span data-stu-id="373c6-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="373c6-215">规划使用直接路由Microsoft Teams成功</span><span class="sxs-lookup"><span data-stu-id="373c6-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="373c6-216">直接路由的更新</span><span class="sxs-lookup"><span data-stu-id="373c6-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="373c6-217">配置</span><span class="sxs-lookup"><span data-stu-id="373c6-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="373c6-218">呼叫计划网站</span><span class="sxs-lookup"><span data-stu-id="373c6-218">Calling Plans sites</span></span>

<span data-ttu-id="373c6-219">为了获取许可证并将电话号码分配给用户，Contoso 按照设置 [呼叫计划 中的步骤操作](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="373c6-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="373c6-220">由于需要分配电话号码的用户数，Contoso 决定使用 PowerShell 分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="373c6-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="373c6-221">若要了解如何使用 PowerShell 以及其他设置分配数字 &mdash; &mdash; ，Contoso 使用了[powerShell](teams-powershell-overview.md)Teams概述 。</span><span class="sxs-lookup"><span data-stu-id="373c6-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="373c6-222">直接路由站点</span><span class="sxs-lookup"><span data-stu-id="373c6-222">Direct Routing sites</span></span>

<span data-ttu-id="373c6-223">为了将 Contoso 本地电话基础结构连接到 Microsoft Teams，Contoso 的管理员遵循了配置直接路由中的步骤，并[](direct-routing-configure.md)查看了 Microsoft Teams 中的视频"[直接路由"获得](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)指导。</span><span class="sxs-lookup"><span data-stu-id="373c6-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="373c6-224">Contoso 还参考了经过认证的 SBC 供应商提供的直接路由部署文档。</span><span class="sxs-lookup"><span data-stu-id="373c6-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="373c6-225">在 SBC 与 Microsoft 电话 系统之间配置直接路由后，Contoso 必须测试配置。</span><span class="sxs-lookup"><span data-stu-id="373c6-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="373c6-226">为此，Contoso 管理员使用了 [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)的直接路由更新会话中讨论的 SIP 测试器客户端。</span><span class="sxs-lookup"><span data-stu-id="373c6-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="373c6-227">SIP 测试器客户端脚本和文档从 PowerShell 脚本下载，用于测试直接路由会话边界控制器连接。</span><span class="sxs-lookup"><span data-stu-id="373c6-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="373c6-228">本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="373c6-228">Local Media Optimization</span></span>

<span data-ttu-id="373c6-229">Contoso 看到了在全球不同区域利用本地媒体优化的机会。</span><span class="sxs-lookup"><span data-stu-id="373c6-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="373c6-230">Contoso 支持的方案在直接路由的本地 [媒体优化中进行了介绍](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="373c6-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="373c6-231">根据 SBC 供应商和 Microsoft 的指导完成本地媒体优化的配置。</span><span class="sxs-lookup"><span data-stu-id="373c6-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="373c6-232">本地媒体优化的配置步骤包括：</span><span class="sxs-lookup"><span data-stu-id="373c6-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="373c6-233">配置用户和 SBC 站点</span><span class="sxs-lookup"><span data-stu-id="373c6-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="373c6-234">根据 SBC 供应商规范配置 SBC，</span><span class="sxs-lookup"><span data-stu-id="373c6-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="373c6-235">将外部受信任的 IP 地址添加到用于本地媒体优化的每个站点</span><span class="sxs-lookup"><span data-stu-id="373c6-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="373c6-236">定义网络拓扑</span><span class="sxs-lookup"><span data-stu-id="373c6-236">Define the network topology</span></span> 

- <span data-ttu-id="373c6-237">定义虚拟网络拓扑</span><span class="sxs-lookup"><span data-stu-id="373c6-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="373c6-238">确定模式："始终绕过"或"仅针对本地用户"</span><span class="sxs-lookup"><span data-stu-id="373c6-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="373c6-239">网络注意事项</span><span class="sxs-lookup"><span data-stu-id="373c6-239">Networking considerations</span></span>

<span data-ttu-id="373c6-240">Contoso 有一些用户需要长时间远程工作，这些用户启用了远程电话系统。</span><span class="sxs-lookup"><span data-stu-id="373c6-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="373c6-241">用户使用 VPN 访问某些业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="373c6-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="373c6-242">在 VPN 上，电话系统用户遇到呼叫质量下降的情况。</span><span class="sxs-lookup"><span data-stu-id="373c6-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="373c6-243">为了解决质量问题，Contoso 实施了 VPN 拆分隧道，允许其 Office 365 流量遍历 Internet，同时与内部应用的连接仍位于 VPN 上。</span><span class="sxs-lookup"><span data-stu-id="373c6-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="373c6-244">为了实施 VPN 拆分隧道，Contoso 遵循为客户端实现 VPN 拆分隧道中的[Office 365。](/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="373c6-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

