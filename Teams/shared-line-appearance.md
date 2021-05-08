---
title: Microsoft Teams 中的共享线路外观
ms.author: serdars
author: SerdarSoysal
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
description: 了解如何向用户发送包含其音频会议信息的电子邮件，Microsoft Teams。
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117040"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="cead0-103">Microsoft Teams 中的共享线路外观</span><span class="sxs-lookup"><span data-stu-id="cead0-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="cead0-104">共享线路外观是委派功能中的一部分，允许用户选择代理人来代表他们应答或处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="cead0-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="cead0-105">如果用户具有定期处理用户呼叫的管理助理，此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="cead0-105">This feature is helpful if a user has an administrative assistant who regularly handles the user's calls.</span></span> <span data-ttu-id="cead0-106">在共享线路外观的上下文中，经理是授权代理人代表他们进行呼叫或接听呼叫的人，代理人可以代表其他人进行呼叫和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="cead0-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cead0-107">此功能仅在仅Teams模式下可用。</span><span class="sxs-lookup"><span data-stu-id="cead0-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="cead0-108">有关部署模式Teams的详细信息，请参阅了解Microsoft Teams Skype for Business[和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="cead0-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="cead0-109">需要许可证</span><span class="sxs-lookup"><span data-stu-id="cead0-109">License required</span></span>

<span data-ttu-id="cead0-110">用户必须具有具有 PSTN 电话系统连接 (呼叫计划许可证或 Direct Routing OnlineVoiceRoutingPolicy) 才能成为代理人或设置委派，并允许其他人代表他们进行或接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="cead0-110">A user must be have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy) to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="cead0-111">经理和代理人都需要使用呼叫电话系统或直接路由 OnlineVoiceRoutingPolicy (PSTN 连接) 。</span><span class="sxs-lookup"><span data-stu-id="cead0-111">Both managers and delegates need to have Phone System with PSTN connectivity (either a Calling Plan license or Direct Routing OnlineVoiceRoutingPolicy).</span></span> <span data-ttu-id="cead0-112">共享线路体验是委派的一部分，包含在电话系统。</span><span class="sxs-lookup"><span data-stu-id="cead0-112">The shared line experience is part of delegation and is included with Phone System.</span></span> <span data-ttu-id="cead0-113">有关许可模型的其他详细信息，请参阅Microsoft Teams[说明。](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="cead0-113">For additional details on the licensing model, See [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="cead0-114">配置委派和共享行外观</span><span class="sxs-lookup"><span data-stu-id="cead0-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="cead0-115">委派和共享行外观是用户驱动的功能：无需配置管理员设置。</span><span class="sxs-lookup"><span data-stu-id="cead0-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="cead0-116">有关如何使用该功能的信息，请参阅 [与代理人共享电话线](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="cead0-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="cead0-117">租户管理员可以通过 **TeamsCallingPolicy AllowDelegation** 设置或 Teams管理门户启用委派，以便此功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="cead0-117">The tenant admin can enable delegation via the **TeamsCallingPolicy AllowDelegation** setting or via Teams Admin Portal for this feature to work.</span></span> 

<span data-ttu-id="cead0-118">租户管理员还可以在管理中心为用户配置Teams关系。</span><span class="sxs-lookup"><span data-stu-id="cead0-118">The tenant admin can also configure delegation relationships for a user in the Teams admin center.</span></span> <span data-ttu-id="cead0-119">此外，最终用户还可以直接在 Teams 中配置其委派关系。</span><span class="sxs-lookup"><span data-stu-id="cead0-119">In addition, the end user can also configure their delegation relationships directly in Teams.</span></span> <span data-ttu-id="cead0-120">租户管理员或用户无法相互阻止配置，但Teams管理中心和Teams应在两处准确显示此关系。</span><span class="sxs-lookup"><span data-stu-id="cead0-120">The Tenant admin or the user cannot block the configuration by each other, but the Teams admin center and Teams client should show this relationship accurately in both places.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cead0-121">当租户管理员在用户 (启用) 后关闭其委派时，还需要在 Teams 管理中心中清理该用户的委派关系，以避免不正确的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="cead0-121">When the tenant admin turns off delegation for a user (after it has been turned on), they also need to clean up delegation relationships for that user in the Teams admin center to avoid incorrect call routing.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="cead0-122">共享线外观功能可用性</span><span class="sxs-lookup"><span data-stu-id="cead0-122">Shared line appearance feature availability</span></span>

<span data-ttu-id="cead0-123">以下应用和设备目前支持共享线外观。</span><span class="sxs-lookup"><span data-stu-id="cead0-123">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="cead0-124">功能</span><span class="sxs-lookup"><span data-stu-id="cead0-124">Capability</span></span> | <span data-ttu-id="cead0-125">Teams桌面</span><span class="sxs-lookup"><span data-stu-id="cead0-125">Teams Desktop</span></span> | <span data-ttu-id="cead0-126">TeamsMac 应用</span><span class="sxs-lookup"><span data-stu-id="cead0-126">Teams Mac App</span></span> | <span data-ttu-id="cead0-127">TeamsWeb 应用 (Edge) </span><span class="sxs-lookup"><span data-stu-id="cead0-127">Teams Web App (Edge)</span></span> |<span data-ttu-id="cead0-128">Teams iOS/Android 应用</span><span class="sxs-lookup"><span data-stu-id="cead0-128">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="cead0-129">TeamsIP 电话</span><span class="sxs-lookup"><span data-stu-id="cead0-129">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="cead0-130">设置委派</span><span class="sxs-lookup"><span data-stu-id="cead0-130">Set up delegation</span></span> | <span data-ttu-id="cead0-131">是</span><span class="sxs-lookup"><span data-stu-id="cead0-131">Yes</span></span> | <span data-ttu-id="cead0-132">是</span><span class="sxs-lookup"><span data-stu-id="cead0-132">Yes</span></span> | <span data-ttu-id="cead0-133">是</span><span class="sxs-lookup"><span data-stu-id="cead0-133">Yes</span></span> | <span data-ttu-id="cead0-134">否</span><span class="sxs-lookup"><span data-stu-id="cead0-134">No</span></span> | <span data-ttu-id="cead0-135">是</span><span class="sxs-lookup"><span data-stu-id="cead0-135">Yes</span></span> |
| <span data-ttu-id="cead0-136">代表另一个接收呼叫</span><span class="sxs-lookup"><span data-stu-id="cead0-136">Receive calls on behalf of another</span></span> | <span data-ttu-id="cead0-137">是</span><span class="sxs-lookup"><span data-stu-id="cead0-137">Yes</span></span> | <span data-ttu-id="cead0-138">是</span><span class="sxs-lookup"><span data-stu-id="cead0-138">Yes</span></span> | <span data-ttu-id="cead0-139">是</span><span class="sxs-lookup"><span data-stu-id="cead0-139">Yes</span></span> | <span data-ttu-id="cead0-140">是</span><span class="sxs-lookup"><span data-stu-id="cead0-140">Yes</span></span> | <span data-ttu-id="cead0-141">是</span><span class="sxs-lookup"><span data-stu-id="cead0-141">Yes</span></span> |
| <span data-ttu-id="cead0-142">代表另一个号码呼叫电话号码</span><span class="sxs-lookup"><span data-stu-id="cead0-142">Call a phone number on behalf of another</span></span> | <span data-ttu-id="cead0-143">是</span><span class="sxs-lookup"><span data-stu-id="cead0-143">Yes</span></span> | <span data-ttu-id="cead0-144">是</span><span class="sxs-lookup"><span data-stu-id="cead0-144">Yes</span></span> | <span data-ttu-id="cead0-145">是</span><span class="sxs-lookup"><span data-stu-id="cead0-145">Yes</span></span> | <span data-ttu-id="cead0-146">是</span><span class="sxs-lookup"><span data-stu-id="cead0-146">Yes</span></span> | <span data-ttu-id="cead0-147">是</span><span class="sxs-lookup"><span data-stu-id="cead0-147">Yes</span></span> |
| <span data-ttu-id="cead0-148">代表Teams呼叫用户</span><span class="sxs-lookup"><span data-stu-id="cead0-148">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="cead0-149">是</span><span class="sxs-lookup"><span data-stu-id="cead0-149">Yes</span></span> | <span data-ttu-id="cead0-150">是</span><span class="sxs-lookup"><span data-stu-id="cead0-150">Yes</span></span> | <span data-ttu-id="cead0-151">是</span><span class="sxs-lookup"><span data-stu-id="cead0-151">Yes</span></span> | <span data-ttu-id="cead0-152">是</span><span class="sxs-lookup"><span data-stu-id="cead0-152">Yes</span></span> | <span data-ttu-id="cead0-153">是</span><span class="sxs-lookup"><span data-stu-id="cead0-153">Yes</span></span> |
| <span data-ttu-id="cead0-154">查看共享行的管理员视图</span><span class="sxs-lookup"><span data-stu-id="cead0-154">See the admin view of shared lines</span></span> | <span data-ttu-id="cead0-155">是</span><span class="sxs-lookup"><span data-stu-id="cead0-155">Yes</span></span> | <span data-ttu-id="cead0-156">是</span><span class="sxs-lookup"><span data-stu-id="cead0-156">Yes</span></span> | <span data-ttu-id="cead0-157">是</span><span class="sxs-lookup"><span data-stu-id="cead0-157">Yes</span></span> | <span data-ttu-id="cead0-158">否</span><span class="sxs-lookup"><span data-stu-id="cead0-158">No</span></span> | <span data-ttu-id="cead0-159">否</span><span class="sxs-lookup"><span data-stu-id="cead0-159">No</span></span> |
| <span data-ttu-id="cead0-160">查看经理呼叫活动的管理员视图</span><span class="sxs-lookup"><span data-stu-id="cead0-160">See the admin view of manager's call activities</span></span> | <span data-ttu-id="cead0-161">是</span><span class="sxs-lookup"><span data-stu-id="cead0-161">Yes</span></span> | <span data-ttu-id="cead0-162">是</span><span class="sxs-lookup"><span data-stu-id="cead0-162">Yes</span></span> | <span data-ttu-id="cead0-163">是</span><span class="sxs-lookup"><span data-stu-id="cead0-163">Yes</span></span> | <span data-ttu-id="cead0-164">否</span><span class="sxs-lookup"><span data-stu-id="cead0-164">No</span></span> | <span data-ttu-id="cead0-165">否</span><span class="sxs-lookup"><span data-stu-id="cead0-165">No</span></span> |
| <span data-ttu-id="cead0-166">查看代理人的经理视图</span><span class="sxs-lookup"><span data-stu-id="cead0-166">See the manager view of delegates</span></span> | <span data-ttu-id="cead0-167">是</span><span class="sxs-lookup"><span data-stu-id="cead0-167">Yes</span></span> | <span data-ttu-id="cead0-168">是</span><span class="sxs-lookup"><span data-stu-id="cead0-168">Yes</span></span> | <span data-ttu-id="cead0-169">是</span><span class="sxs-lookup"><span data-stu-id="cead0-169">Yes</span></span> | <span data-ttu-id="cead0-170">否</span><span class="sxs-lookup"><span data-stu-id="cead0-170">No</span></span> | <span data-ttu-id="cead0-171">否</span><span class="sxs-lookup"><span data-stu-id="cead0-171">No</span></span> |
| <span data-ttu-id="cead0-172">管理员或经理可以保留或恢复</span><span class="sxs-lookup"><span data-stu-id="cead0-172">Admin or manager can hold or resume</span></span> | <span data-ttu-id="cead0-173">是</span><span class="sxs-lookup"><span data-stu-id="cead0-173">Yes</span></span> | <span data-ttu-id="cead0-174">是</span><span class="sxs-lookup"><span data-stu-id="cead0-174">Yes</span></span> | <span data-ttu-id="cead0-175">是</span><span class="sxs-lookup"><span data-stu-id="cead0-175">Yes</span></span> | <span data-ttu-id="cead0-176">否</span><span class="sxs-lookup"><span data-stu-id="cead0-176">No</span></span> | <span data-ttu-id="cead0-177">否</span><span class="sxs-lookup"><span data-stu-id="cead0-177">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="cead0-178">限制</span><span class="sxs-lookup"><span data-stu-id="cead0-178">Limitations</span></span>

<span data-ttu-id="cead0-179">经理可添加多达 25 名代理人，代理人最多只能有 25 名经理。</span><span class="sxs-lookup"><span data-stu-id="cead0-179">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="cead0-180">可以在租户中创建的委派关系数没有限制。</span><span class="sxs-lookup"><span data-stu-id="cead0-180">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="cead0-181">如果委派方和代理人不在同一地理位置，则由 PSTN 提供商负责允许呼叫者 ID 代表) 呼叫从委派的 (显示。</span><span class="sxs-lookup"><span data-stu-id="cead0-181">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="cead0-182">更多信息</span><span class="sxs-lookup"><span data-stu-id="cead0-182">More information</span></span>

[<span data-ttu-id="cead0-183">与代理人共享电话线</span><span class="sxs-lookup"><span data-stu-id="cead0-183">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)