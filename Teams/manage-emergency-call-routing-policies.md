---
title: 管理 Microsoft 团队中的紧急呼叫路由策略
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中使用和管理紧急呼叫路由策略。
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 4520bc1d9cc6a4e84a3702e32db859b784ae02bc
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998800"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="a4933-103">管理 Microsoft 团队中的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="a4933-104">如果您已在您的组织中部署了手机系统直接路由，则可以使用 Microsoft 团队中的紧急呼叫路由策略来设置紧急电话号码，并指定如何路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="a4933-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="a4933-105">紧急呼叫路由策略确定是否为分配了该策略的用户启用增强的紧急服务、用于呼叫紧急服务的号码（例如，911在美国），以及如何路由紧急服务通话。</span><span class="sxs-lookup"><span data-stu-id="a4933-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="a4933-106">通过转到 Microsoft 团队管理中心或使用 Windows PowerShell 中的**语音** > **紧急策略**，管理紧急呼叫路由策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="a4933-107">可将策略分配给用户和[网络站点](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a4933-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="a4933-108">对于用户，你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="a4933-109">除非你创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a4933-110">请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="a4933-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="a4933-111">对于网络站点，您可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="a4933-112">如果为某个网络网站和用户分配了紧急呼叫路由策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="a4933-113">创建自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a4933-114">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="a4933-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a4933-115">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫路由策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4933-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="a4933-116">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4933-116">Click **Add**.</span></span>
3. <span data-ttu-id="a4933-117">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a4933-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="a4933-118">若要启用增强的紧急服务，请打开**增强的紧急服务**。</span><span class="sxs-lookup"><span data-stu-id="a4933-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="a4933-119">启用 "增强紧急服务" 时，团队将从服务中检索策略和位置信息，并将该信息作为紧急呼叫的一部分包括在其中。</span><span class="sxs-lookup"><span data-stu-id="a4933-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="a4933-120">定义一个更紧急的号码。</span><span class="sxs-lookup"><span data-stu-id="a4933-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="a4933-121">若要执行此操作，请在 "**紧急电话号码**" 下执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a4933-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="a4933-122">**紧急拨号字符串**：输入 "紧急拨号" 字符串。</span><span class="sxs-lookup"><span data-stu-id="a4933-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="a4933-123">此拨号字符串表示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="a4933-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="a4933-124">对于直接路由，我们将通过 "+" 在 "紧急拨号" 字符串前面的 "+" 发送紧急呼叫的团队客户进行转移。</span><span class="sxs-lookup"><span data-stu-id="a4933-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="a4933-125">在转换完成之前，与紧急拨号字符串匹配的语音路线模式应确保对具有前面没有 "+" （如911和 + 911）的字符串进行匹配。</span><span class="sxs-lookup"><span data-stu-id="a4933-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="a4933-126">例如，^\\+？911或. \*。</span><span class="sxs-lookup"><span data-stu-id="a4933-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="a4933-127">**紧急拨号掩码**：对于每个紧急电话号码，您可以指定零个或多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="a4933-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="a4933-128">拨号掩码是要转换为 "紧急拨号字符串" 值的数字。</span><span class="sxs-lookup"><span data-stu-id="a4933-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="a4933-129">这允许拨打备用紧急号码，并且仍然可以拨打紧急服务。</span><span class="sxs-lookup"><span data-stu-id="a4933-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="a4933-130">例如，您将112添加为 "紧急拨号掩码"，这是欧洲大多数欧洲的紧急服务号码，911作为 "紧急拨号" 字符串。</span><span class="sxs-lookup"><span data-stu-id="a4933-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="a4933-131">欧洲来访的团队用户可能不知道911是美国的紧急电话，当他们拨打112时，将拨打911。</span><span class="sxs-lookup"><span data-stu-id="a4933-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="a4933-132">若要定义多个拨号掩码，请用分号分隔每个值。</span><span class="sxs-lookup"><span data-stu-id="a4933-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="a4933-133">例如，112; 212。</span><span class="sxs-lookup"><span data-stu-id="a4933-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="a4933-134">**PSTN 使用**：选择公共交换电话网络（PSTN）使用。</span><span class="sxs-lookup"><span data-stu-id="a4933-134">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="a4933-135">PSTN 使用用于确定使用哪种路由从有权使用它们的用户路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="a4933-135">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="a4933-136">与此使用相关联的路由应指向专用于紧急呼叫的 SIP 中继，或者指向紧急位置标识号码（ELIN）网关，该网关将紧急呼叫路由到最近的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="a4933-136">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a4933-137">拨号式字符串和拨号掩码在策略中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a4933-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="a4933-138">这意味着对于策略，你可以定义多个紧急号码，并且可以为拨号字符串设置多个拨号掩码，但每个拨号字符串和拨号掩码只能使用一次。</span><span class="sxs-lookup"><span data-stu-id="a4933-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="a4933-139">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a4933-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a4933-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4933-140">Using PowerShell</span></span>

<span data-ttu-id="a4933-141">请参阅[新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4933-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="a4933-142">编辑紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a4933-143">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="a4933-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a4933-144">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="a4933-145">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫路由策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4933-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="a4933-146">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="a4933-147">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a4933-148">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4933-148">Using PowerShell</span></span>

<span data-ttu-id="a4933-149">请参阅[设置-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4933-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="a4933-150">为用户分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-150">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a4933-151">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="a4933-151">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a4933-152">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="a4933-152">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a4933-153">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-153">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="a4933-154">在 "**紧急呼叫路由策略**" 下，选择要分配的策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-154">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="a4933-155">若要一次为多个用户分配自定义团队策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="a4933-155">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="a4933-156">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a4933-156">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a4933-157">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **紧急策略**"，然后单击 "**呼叫路由策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4933-157">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="a4933-158">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-158">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="a4933-159">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-159">Select **Manage users**.</span></span>
4. <span data-ttu-id="a4933-160">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-160">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a4933-161">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="a4933-161">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="a4933-162">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a4933-162">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a4933-163">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4933-163">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="a4933-164">为用户分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-164">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="a4933-165">请参阅[授权-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a4933-165">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="a4933-166">为组中的用户分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-166">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="a4933-167">您可能希望将自定义紧急呼叫路由策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="a4933-167">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="a4933-168">例如，你可能想要向安全组或通讯组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-168">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="a4933-169">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a4933-169">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="a4933-170">在此示例中，我们将名为 "HR 紧急呼叫路由策略" 的策略分配给 "Contoso HR" 组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="a4933-170">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="a4933-171">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="a4933-171">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="a4933-172">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="a4933-172">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="a4933-173">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="a4933-173">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="a4933-174">将组中的所有用户分配到特定团队策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-174">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="a4933-175">在此示例中，它是 HR 紧急呼叫路由策略。</span><span class="sxs-lookup"><span data-stu-id="a4933-175">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="a4933-176">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="a4933-176">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="a4933-177">为网络站点分配自定义紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="a4933-177">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="a4933-178">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫路由策略分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="a4933-178">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="a4933-179">此示例显示了如何将名为 "紧急呼叫路由策略 1" 的策略分配给 Site1 网站。</span><span class="sxs-lookup"><span data-stu-id="a4933-179">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="a4933-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="a4933-180">Related topics</span></span>

- [<span data-ttu-id="a4933-181">管理团队中的紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="a4933-181">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="a4933-182">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="a4933-182">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
