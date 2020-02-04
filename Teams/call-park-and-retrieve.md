---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: 使用呼叫驻留和检索将呼叫置于云中的团队服务中的 "暂候" 状态。
ms.openlocfilehash: 4bd77fcd90cb17f0ca5b09f784d6532d552df473
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695617"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="83f36-103">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="83f36-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="83f36-104">呼叫寄存和检索是允许用户在云中的团队服务中将呼叫置于保持状态的功能。</span><span class="sxs-lookup"><span data-stu-id="83f36-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="83f36-105">当通话暂停时，该服务将生成一个唯一的通话检索代码。</span><span class="sxs-lookup"><span data-stu-id="83f36-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="83f36-106">停用呼叫或其他人的用户可以使用该代码和受支持的应用或设备来检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="83f36-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="83f36-107">使用呼叫寄存的一些常见方案是：</span><span class="sxs-lookup"><span data-stu-id="83f36-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="83f36-108">在工厂中工作的一位接待员公园通话。</span><span class="sxs-lookup"><span data-stu-id="83f36-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="83f36-109">然后，接待员通过公共地址系统宣布呼叫和代码编号。</span><span class="sxs-lookup"><span data-stu-id="83f36-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="83f36-110">通话的用户可以在工厂车间中选择一个团队电话，并输入代码以检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="83f36-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="83f36-111">由于设备电池电量用完，用户在移动设备上公园通话。</span><span class="sxs-lookup"><span data-stu-id="83f36-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="83f36-112">然后，用户可以输入代码以从团队桌面电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="83f36-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="83f36-113">支持代表负责客户呼叫，并在团队频道上发送公告以检索呼叫和帮助客户。</span><span class="sxs-lookup"><span data-stu-id="83f36-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="83f36-114">专家输入团队客户的代码以检索呼叫</span><span class="sxs-lookup"><span data-stu-id="83f36-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83f36-115">此功能仅适用于 "仅限团队" 部署模式。</span><span class="sxs-lookup"><span data-stu-id="83f36-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="83f36-116">有关团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="83f36-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="83f36-117">需要许可证</span><span class="sxs-lookup"><span data-stu-id="83f36-117">License required</span></span>

<span data-ttu-id="83f36-118">若要寄存和检索呼叫，用户必须是企业语音用户，并且管理员必须向用户授予呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="83f36-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="83f36-119">有关许可模型的详细信息，请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="83f36-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="83f36-120">呼叫寄存和检索功能可用性</span><span class="sxs-lookup"><span data-stu-id="83f36-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="83f36-121">电话寄存和检索目前由以下客户和设备支持。</span><span class="sxs-lookup"><span data-stu-id="83f36-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="83f36-122">（在 "仅限团队" 模式下受支持，有或没有 PSTN 连接。）</span><span class="sxs-lookup"><span data-stu-id="83f36-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="83f36-123">能</span><span class="sxs-lookup"><span data-stu-id="83f36-123">Capability</span></span> | <span data-ttu-id="83f36-124">团队桌面版</span><span class="sxs-lookup"><span data-stu-id="83f36-124">Teams Desktop</span></span> | <span data-ttu-id="83f36-125">团队 Mac 应用</span><span class="sxs-lookup"><span data-stu-id="83f36-125">Teams Mac App</span></span> | <span data-ttu-id="83f36-126">团队 Web App （Edge）</span><span class="sxs-lookup"><span data-stu-id="83f36-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="83f36-127">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="83f36-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="83f36-128">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="83f36-128">Teams IP phone</span></span> | <span data-ttu-id="83f36-129">Skype for Business IP 电话</span><span class="sxs-lookup"><span data-stu-id="83f36-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="83f36-130">寄存 a 呼叫</span><span class="sxs-lookup"><span data-stu-id="83f36-130">Park a call</span></span> | <span data-ttu-id="83f36-131">是</span><span class="sxs-lookup"><span data-stu-id="83f36-131">Yes</span></span> | <span data-ttu-id="83f36-132">是</span><span class="sxs-lookup"><span data-stu-id="83f36-132">Yes</span></span> | <span data-ttu-id="83f36-133">是</span><span class="sxs-lookup"><span data-stu-id="83f36-133">Yes</span></span> | <span data-ttu-id="83f36-134">是</span><span class="sxs-lookup"><span data-stu-id="83f36-134">Yes</span></span> | <span data-ttu-id="83f36-135">即将提供</span><span class="sxs-lookup"><span data-stu-id="83f36-135">Coming soon</span></span>| <span data-ttu-id="83f36-136">否</span><span class="sxs-lookup"><span data-stu-id="83f36-136">No</span></span> |
| <span data-ttu-id="83f36-137">检索寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="83f36-137">Retrieve a parked call</span></span> | <span data-ttu-id="83f36-138">是</span><span class="sxs-lookup"><span data-stu-id="83f36-138">Yes</span></span> | <span data-ttu-id="83f36-139">是</span><span class="sxs-lookup"><span data-stu-id="83f36-139">Yes</span></span> | <span data-ttu-id="83f36-140">是</span><span class="sxs-lookup"><span data-stu-id="83f36-140">Yes</span></span> | <span data-ttu-id="83f36-141">是</span><span class="sxs-lookup"><span data-stu-id="83f36-141">Yes</span></span> | <span data-ttu-id="83f36-142">即将提供</span><span class="sxs-lookup"><span data-stu-id="83f36-142">Coming soon</span></span>| <span data-ttu-id="83f36-143">否</span><span class="sxs-lookup"><span data-stu-id="83f36-143">No</span></span> |
| <span data-ttu-id="83f36-144">Unretrieved 电话铃声返回</span><span class="sxs-lookup"><span data-stu-id="83f36-144">Unretrieved call ring back</span></span> | <span data-ttu-id="83f36-145">是</span><span class="sxs-lookup"><span data-stu-id="83f36-145">Yes</span></span> | <span data-ttu-id="83f36-146">是</span><span class="sxs-lookup"><span data-stu-id="83f36-146">Yes</span></span> | <span data-ttu-id="83f36-147">是</span><span class="sxs-lookup"><span data-stu-id="83f36-147">Yes</span></span> | <span data-ttu-id="83f36-148">是</span><span class="sxs-lookup"><span data-stu-id="83f36-148">Yes</span></span> | <span data-ttu-id="83f36-149">即将提供</span><span class="sxs-lookup"><span data-stu-id="83f36-149">Coming soon</span></span>| <span data-ttu-id="83f36-150">否</span><span class="sxs-lookup"><span data-stu-id="83f36-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="83f36-151">配置呼叫驻留和检索</span><span class="sxs-lookup"><span data-stu-id="83f36-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="83f36-152">只有管理员才能配置呼叫寄存和检索，并且默认情况下禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="83f36-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="83f36-153">你可以为用户启用它，并使用呼叫寄存策略创建用户组。</span><span class="sxs-lookup"><span data-stu-id="83f36-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="83f36-154">将同一策略应用到一组用户时，他们可以在其自身间停止和检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="83f36-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="83f36-155">若要为用户配置呼叫寄存和创建呼叫寄存用户组，请按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)流程操作。</span><span class="sxs-lookup"><span data-stu-id="83f36-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="83f36-156">有关如何使用通话寄存和检索功能的信息，请参阅[在团队中寄存通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="83f36-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="83f36-157">启用呼叫寄存政策</span><span class="sxs-lookup"><span data-stu-id="83f36-157">Enable a call park policy</span></span>

<span data-ttu-id="83f36-158">请按照以下步骤启用呼叫寄存策略：</span><span class="sxs-lookup"><span data-stu-id="83f36-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="83f36-159">转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。</span><span class="sxs-lookup"><span data-stu-id="83f36-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="83f36-160">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="83f36-160">Select **New policy**.</span></span>
3. <span data-ttu-id="83f36-161">为策略命名，然后将 "**允许呼叫寄存**" 切换为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="83f36-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="83f36-162">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="83f36-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="83f36-163">分配呼叫寄存政策</span><span class="sxs-lookup"><span data-stu-id="83f36-163">Assign a call park policy</span></span>

<span data-ttu-id="83f36-164">按照以下步骤将呼叫寄存策略分配给一个或多个用户：</span><span class="sxs-lookup"><span data-stu-id="83f36-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="83f36-165">转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。</span><span class="sxs-lookup"><span data-stu-id="83f36-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="83f36-166">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="83f36-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="83f36-167">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="83f36-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="83f36-168">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="83f36-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="83f36-169">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="83f36-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="83f36-170">完成添加用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="83f36-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="83f36-171">配置与 PowerShell 的通话寄存和检索</span><span class="sxs-lookup"><span data-stu-id="83f36-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="83f36-172">使用[全新的 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="83f36-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="83f36-173">使用[grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="83f36-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="83f36-174">可以使用 "[设置-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) " 更改默认设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83f36-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="83f36-175">疑难解答</span><span class="sxs-lookup"><span data-stu-id="83f36-175">Troubleshooting</span></span>

<span data-ttu-id="83f36-176">如果用户看不到 "寄存" 或 "检索" 按钮：</span><span class="sxs-lookup"><span data-stu-id="83f36-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="83f36-177">检查用户是否已启用 "呼叫寄存" 策略。</span><span class="sxs-lookup"><span data-stu-id="83f36-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="83f36-178">如果用户尝试检索呼叫，但未成功，请检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="83f36-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="83f36-179">验证用户使用的是团队客户端还是启用团队的设备/电话</span><span class="sxs-lookup"><span data-stu-id="83f36-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="83f36-180">分组-用户是呼叫驻留组的成员，它基于分配了寄存策略的相同团队调用。</span><span class="sxs-lookup"><span data-stu-id="83f36-180">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="83f36-181">岛模式-通话寄存和检索在团队岛模式下不可用。</span><span class="sxs-lookup"><span data-stu-id="83f36-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="83f36-182">通话已被检索或终止。</span><span class="sxs-lookup"><span data-stu-id="83f36-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="83f36-183">更多信息</span><span class="sxs-lookup"><span data-stu-id="83f36-183">More information</span></span>

<span data-ttu-id="83f36-184">[在团队中寄存 a 通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="83f36-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>
