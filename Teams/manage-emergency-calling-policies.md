---
title: 在 Microsoft Teams 中管理紧急呼叫策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft Teams 中的紧急呼叫策略，以定义当贵组织的 Teams 用户进行紧急呼叫时会发生什么情况。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973136"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="21a3e-103">在 Microsoft Teams 中管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="21a3e-104">如果你 [的组织使用呼叫](set-up-calling-plans.md) 计划或已部署的电话系统直接 [路由](direct-routing-landing-page.md)，可以使用 Microsoft Teams 中的紧急呼叫策略来定义当贵组织的 Teams 用户进行紧急呼叫时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="21a3e-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="21a3e-105">可以设置在分配有策略的用户呼叫紧急服务时要通知谁以及如何通知他们。</span><span class="sxs-lookup"><span data-stu-id="21a3e-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="21a3e-106">例如，可以将策略设置配置为自动通知组织的安全服务台，让他们在紧急呼叫中收听。</span><span class="sxs-lookup"><span data-stu-id="21a3e-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="21a3e-107">通过访问 Microsoft Teams 管理中心中的语音紧急策略或通过使用语音呼叫策略来管理  >  紧急呼叫Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21a3e-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="21a3e-108">可以将策略分配给用户和网络 [网站](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="21a3e-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="21a3e-109">对于用户，可以使用全局 (组织范围内的默认) 策略或创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="21a3e-110">除非创建并分配了自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="21a3e-111">请记住，可以在全局策略中编辑设置，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="21a3e-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="21a3e-112">对于网络站点，请创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="21a3e-113">如果将紧急呼叫策略分配给网络站点和用户，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="21a3e-114">创建自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="21a3e-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="21a3e-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="21a3e-116">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音** 紧急策略"，然后单击"呼叫  >  **策略"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="21a3e-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="21a3e-117">单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="21a3e-117">Click **Add**.</span></span>
3. <span data-ttu-id="21a3e-118">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="21a3e-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="21a3e-119">设置当您进行紧急呼叫时您希望如何通知组织内部人员（通常是安全服务台）。</span><span class="sxs-lookup"><span data-stu-id="21a3e-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="21a3e-120">为此，请在通知 **模式下** 选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="21a3e-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="21a3e-121">**仅发送通知**：Teams 聊天消息将发送到指定的用户和组。</span><span class="sxs-lookup"><span data-stu-id="21a3e-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="21a3e-122">已 **静音** 且无法取消静音的会议：Teams 聊天消息将发送到你指定的用户和组，他们可以侦听 (，但不能) 呼叫方和 PSAP 操作员之间的对话中参与聊天。</span><span class="sxs-lookup"><span data-stu-id="21a3e-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="21a3e-123">已 **静音** 但能够取消静音的会议：Teams 聊天消息将发送给你指定的用户和组，他们可以取消静音以收听和参与呼叫方与 PSAP 操作员之间的对话。</span><span class="sxs-lookup"><span data-stu-id="21a3e-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="21a3e-124">如果在静音通知模式下选择了任一会议，可在"拨打紧急呼叫通知号码"框中输入用户或组的 PSTN 电话号码，以呼叫和加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21a3e-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="21a3e-125">例如，输入组织安全服务台的号码，当进行紧急呼叫时，谁将接收呼叫，然后可以侦听呼叫。</span><span class="sxs-lookup"><span data-stu-id="21a3e-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="21a3e-126">PSTN 电话无法取消静音，即使模式设置为静音但 **能够取消静音**。</span><span class="sxs-lookup"><span data-stu-id="21a3e-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="21a3e-127">搜索并选择一个或多个用户或组（例如组织的安全服务台）以在拨打紧急呼叫时通知。</span><span class="sxs-lookup"><span data-stu-id="21a3e-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="21a3e-128">通知可以发送到用户、通讯组和安全组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="21a3e-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="21a3e-129">最多可以通知 50 个用户。</span><span class="sxs-lookup"><span data-stu-id="21a3e-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="21a3e-130">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="21a3e-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="21a3e-131">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="21a3e-131">Using PowerShell</span></span>

<span data-ttu-id="21a3e-132">请参阅[New-CsTeamsEmergencyCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="21a3e-132">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="21a3e-133">编辑紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="21a3e-134">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="21a3e-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="21a3e-135">可以编辑全局策略或创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="21a3e-136">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"语音** 紧急策略"，然后单击"呼叫  >  **策略"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="21a3e-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="21a3e-137">单击策略名称左侧选择策略，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="21a3e-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="21a3e-138">进行您需要的更改，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="21a3e-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="21a3e-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="21a3e-139">Using PowerShell</span></span>

<span data-ttu-id="21a3e-140">请参阅[Set-CsTeamsEmergencyCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="21a3e-140">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="21a3e-141">向用户分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="21a3e-142">另请参阅[Grant-CsTeamsEmergencyCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="21a3e-142">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="21a3e-143">向网络站点分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="21a3e-144">使用 [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 向网络站点分配紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="21a3e-144">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="21a3e-145">以下示例演示如何将名为 Contoso 紧急呼叫策略 1 的策略分配给 Site1 站点。</span><span class="sxs-lookup"><span data-stu-id="21a3e-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="21a3e-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="21a3e-146">Related topics</span></span>

[<span data-ttu-id="21a3e-147">在 Teams 中管理紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="21a3e-148">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="21a3e-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="21a3e-149">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="21a3e-149">Assign policies to your users in Teams</span></span>](assign-policies.md)
