---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: serdars
author: SerdarSoysal
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
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫驻留和检索在云中的团队服务中将呼叫置于保持状态。
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582649"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="ea359-103">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="ea359-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="ea359-104">呼叫寄存和检索是允许用户在云中的团队服务中将呼叫置于保持状态的功能。</span><span class="sxs-lookup"><span data-stu-id="ea359-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="ea359-105">当通话暂停时，该服务将生成一个唯一的通话检索代码。</span><span class="sxs-lookup"><span data-stu-id="ea359-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="ea359-106">停用呼叫或其他人的用户可以使用该代码和受支持的应用或设备来检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea359-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="ea359-107">使用呼叫寄存的一些常见方案是：</span><span class="sxs-lookup"><span data-stu-id="ea359-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="ea359-108">在工厂中工作的一位接待员公园通话。</span><span class="sxs-lookup"><span data-stu-id="ea359-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="ea359-109">然后，接待员通过公共地址系统宣布呼叫和代码编号。</span><span class="sxs-lookup"><span data-stu-id="ea359-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="ea359-110">通话的用户可以在工厂车间中选择一个团队电话，并输入代码以检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea359-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="ea359-111">由于设备电池电量用完，用户在移动设备上公园通话。</span><span class="sxs-lookup"><span data-stu-id="ea359-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="ea359-112">然后，用户可以输入代码以从团队桌面电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea359-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="ea359-113">支持代表负责客户呼叫，并在团队频道上发送公告以检索呼叫和帮助客户。</span><span class="sxs-lookup"><span data-stu-id="ea359-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="ea359-114">专家输入团队客户的代码以检索呼叫</span><span class="sxs-lookup"><span data-stu-id="ea359-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea359-115">此功能仅适用于 "仅限团队" 部署模式。</span><span class="sxs-lookup"><span data-stu-id="ea359-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="ea359-116">有关团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="ea359-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="ea359-117">需要许可证</span><span class="sxs-lookup"><span data-stu-id="ea359-117">License required</span></span>

<span data-ttu-id="ea359-118">若要寄存和检索呼叫，用户必须是企业语音用户，并且管理员必须向用户授予呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="ea359-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="ea359-119">有关许可模型的详细信息，请参阅[Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ea359-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="ea359-120">呼叫寄存和检索功能可用性</span><span class="sxs-lookup"><span data-stu-id="ea359-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="ea359-121">电话寄存和检索目前由以下客户和设备支持。</span><span class="sxs-lookup"><span data-stu-id="ea359-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="ea359-122"> (在 "仅限团队模式" 模式下受支持，有或没有 PSTN 连接。 ) </span><span class="sxs-lookup"><span data-stu-id="ea359-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="ea359-123">功能</span><span class="sxs-lookup"><span data-stu-id="ea359-123">Capability</span></span> | <span data-ttu-id="ea359-124">团队桌面版</span><span class="sxs-lookup"><span data-stu-id="ea359-124">Teams Desktop</span></span> | <span data-ttu-id="ea359-125">团队 Mac 应用</span><span class="sxs-lookup"><span data-stu-id="ea359-125">Teams Mac App</span></span> | <span data-ttu-id="ea359-126">团队 Web App (边缘) </span><span class="sxs-lookup"><span data-stu-id="ea359-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="ea359-127">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="ea359-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="ea359-128">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="ea359-128">Teams IP phone</span></span> | <span data-ttu-id="ea359-129">Skype for Business IP 电话</span><span class="sxs-lookup"><span data-stu-id="ea359-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="ea359-130">寄存 a 呼叫</span><span class="sxs-lookup"><span data-stu-id="ea359-130">Park a call</span></span> | <span data-ttu-id="ea359-131">是</span><span class="sxs-lookup"><span data-stu-id="ea359-131">Yes</span></span> | <span data-ttu-id="ea359-132">是</span><span class="sxs-lookup"><span data-stu-id="ea359-132">Yes</span></span> | <span data-ttu-id="ea359-133">是</span><span class="sxs-lookup"><span data-stu-id="ea359-133">Yes</span></span> | <span data-ttu-id="ea359-134">是</span><span class="sxs-lookup"><span data-stu-id="ea359-134">Yes</span></span> | <span data-ttu-id="ea359-135">是</span><span class="sxs-lookup"><span data-stu-id="ea359-135">Yes</span></span> | <span data-ttu-id="ea359-136">否</span><span class="sxs-lookup"><span data-stu-id="ea359-136">No</span></span> |
| <span data-ttu-id="ea359-137">检索寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="ea359-137">Retrieve a parked call</span></span> | <span data-ttu-id="ea359-138">是</span><span class="sxs-lookup"><span data-stu-id="ea359-138">Yes</span></span> | <span data-ttu-id="ea359-139">是</span><span class="sxs-lookup"><span data-stu-id="ea359-139">Yes</span></span> | <span data-ttu-id="ea359-140">是</span><span class="sxs-lookup"><span data-stu-id="ea359-140">Yes</span></span> | <span data-ttu-id="ea359-141">是</span><span class="sxs-lookup"><span data-stu-id="ea359-141">Yes</span></span> | <span data-ttu-id="ea359-142">是</span><span class="sxs-lookup"><span data-stu-id="ea359-142">Yes</span></span> | <span data-ttu-id="ea359-143">否</span><span class="sxs-lookup"><span data-stu-id="ea359-143">No</span></span> |
| <span data-ttu-id="ea359-144">Unretrieved 电话铃声返回</span><span class="sxs-lookup"><span data-stu-id="ea359-144">Unretrieved call ring back</span></span> | <span data-ttu-id="ea359-145">是</span><span class="sxs-lookup"><span data-stu-id="ea359-145">Yes</span></span> | <span data-ttu-id="ea359-146">是</span><span class="sxs-lookup"><span data-stu-id="ea359-146">Yes</span></span> | <span data-ttu-id="ea359-147">是</span><span class="sxs-lookup"><span data-stu-id="ea359-147">Yes</span></span> | <span data-ttu-id="ea359-148">是</span><span class="sxs-lookup"><span data-stu-id="ea359-148">Yes</span></span> | <span data-ttu-id="ea359-149">是</span><span class="sxs-lookup"><span data-stu-id="ea359-149">Yes</span></span> | <span data-ttu-id="ea359-150">否</span><span class="sxs-lookup"><span data-stu-id="ea359-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="ea359-151">配置通话寄存和检索</span><span class="sxs-lookup"><span data-stu-id="ea359-151">Configure call park and retrieve</span></span>

<span data-ttu-id="ea359-152">只有管理员才能配置呼叫寄存和检索，并且默认情况下禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="ea359-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="ea359-153">你可以为用户启用它，并使用呼叫寄存策略创建用户组。</span><span class="sxs-lookup"><span data-stu-id="ea359-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="ea359-154">将同一策略应用到一组用户时，他们可以在其自身间停止和检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea359-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="ea359-155">若要为用户配置呼叫寄存和创建呼叫寄存用户组，请按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)流程操作。</span><span class="sxs-lookup"><span data-stu-id="ea359-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="ea359-156">有关如何使用通话寄存和检索功能的信息，请参阅[在团队中寄存通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="ea359-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="ea359-157">启用呼叫寄存政策</span><span class="sxs-lookup"><span data-stu-id="ea359-157">Enable a call park policy</span></span>

1. <span data-ttu-id="ea359-158">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫驻留策略**"。</span><span class="sxs-lookup"><span data-stu-id="ea359-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="ea359-159">选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ea359-159">Select **Add**.</span></span>
3. <span data-ttu-id="ea359-160">为策略命名，然后将 "**允许呼叫寄存**" 切换为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="ea359-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="ea359-161">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ea359-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="ea359-162">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea359-162">Using PowerShell</span></span>

<span data-ttu-id="ea359-163">请参阅[新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ea359-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="ea359-164">编辑呼叫寄存政策</span><span class="sxs-lookup"><span data-stu-id="ea359-164">Edit a call park policy</span></span>

1. <span data-ttu-id="ea359-165">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫驻留策略**"。</span><span class="sxs-lookup"><span data-stu-id="ea359-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="ea359-166">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="ea359-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="ea359-167">切换**允许呼叫寄存**为**Off** "关 **" 或 "开"**。</span><span class="sxs-lookup"><span data-stu-id="ea359-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="ea359-168">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ea359-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="ea359-169">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea359-169">Using PowerShell</span></span>

<span data-ttu-id="ea359-170">请参阅[设置-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ea359-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="ea359-171">例如，若要更改默认设置，请运行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea359-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="ea359-172">分配呼叫寄存政策</span><span class="sxs-lookup"><span data-stu-id="ea359-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="ea359-173">另请参阅[授权 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ea359-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ea359-174">故障排除</span><span class="sxs-lookup"><span data-stu-id="ea359-174">Troubleshooting</span></span>

<span data-ttu-id="ea359-175">如果用户看不到 "寄存" 或 "检索" 按钮：</span><span class="sxs-lookup"><span data-stu-id="ea359-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="ea359-176">检查用户是否已启用 "呼叫寄存" 策略。</span><span class="sxs-lookup"><span data-stu-id="ea359-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="ea359-177">如果用户尝试检索呼叫，但未成功，请检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="ea359-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="ea359-178">验证用户使用的是团队客户端还是启用团队的设备/电话</span><span class="sxs-lookup"><span data-stu-id="ea359-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="ea359-179">分组-用户是呼叫驻留组的成员，它基于分配了寄存策略的相同团队调用。</span><span class="sxs-lookup"><span data-stu-id="ea359-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="ea359-180">岛模式-通话寄存和检索在团队岛模式下不可用。</span><span class="sxs-lookup"><span data-stu-id="ea359-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="ea359-181">通话已被检索或终止。</span><span class="sxs-lookup"><span data-stu-id="ea359-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea359-182">相关主题</span><span class="sxs-lookup"><span data-stu-id="ea359-182">Related topics</span></span>

[<span data-ttu-id="ea359-183">在团队中寄存 a 通话</span><span class="sxs-lookup"><span data-stu-id="ea359-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="ea359-184">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="ea359-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
