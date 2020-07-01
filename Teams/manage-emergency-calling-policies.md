---
title: 管理 Microsoft 团队中的紧急呼叫策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的紧急呼叫策略，定义当组织中的团队用户拨打紧急电话时会发生什么情况。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12d2e114a53c47e6c938c6c2cb4bf3cb83c81180
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938431"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="2fe19-103">管理 Microsoft 团队中的紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="2fe19-104">如果您的组织使用[呼叫计划](set-up-calling-plans.md)或部署的[电话系统直接路由](direct-routing-landing-page.md)，则可以使用 Microsoft 团队中的紧急呼叫策略定义当组织中的团队用户进行紧急呼叫时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2fe19-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="2fe19-105">你可以设置被分配了策略的用户呼叫紧急服务时通知的人员以及通知的方式。</span><span class="sxs-lookup"><span data-stu-id="2fe19-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="2fe19-106">例如，你可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急呼叫中进行侦听。</span><span class="sxs-lookup"><span data-stu-id="2fe19-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="2fe19-107">通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**紧急策略**来管理紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="2fe19-108">可将策略分配给用户和[网络站点](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe19-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="2fe19-109">对于用户，你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2fe19-110">除非你创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2fe19-111">请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="2fe19-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="2fe19-112">对于网络站点，您可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="2fe19-113">如果你为某个网络网站和用户分配了紧急呼叫策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="2fe19-114">创建自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2fe19-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="2fe19-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2fe19-116">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fe19-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2fe19-117">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2fe19-117">Click **Add**.</span></span>
3. <span data-ttu-id="2fe19-118">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2fe19-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2fe19-119">设置当进行紧急呼叫时，您希望将组织中的人员（通常是安全桌面）通知的方式。</span><span class="sxs-lookup"><span data-stu-id="2fe19-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="2fe19-120">若要执行此操作，请在 "**通知模式**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2fe19-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="2fe19-121">**仅发送通知**：团队聊天消息将发送到您指定的用户和组。</span><span class="sxs-lookup"><span data-stu-id="2fe19-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="2fe19-122">**Conferenced in 但静音**：将团队聊天消息发送给你指定的用户和组，他们可以在呼叫方和 PSAP 运营商之间的对话中侦听（但不参与）。</span><span class="sxs-lookup"><span data-stu-id="2fe19-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="2fe19-123">**Conferenced 在已取消静音** **（即将推出）**：团队聊天消息将发送给你指定的用户和组，并且可以取消静音以侦听和参与调用方和 PSAP 运算符之间的对话。</span><span class="sxs-lookup"><span data-stu-id="2fe19-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="2fe19-124">如果您选择了 "Conferenced"，**但处于静音**通知模式，请在 "**拨打紧急电话通知的号码**" 框中，输入用户或组的 PSTN 电话号码以呼叫并加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="2fe19-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="2fe19-125">例如，输入您的组织的安全桌面号码，当进行紧急呼叫时，您将收到呼叫，然后就能接听电话。</span><span class="sxs-lookup"><span data-stu-id="2fe19-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="2fe19-126">搜索并选择一个或多个用户或组（如组织的安全桌面），以便在发生紧急呼叫时发出通知。</span><span class="sxs-lookup"><span data-stu-id="2fe19-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="2fe19-127">通知可以发送到用户、通讯组和安全组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2fe19-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="2fe19-128">最多可通知50用户。</span><span class="sxs-lookup"><span data-stu-id="2fe19-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="2fe19-129">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="2fe19-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2fe19-130">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fe19-130">Using PowerShell</span></span>

<span data-ttu-id="2fe19-131">请参阅[新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2fe19-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="2fe19-132">编辑紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2fe19-133">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="2fe19-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2fe19-134">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="2fe19-135">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fe19-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2fe19-136">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="2fe19-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2fe19-137">进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="2fe19-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2fe19-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fe19-138">Using PowerShell</span></span>

<span data-ttu-id="2fe19-139">请参阅[设置-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2fe19-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="2fe19-140">为用户分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="2fe19-141">另请参阅[授权 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2fe19-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="2fe19-142">将自定义紧急呼叫策略分配给网络站点</span><span class="sxs-lookup"><span data-stu-id="2fe19-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="2fe19-143">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="2fe19-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="2fe19-144">以下示例显示了如何将名为 Contoso 紧急呼叫策略1的策略分配给 Site1 网站。</span><span class="sxs-lookup"><span data-stu-id="2fe19-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="2fe19-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="2fe19-145">Related topics</span></span>

[<span data-ttu-id="2fe19-146">管理团队中的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="2fe19-147">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="2fe19-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="2fe19-148">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="2fe19-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
