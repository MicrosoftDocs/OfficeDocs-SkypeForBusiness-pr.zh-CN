---
title: 管理 Microsoft 团队中的呼叫者 ID 策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: a4dbdbac0922bb475f47447a3cf8b2d0f001909c
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224247"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="e312b-103">管理 Microsoft 团队中的呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="e312b-104">作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。</span><span class="sxs-lookup"><span data-stu-id="e312b-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="e312b-105">默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e312b-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="e312b-106">可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。</span><span class="sxs-lookup"><span data-stu-id="e312b-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="e312b-107">例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e312b-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="e312b-108">通过转到**Voice**  >  "Microsoft 团队管理中心" 中的 "语音来电显示"**策略**来管理呼叫者 id 策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e312b-109">可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e312b-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="e312b-110">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="e312b-111">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="e312b-112">如果向用户分配了自定义策略，则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="e312b-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="e312b-113">如果未向用户分配自定义策略，则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="e312b-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="e312b-114">创建自定义呼叫方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="e312b-115">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e312b-116">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e312b-116">Click **Add**.</span></span> <br>
<span data-ttu-id="e312b-117">![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e312b-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="e312b-118">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e312b-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e312b-119">在此处，选择所需的设置：</span><span class="sxs-lookup"><span data-stu-id="e312b-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="e312b-120">**阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="e312b-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="e312b-121">**替代呼叫方 ID 策略**：启用此设置，让用户覆盖策略中的设置以将其号码显示为 callees。</span><span class="sxs-lookup"><span data-stu-id="e312b-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="e312b-122">这意味着用户可以选择是否要显示其呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="e312b-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="e312b-123">有关详细信息，请参阅[最终用户对出站呼叫程序 ID 的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。</span><span class="sxs-lookup"><span data-stu-id="e312b-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="e312b-124">将**来电显示替换**为：通过选择下列操作之一，设置要为用户显示的呼叫者 id：</span><span class="sxs-lookup"><span data-stu-id="e312b-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="e312b-125">**用户号码**：显示用户的号码。</span><span class="sxs-lookup"><span data-stu-id="e312b-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="e312b-126">**服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="e312b-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="e312b-127">**匿名**：以匿名方式显示呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="e312b-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="e312b-128">**将呼叫方 Id 替换为此服务号码**：选择服务号码以替换用户的来电显示。</span><span class="sxs-lookup"><span data-stu-id="e312b-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="e312b-129">如果在 **"将呼叫方 ID 替换为**" 中选择了 "**服务编号**"，则此选项可用。</span><span class="sxs-lookup"><span data-stu-id="e312b-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="e312b-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e312b-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="e312b-131">编辑呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-131">Edit a caller ID policy</span></span>

<span data-ttu-id="e312b-132">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="e312b-133">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e312b-134">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e312b-135">更改所需的设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="e312b-136">为用户分配自定义呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="e312b-137">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便为用户组（如安全组或通讯组）分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="e312b-138">为用户分配自定义呼叫者线路 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-138">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="e312b-139">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e312b-139">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e312b-140">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-140">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="e312b-141">在 "**呼叫者 ID 策略**" 下，选择要分配的策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-141">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="e312b-142">一次为多个用户分配自定义呼叫线路 ID 策略</span><span class="sxs-lookup"><span data-stu-id="e312b-142">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="e312b-143">若要一次为多个用户分配自定义呼叫线路 Id 策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="e312b-143">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="e312b-144">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e312b-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e312b-145">转到**Microsoft 团队管理中心**  >  **语音**  >  **呼叫方 ID 策略**。</span><span class="sxs-lookup"><span data-stu-id="e312b-145">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="e312b-146">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e312b-147">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e312b-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="e312b-148">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="e312b-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e312b-149">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e312b-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e312b-150">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e312b-150">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="e312b-151">将自定义呼叫方 ID 策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="e312b-151">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="e312b-152">你可能需要向已标识的多个用户分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-152">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="e312b-153">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-153">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="e312b-154">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e312b-154">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="e312b-155">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e312b-155">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="e312b-156">在此示例中，我们为 Contoso 支持组中的所有用户分配一个名为支持呼叫者 ID 策略的自定义呼叫者盖子策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-156">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="e312b-157">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="e312b-157">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e312b-158">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="e312b-158">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="e312b-159">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="e312b-159">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e312b-160">将组中的所有用户分配给特定的呼叫者 ID 策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-160">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="e312b-161">在此示例中，它支持呼叫方 ID 策略。</span><span class="sxs-lookup"><span data-stu-id="e312b-161">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="e312b-162">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="e312b-162">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="e312b-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="e312b-163">Related topics</span></span>

- [<span data-ttu-id="e312b-164">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="e312b-164">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

