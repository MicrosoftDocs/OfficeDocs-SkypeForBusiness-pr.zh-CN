---
title: 做出电话系统直接路由服务决策 - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解直接路由、许可和需要制定的决策。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d3410616cf3e841ab6689ffd0fea772975b484c
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271431"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="7e40c-103">作出我的服务决策</span><span class="sxs-lookup"><span data-stu-id="7e40c-103">Make my service decisions</span></span>

<span data-ttu-id="7e40c-104">若要规划手机系统直接路由 ("直接路由") 的技术实施, 您必须提前制定一系列服务决策, 以便更好地准备您的组织来实施满足您定义的业务要求的解决方案。</span><span class="sxs-lookup"><span data-stu-id="7e40c-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="7e40c-105">在团队中通话</span><span class="sxs-lookup"><span data-stu-id="7e40c-105">Calling in Teams</span></span>

<span data-ttu-id="7e40c-106">通过 Microsoft 团队, 您的用户可以拨打或接听公共交换电话网络 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="7e40c-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="7e40c-107">您的用户可以使用他们自己专用的电话号码从团队客户应用程序中拨打和接收国内和国际电话 (包括语音邮件)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="7e40c-108">直接路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-108">Direct Routing</span></span>

<span data-ttu-id="7e40c-109">为了使团队用户能够放置和接收 PSTN 呼叫, 需要为电话系统 (Office 365 中的一项功能) 启用它们。</span><span class="sxs-lookup"><span data-stu-id="7e40c-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="7e40c-110">若要启用与 PSTN 的连接, 你可以使用直接路由让你的组织中的人员能够通过 PSTN 拨打和接听组织外部的电话。</span><span class="sxs-lookup"><span data-stu-id="7e40c-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="7e40c-111">通过直接路由, PSTN 连接由第三方提供商加速, 让你能够继续使用 PSTN 服务提供商提供的现有 PSTN 中继。</span><span class="sxs-lookup"><span data-stu-id="7e40c-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="7e40c-112">这允许在带有呼叫计划 ("通话计划") 的电话系统不可用的国家或地区内进行部署, 或在需要维护现有 PSTN 服务提供商合同或与某些内部部署系统进行互操作的部署中使用必填。</span><span class="sxs-lookup"><span data-stu-id="7e40c-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="7e40c-113">直接路由的可用性</span><span class="sxs-lookup"><span data-stu-id="7e40c-113">Availability of Direct Routing</span></span>

<span data-ttu-id="7e40c-114">直接路由适用于任何可用 Office 365 的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="7e40c-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="7e40c-115">有关这些国家/地区的列表, 请参阅[国际供应](https://products.office.com/business/international-availability)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="7e40c-116">确认您的组织可以获取电话系统功能后, 请根据可用的国家和地区列表, 将您将在其中实施电话系统的用户位置或办事处的列表进行编译。</span><span class="sxs-lookup"><span data-stu-id="7e40c-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="7e40c-117">同时确定要为每个位置启用呼叫计划或直接路由的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-118">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-118">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-119">确定要在其中实施电话系统的用户位置或办公室。</span><span class="sxs-lookup"><span data-stu-id="7e40c-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="7e40c-120">确定要为每个位置启用呼叫计划或直接路由的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-121">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-122">记录要为电话系统启用的用户位置或办公室。</span><span class="sxs-lookup"><span data-stu-id="7e40c-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="7e40c-123">记录要为每个您拥有的位置启用呼叫计划或直接路由的用户列表</span><span class="sxs-lookup"><span data-stu-id="7e40c-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="7e40c-124">下面是直接路由网站支持列表的示例。</span><span class="sxs-lookup"><span data-stu-id="7e40c-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="7e40c-125">**Office**</span><span class="sxs-lookup"><span data-stu-id="7e40c-125">**Office**</span></span>                     | <span data-ttu-id="7e40c-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="7e40c-126">**Location**</span></span>   | <span data-ttu-id="7e40c-127">**电话系统服务**</span><span class="sxs-lookup"><span data-stu-id="7e40c-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="7e40c-128">一个 Epping 道路</span><span class="sxs-lookup"><span data-stu-id="7e40c-128">One Epping Road</span></span>                | <span data-ttu-id="7e40c-129">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="7e40c-129">Australia</span></span>      | <span data-ttu-id="7e40c-130">旧版 PSTN 服务</span><span class="sxs-lookup"><span data-stu-id="7e40c-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="7e40c-131">100 Cyberport 路</span><span class="sxs-lookup"><span data-stu-id="7e40c-131">100 Cyberport Road</span></span>             | <span data-ttu-id="7e40c-132">中国香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="7e40c-132">Hong Kong SAR</span></span>  | <span data-ttu-id="7e40c-133">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="7e40c-134">一个 Marina Boulevard royal</span><span class="sxs-lookup"><span data-stu-id="7e40c-134">One Marina Boulevard</span></span>           | <span data-ttu-id="7e40c-135">新加坡</span><span class="sxs-lookup"><span data-stu-id="7e40c-135">Singapore</span></span>      | <span data-ttu-id="7e40c-136">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="7e40c-137">32伦敦 Bridge 大街</span><span class="sxs-lookup"><span data-stu-id="7e40c-137">32 London Bridge Street</span></span>        | <span data-ttu-id="7e40c-138">英国</span><span class="sxs-lookup"><span data-stu-id="7e40c-138">United Kingdom</span></span> | <span data-ttu-id="7e40c-139">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="7e40c-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="7e40c-140">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="7e40c-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="7e40c-141">法国</span><span class="sxs-lookup"><span data-stu-id="7e40c-141">France</span></span>         | <span data-ttu-id="7e40c-142">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="7e40c-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="7e40c-143">电话号码和紧急位置</span><span class="sxs-lookup"><span data-stu-id="7e40c-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="7e40c-144">电话系统要求组织中的每个用户都有一个唯一的直接向内拨号 (已拨) 电话号码。</span><span class="sxs-lookup"><span data-stu-id="7e40c-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="7e40c-145">通过直接路由, 电话号码和紧急服务由 PSTN 服务提供商提供。</span><span class="sxs-lookup"><span data-stu-id="7e40c-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="7e40c-146">通过直接路由, 你的用户可以继续使用由 PSTN 服务提供商提供的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7e40c-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="7e40c-147">可以使用以下模板记录电话号码的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7e40c-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="7e40c-148">用户</span><span class="sxs-lookup"><span data-stu-id="7e40c-148">User</span></span> |<span data-ttu-id="7e40c-149">电话号码</span><span class="sxs-lookup"><span data-stu-id="7e40c-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="7e40c-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="7e40c-150">Emily Braun</span></span> | <span data-ttu-id="7e40c-151">+ 44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="7e40c-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="7e40c-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="7e40c-152">Lidia Holloway</span></span> | <span data-ttu-id="7e40c-153">+ 44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="7e40c-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="7e40c-154">Lahr 港</span><span class="sxs-lookup"><span data-stu-id="7e40c-154">Louis Lahr</span></span> | <span data-ttu-id="7e40c-155">+ 44 23 4567 8921</span><span class="sxs-lookup"><span data-stu-id="7e40c-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="7e40c-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="7e40c-156">Marcel Beauchamp</span></span> | <span data-ttu-id="7e40c-157">TBA</span><span class="sxs-lookup"><span data-stu-id="7e40c-157">TBA</span></span> |
> |<span data-ttu-id="7e40c-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="7e40c-158">Rachelle Cormier</span></span> | <span data-ttu-id="7e40c-159">TBA</span><span class="sxs-lookup"><span data-stu-id="7e40c-159">TBA</span></span> |
> |<span data-ttu-id="7e40c-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="7e40c-160">Isabell Potvin</span></span> | <span data-ttu-id="7e40c-161">TBA</span><span class="sxs-lookup"><span data-stu-id="7e40c-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="7e40c-162">语音邮件</span><span class="sxs-lookup"><span data-stu-id="7e40c-162">Voicemail</span></span>

<span data-ttu-id="7e40c-163">云语音邮件 (由 Azure 语音邮件服务提供支持) 仅支持 Exchange 邮箱的语音邮件存款, 不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="7e40c-163">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="7e40c-164">云语音邮件包括语音邮件脚本, 默认情况下为组织中的所有用户启用。</span><span class="sxs-lookup"><span data-stu-id="7e40c-164">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="7e40c-165">您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。</span><span class="sxs-lookup"><span data-stu-id="7e40c-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="7e40c-166">如果您的组织决定保持启用语音邮件脚本, 还需要考虑是否需要启用语音邮件。</span><span class="sxs-lookup"><span data-stu-id="7e40c-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="7e40c-167">有关详细信息, 请参阅[设置组织中的语音邮件策略](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="7e40c-168">有关手机系统实现中的语音邮件的详细信息, 请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-168">For more information about voicemail in a Phone System implementation, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-169">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-169">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-170">确定是否要在直接路由实现中启用云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="7e40c-170">Decide whether you’ll enable Cloud Voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="7e40c-171">确定是在整个组织中还是针对特定用户启用或禁用语音邮件脚本和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="7e40c-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-172">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-173">如果适用, 请记录支持云语音邮件的决策点。</span><span class="sxs-lookup"><span data-stu-id="7e40c-173">If applicable, document the decision points to support Cloud Voicemail.</span></span><li><span data-ttu-id="7e40c-174">如果你将启用或禁用语音邮件、语音邮件脚本和语音邮件仅针对特定用户的猥亵屏蔽, 请记录该用户列表。</span><span class="sxs-lookup"><span data-stu-id="7e40c-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="7e40c-175">可在下表中记录有关呼叫计划实施的云语音邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7e40c-175">Cloud Voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="7e40c-176">**User**</span><span class="sxs-lookup"><span data-stu-id="7e40c-176">**User**</span></span>         | <span data-ttu-id="7e40c-177">**Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="7e40c-177">**Exchange mailbox**</span></span> | <span data-ttu-id="7e40c-178">**启用语音邮件？**</span><span class="sxs-lookup"><span data-stu-id="7e40c-178">**Enable voicemail?**</span></span> | <span data-ttu-id="7e40c-179">**语音邮件脚本**</span><span class="sxs-lookup"><span data-stu-id="7e40c-179">**Voicemail transcription**</span></span> | <span data-ttu-id="7e40c-180">**语音邮件功能猥亵猥亵屏蔽**</span><span class="sxs-lookup"><span data-stu-id="7e40c-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="7e40c-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="7e40c-181">Emily Braun</span></span>      | <span data-ttu-id="7e40c-182">Online</span><span class="sxs-lookup"><span data-stu-id="7e40c-182">Online</span></span>               | <span data-ttu-id="7e40c-183">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-183">Yes</span></span>                   | <span data-ttu-id="7e40c-184">已启用</span><span class="sxs-lookup"><span data-stu-id="7e40c-184">Enabled</span></span>                     | <span data-ttu-id="7e40c-185">已启用</span><span class="sxs-lookup"><span data-stu-id="7e40c-185">Enabled</span></span>                                       |
> | <span data-ttu-id="7e40c-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="7e40c-186">Lidia Holloway</span></span>   | <span data-ttu-id="7e40c-187">Online</span><span class="sxs-lookup"><span data-stu-id="7e40c-187">Online</span></span>               | <span data-ttu-id="7e40c-188">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-188">Yes</span></span>                   | <span data-ttu-id="7e40c-189">已启用</span><span class="sxs-lookup"><span data-stu-id="7e40c-189">Enabled</span></span>                     | <span data-ttu-id="7e40c-190">已禁用</span><span class="sxs-lookup"><span data-stu-id="7e40c-190">Disabled</span></span>                                      |
> | <span data-ttu-id="7e40c-191">Lahr 港</span><span class="sxs-lookup"><span data-stu-id="7e40c-191">Louis Lahr</span></span>       | <span data-ttu-id="7e40c-192">本地部署</span><span class="sxs-lookup"><span data-stu-id="7e40c-192">On-premises</span></span>          | <span data-ttu-id="7e40c-193">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-193">Yes</span></span>                   | <span data-ttu-id="7e40c-194">已启用</span><span class="sxs-lookup"><span data-stu-id="7e40c-194">Enabled</span></span>                     | <span data-ttu-id="7e40c-195">已启用</span><span class="sxs-lookup"><span data-stu-id="7e40c-195">Enabled</span></span>                                       |
> | <span data-ttu-id="7e40c-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="7e40c-196">Marcel Beauchamp</span></span> | <span data-ttu-id="7e40c-197">本地部署</span><span class="sxs-lookup"><span data-stu-id="7e40c-197">On-premises</span></span>          | <span data-ttu-id="7e40c-198">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-198">Yes</span></span>                   | <span data-ttu-id="7e40c-199">已禁用</span><span class="sxs-lookup"><span data-stu-id="7e40c-199">Disabled</span></span>                    | <span data-ttu-id="7e40c-200">不适用</span><span class="sxs-lookup"><span data-stu-id="7e40c-200">N/A</span></span>                                           |
> | <span data-ttu-id="7e40c-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="7e40c-201">Rachelle Cormier</span></span> | <span data-ttu-id="7e40c-202">Online</span><span class="sxs-lookup"><span data-stu-id="7e40c-202">Online</span></span>               | <span data-ttu-id="7e40c-203">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-203">Yes</span></span>                   | <span data-ttu-id="7e40c-204">已禁用</span><span class="sxs-lookup"><span data-stu-id="7e40c-204">Disabled</span></span>                    | <span data-ttu-id="7e40c-205">不适用</span><span class="sxs-lookup"><span data-stu-id="7e40c-205">N/A</span></span>                                           |
> | <span data-ttu-id="7e40c-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="7e40c-206">Isabell Potvin</span></span>   | <span data-ttu-id="7e40c-207">本地部署</span><span class="sxs-lookup"><span data-stu-id="7e40c-207">On-premises</span></span>          | <span data-ttu-id="7e40c-208">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-208">Yes</span></span>                   | <span data-ttu-id="7e40c-209">已禁用</span><span class="sxs-lookup"><span data-stu-id="7e40c-209">Disabled</span></span>                    | <span data-ttu-id="7e40c-210">不适用</span><span class="sxs-lookup"><span data-stu-id="7e40c-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="7e40c-211">若要使用团队和语音邮件, 您的用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="7e40c-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="7e40c-212">有关详细信息, 请参阅[Exchange 和 Microsoft 团队的交互方式](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="7e40c-213">直接路由的许可</span><span class="sxs-lookup"><span data-stu-id="7e40c-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="7e40c-214">如果你的组织打算使用直接路由, 则需要获取所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="7e40c-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="7e40c-215">直接路由用户必须在 Office 365 中分配以下许可证:</span><span class="sxs-lookup"><span data-stu-id="7e40c-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="7e40c-216">Microsoft Phone 系统</span><span class="sxs-lookup"><span data-stu-id="7e40c-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="7e40c-217">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e40c-217">Microsoft Teams</span></span>

-   <span data-ttu-id="7e40c-218">音频会议</span><span class="sxs-lookup"><span data-stu-id="7e40c-218">Audio Conferencing</span></span>

<span data-ttu-id="7e40c-219">将外部参与者添加到计划会议需要使用音频会议许可证, 方法是通过拨出或提供拨入号码。</span><span class="sxs-lookup"><span data-stu-id="7e40c-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="7e40c-220">向外拨出外部参与者时, 音频会议服务通过使用在线呼叫功能来呼叫呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e40c-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="7e40c-221">音频会议许可证是可选的, 并且仅对将组织加入音频会议的团队会议所必需的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="7e40c-222">要提供免费的会议桥接电话号码, 并支持向国际电话号码拨出的会议, 您应该为您的组织设置[通讯信用点数](what-are-communications-credits.md)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="7e40c-223">对于拥有 Office 365 E3 或 E1 订阅计划的现有客户的附加服务, 音频会议和电话系统可以单独获得许可;它们已包含在 Office 365 E5 订阅计划中。</span><span class="sxs-lookup"><span data-stu-id="7e40c-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="7e40c-224">您还可以在将呼叫计划传送给第三方 Pbx 时, 对启用了呼叫计划的用户使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="7e40c-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="7e40c-225">有关更多详细信息, 请参阅[直接路由的许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-226">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-226">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-227">如果你的组织没有所需的电话系统许可证, 请确定你是否将通过执行现有 Office 365 订阅或获取手机系统加载项服务来获取电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="7e40c-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="7e40c-228">确定你是否需要直接路由实现的通信信用点数。</span><span class="sxs-lookup"><span data-stu-id="7e40c-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-229">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-229">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-230">记录分配电话系统许可证的部门、部门、办公室或用户组。</span><span class="sxs-lookup"><span data-stu-id="7e40c-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="7e40c-231">如果具有免费电话号码的音频会议在范围内, 请记录您将启用通信信用点数的 "部门"、"部门"、"office" 或 "用户组"。</span><span class="sxs-lookup"><span data-stu-id="7e40c-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="7e40c-232">Office 365 注意事项</span><span class="sxs-lookup"><span data-stu-id="7e40c-232">Office 365 considerations</span></span>

<span data-ttu-id="7e40c-233">任何将启用直接路由的用户都必须托管在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="7e40c-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="7e40c-234">对于具有本地 Skype for Business 服务器或 Lync Server 的混合部署, 在将用户配置为使用与团队的直接路由之前, 需要将用户移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="7e40c-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="7e40c-235">必须为团队启用直接路由实现范围内的所有用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="7e40c-236">必须为你的 Office 365 租户启用一个或多个域, 因为\*onmicrosoft.com 域不能与直接路由一起使用。</span><span class="sxs-lookup"><span data-stu-id="7e40c-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="7e40c-237">有关域和 Office 365 租户的详细信息, 请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-238">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-238">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-239">确定是否需要将任何用户迁移到 Skype for business Online 以支持直接路由。</span><span class="sxs-lookup"><span data-stu-id="7e40c-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="7e40c-240">标识需要为团队启用的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-241">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-241">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-242">记录需要移动到 Skype for Business Online 并为团队启用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="7e40c-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="7e40c-243">SBC 注意事项</span><span class="sxs-lookup"><span data-stu-id="7e40c-243">SBC considerations</span></span>

<span data-ttu-id="7e40c-244">需要使用经认证且支持的会话边界控制器 (SBCs), 需要将其配对到直接路由服务才能为你的用户提供 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="7e40c-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="7e40c-245">有关已验证的 SBCs 的列表, 请参阅[支持的会话边界控制器](direct-routing-plan.md#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="7e40c-246">根据你的环境、位置数和语音路由需求, 你可能需要部署多个 SBCs 以支持你的用户群。</span><span class="sxs-lookup"><span data-stu-id="7e40c-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="7e40c-247">SBC 域名称</span><span class="sxs-lookup"><span data-stu-id="7e40c-247">SBC domain names</span></span>

<span data-ttu-id="7e40c-248">与直接路由配对的每个 SBC 必须具有唯一的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="7e40c-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="7e40c-249">SBC DNS 名称必须来自 Office 365 租户中注册的其中一个域名。</span><span class="sxs-lookup"><span data-stu-id="7e40c-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="7e40c-250">如果你的租户已分配有多个域名, 则你可以在规划 SBCs "DNS 名称时使用这些域名中的任何一个名称。</span><span class="sxs-lookup"><span data-stu-id="7e40c-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e40c-251">不允许对 SBC DNS 名称使用 \*. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="7e40c-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="7e40c-252">证书</span><span class="sxs-lookup"><span data-stu-id="7e40c-252">Certificates</span></span>

<span data-ttu-id="7e40c-253">使用直接路由部署的每个 SBC 都需要从受支持的证书颁发机构列表获得证书。</span><span class="sxs-lookup"><span data-stu-id="7e40c-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="7e40c-254">证书必须在 "主题"、"主题备用名称" 或 "公用名称" 字段中包含 SBC DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="7e40c-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="7e40c-255">也支持使用 SBCs 的通配符证书。</span><span class="sxs-lookup"><span data-stu-id="7e40c-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="7e40c-256">有关详细信息和受支持的证书颁发机构的列表, 请参阅[SBC 的公共受信任证书](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="7e40c-257">SBC IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="7e40c-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="7e40c-258">每个 SBC 都必须使用从 Office 365 数据中心访问的公共 IP 地址进行配置。</span><span class="sxs-lookup"><span data-stu-id="7e40c-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="7e40c-259">你还可以配置网络地址转换 (NAT) 以将你的 SBCs 发布到 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="7e40c-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="7e40c-260">SBCs 需要双向连接才能与用于信号和媒体的云服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="7e40c-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="7e40c-261">信号由名为*SIP 代理*的组件处理, 媒体由*媒体处理器*处理。</span><span class="sxs-lookup"><span data-stu-id="7e40c-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="7e40c-262">你需要在每个 SBC 上为 SIP 信号和媒体定义特定的端口号, 并将防火墙配置为允许指向这些端口的双向通信以及与其关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7e40c-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="7e40c-263">有关更多详细信息, 请参阅[SIP 信号: fqdn](direct-routing-plan.md#sip-signaling-fqdns)和[媒体流量: 端口范围](direct-routing-plan.md#media-traffic-port-ranges)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-263">For more details, see [SIP Signaling: FQDNs](direct-routing-plan.md#sip-signaling-fqdns) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="7e40c-264">强烈建议基于 SBC 模型为每个 SBC 设置最大并发会话限制。</span><span class="sxs-lookup"><span data-stu-id="7e40c-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="7e40c-265">然后, 该限制将在 SBC 运行在其容量或接近其容量时触发通知。</span><span class="sxs-lookup"><span data-stu-id="7e40c-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-266">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-266">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-267">确定要部署 SBCs 的位置。</span><span class="sxs-lookup"><span data-stu-id="7e40c-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="7e40c-268">为你计划部署的每个 SBC 确定一个 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="7e40c-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="7e40c-269">根据 SBC 域名决策, 确定你是否要使用通配符证书支持部署中的所有 SBCs 或每个 SBC 专用的证书。</span><span class="sxs-lookup"><span data-stu-id="7e40c-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="7e40c-270">确定从哪个公共证书颁发机构获取用于您的 SBCs 的证书。</span><span class="sxs-lookup"><span data-stu-id="7e40c-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="7e40c-271">为你要部署的每个 SBC 定义一个公共 IP 地址/端口对, 并确定你是将公共 IP 地址分配给 SBCs 还是使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="7e40c-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="7e40c-272">标识每个 SBC 支持或可以处理的最大并发会话数。</span><span class="sxs-lookup"><span data-stu-id="7e40c-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="7e40c-273">确定使用 "媒体绕过" 配置哪一个 SBCs。</span><span class="sxs-lookup"><span data-stu-id="7e40c-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-274">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-274">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-275">通过使用以下示例表来记录针对 SBCs 进行的每个决策。</span><span class="sxs-lookup"><span data-stu-id="7e40c-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="7e40c-276">使用以下模板记录直接路由部署的 SBC 详细信息。</span><span class="sxs-lookup"><span data-stu-id="7e40c-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="7e40c-277">**SBC DNS 名称 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="7e40c-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="7e40c-278">**SBC 和型号**</span><span class="sxs-lookup"><span data-stu-id="7e40c-278">**SBC make and model**</span></span> | <span data-ttu-id="7e40c-279">**证书**</span><span class="sxs-lookup"><span data-stu-id="7e40c-279">**Certificate**</span></span> | <span data-ttu-id="7e40c-280">**位置**</span><span class="sxs-lookup"><span data-stu-id="7e40c-280">**Location**</span></span>  | <span data-ttu-id="7e40c-281">**IP 地址**</span><span class="sxs-lookup"><span data-stu-id="7e40c-281">**IP address**</span></span> | <span data-ttu-id="7e40c-282">**SIP 信号端口**</span><span class="sxs-lookup"><span data-stu-id="7e40c-282">**SIP signaling port**</span></span> | <span data-ttu-id="7e40c-283">**NAT?**</span><span class="sxs-lookup"><span data-stu-id="7e40c-283">**NAT?**</span></span> | <span data-ttu-id="7e40c-284">**最大并发会话数**</span><span class="sxs-lookup"><span data-stu-id="7e40c-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="7e40c-285">**已启用媒体旁路？**</span><span class="sxs-lookup"><span data-stu-id="7e40c-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="7e40c-286">SBC-Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="7e40c-287">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-287">TBD</span></span> | <span data-ttu-id="7e40c-288">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-288">\*.contoso.com</span></span> | <span data-ttu-id="7e40c-289">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="7e40c-289">Amsterdam</span></span> | <span data-ttu-id="7e40c-290">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-290">TBD</span></span> | <span data-ttu-id="7e40c-291">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-291">TBD</span></span> | <span data-ttu-id="7e40c-292">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-292">Yes</span></span> | <span data-ttu-id="7e40c-293">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-293">TBD</span></span> | <span data-ttu-id="7e40c-294">否</span><span class="sxs-lookup"><span data-stu-id="7e40c-294">No</span></span> |
> | <span data-ttu-id="7e40c-295">SBC-Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="7e40c-296">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-296">TBD</span></span> | <span data-ttu-id="7e40c-297">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-297">\*.contoso.com</span></span> | <span data-ttu-id="7e40c-298">中国香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="7e40c-298">Hong Kong SAR</span></span> | <span data-ttu-id="7e40c-299">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-299">TBD</span></span> | <span data-ttu-id="7e40c-300">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-300">TBD</span></span> | <span data-ttu-id="7e40c-301">否</span><span class="sxs-lookup"><span data-stu-id="7e40c-301">No</span></span> | <span data-ttu-id="7e40c-302">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-302">TBD</span></span> | <span data-ttu-id="7e40c-303">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-303">Yes</span></span> |
> | <span data-ttu-id="7e40c-304">SBC-Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="7e40c-305">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-305">TBD</span></span> | <span data-ttu-id="7e40c-306">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-306">\*.contoso.com</span></span> | <span data-ttu-id="7e40c-307">约翰内斯堡</span><span class="sxs-lookup"><span data-stu-id="7e40c-307">Johannesburg</span></span> | <span data-ttu-id="7e40c-308">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-308">TBD</span></span> | <span data-ttu-id="7e40c-309">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-309">TBD</span></span> | <span data-ttu-id="7e40c-310">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-310">Yes</span></span> | <span data-ttu-id="7e40c-311">TBD</span><span class="sxs-lookup"><span data-stu-id="7e40c-311">TBD</span></span> | <span data-ttu-id="7e40c-312">是</span><span class="sxs-lookup"><span data-stu-id="7e40c-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="7e40c-313">语音路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-313">Voice routing</span></span>

<span data-ttu-id="7e40c-314">您需要将 Microsoft Phone 系统配置为将呼叫路由到特定 SBCs 以进行直接路由。</span><span class="sxs-lookup"><span data-stu-id="7e40c-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="7e40c-315">您可以根据以下内容配置语音路由:</span><span class="sxs-lookup"><span data-stu-id="7e40c-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="7e40c-316">名为 "数字模式"。</span><span class="sxs-lookup"><span data-stu-id="7e40c-316">Called number pattern.</span></span>

-   <span data-ttu-id="7e40c-317">称为 "号码模式" + 进行呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="7e40c-318">呼叫路由由以下元素组成:</span><span class="sxs-lookup"><span data-stu-id="7e40c-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="7e40c-319">语音路由策略-PSTN 使用的容器;可以分配给用户或多个用户</span><span class="sxs-lookup"><span data-stu-id="7e40c-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="7e40c-320">PSTN 用法–用于语音路由和 PSTN 使用的容器;可以在不同的语音路由策略中共享</span><span class="sxs-lookup"><span data-stu-id="7e40c-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="7e40c-321">语音路由-用于呼叫与模式匹配的呼叫的数字模式和联机 PSTN 网关集</span><span class="sxs-lookup"><span data-stu-id="7e40c-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="7e40c-322">Online PSTN 网关-位于 SBC 的指针还存储通过 SBC 发出调用时应用的配置, 例如, 前 P 声明的身份 (PAI) 或首选编解码器;可以添加到语音路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="7e40c-323">您可以通过直接路由来配置您的语音路线, 以便与通话计划共存。</span><span class="sxs-lookup"><span data-stu-id="7e40c-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="7e40c-324">该配置允许调用计划使用直接路由将某些调用路由到特定的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="7e40c-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="7e40c-325">SBCs 可以指定为 "*活动*" 和 "*备份*"。</span><span class="sxs-lookup"><span data-stu-id="7e40c-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="7e40c-326">这意味着当为此号码模式 (或数字模式 + 特定用户) 配置为活动的 SBC 不可用时, 呼叫将路由到 backup SBC。</span><span class="sxs-lookup"><span data-stu-id="7e40c-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-327">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-327">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-328">确定你将创建的用于支持直接路由实现范围内的用户位置或分支的语音路由策略、PSTN 用法和语音路由。</span><span class="sxs-lookup"><span data-stu-id="7e40c-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-329">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-329">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-330">为你的组织记录语音路由策略、PSTN 使用情况和语音路由。</span><span class="sxs-lookup"><span data-stu-id="7e40c-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="7e40c-331">将为您定义的每个语音路由策略分配的用户记录到文档中。</span><span class="sxs-lookup"><span data-stu-id="7e40c-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="7e40c-332">使用以下模板为直接路由部署记录语音策略。</span><span class="sxs-lookup"><span data-stu-id="7e40c-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="7e40c-333">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="7e40c-333">**PSTN usage**</span></span> | <span data-ttu-id="7e40c-334">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="7e40c-334">**Voice route**</span></span> | <span data-ttu-id="7e40c-335">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="7e40c-335">**Number pattern**</span></span> | <span data-ttu-id="7e40c-336">**优先级**</span><span class="sxs-lookup"><span data-stu-id="7e40c-336">**Priority**</span></span> | <span data-ttu-id="7e40c-337">**SBC**</span><span class="sxs-lookup"><span data-stu-id="7e40c-337">**SBC**</span></span> | <span data-ttu-id="7e40c-338">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e40c-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="7e40c-339">仅限美国</span><span class="sxs-lookup"><span data-stu-id="7e40c-339">US only</span></span> | <span data-ttu-id="7e40c-340">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="7e40c-340">“Redmond 1”</span></span> | <span data-ttu-id="7e40c-341">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="7e40c-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="7e40c-342">1</span><span class="sxs-lookup"><span data-stu-id="7e40c-342">1</span></span> | <span data-ttu-id="7e40c-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="7e40c-344">拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="7e40c-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="7e40c-345">仅限美国</span><span class="sxs-lookup"><span data-stu-id="7e40c-345">US only</span></span> | <span data-ttu-id="7e40c-346">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="7e40c-346">“Redmond 2”</span></span> | <span data-ttu-id="7e40c-347">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="7e40c-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="7e40c-348">2</span><span class="sxs-lookup"><span data-stu-id="7e40c-348">2</span></span> | <span data-ttu-id="7e40c-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="7e40c-350">已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx</span><span class="sxs-lookup"><span data-stu-id="7e40c-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="7e40c-351">仅限美国</span><span class="sxs-lookup"><span data-stu-id="7e40c-351">US only</span></span> | <span data-ttu-id="7e40c-352">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="7e40c-352">"Other +1”</span></span> | <span data-ttu-id="7e40c-353">\^\\+ 1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="7e40c-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="7e40c-354">3</span><span class="sxs-lookup"><span data-stu-id="7e40c-354">3</span></span> | <span data-ttu-id="7e40c-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="7e40c-356">呼叫号码 + 1 XXX XXX xx (除 + 1 425 XXX xx 或 + 1 206 XXX xx 之间) 的路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="7e40c-357">International</span><span class="sxs-lookup"><span data-stu-id="7e40c-357">International</span></span> | <span data-ttu-id="7e40c-358">International</span><span class="sxs-lookup"><span data-stu-id="7e40c-358">International</span></span> | <span data-ttu-id="7e40c-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="7e40c-359">\\d+</span></span> | <span data-ttu-id="7e40c-360">4</span><span class="sxs-lookup"><span data-stu-id="7e40c-360">4</span></span> | <span data-ttu-id="7e40c-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7e40c-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="7e40c-362">任何数字模式的路由</span><span class="sxs-lookup"><span data-stu-id="7e40c-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="7e40c-363">语音路由策略中的 PSTN 用法按顺序应用, 如果在第一次使用中发现了匹配项, 则永远不会评估其他用法。</span><span class="sxs-lookup"><span data-stu-id="7e40c-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="7e40c-364">通话和互操作策略</span><span class="sxs-lookup"><span data-stu-id="7e40c-364">Calling and Interop policies</span></span>

<span data-ttu-id="7e40c-365">直接路由仅受 Microsoft 团队支持。</span><span class="sxs-lookup"><span data-stu-id="7e40c-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="7e40c-366">要通过直接路由放置或接收 PSTN 呼叫, 您需要配置必要的策略以确保在团队中接收传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e40c-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="7e40c-367">启用直接路由的用户不能通过使用 Skype for Business 来放置或接收直接路由呼叫, 因此必须部署团队客户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="7e40c-368">你可以通过以下两种方法中的一种将你的用户配置为将团队设置为其首选客户端调用:</span><span class="sxs-lookup"><span data-stu-id="7e40c-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="7e40c-369">为仅限团队模式配置用户</span><span class="sxs-lookup"><span data-stu-id="7e40c-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="7e40c-370">通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 将团队配置为首选调用客户端。</span><span class="sxs-lookup"><span data-stu-id="7e40c-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="7e40c-371">有关更多详细信息, 请参阅[将 Microsoft 团队设置为用户的首选调用客户端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="7e40c-372">决策点</span><span class="sxs-lookup"><span data-stu-id="7e40c-372">Decision points</span></span>|<ul><li><span data-ttu-id="7e40c-373">确定你将使用哪种方法将团队设置为首选客户端进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e40c-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="7e40c-374">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e40c-374">Next steps</span></span>|<ul><li><span data-ttu-id="7e40c-375">记录要通过互操作和呼叫策略配置的用户。</span><span class="sxs-lookup"><span data-stu-id="7e40c-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="7e40c-376">当用户配置为仅限工作组模式时, 此用户无法再登录 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="7e40c-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="7e40c-377">若要让你的用户在团队客户端中看到 "呼叫" 选项卡, 你需要在租户的组织级别启用专用呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e40c-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="7e40c-378">有关如何启用私人通话的详细信息, 请参阅[启用 Microsoft 团队呼叫](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="7e40c-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="7e40c-379">文档服务决策</span><span class="sxs-lookup"><span data-stu-id="7e40c-379">Document service decisions</span></span>

<span data-ttu-id="7e40c-380">使用本文前面部分中的信息记录您的服务决策。</span><span class="sxs-lookup"><span data-stu-id="7e40c-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="7e40c-381">通常, 本文档将包含以下主要部分:</span><span class="sxs-lookup"><span data-stu-id="7e40c-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="7e40c-382">带有呼叫计划网站支持列表的电话系统</span><span class="sxs-lookup"><span data-stu-id="7e40c-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="7e40c-383">语音邮件配置详细信息</span><span class="sxs-lookup"><span data-stu-id="7e40c-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="7e40c-384">电话系统直接路由用户的许可证分配</span><span class="sxs-lookup"><span data-stu-id="7e40c-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="7e40c-385">SBC 配置详细信息</span><span class="sxs-lookup"><span data-stu-id="7e40c-385">SBC configuration details</span></span>

-   <span data-ttu-id="7e40c-386">语音路由策略和路由详细信息</span><span class="sxs-lookup"><span data-stu-id="7e40c-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="7e40c-387">互操作性和通话策略详细信息</span><span class="sxs-lookup"><span data-stu-id="7e40c-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
