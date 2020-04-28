---
title: Microsoft Teams 中的共享线路外观
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 了解如何在 Microsoft 团队中向用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 52f4257d5e5603c0f7ed812d5ab677a18ed47fb9
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905544"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="9fd63-103">Microsoft Teams 中的共享线路外观</span><span class="sxs-lookup"><span data-stu-id="9fd63-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="9fd63-104">共享行的外观是委派功能的一部分，允许用户选择代理人代表他们应答或处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="9fd63-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="9fd63-105">如果用户有一个管理助理负责定期处理用户的通话，此功能将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="9fd63-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="9fd63-106">在共享行外观的上下文中，经理是指授权代理人代表他们拨打或接听呼叫的人员，而代理人可以代表其他人拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="9fd63-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fd63-107">此功能仅适用于 "仅限团队" 部署模式。</span><span class="sxs-lookup"><span data-stu-id="9fd63-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="9fd63-108">有关团队部署模式的更多详细信息，请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="9fd63-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="9fd63-109">需要许可证</span><span class="sxs-lookup"><span data-stu-id="9fd63-109">License required</span></span>

<span data-ttu-id="9fd63-110">用户必须使用具有 PSTN 连接的电话系统（呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy）作为代理人，或者设置委派并允许其他人代表他们进行或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="9fd63-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="9fd63-111">管理者和代理人都需要具有 PSTN 连接的电话系统（呼叫计划许可证或直接路由 OnlineVoiceRoutingPolicy）。</span><span class="sxs-lookup"><span data-stu-id="9fd63-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="9fd63-112">共享线路体验是委派的一部分，并包含在电话系统中。</span><span class="sxs-lookup"><span data-stu-id="9fd63-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="9fd63-113">有关许可模型的其他详细信息，请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="9fd63-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="9fd63-114">配置委派和共享行的外观</span><span class="sxs-lookup"><span data-stu-id="9fd63-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="9fd63-115">委派和共享行的外观是用户驱动的功能：没有要配置的管理员设置。</span><span class="sxs-lookup"><span data-stu-id="9fd63-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="9fd63-116">有关如何使用该功能的信息，请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="9fd63-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="9fd63-117">租户管理员可通过**TeamsCallingPolicy AllowDelegation**设置或通过团队管理门户启用委派，此功能将起作用。</span><span class="sxs-lookup"><span data-stu-id="9fd63-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="9fd63-118">租户管理员还可以为团队管理中心中的用户配置委派关系。</span><span class="sxs-lookup"><span data-stu-id="9fd63-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="9fd63-119">此外，最终用户还可以直接在团队中配置其委派关系。</span><span class="sxs-lookup"><span data-stu-id="9fd63-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="9fd63-120">租户管理员或用户无法彼此阻止配置，但团队管理中心和团队客户应在这两个位置中准确显示此关系。</span><span class="sxs-lookup"><span data-stu-id="9fd63-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9fd63-121">当租户管理员为用户关闭委派时（在已启用）时，他们还需要清理团队管理中心中该用户的委派关系，以避免不正确的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="9fd63-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="9fd63-122">共享行外观功能的可用性</span><span class="sxs-lookup"><span data-stu-id="9fd63-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="9fd63-123">以下应用和设备当前支持共享行的外观。</span><span class="sxs-lookup"><span data-stu-id="9fd63-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="9fd63-124">功能</span><span class="sxs-lookup"><span data-stu-id="9fd63-124">Capability</span></span> | <span data-ttu-id="9fd63-125">团队桌面版</span><span class="sxs-lookup"><span data-stu-id="9fd63-125">Teams Desktop</span></span> | <span data-ttu-id="9fd63-126">团队 Mac 应用</span><span class="sxs-lookup"><span data-stu-id="9fd63-126">Teams Mac App</span></span> | <span data-ttu-id="9fd63-127">团队 Web App （Edge）</span><span class="sxs-lookup"><span data-stu-id="9fd63-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="9fd63-128">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="9fd63-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="9fd63-129">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="9fd63-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="9fd63-130">设置委派</span><span class="sxs-lookup"><span data-stu-id="9fd63-130">Set up delegation</span></span> | <span data-ttu-id="9fd63-131">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-131">Yes</span></span> | <span data-ttu-id="9fd63-132">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-132">Yes</span></span> | <span data-ttu-id="9fd63-133">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-133">Yes</span></span> | <span data-ttu-id="9fd63-134">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-134">No</span></span> | <span data-ttu-id="9fd63-135">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-135">No</span></span> |
| <span data-ttu-id="9fd63-136">代表他人接听电话</span><span class="sxs-lookup"><span data-stu-id="9fd63-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="9fd63-137">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-137">Yes</span></span> | <span data-ttu-id="9fd63-138">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-138">Yes</span></span> | <span data-ttu-id="9fd63-139">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-139">Yes</span></span> | <span data-ttu-id="9fd63-140">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-140">Yes</span></span> | <span data-ttu-id="9fd63-141">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-141">Yes</span></span> |
| <span data-ttu-id="9fd63-142">代表另一个电话号码拨打电话</span><span class="sxs-lookup"><span data-stu-id="9fd63-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="9fd63-143">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-143">Yes</span></span> | <span data-ttu-id="9fd63-144">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-144">Yes</span></span> | <span data-ttu-id="9fd63-145">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-145">Yes</span></span> | <span data-ttu-id="9fd63-146">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-146">Yes</span></span> | <span data-ttu-id="9fd63-147">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-147">Yes</span></span> |
| <span data-ttu-id="9fd63-148">代表另一个团队用户调用团队用户</span><span class="sxs-lookup"><span data-stu-id="9fd63-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="9fd63-149">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-149">Yes</span></span> | <span data-ttu-id="9fd63-150">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-150">Yes</span></span> | <span data-ttu-id="9fd63-151">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-151">Yes</span></span> | <span data-ttu-id="9fd63-152">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-152">Yes</span></span> | <span data-ttu-id="9fd63-153">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-153">Yes</span></span> |
| <span data-ttu-id="9fd63-154">查看共享行的管理员视图</span><span class="sxs-lookup"><span data-stu-id="9fd63-154">See the admin view of shared lines</span></span> | <span data-ttu-id="9fd63-155">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-155">Yes</span></span> | <span data-ttu-id="9fd63-156">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-156">Yes</span></span> | <span data-ttu-id="9fd63-157">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-157">Yes</span></span> | <span data-ttu-id="9fd63-158">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-158">No</span></span> | <span data-ttu-id="9fd63-159">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-159">No</span></span> |
| <span data-ttu-id="9fd63-160">查看经理的通话活动的管理员视图</span><span class="sxs-lookup"><span data-stu-id="9fd63-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="9fd63-161">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-161">Yes</span></span> | <span data-ttu-id="9fd63-162">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-162">Yes</span></span> | <span data-ttu-id="9fd63-163">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-163">Yes</span></span> | <span data-ttu-id="9fd63-164">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-164">No</span></span> | <span data-ttu-id="9fd63-165">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-165">No</span></span> |
| <span data-ttu-id="9fd63-166">查看代理人的管理者视图</span><span class="sxs-lookup"><span data-stu-id="9fd63-166">See the manager view of delegates</span></span> | <span data-ttu-id="9fd63-167">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-167">Yes</span></span> | <span data-ttu-id="9fd63-168">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-168">Yes</span></span> | <span data-ttu-id="9fd63-169">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-169">Yes</span></span> | <span data-ttu-id="9fd63-170">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-170">No</span></span> | <span data-ttu-id="9fd63-171">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-171">No</span></span> |
| <span data-ttu-id="9fd63-172">管理员或管理者可以保留或继续</span><span class="sxs-lookup"><span data-stu-id="9fd63-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="9fd63-173">必需</span><span class="sxs-lookup"><span data-stu-id="9fd63-173">Yes</span></span> | <span data-ttu-id="9fd63-174">是 </span><span class="sxs-lookup"><span data-stu-id="9fd63-174">Yes</span></span> | <span data-ttu-id="9fd63-175">是</span><span class="sxs-lookup"><span data-stu-id="9fd63-175">Yes</span></span> | <span data-ttu-id="9fd63-176">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-176">No</span></span> | <span data-ttu-id="9fd63-177">否</span><span class="sxs-lookup"><span data-stu-id="9fd63-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="9fd63-178">优缺点</span><span class="sxs-lookup"><span data-stu-id="9fd63-178">Limitations</span></span>

<span data-ttu-id="9fd63-179">经理最多可以添加25位代理人，并且代理人最多可以有25名经理。</span><span class="sxs-lookup"><span data-stu-id="9fd63-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="9fd63-180">对于可在租户中创建的委派关系的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="9fd63-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="9fd63-181">如果委托人进行通话和代理人不在同一地理位置，则由 PSTN 提供商允许呼叫者 ID 显示来自不同地理位置的委派（代表）呼叫。</span><span class="sxs-lookup"><span data-stu-id="9fd63-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="9fd63-182">更多信息</span><span class="sxs-lookup"><span data-stu-id="9fd63-182">More information</span></span>

[<span data-ttu-id="9fd63-183">与代理人共享电话线路</span><span class="sxs-lookup"><span data-stu-id="9fd63-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
