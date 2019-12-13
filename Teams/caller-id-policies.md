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
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的呼叫者 ID 策略更改或阻止组织中的团队用户的来电显示 ID。
ms.openlocfilehash: 8a8e235c1adf24e5a11b0b62e7542d5fcae194be
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998820"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="137ed-103">管理 Microsoft 团队中的呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="137ed-104">作为管理员，你可以使用 Microsoft 团队中的来电显示策略来更改或阻止来电显示（也称为呼叫线路 ID）。</span><span class="sxs-lookup"><span data-stu-id="137ed-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="137ed-105">默认情况下，当用户呼叫 PSTN 电话时，可以看到团队用户的电话号码，并且在呼叫团队用户时可以看到 PSTN 呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="137ed-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="137ed-106">可以使用来电显示策略为组织中的团队用户显示备用电话号码，或阻止显示传入号码。</span><span class="sxs-lookup"><span data-stu-id="137ed-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="137ed-107">例如，当用户进行呼叫时，您可以更改来电显示以显示组织的主要电话号码，而不是用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="137ed-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="137ed-108">通过转到 "Microsoft 团队管理中心" 中的 "**语音** > **来电**显示" 策略来管理呼叫者 id 策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="137ed-109">你可以使用全局（组织范围默认）策略或创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="137ed-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="137ed-110">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="137ed-111">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="137ed-112">如果向用户分配了自定义策略，则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="137ed-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="137ed-113">如果未向用户分配自定义策略，则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="137ed-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="137ed-114">创建自定义呼叫方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="137ed-115">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="137ed-116">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="137ed-116">Click **Add**.</span></span>
<span data-ttu-id="137ed-117">![管理中心中新来电显示策略页面的屏幕截图](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="137ed-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="137ed-118">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="137ed-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="137ed-119">在此处，选择所需的设置：</span><span class="sxs-lookup"><span data-stu-id="137ed-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="137ed-120">**阻止来电呼叫者 id**：启用此设置可阻止显示传入呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="137ed-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="137ed-121">**用户可以替代呼叫方 ID 策略**：启用此设置可让用户替代策略中的设置，将其号码显示为 callees。</span><span class="sxs-lookup"><span data-stu-id="137ed-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="137ed-122">这意味着用户可以选择是否要显示其呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="137ed-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="137ed-123">**替换呼叫者 id**：通过选择下列操作之一，设置要为用户显示的来电显示：</span><span class="sxs-lookup"><span data-stu-id="137ed-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="137ed-124">**用户号码**：显示用户的号码。</span><span class="sxs-lookup"><span data-stu-id="137ed-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="137ed-125">**服务号码**：允许您将服务电话号码设置为显示为呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="137ed-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="137ed-126">**匿名**：以匿名方式显示呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="137ed-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="137ed-127">用于**替换呼叫方 id 的服务号码**：选择服务号码以替换用户的来电显示。</span><span class="sxs-lookup"><span data-stu-id="137ed-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="137ed-128">如果在 "**替换呼叫方 ID**" 中选择了 "**服务号码**"，则此选项可用。</span><span class="sxs-lookup"><span data-stu-id="137ed-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="137ed-129">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="137ed-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="137ed-130">编辑呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-130">Edit a caller ID policy</span></span>

<span data-ttu-id="137ed-131">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="137ed-132">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音** > **呼叫者 ID 策略**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="137ed-133">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="137ed-134">更改所需的设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="137ed-135">为用户分配自定义呼叫者 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="137ed-136">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便为用户组（如安全组或通讯组）分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="137ed-137">为用户分配自定义呼叫者线路 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="137ed-138">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="137ed-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="137ed-139">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="137ed-140">在 "**呼叫者 ID 策略**" 下，选择要分配的策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="137ed-141">一次为多个用户分配自定义呼叫线路 ID 策略</span><span class="sxs-lookup"><span data-stu-id="137ed-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="137ed-142">若要一次为多个用户分配自定义呼叫线路 Id 策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="137ed-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="137ed-143">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="137ed-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="137ed-144">转到**Microsoft 团队管理中心** > **语音** > **呼叫方 ID 策略**。</span><span class="sxs-lookup"><span data-stu-id="137ed-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="137ed-145">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="137ed-146">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="137ed-147">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="137ed-148">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="137ed-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="137ed-149">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="137ed-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="137ed-150">将自定义呼叫方 ID 策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="137ed-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="137ed-151">你可能需要向已标识的多个用户分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="137ed-152">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="137ed-153">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="137ed-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="137ed-154">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="137ed-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="137ed-155">在此示例中，我们为 Contoso 支持组中的所有用户分配一个名为支持呼叫者 ID 策略的自定义呼叫者盖子策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="137ed-156">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="137ed-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="137ed-157">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="137ed-157">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="137ed-158">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="137ed-158">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="137ed-159">将组中的所有用户分配给特定的呼叫者 ID 策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="137ed-160">在此示例中，它支持呼叫方 ID 策略。</span><span class="sxs-lookup"><span data-stu-id="137ed-160">In this example, it's Support Caller ID Policy.</span></span>
```
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="137ed-161">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="137ed-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="137ed-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="137ed-162">Related topics</span></span>

- [<span data-ttu-id="137ed-163">新-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="137ed-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

