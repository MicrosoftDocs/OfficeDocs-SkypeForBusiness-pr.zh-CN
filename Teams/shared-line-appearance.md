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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共享的行外观允许用户选择代理人应答或处理代表其拨打的呼叫。
ms.openlocfilehash: d16fe4b3241e814609999d8068ee47743bfca516
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204488"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a><span data-ttu-id="7a035-103">Microsoft Teams 中的共享线路外观</span><span class="sxs-lookup"><span data-stu-id="7a035-103">Shared line appearance in Microsoft Teams</span></span>

<span data-ttu-id="7a035-104">共享的行外观是允许用户选择代理人应答或处理代表其拨打的呼叫委派功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="7a035-104">Shared line appearance is part of the delegation feature that lets a user choose a delegate to answer or handle calls on their behalf.</span></span> <span data-ttu-id="7a035-105">此功能很有用，如果用户具有行政助理定期处理用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7a035-105">This feature is helpful if a user has an administrative assistant who regularly handles the user’s calls.</span></span> <span data-ttu-id="7a035-106">在上下文中共享的行外观，管理器是某人人员授予要发起或接收呼叫代表自己的委托和代理人可以发起和接收代表别人呼叫。</span><span class="sxs-lookup"><span data-stu-id="7a035-106">In the context of shared line appearance, a manager is someone who authorizes a delegate to make or receive calls on their behalf, and a delegate can make and receive calls on behalf of someone else.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a035-107">此功能才可用在仅团队部署模式下。</span><span class="sxs-lookup"><span data-stu-id="7a035-107">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="7a035-108">团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="7a035-108">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="7a035-109">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="7a035-109">License required</span></span>

<span data-ttu-id="7a035-110">用户必须是企业语音用户成为代理人或设置委派和允许其他人发起或接收代表其拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7a035-110">A user must be an enterprise voice user to be a delegate or set up delegation and enable others to make or receive calls on their behalf.</span></span>

<span data-ttu-id="7a035-111">同时将经理和代理人必须是启用的企业语音。</span><span class="sxs-lookup"><span data-stu-id="7a035-111">Both managers and delegates need to be enterprise voice enabled.</span></span> <span data-ttu-id="7a035-112">共享的行体验一部分委派，而且不需要其他许可证。</span><span class="sxs-lookup"><span data-stu-id="7a035-112">The shared line experience is part of delegation, and requires no additional license.</span></span> <span data-ttu-id="7a035-113">有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="7a035-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configuring-delegation-and-shared-line-appearance"></a><span data-ttu-id="7a035-114">配置委派和共享的行外观</span><span class="sxs-lookup"><span data-stu-id="7a035-114">Configuring delegation and shared line appearance</span></span>

<span data-ttu-id="7a035-115">委派和共享的行外观是用户驱动的功能： 没有管理员设置配置。</span><span class="sxs-lookup"><span data-stu-id="7a035-115">Delegation and shared line appearance are user-driven features: there are no admin settings to configure.</span></span> <span data-ttu-id="7a035-116">有关如何使用该功能的信息，请参阅[共享与代理人的电话线路](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span><span class="sxs-lookup"><span data-stu-id="7a035-116">For information about how to use the feature, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)</span></span>

<span data-ttu-id="7a035-117">租户管理员应启用此功能**TeamsCallingPolicy AllowDelegation**设置，以便通过委派。</span><span class="sxs-lookup"><span data-stu-id="7a035-117">The tenant admin should enable delegation via the **TeamsCallingPolicy AllowDelegation** setting for this feature to work.</span></span>

## <a name="shared-line-appearance-feature-availability"></a><span data-ttu-id="7a035-118">共享行外观功能可用性</span><span class="sxs-lookup"><span data-stu-id="7a035-118">Shared line appearance feature availability</span></span>

<span data-ttu-id="7a035-119">共享的行外观是当前支持以下应用程序和设备。</span><span class="sxs-lookup"><span data-stu-id="7a035-119">Shared line appearance is currently supported by the following apps and devices.</span></span>

| <span data-ttu-id="7a035-120">功能</span><span class="sxs-lookup"><span data-stu-id="7a035-120">Capability</span></span> | <span data-ttu-id="7a035-121">团队桌面</span><span class="sxs-lookup"><span data-stu-id="7a035-121">Teams Desktop</span></span> | <span data-ttu-id="7a035-122">团队 Mac 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a035-122">Teams Mac App</span></span> | <span data-ttu-id="7a035-123">工作组 Web 应用程序 （边缘）</span><span class="sxs-lookup"><span data-stu-id="7a035-123">Teams Web App (Edge)</span></span> |<span data-ttu-id="7a035-124">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="7a035-124">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="7a035-125">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="7a035-125">Teams IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| <span data-ttu-id="7a035-126">设置委派</span><span class="sxs-lookup"><span data-stu-id="7a035-126">Set up delegation</span></span> | <span data-ttu-id="7a035-127">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-127">Yes</span></span> | <span data-ttu-id="7a035-128">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-128">Yes</span></span> | <span data-ttu-id="7a035-129">是</span><span class="sxs-lookup"><span data-stu-id="7a035-129">Yes</span></span> | <span data-ttu-id="7a035-130">否</span><span class="sxs-lookup"><span data-stu-id="7a035-130">No</span></span> | <span data-ttu-id="7a035-131">否</span><span class="sxs-lookup"><span data-stu-id="7a035-131">No</span></span> |
| <span data-ttu-id="7a035-132">接收代表另一个呼叫</span><span class="sxs-lookup"><span data-stu-id="7a035-132">Receive calls on behalf of another</span></span> | <span data-ttu-id="7a035-133">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-133">Yes</span></span> | <span data-ttu-id="7a035-134">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-134">Yes</span></span> | <span data-ttu-id="7a035-135">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-135">Yes</span></span> | <span data-ttu-id="7a035-136">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-136">Yes</span></span> | <span data-ttu-id="7a035-137">是</span><span class="sxs-lookup"><span data-stu-id="7a035-137">Yes</span></span> |
| <span data-ttu-id="7a035-138">呼叫代表另一个电话号码</span><span class="sxs-lookup"><span data-stu-id="7a035-138">Call a phone number on behalf of another</span></span> | <span data-ttu-id="7a035-139">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-139">Yes</span></span> | <span data-ttu-id="7a035-140">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-140">Yes</span></span> | <span data-ttu-id="7a035-141">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-141">Yes</span></span> | <span data-ttu-id="7a035-142">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-142">Yes</span></span> | <span data-ttu-id="7a035-143">是</span><span class="sxs-lookup"><span data-stu-id="7a035-143">Yes</span></span> |
| <span data-ttu-id="7a035-144">代表其他呼叫团队用户</span><span class="sxs-lookup"><span data-stu-id="7a035-144">Call a Teams user on behalf of another</span></span> | <span data-ttu-id="7a035-145">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-145">Yes</span></span> | <span data-ttu-id="7a035-146">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-146">Yes</span></span> | <span data-ttu-id="7a035-147">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-147">Yes</span></span> | <span data-ttu-id="7a035-148">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-148">Yes</span></span> | <span data-ttu-id="7a035-149">是</span><span class="sxs-lookup"><span data-stu-id="7a035-149">Yes</span></span> |
| <span data-ttu-id="7a035-150">查看共享的行的管理视图</span><span class="sxs-lookup"><span data-stu-id="7a035-150">See the admin view of shared lines</span></span> | <span data-ttu-id="7a035-151">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-151">Yes</span></span> | <span data-ttu-id="7a035-152">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-152">Yes</span></span> | <span data-ttu-id="7a035-153">是</span><span class="sxs-lookup"><span data-stu-id="7a035-153">Yes</span></span> | <span data-ttu-id="7a035-154">否</span><span class="sxs-lookup"><span data-stu-id="7a035-154">No</span></span> | <span data-ttu-id="7a035-155">否</span><span class="sxs-lookup"><span data-stu-id="7a035-155">No</span></span> |
| <span data-ttu-id="7a035-156">请参阅经理的呼叫活动的管理视图</span><span class="sxs-lookup"><span data-stu-id="7a035-156">See the admin view of manager's call activities</span></span> | <span data-ttu-id="7a035-157">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-157">Yes</span></span> | <span data-ttu-id="7a035-158">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-158">Yes</span></span> | <span data-ttu-id="7a035-159">是</span><span class="sxs-lookup"><span data-stu-id="7a035-159">Yes</span></span> | <span data-ttu-id="7a035-160">否</span><span class="sxs-lookup"><span data-stu-id="7a035-160">No</span></span> | <span data-ttu-id="7a035-161">否</span><span class="sxs-lookup"><span data-stu-id="7a035-161">No</span></span> |
| <span data-ttu-id="7a035-162">查看代理人的管理器视图</span><span class="sxs-lookup"><span data-stu-id="7a035-162">See the manager view of delegates</span></span> | <span data-ttu-id="7a035-163">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-163">Yes</span></span> | <span data-ttu-id="7a035-164">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-164">Yes</span></span> | <span data-ttu-id="7a035-165">是</span><span class="sxs-lookup"><span data-stu-id="7a035-165">Yes</span></span> | <span data-ttu-id="7a035-166">否</span><span class="sxs-lookup"><span data-stu-id="7a035-166">No</span></span> | <span data-ttu-id="7a035-167">否</span><span class="sxs-lookup"><span data-stu-id="7a035-167">No</span></span> |
| <span data-ttu-id="7a035-168">管理员或管理器可以保持或恢复</span><span class="sxs-lookup"><span data-stu-id="7a035-168">Admin or manager can hold or resume</span></span> | <span data-ttu-id="7a035-169">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-169">Yes</span></span> | <span data-ttu-id="7a035-170">是 </span><span class="sxs-lookup"><span data-stu-id="7a035-170">Yes</span></span> | <span data-ttu-id="7a035-171">是</span><span class="sxs-lookup"><span data-stu-id="7a035-171">Yes</span></span> | <span data-ttu-id="7a035-172">否</span><span class="sxs-lookup"><span data-stu-id="7a035-172">No</span></span> | <span data-ttu-id="7a035-173">否</span><span class="sxs-lookup"><span data-stu-id="7a035-173">No</span></span> |

## <a name="limitations"></a><span data-ttu-id="7a035-174">限制</span><span class="sxs-lookup"><span data-stu-id="7a035-174">Limitations</span></span>

<span data-ttu-id="7a035-175">管理员可以添加最多 25 代理人，代理人可以有最多 25 个经理。</span><span class="sxs-lookup"><span data-stu-id="7a035-175">Managers can add up to 25 delegates, and delegates can have up to 25 managers.</span></span> <span data-ttu-id="7a035-176">可在租户中创建的委派关系的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="7a035-176">There is no limit to the number of delegation relationships that can be created in a tenant.</span></span> 
 
<span data-ttu-id="7a035-177">如果代理者和代理人不在相同的地理位置，则由要允许呼叫者 ID 显示从不同地理位置的委派 （代表的） 呼叫的 PSTN 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a035-177">If the delegator and delegate are not in the same geographic location, it is up to the PSTN provider to allow caller ID to show up from a different geographic location for a delegated (on behalf of) call.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="7a035-178">更多信息</span><span class="sxs-lookup"><span data-stu-id="7a035-178">More information</span></span>

[<span data-ttu-id="7a035-179">与代理人共享电话线路</span><span class="sxs-lookup"><span data-stu-id="7a035-179">Share a phone line with a delegate</span></span>](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
