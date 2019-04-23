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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 使用呼叫寄存和取回呼叫置于保持状态，云中团队服务中。
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993499"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="90d66-103">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="90d66-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="90d66-104">呼叫寄存和取回是一种功能，允许用户将呼叫置于保留在云中团队服务中。</span><span class="sxs-lookup"><span data-stu-id="90d66-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="90d66-105">驻留呼叫后，该服务将生成一个唯一的代码调用检索。</span><span class="sxs-lookup"><span data-stu-id="90d66-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="90d66-106">寄存呼叫或其他人的用户然后可以使用该代码和支持的应用程序或设备取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="90d66-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="90d66-107">下面是一些使用呼叫寄存的常见方案：</span><span class="sxs-lookup"><span data-stu-id="90d66-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="90d66-108">前台接待员 parks 呼叫的人在执行出厂中工作。</span><span class="sxs-lookup"><span data-stu-id="90d66-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="90d66-109">接待员然后宣布呼叫和代码编号，通过公共地址系统。</span><span class="sxs-lookup"><span data-stu-id="90d66-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="90d66-110">被叫的用户可以拿起在工厂团队电话，然后输入代码以取回呼叫。</span><span class="sxs-lookup"><span data-stu-id="90d66-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="90d66-111">用户 parks 移动设备上的呼叫，因为设备电池不足电源。</span><span class="sxs-lookup"><span data-stu-id="90d66-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="90d66-112">然后，用户可以输入代码以从团队桌面电话取回该呼叫。</span><span class="sxs-lookup"><span data-stu-id="90d66-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="90d66-113">支持代表性公园客户呼叫和专家取回该呼叫并帮助客户团队通道上发送通知。</span><span class="sxs-lookup"><span data-stu-id="90d66-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="90d66-114">专家进入团队客户端取回呼叫中的代码</span><span class="sxs-lookup"><span data-stu-id="90d66-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90d66-115">此功能才可用在仅团队部署模式下。</span><span class="sxs-lookup"><span data-stu-id="90d66-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="90d66-116">有关团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="90d66-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="90d66-117">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="90d66-117">License required</span></span>

<span data-ttu-id="90d66-118">若要寄存并取回呼叫，用户必须是企业语音的用户和管理员必须授予该用户的呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="90d66-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="90d66-119">有关许可模型的详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="90d66-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="90d66-120">呼叫驻留和检索功能可用性</span><span class="sxs-lookup"><span data-stu-id="90d66-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="90d66-121">呼叫寄存和取回是当前支持以下客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="90d66-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="90d66-122">（支持在仅工作组模式中，使用或不 PSTN 连接。）</span><span class="sxs-lookup"><span data-stu-id="90d66-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="90d66-123">功能</span><span class="sxs-lookup"><span data-stu-id="90d66-123">Capability</span></span> | <span data-ttu-id="90d66-124">团队桌面</span><span class="sxs-lookup"><span data-stu-id="90d66-124">Teams Desktop</span></span> | <span data-ttu-id="90d66-125">团队 Mac 应用程序</span><span class="sxs-lookup"><span data-stu-id="90d66-125">Teams Mac App</span></span> | <span data-ttu-id="90d66-126">工作组 Web 应用程序 （边缘）</span><span class="sxs-lookup"><span data-stu-id="90d66-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="90d66-127">团队移动 iOS/Android 应用程序</span><span class="sxs-lookup"><span data-stu-id="90d66-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="90d66-128">团队 IP 电话</span><span class="sxs-lookup"><span data-stu-id="90d66-128">Teams IP phone</span></span> | <span data-ttu-id="90d66-129">Skype 业务 IP 电话</span><span class="sxs-lookup"><span data-stu-id="90d66-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="90d66-130">驻留呼叫</span><span class="sxs-lookup"><span data-stu-id="90d66-130">Park a call</span></span> | <span data-ttu-id="90d66-131">是</span><span class="sxs-lookup"><span data-stu-id="90d66-131">Yes</span></span> | <span data-ttu-id="90d66-132">是</span><span class="sxs-lookup"><span data-stu-id="90d66-132">Yes</span></span> | <span data-ttu-id="90d66-133">是</span><span class="sxs-lookup"><span data-stu-id="90d66-133">Yes</span></span> | <span data-ttu-id="90d66-134">是</span><span class="sxs-lookup"><span data-stu-id="90d66-134">Yes</span></span> | <span data-ttu-id="90d66-135">即将提供</span><span class="sxs-lookup"><span data-stu-id="90d66-135">Coming soon</span></span>| <span data-ttu-id="90d66-136">否</span><span class="sxs-lookup"><span data-stu-id="90d66-136">No</span></span> |
| <span data-ttu-id="90d66-137">取回驻留的呼叫</span><span class="sxs-lookup"><span data-stu-id="90d66-137">Retrieve a parked call</span></span> | <span data-ttu-id="90d66-138">是</span><span class="sxs-lookup"><span data-stu-id="90d66-138">Yes</span></span> | <span data-ttu-id="90d66-139">是</span><span class="sxs-lookup"><span data-stu-id="90d66-139">Yes</span></span> | <span data-ttu-id="90d66-140">是</span><span class="sxs-lookup"><span data-stu-id="90d66-140">Yes</span></span> | <span data-ttu-id="90d66-141">是</span><span class="sxs-lookup"><span data-stu-id="90d66-141">Yes</span></span> | <span data-ttu-id="90d66-142">即将提供</span><span class="sxs-lookup"><span data-stu-id="90d66-142">Coming soon</span></span>| <span data-ttu-id="90d66-143">否</span><span class="sxs-lookup"><span data-stu-id="90d66-143">No</span></span> |
| <span data-ttu-id="90d66-144">返回未检索的电话铃声</span><span class="sxs-lookup"><span data-stu-id="90d66-144">Unretrieved call ring back</span></span> | <span data-ttu-id="90d66-145">是</span><span class="sxs-lookup"><span data-stu-id="90d66-145">Yes</span></span> | <span data-ttu-id="90d66-146">是</span><span class="sxs-lookup"><span data-stu-id="90d66-146">Yes</span></span> | <span data-ttu-id="90d66-147">是</span><span class="sxs-lookup"><span data-stu-id="90d66-147">Yes</span></span> | <span data-ttu-id="90d66-148">是</span><span class="sxs-lookup"><span data-stu-id="90d66-148">Yes</span></span> | <span data-ttu-id="90d66-149">即将提供</span><span class="sxs-lookup"><span data-stu-id="90d66-149">Coming soon</span></span>| <span data-ttu-id="90d66-150">否</span><span class="sxs-lookup"><span data-stu-id="90d66-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="90d66-151">配置呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="90d66-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="90d66-152">您必须是管理员能够配置呼叫寄存和取回，和默认情况下禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="90d66-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="90d66-153">您可以为用户启用它，并创建使用呼叫寄存策略的用户组。</span><span class="sxs-lookup"><span data-stu-id="90d66-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="90d66-154">时为一组用户应用同一策略，他们可以寄存并取回呼叫之间本身。</span><span class="sxs-lookup"><span data-stu-id="90d66-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="90d66-155">若要配置呼叫寄存的用户和用户组创建呼叫寄存，按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)过程。</span><span class="sxs-lookup"><span data-stu-id="90d66-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="90d66-156">有关如何使用呼叫寄存和检索功能的信息，请参阅[寄存团队中的呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="90d66-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="90d66-157">启用呼叫寄存策略</span><span class="sxs-lookup"><span data-stu-id="90d66-157">Enable a call park policy</span></span>

<span data-ttu-id="90d66-158">请按照下列步骤来启用呼叫寄存策略：</span><span class="sxs-lookup"><span data-stu-id="90d66-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="90d66-159">转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。</span><span class="sxs-lookup"><span data-stu-id="90d66-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="90d66-160">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="90d66-160">Select **New policy**.</span></span>
3. <span data-ttu-id="90d66-161">为策略指定名称，然后切换到**上**的**允许呼叫寄存**。</span><span class="sxs-lookup"><span data-stu-id="90d66-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="90d66-162">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="90d66-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="90d66-163">分配呼叫寄存策略</span><span class="sxs-lookup"><span data-stu-id="90d66-163">Assign a call park policy</span></span>

<span data-ttu-id="90d66-164">按照以下步骤为一个或多个用户分配呼叫寄存策略：</span><span class="sxs-lookup"><span data-stu-id="90d66-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="90d66-165">转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。</span><span class="sxs-lookup"><span data-stu-id="90d66-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="90d66-166">通过单击左侧的策略名称选择的策略。</span><span class="sxs-lookup"><span data-stu-id="90d66-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="90d66-167">选择**管理用户**。</span><span class="sxs-lookup"><span data-stu-id="90d66-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="90d66-168">在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="90d66-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="90d66-169">要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="90d66-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="90d66-170">添加完用户后，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="90d66-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="90d66-171">配置呼叫寄存和检索与 PowerShell</span><span class="sxs-lookup"><span data-stu-id="90d66-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="90d66-172">使用[新建 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="90d66-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="90d66-173">使用[授予 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予的呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="90d66-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="90d66-174">您可以使用[集 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) ，如下所示更改默认设置：</span><span class="sxs-lookup"><span data-stu-id="90d66-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="90d66-175">疑难解答</span><span class="sxs-lookup"><span data-stu-id="90d66-175">Troubleshooting</span></span>

<span data-ttu-id="90d66-176">如果用户不能看到寄存或检索按钮：</span><span class="sxs-lookup"><span data-stu-id="90d66-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="90d66-177">检查用户具有启用呼叫寄存策略。</span><span class="sxs-lookup"><span data-stu-id="90d66-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="90d66-178">如果用户尝试检索呼叫，并且不成功，检查以下项目：</span><span class="sxs-lookup"><span data-stu-id="90d66-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="90d66-179">验证用户使用团队客户端或工作组启用设备/电话</span><span class="sxs-lookup"><span data-stu-id="90d66-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="90d66-180">分组 – 是呼叫寄存组的成员的用户？</span><span class="sxs-lookup"><span data-stu-id="90d66-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="90d66-181">岛模式 – 呼叫寄存和取回是团队岛模式中不可用。</span><span class="sxs-lookup"><span data-stu-id="90d66-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="90d66-182">已检索或终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="90d66-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="90d66-183">更多信息</span><span class="sxs-lookup"><span data-stu-id="90d66-183">More information</span></span>

<span data-ttu-id="90d66-184">[寄存呼叫的团队](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="90d66-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>