---
title: 做出电话系统直接路由服务决策 - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 了解直接路由，许可，并需要进行决策。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aca4fc24cb39fd1dc607825a73b9f3751992de3d
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569763"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="ce2ac-103">决定我服务</span><span class="sxs-lookup"><span data-stu-id="ce2ac-103">Make my service decisions</span></span>

<span data-ttu-id="ce2ac-104">若要规划的电话系统直接路由 （"直接路由"） 的技术实现，则必须进行一系列服务决策提前更好地准备您的组织，以实现解决方案满足业务要求您已定义。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="ce2ac-105">团队呼叫</span><span class="sxs-lookup"><span data-stu-id="ce2ac-105">Calling in Teams</span></span>

<span data-ttu-id="ce2ac-106">与 Microsoft 团队，用户可以发起和接收电话呼叫或从公用电话交换网 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ce2ac-107">您的用户可以使用自己的专用的电话号码发起和接收国内和国际电话呼叫 （包括语音邮件） 的团队客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="ce2ac-108">直接路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-108">Direct Routing</span></span>

<span data-ttu-id="ce2ac-109">对于能够发起和接收 PSTN 呼叫的团队用户，他们需要为启用电话系统，Office 365 中的功能。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="ce2ac-110">若要启用与 PSTN 连接，您可以使用直接路由授予您的组织能够发起和接收组织外部的电话呼叫通过 PSTN 中的人员。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="ce2ac-111">使用直接路由时，通过第三方提供程序，使您能够继续使用您现有的 PSTN 中继 PSTN 服务提供商提供方便了 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="ce2ac-112">这将允许部署在国家/地区与调用计划 （"调用计划"） 的电话系统不会可用，或在部署中，需要进行维护现有 PSTN 服务提供程序合同或与特定的本地系统的互操作性必填。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="ce2ac-113">直接路由的可用性</span><span class="sxs-lookup"><span data-stu-id="ce2ac-113">Availability of Direct Routing</span></span>

<span data-ttu-id="ce2ac-114">直接路由位于 Office 365 有任何国家/地区。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="ce2ac-115">有关这些国家/地区的列表，请参阅[国际可用性](https://products.office.com/business/international-availability)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="ce2ac-116">确认您的组织可以获取电话系统功能之后, 编译用户位置或办公室，您将可以实施基于在可用的国家 / 地区列表的电话系统的列表。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="ce2ac-117">同时也会指出您打算对您有每个位置启用调用计划或直接路由的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-118">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-118">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-119">标识用户位置或在其中将实现电话系统的办公室。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="ce2ac-120">确定要对您有每个位置启用调用计划或直接路由的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-121">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-122">文档的用户的位置或办公室电话系统要启用。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="ce2ac-123">文档的用户要为每个位置必须启用调用计划或直接路由的列表</span><span class="sxs-lookup"><span data-stu-id="ce2ac-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="ce2ac-124">下面是直接路由网站启用列表的示例。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="ce2ac-125">**Office**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-125">**Office**</span></span>                     | <span data-ttu-id="ce2ac-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-126">**Location**</span></span>   | <span data-ttu-id="ce2ac-127">**电话系统服务**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="ce2ac-128">一个 Epping 旅途</span><span class="sxs-lookup"><span data-stu-id="ce2ac-128">One Epping Road</span></span>                | <span data-ttu-id="ce2ac-129">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="ce2ac-129">Australia</span></span>      | <span data-ttu-id="ce2ac-130">旧 PSTN 服务</span><span class="sxs-lookup"><span data-stu-id="ce2ac-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="ce2ac-131">100 Cyberport 旅途</span><span class="sxs-lookup"><span data-stu-id="ce2ac-131">100 Cyberport Road</span></span>             | <span data-ttu-id="ce2ac-132">（香港特别行政区)</span><span class="sxs-lookup"><span data-stu-id="ce2ac-132">Hong Kong SAR</span></span>  | <span data-ttu-id="ce2ac-133">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="ce2ac-134">一个船坞 Boulevard</span><span class="sxs-lookup"><span data-stu-id="ce2ac-134">One Marina Boulevard</span></span>           | <span data-ttu-id="ce2ac-135">新加坡</span><span class="sxs-lookup"><span data-stu-id="ce2ac-135">Singapore</span></span>      | <span data-ttu-id="ce2ac-136">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="ce2ac-137">32 伦敦桥-街道</span><span class="sxs-lookup"><span data-stu-id="ce2ac-137">32 London Bridge Street</span></span>        | <span data-ttu-id="ce2ac-138">英国</span><span class="sxs-lookup"><span data-stu-id="ce2ac-138">United Kingdom</span></span> | <span data-ttu-id="ce2ac-139">调用计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="ce2ac-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="ce2ac-140">39 quai 是 Président 罗斯福总统那个时代</span><span class="sxs-lookup"><span data-stu-id="ce2ac-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="ce2ac-141">法国</span><span class="sxs-lookup"><span data-stu-id="ce2ac-141">France</span></span>         | <span data-ttu-id="ce2ac-142">调用计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="ce2ac-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="ce2ac-143">电话号码和紧急位置</span><span class="sxs-lookup"><span data-stu-id="ce2ac-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="ce2ac-144">电话系统要求在组织中的每个用户具有唯一直接向内分机 (DID) 电话号码。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="ce2ac-145">使用直接路由时，由 PSTN 服务提供商提供的电话号码和紧急服务。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="ce2ac-146">直接路由中，使用您的用户可以继续使用自己的电话号码，PSTN 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="ce2ac-147">您可以使用以下模板文档的电话号码的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="ce2ac-148">用户</span><span class="sxs-lookup"><span data-stu-id="ce2ac-148">User</span></span> |<span data-ttu-id="ce2ac-149">电话号码</span><span class="sxs-lookup"><span data-stu-id="ce2ac-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="ce2ac-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="ce2ac-150">Emily Braun</span></span> | <span data-ttu-id="ce2ac-151">+ 44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="ce2ac-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="ce2ac-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="ce2ac-152">Lidia Holloway</span></span> | <span data-ttu-id="ce2ac-153">+ 44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="ce2ac-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="ce2ac-154">港 Lahr</span><span class="sxs-lookup"><span data-stu-id="ce2ac-154">Louis Lahr</span></span> | <span data-ttu-id="ce2ac-155">+ 44 23 4567 8921</span><span class="sxs-lookup"><span data-stu-id="ce2ac-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="ce2ac-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="ce2ac-156">Marcel Beauchamp</span></span> | <span data-ttu-id="ce2ac-157">TBA</span><span class="sxs-lookup"><span data-stu-id="ce2ac-157">TBA</span></span> |
> |<span data-ttu-id="ce2ac-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="ce2ac-158">Rachelle Cormier</span></span> | <span data-ttu-id="ce2ac-159">TBA</span><span class="sxs-lookup"><span data-stu-id="ce2ac-159">TBA</span></span> |
> |<span data-ttu-id="ce2ac-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="ce2ac-160">Isabell Potvin</span></span> | <span data-ttu-id="ce2ac-161">TBA</span><span class="sxs-lookup"><span data-stu-id="ce2ac-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="ce2ac-162">语音邮件</span><span class="sxs-lookup"><span data-stu-id="ce2ac-162">Voicemail</span></span>

<span data-ttu-id="ce2ac-163">电话系统的语音邮件，由 Azure 语音邮件服务，支持语音邮件存款仅 Exchange 邮箱和不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-163">Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="ce2ac-164">电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-164">Phone System voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="ce2ac-165">您的业务需求可能需要您禁用语音邮件转录的特定用户或整个组织中的每个人。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="ce2ac-166">如果您的组织决定保留启用语音邮件转录，您需要还考虑是否需要启用语音邮件转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="ce2ac-167">有关详细信息，请参阅[设置您的组织中的语音邮件策略](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="ce2ac-168">有关在电话系统的实施中的语音邮件的详细信息，请参阅[设置电话系统的语音邮件](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-168">For more information about voicemail in a Phone System implementation, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-169">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-169">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-170">决定是否将直接路由中实现中启用电话系统的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-170">Decide whether you’ll enable Phone System voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="ce2ac-171">决定是否将启用或禁用语音邮件转录和语音邮件转录亵渎屏蔽在整个组织或特定用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-172">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-173">如果适用，记录以支持电话系统的语音邮件的决策点。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-173">If applicable, document the decision points to support Phone System voicemail.</span></span><li><span data-ttu-id="ce2ac-174">如果您将启用或禁用语音邮件、 语音邮件转录和仅为特定用户的语音邮件转录亵渎遮蔽，文档的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="ce2ac-175">按下表可以记录调用计划实现的电话系统的语音邮件详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-175">Phone System voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="ce2ac-176">**User**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-176">**User**</span></span>         | <span data-ttu-id="ce2ac-177">**Exchange 邮箱**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-177">**Exchange mailbox**</span></span> | <span data-ttu-id="ce2ac-178">**启用语音邮件？**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-178">**Enable voicemail?**</span></span> | <span data-ttu-id="ce2ac-179">**语音邮件转录**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-179">**Voicemail transcription**</span></span> | <span data-ttu-id="ce2ac-180">**语音邮件转录亵渎屏蔽**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="ce2ac-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="ce2ac-181">Emily Braun</span></span>      | <span data-ttu-id="ce2ac-182">Online</span><span class="sxs-lookup"><span data-stu-id="ce2ac-182">Online</span></span>               | <span data-ttu-id="ce2ac-183">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-183">Yes</span></span>                   | <span data-ttu-id="ce2ac-184">已启用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-184">Enabled</span></span>                     | <span data-ttu-id="ce2ac-185">已启用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-185">Enabled</span></span>                                       |
> | <span data-ttu-id="ce2ac-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="ce2ac-186">Lidia Holloway</span></span>   | <span data-ttu-id="ce2ac-187">Online</span><span class="sxs-lookup"><span data-stu-id="ce2ac-187">Online</span></span>               | <span data-ttu-id="ce2ac-188">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-188">Yes</span></span>                   | <span data-ttu-id="ce2ac-189">已启用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-189">Enabled</span></span>                     | <span data-ttu-id="ce2ac-190">已禁用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-190">Disabled</span></span>                                      |
> | <span data-ttu-id="ce2ac-191">港 Lahr</span><span class="sxs-lookup"><span data-stu-id="ce2ac-191">Louis Lahr</span></span>       | <span data-ttu-id="ce2ac-192">本地部署</span><span class="sxs-lookup"><span data-stu-id="ce2ac-192">On-premises</span></span>          | <span data-ttu-id="ce2ac-193">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-193">Yes</span></span>                   | <span data-ttu-id="ce2ac-194">已启用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-194">Enabled</span></span>                     | <span data-ttu-id="ce2ac-195">已启用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-195">Enabled</span></span>                                       |
> | <span data-ttu-id="ce2ac-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="ce2ac-196">Marcel Beauchamp</span></span> | <span data-ttu-id="ce2ac-197">本地部署</span><span class="sxs-lookup"><span data-stu-id="ce2ac-197">On-premises</span></span>          | <span data-ttu-id="ce2ac-198">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-198">Yes</span></span>                   | <span data-ttu-id="ce2ac-199">已禁用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-199">Disabled</span></span>                    | <span data-ttu-id="ce2ac-200">不适用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-200">N/A</span></span>                                           |
> | <span data-ttu-id="ce2ac-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="ce2ac-201">Rachelle Cormier</span></span> | <span data-ttu-id="ce2ac-202">Online</span><span class="sxs-lookup"><span data-stu-id="ce2ac-202">Online</span></span>               | <span data-ttu-id="ce2ac-203">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-203">Yes</span></span>                   | <span data-ttu-id="ce2ac-204">已禁用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-204">Disabled</span></span>                    | <span data-ttu-id="ce2ac-205">不适用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-205">N/A</span></span>                                           |
> | <span data-ttu-id="ce2ac-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="ce2ac-206">Isabell Potvin</span></span>   | <span data-ttu-id="ce2ac-207">本地部署</span><span class="sxs-lookup"><span data-stu-id="ce2ac-207">On-premises</span></span>          | <span data-ttu-id="ce2ac-208">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-208">Yes</span></span>                   | <span data-ttu-id="ce2ac-209">已禁用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-209">Disabled</span></span>                    | <span data-ttu-id="ce2ac-210">不适用</span><span class="sxs-lookup"><span data-stu-id="ce2ac-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="ce2ac-211">若要使用团队和语音邮件，您的用户必须具有 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="ce2ac-212">有关详细信息，请参阅[如何 Exchange 和 Microsoft 团队进行交互](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="ce2ac-213">许可直接路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="ce2ac-214">如果组织打算使用直接路由，则需要获得所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="ce2ac-215">直接路由中的用户必须具有以下许可证分配 Office 365 中：</span><span class="sxs-lookup"><span data-stu-id="ce2ac-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="ce2ac-216">Microsoft 电话系统</span><span class="sxs-lookup"><span data-stu-id="ce2ac-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="ce2ac-217">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce2ac-217">Microsoft Teams</span></span>

-   <span data-ttu-id="ce2ac-218">音频会议</span><span class="sxs-lookup"><span data-stu-id="ce2ac-218">Audio Conferencing</span></span>

<span data-ttu-id="ce2ac-219">需要向计划的会议，外部参与者通过向他们拨出或通过提供的电话拨入式号码音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="ce2ac-220">时为情况下，外部参与者拨出，音频会议服务呼叫使用放置 online 呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="ce2ac-221">音频会议许可证是可选的和所需的用户仅将组织者团队包括音频会议的会议。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="ce2ac-222">要提供免费的会议桥接电话号码，并以支持会议拨出式国际电话号码，您应为组织设置[Communications 字幕式](what-are-communications-credits.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="ce2ac-223">音频会议和电话系统可以授权单独作为附加服务的现有用户拥有 Office 365 E3 或 E1 订阅计划;它们已作为 Office 365 E5 订阅计划的一部分包含。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="ce2ac-224">您还可以使用直接路由中的第三方 Pbx 其呼叫路由时启用了调用计划的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="ce2ac-225">有关详细信息，请参阅[授权和其他要求的直接路由](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-226">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-226">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-227">如果您的组织没有所需的电话系统许可证，决定是否按您现有的 Office 365 订阅逐步升级，或获取电话系统加载项服务，您将能够获得的电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="ce2ac-228">决定是否需要 Communications 字幕式直接路由中实现的。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-229">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-229">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-230">文档将分配电话系统许可证的部门、 部门、 office 或用户组。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="ce2ac-231">范围与免费电话号码的音频会议时，文档将启用 Communications 字幕式部门、 部门、 office 或用户组。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="ce2ac-232">Office 365 注意事项</span><span class="sxs-lookup"><span data-stu-id="ce2ac-232">Office 365 considerations</span></span>

<span data-ttu-id="ce2ac-233">将为直接路由启用的任何用户必须驻留在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="ce2ac-234">对于使用本地 Skype 业务服务器或 Lync Server 混合部署，需要将用户迁移到 Skype 业务 online 之前将其配置为使用直接路由团队。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="ce2ac-235">直接路由中实现的范围中的所有用户必须都启用团队。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="ce2ac-236">Office 365 租户必须启用与一个或多个域，因为默认\*。 onmicrosoft.com 域不能用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="ce2ac-237">有关域和 Office 365 租户的详细信息，请参阅[域常见问题](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-238">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-238">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-239">决定是否需要迁移到 Skype 业务 Online 支持直接路由中的任何用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="ce2ac-240">确定需要团队启用的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-241">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-241">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-242">文档的用户移动到 Skype 的业务联机和团队启用所需的列表。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="ce2ac-243">SBC 注意事项</span><span class="sxs-lookup"><span data-stu-id="ce2ac-243">SBC considerations</span></span>

<span data-ttu-id="ce2ac-244">您需要使用认证和受支持的会话边界控制器 (Sbc) 所需的直接路由服务为用户提供 PSTN 连接到配对。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="ce2ac-245">认证的 Sbc 的列表，请参阅[支持的会话边界控制器](direct-routing-plan.md#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="ce2ac-246">根据您的环境，位置数，以及语音路由要求，您可能需要部署多个 SBCs 以支持用户群。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="ce2ac-247">SBC 域名</span><span class="sxs-lookup"><span data-stu-id="ce2ac-247">SBC domain names</span></span>

<span data-ttu-id="ce2ac-248">每个直接路由与配对的 SBC 必须具有唯一的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="ce2ac-249">SBC DNS 名称必须介于 1 中的 Office 365 租户注册的域名。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="ce2ac-250">如果您的租户已分配多个域名，您可以使用这些域名的任何规划 SBCs 的 DNS 名称时。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce2ac-251">使用 \*。 不允许 onmicrosoft.com 的 SBC DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="ce2ac-252">证书</span><span class="sxs-lookup"><span data-stu-id="ce2ac-252">Certificates</span></span>

<span data-ttu-id="ce2ac-253">每个直接路由与部署的 SBC 要求从列表中受支持的证书颁发机构获取证书。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="ce2ac-254">证书必须主题、 使用者替代名称或公共名称字段中包括的 SBC DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="ce2ac-255">此外支持与 Sbc 的通配符证书的使用。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="ce2ac-256">有关受支持的证书颁发机构的列表和详细信息，请参阅[SBC 的受信任的公共证书](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="ce2ac-257">SBC IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="ce2ac-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="ce2ac-258">必须使用可从 Office 365 数据中心访问公共 IP 地址配置每个 SBC。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="ce2ac-259">您还可以配置网络地址转换 (NAT) 将您的 Sbc 发布到 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="ce2ac-260">Sbc 需要双向连接与信号和媒体的云服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="ce2ac-261">信号是通过名为*SIP 代理服务器*的组件和处理媒体处理*媒体处理器*。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="ce2ac-262">您需要在每个 SIP 信号和媒体的 SBC 上定义特定端口号，配置防火墙以允许对这些端口和其关联的 IP 地址的双向通信。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="ce2ac-263">有关详细信息，请参阅[SIP 信号： Fqdn 和防火墙端口](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports)和[媒体流量： 端口范围](direct-routing-plan.md#media-traffic-port-ranges)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-263">For more details, see [SIP Signaling: FQDNs and firewall ports](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="ce2ac-264">我们强烈建议基于 SBC 模型的每个 SBC 设置最大并发会话限制。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="ce2ac-265">SBC 或将达到其容量运行时，该限制将然后触发通知。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-266">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-266">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-267">决定哪些位置将部署 SBCs。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="ce2ac-268">确定每个 SBC 您打算部署的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="ce2ac-269">根据 SBC 域名称决策，决定是否要使用通配符证书支持您的部署中的所有 SBCs 或专用每 SBC 证书。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="ce2ac-270">决定哪些公共证书颁发机构您将为您 SBCs 从获取证书。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="ce2ac-271">定义公共 IP 地址/端口对每个 SBC 您将部署，并决定是否将在分配 SBCs 公共 IP 地址，或使用 nat。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="ce2ac-272">识别每个 SBC 支持的并发会话的最大数目或可以处理。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="ce2ac-273">决定将使用媒体绕过配置的 Sbc。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-274">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-274">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-275">记录每个的 Sbc 中使用如下表所做的决策。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="ce2ac-276">使用以下模板文档直接路由中部署的 SBC 详细信息。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="ce2ac-277">**SBC DNS 域名 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="ce2ac-278">**SBC 品牌和型号**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-278">**SBC make and model**</span></span> | <span data-ttu-id="ce2ac-279">**证书**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-279">**Certificate**</span></span> | <span data-ttu-id="ce2ac-280">**位置**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-280">**Location**</span></span>  | <span data-ttu-id="ce2ac-281">**IP 地址**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-281">**IP address**</span></span> | <span data-ttu-id="ce2ac-282">**SIP 信号端口**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-282">**SIP signaling port**</span></span> | <span data-ttu-id="ce2ac-283">**NAT？**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-283">**NAT?**</span></span> | <span data-ttu-id="ce2ac-284">**最大并发会话**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="ce2ac-285">**启用媒体绕过？**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="ce2ac-286">SBC Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="ce2ac-287">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-287">TBD</span></span> | <span data-ttu-id="ce2ac-288">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-288">\*.contoso.com</span></span> | <span data-ttu-id="ce2ac-289">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="ce2ac-289">Amsterdam</span></span> | <span data-ttu-id="ce2ac-290">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-290">TBD</span></span> | <span data-ttu-id="ce2ac-291">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-291">TBD</span></span> | <span data-ttu-id="ce2ac-292">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-292">Yes</span></span> | <span data-ttu-id="ce2ac-293">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-293">TBD</span></span> | <span data-ttu-id="ce2ac-294">否</span><span class="sxs-lookup"><span data-stu-id="ce2ac-294">No</span></span> |
> | <span data-ttu-id="ce2ac-295">SBC Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="ce2ac-296">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-296">TBD</span></span> | <span data-ttu-id="ce2ac-297">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-297">\*.contoso.com</span></span> | <span data-ttu-id="ce2ac-298">（香港特别行政区)</span><span class="sxs-lookup"><span data-stu-id="ce2ac-298">Hong Kong SAR</span></span> | <span data-ttu-id="ce2ac-299">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-299">TBD</span></span> | <span data-ttu-id="ce2ac-300">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-300">TBD</span></span> | <span data-ttu-id="ce2ac-301">否</span><span class="sxs-lookup"><span data-stu-id="ce2ac-301">No</span></span> | <span data-ttu-id="ce2ac-302">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-302">TBD</span></span> | <span data-ttu-id="ce2ac-303">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-303">Yes</span></span> |
> | <span data-ttu-id="ce2ac-304">SBC Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="ce2ac-305">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-305">TBD</span></span> | <span data-ttu-id="ce2ac-306">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-306">\*.contoso.com</span></span> | <span data-ttu-id="ce2ac-307">约翰内斯堡</span><span class="sxs-lookup"><span data-stu-id="ce2ac-307">Johannesburg</span></span> | <span data-ttu-id="ce2ac-308">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-308">TBD</span></span> | <span data-ttu-id="ce2ac-309">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-309">TBD</span></span> | <span data-ttu-id="ce2ac-310">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-310">Yes</span></span> | <span data-ttu-id="ce2ac-311">TBD</span><span class="sxs-lookup"><span data-stu-id="ce2ac-311">TBD</span></span> | <span data-ttu-id="ce2ac-312">是</span><span class="sxs-lookup"><span data-stu-id="ce2ac-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="ce2ac-313">语音路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-313">Voice routing</span></span>

<span data-ttu-id="ce2ac-314">您需要配置 Microsoft 电话系统，以将呼叫路由至特定的 Sbc 直接路由的。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="ce2ac-315">您可以配置基于语音路由：</span><span class="sxs-lookup"><span data-stu-id="ce2ac-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="ce2ac-316">呼叫的号码模式。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-316">Called number pattern.</span></span>

-   <span data-ttu-id="ce2ac-317">呼叫的号码模式 + 调用的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="ce2ac-318">呼叫路由组成的以下元素：</span><span class="sxs-lookup"><span data-stu-id="ce2ac-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="ce2ac-319">语音路由策略 – 容器的 PSTN 用法;可分配给用户或多个用户</span><span class="sxs-lookup"><span data-stu-id="ce2ac-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="ce2ac-320">PSTN 用法 – 语音路由和 PSTN 用法; 容器可以共享在不同的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="ce2ac-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="ce2ac-321">语音路由 – 号码模式和联机 PSTN 网关要用于呼叫呼叫号码与模式匹配的其中一组</span><span class="sxs-lookup"><span data-stu-id="ce2ac-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="ce2ac-322">联机 PSTN 网关-指针位于 SBC，还会存储通过 SBC，如转发 P 已断言标识 (PAI) 或首选的编解码器; 发出呼叫时应用的配置可以添加到语音路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="ce2ac-323">您可以直接路由与调用计划的共存配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="ce2ac-324">配置允许调用计划路由到特定的 Sbc 呼叫的一些使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="ce2ac-325">Sbc 可以被指定为*活动状态*且*备份*。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="ce2ac-326">这意味着，在 SBC 配置为活动，此数字模式 — 号码模式 + 特定用户或 — 不可用，呼叫将被路由至备份 SBC。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-327">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-327">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-328">决定语音路由策略、 PSTN 用法和语音路由，您将创建为支持用户位置或直接路由实现的范围内的办公室。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-329">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-329">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-330">文档语音路由策略、 PSTN 用法和您的组织的语音路由。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="ce2ac-331">文档用户对于您定义的每个语音路由策略分配。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="ce2ac-332">使用以下模板文档直接路由中部署的语音策略。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="ce2ac-333">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-333">**PSTN usage**</span></span> | <span data-ttu-id="ce2ac-334">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-334">**Voice route**</span></span> | <span data-ttu-id="ce2ac-335">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-335">**Number pattern**</span></span> | <span data-ttu-id="ce2ac-336">**优先级**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-336">**Priority**</span></span> | <span data-ttu-id="ce2ac-337">**SBC**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-337">**SBC**</span></span> | <span data-ttu-id="ce2ac-338">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce2ac-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="ce2ac-339">仅限美国</span><span class="sxs-lookup"><span data-stu-id="ce2ac-339">US only</span></span> | <span data-ttu-id="ce2ac-340">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="ce2ac-340">“Redmond 1”</span></span> | <span data-ttu-id="ce2ac-341">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="ce2ac-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="ce2ac-342">1</span><span class="sxs-lookup"><span data-stu-id="ce2ac-342">1</span></span> | <span data-ttu-id="ce2ac-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="ce2ac-344">活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码</span><span class="sxs-lookup"><span data-stu-id="ce2ac-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="ce2ac-345">仅限美国</span><span class="sxs-lookup"><span data-stu-id="ce2ac-345">US only</span></span> | <span data-ttu-id="ce2ac-346">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="ce2ac-346">“Redmond 2”</span></span> | <span data-ttu-id="ce2ac-347">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="ce2ac-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="ce2ac-348">2</span><span class="sxs-lookup"><span data-stu-id="ce2ac-348">2</span></span> | <span data-ttu-id="ce2ac-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="ce2ac-350">备份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX 拨电话号码</span><span class="sxs-lookup"><span data-stu-id="ce2ac-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="ce2ac-351">仅限美国</span><span class="sxs-lookup"><span data-stu-id="ce2ac-351">US only</span></span> | <span data-ttu-id="ce2ac-352">"其他 + 1"</span><span class="sxs-lookup"><span data-stu-id="ce2ac-352">"Other +1”</span></span> | <span data-ttu-id="ce2ac-353">\^\\+ 1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="ce2ac-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="ce2ac-354">3</span><span class="sxs-lookup"><span data-stu-id="ce2ac-354">3</span></span> | <span data-ttu-id="ce2ac-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="ce2ac-356">呼叫的号码的路由 （除 +1 425 XXX XX XX 或 +1 206 XXX XX XX） + 1 XXX XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="ce2ac-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="ce2ac-357">International</span><span class="sxs-lookup"><span data-stu-id="ce2ac-357">International</span></span> | <span data-ttu-id="ce2ac-358">International</span><span class="sxs-lookup"><span data-stu-id="ce2ac-358">International</span></span> | <span data-ttu-id="ce2ac-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="ce2ac-359">\\d+</span></span> | <span data-ttu-id="ce2ac-360">4</span><span class="sxs-lookup"><span data-stu-id="ce2ac-360">4</span></span> | <span data-ttu-id="ce2ac-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce2ac-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="ce2ac-362">任何号码模式的路由</span><span class="sxs-lookup"><span data-stu-id="ce2ac-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="ce2ac-363">在语音路由策略中的 PSTN 用法的顺序，应用，如果第一个用法中找到匹配项，则永远不会计算其他用法。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="ce2ac-364">呼叫和互操作策略</span><span class="sxs-lookup"><span data-stu-id="ce2ac-364">Calling and Interop policies</span></span>

<span data-ttu-id="ce2ac-365">与 Microsoft 团队才支持直接路由。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="ce2ac-366">若要发起或接收直接路由通过 PSTN 呼叫，您需要配置所需的策略，以确保团队中收到传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ce2ac-367">启用直接路由不能发起或接收的用户路由呼叫定向使用 Skype 业务，并因此必须部署团队客户端。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="ce2ac-368">您可以配置用户设置为其首选的客户端的呼叫的团队，通过以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="ce2ac-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="ce2ac-369">配置为仅团队模式的用户</span><span class="sxs-lookup"><span data-stu-id="ce2ac-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="ce2ac-370">配置为首选调用客户端通过分配 TeamsCallingPolicy 和 TeamsInteropPolicy 团队。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="ce2ac-371">有关详细信息，请参阅[设置为首选的 Microsoft 团队呼叫的用户的客户端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="ce2ac-372">决策点</span><span class="sxs-lookup"><span data-stu-id="ce2ac-372">Decision points</span></span>|<ul><li><span data-ttu-id="ce2ac-373">决定哪种方法，您将使用设置为首选客户端的呼叫的团队。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="ce2ac-374">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce2ac-374">Next steps</span></span>|<ul><li><span data-ttu-id="ce2ac-375">文档用互操作和呼叫策略来配置的用户。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="ce2ac-376">当用户配置为仅团队模式时，此用户可以不再登录到 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="ce2ac-377">要让您用户可以查看团队客户端中的呼叫选项卡，您需要启用专用的租户组织级别呼叫。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="ce2ac-378">有关如何启用接听私人电话的详细信息，请参阅[启用 Microsoft 团队呼叫](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="ce2ac-379">文档服务决策</span><span class="sxs-lookup"><span data-stu-id="ce2ac-379">Document service decisions</span></span>

<span data-ttu-id="ce2ac-380">使用从本文前面几节的信息来记录您服务的决策。</span><span class="sxs-lookup"><span data-stu-id="ce2ac-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="ce2ac-381">一般情况下，本文档将包含以下主要章节：</span><span class="sxs-lookup"><span data-stu-id="ce2ac-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="ce2ac-382">与调用计划网站启用列表的电话系统</span><span class="sxs-lookup"><span data-stu-id="ce2ac-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="ce2ac-383">语音邮件配置详细信息</span><span class="sxs-lookup"><span data-stu-id="ce2ac-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="ce2ac-384">电话系统直接路由的用户的的许可证分配</span><span class="sxs-lookup"><span data-stu-id="ce2ac-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="ce2ac-385">SBC 配置详细信息</span><span class="sxs-lookup"><span data-stu-id="ce2ac-385">SBC configuration details</span></span>

-   <span data-ttu-id="ce2ac-386">语音路由策略和路由详细信息</span><span class="sxs-lookup"><span data-stu-id="ce2ac-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="ce2ac-387">互操作性和调用策略的详细信息</span><span class="sxs-lookup"><span data-stu-id="ce2ac-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
