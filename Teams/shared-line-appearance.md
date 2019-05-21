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
- Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共享行的外观使用户可以选择代表代表他们应答或处理呼叫的代理人。
ms.openlocfilehash: 619e011e1af5a765bc86ca6bd68134dc5ab1e9fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298652"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="37765-103">Microsoft Teams 中的共享线路外观</span><span class="sxs-lookup"><span data-stu-id="37765-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="37765-104">共享行的外观是委派功能的一部分, 允许用户选择代理人代表他们应答或处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="37765-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="37765-105">如果用户有一个管理助理负责定期处理用户的通话, 此功能将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="37765-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="37765-106">在共享行外观的上下文中, 经理是指授权代理人代表他们拨打或接听呼叫的人员, 而代理人可以代表其他人拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="37765-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37765-107">此功能仅适用于 "仅限团队" 部署模式。</span><span class="sxs-lookup"><span data-stu-id="37765-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="37765-108">有关团队部署模式的更多详细信息, 请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="37765-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="37765-109">需要许可证</span><span class="sxs-lookup"><span data-stu-id="37765-109">License required</span></span>

<span data-ttu-id="37765-110">用户必须是企业语音用户才能成为代理人或设置委派, 并允许其他人代表他们进行或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="37765-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="37765-111">经理和代理人都需要具备企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="37765-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="37765-112">共享行体验是委派的一部分, 不需要额外许可证。</span><span class="sxs-lookup"><span data-stu-id="37765-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="37765-113">有关许可模型的其他详细信息, 请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="37765-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="37765-114">配置委派和共享行的外观</span><span class="sxs-lookup"><span data-stu-id="37765-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="37765-115">委派和共享行的外观是用户驱动的功能: 没有要配置的管理员设置。</span><span class="sxs-lookup"><span data-stu-id="37765-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="37765-116">有关如何使用该功能的信息, 请参阅[与代理人共享电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="37765-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="37765-117">租户管理员应通过**TeamsCallingPolicy AllowDelegation**设置启用委派, 此功能才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="37765-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="37765-118">共享行外观功能的可用性</span><span class="sxs-lookup"><span data-stu-id="37765-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="37765-119">以下应用和设备当前支持共享行的外观。</span><span class="sxs-lookup"><span data-stu-id="37765-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="37765-120">能</span><span class="sxs-lookup"><span data-stu-id="37765-120">Capability</span></span> | <span data-ttu-id="37765-121">团队桌面版</span><span class="sxs-lookup"><span data-stu-id="37765-121">Teams Desktop</span></span> | <span data-ttu-id="37765-122">团队 Mac 应用</span><span class="sxs-lookup"><span data-stu-id="37765-122">Teams Mac App</span></span> | <span data-ttu-id="37765-123">团队 Web App (Edge)</span><span class="sxs-lookup"><span data-stu-id="37765-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="37765-124">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="37765-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="37765-125">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="37765-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="37765-126">设置委派</span><span class="sxs-lookup"><span data-stu-id="37765-126">Set up delegation</span></span> | <span data-ttu-id="37765-127">是</span><span class="sxs-lookup"><span data-stu-id="37765-127">Yes</span></span> | <span data-ttu-id="37765-128">是</span><span class="sxs-lookup"><span data-stu-id="37765-128">Yes</span></span> | <span data-ttu-id="37765-129">是</span><span class="sxs-lookup"><span data-stu-id="37765-129">Yes</span></span> | <span data-ttu-id="37765-130">否</span><span class="sxs-lookup"><span data-stu-id="37765-130">No</span></span> | <span data-ttu-id="37765-131">否</span><span class="sxs-lookup"><span data-stu-id="37765-131">No</span></span> |
| <span data-ttu-id="37765-132">代表他人接听电话</span><span class="sxs-lookup"><span data-stu-id="37765-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="37765-133">是</span><span class="sxs-lookup"><span data-stu-id="37765-133">Yes</span></span> | <span data-ttu-id="37765-134">是</span><span class="sxs-lookup"><span data-stu-id="37765-134">Yes</span></span> | <span data-ttu-id="37765-135">是</span><span class="sxs-lookup"><span data-stu-id="37765-135">Yes</span></span> | <span data-ttu-id="37765-136">是</span><span class="sxs-lookup"><span data-stu-id="37765-136">Yes</span></span> | <span data-ttu-id="37765-137">是</span><span class="sxs-lookup"><span data-stu-id="37765-137">Yes</span></span> |
| <span data-ttu-id="37765-138">代表另一个电话号码拨打电话</span><span class="sxs-lookup"><span data-stu-id="37765-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="37765-139">是</span><span class="sxs-lookup"><span data-stu-id="37765-139">Yes</span></span> | <span data-ttu-id="37765-140">是</span><span class="sxs-lookup"><span data-stu-id="37765-140">Yes</span></span> | <span data-ttu-id="37765-141">是</span><span class="sxs-lookup"><span data-stu-id="37765-141">Yes</span></span> | <span data-ttu-id="37765-142">是</span><span class="sxs-lookup"><span data-stu-id="37765-142">Yes</span></span> | <span data-ttu-id="37765-143">是</span><span class="sxs-lookup"><span data-stu-id="37765-143">Yes</span></span> |
| <span data-ttu-id="37765-144">代表另一个团队用户调用团队用户</span><span class="sxs-lookup"><span data-stu-id="37765-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="37765-145">是</span><span class="sxs-lookup"><span data-stu-id="37765-145">Yes</span></span> | <span data-ttu-id="37765-146">是</span><span class="sxs-lookup"><span data-stu-id="37765-146">Yes</span></span> | <span data-ttu-id="37765-147">是</span><span class="sxs-lookup"><span data-stu-id="37765-147">Yes</span></span> | <span data-ttu-id="37765-148">是</span><span class="sxs-lookup"><span data-stu-id="37765-148">Yes</span></span> | <span data-ttu-id="37765-149">是</span><span class="sxs-lookup"><span data-stu-id="37765-149">Yes</span></span> |
| <span data-ttu-id="37765-150">查看共享行的管理员视图</span><span class="sxs-lookup"><span data-stu-id="37765-150">See the admin view of shared lines</span></span> | <span data-ttu-id="37765-151">是</span><span class="sxs-lookup"><span data-stu-id="37765-151">Yes</span></span> | <span data-ttu-id="37765-152">是</span><span class="sxs-lookup"><span data-stu-id="37765-152">Yes</span></span> | <span data-ttu-id="37765-153">是</span><span class="sxs-lookup"><span data-stu-id="37765-153">Yes</span></span> | <span data-ttu-id="37765-154">否</span><span class="sxs-lookup"><span data-stu-id="37765-154">No</span></span> | <span data-ttu-id="37765-155">否</span><span class="sxs-lookup"><span data-stu-id="37765-155">No</span></span> |
| <span data-ttu-id="37765-156">查看经理的通话活动的管理员视图</span><span class="sxs-lookup"><span data-stu-id="37765-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="37765-157">是</span><span class="sxs-lookup"><span data-stu-id="37765-157">Yes</span></span> | <span data-ttu-id="37765-158">是</span><span class="sxs-lookup"><span data-stu-id="37765-158">Yes</span></span> | <span data-ttu-id="37765-159">是</span><span class="sxs-lookup"><span data-stu-id="37765-159">Yes</span></span> | <span data-ttu-id="37765-160">否</span><span class="sxs-lookup"><span data-stu-id="37765-160">No</span></span> | <span data-ttu-id="37765-161">否</span><span class="sxs-lookup"><span data-stu-id="37765-161">No</span></span> |
| <span data-ttu-id="37765-162">查看代理人的管理者视图</span><span class="sxs-lookup"><span data-stu-id="37765-162">See the manager view of delegates</span></span> | <span data-ttu-id="37765-163">是</span><span class="sxs-lookup"><span data-stu-id="37765-163">Yes</span></span> | <span data-ttu-id="37765-164">是</span><span class="sxs-lookup"><span data-stu-id="37765-164">Yes</span></span> | <span data-ttu-id="37765-165">是</span><span class="sxs-lookup"><span data-stu-id="37765-165">Yes</span></span> | <span data-ttu-id="37765-166">否</span><span class="sxs-lookup"><span data-stu-id="37765-166">No</span></span> | <span data-ttu-id="37765-167">否</span><span class="sxs-lookup"><span data-stu-id="37765-167">No</span></span> |
| <span data-ttu-id="37765-168">管理员或管理者可以保留或继续</span><span class="sxs-lookup"><span data-stu-id="37765-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="37765-169">是</span><span class="sxs-lookup"><span data-stu-id="37765-169">Yes</span></span> | <span data-ttu-id="37765-170">是</span><span class="sxs-lookup"><span data-stu-id="37765-170">Yes</span></span> | <span data-ttu-id="37765-171">是</span><span class="sxs-lookup"><span data-stu-id="37765-171">Yes</span></span> | <span data-ttu-id="37765-172">否</span><span class="sxs-lookup"><span data-stu-id="37765-172">No</span></span> | <span data-ttu-id="37765-173">否</span><span class="sxs-lookup"><span data-stu-id="37765-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="37765-174">优缺点</span><span class="sxs-lookup"><span data-stu-id="37765-174">Limitations</span></span>

<span data-ttu-id="37765-175">经理最多可以添加25位代理人, 并且代理人最多可以有25名经理。</span><span class="sxs-lookup"><span data-stu-id="37765-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="37765-176">对于可在租户中创建的委派关系的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="37765-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="37765-177">如果委托人进行通话和代理人不在同一地理位置, 则由 PSTN 提供商允许呼叫者 ID 显示来自不同地理位置的委派 (代表) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="37765-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="37765-178">详细信息</span><span class="sxs-lookup"><span data-stu-id="37765-178">More information</span></span>

[<span data-ttu-id="37765-179">与代理人共享电话线路</span><span class="sxs-lookup"><span data-stu-id="37765-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
