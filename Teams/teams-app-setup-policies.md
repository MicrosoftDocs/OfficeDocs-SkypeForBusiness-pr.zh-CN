---
title: 在 Microsoft Teams 中管理应用设置策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解 Microsoft 团队中的应用设置策略以及如何使用它们来固定应用, 以便为你的组织中的用户自定义团队。
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: e26dc18f056f3493f6fcbdea2edee747d8abfa0b
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548818"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="992db-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="992db-104">如果启用了组织范围的应用权限策略设置,**允许与自定义应用交互**, 则你可能看不到 Microsoft 团队管理中心中的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="992db-104">If you enabled the org-wide app permission policy setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="992db-105">它目前正在推出, 即将在您的组织中提供。</span><span class="sxs-lookup"><span data-stu-id="992db-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="992db-106">作为管理员, 你可以使用应用设置策略自定义 Microsoft 团队, 以突出显示对你的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-106">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="992db-107">你可以选择要固定的应用, 并设置它们的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="992db-107">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="992db-108">应用设置策略允许你展示组织中的用户所需的应用, 包括由第三方或你的组织中的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-108">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="992db-109">你还可以使用应用设置策略来管理内置功能的显示方式。</span><span class="sxs-lookup"><span data-stu-id="992db-109">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="992db-110">应用程序将固定到应用栏。</span><span class="sxs-lookup"><span data-stu-id="992db-110">Apps are pinned to the app bar.</span></span> <span data-ttu-id="992db-111">这是团队桌面客户端和团队移动客户端 (iOS 和 Android) 底部的栏。</span><span class="sxs-lookup"><span data-stu-id="992db-111">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="992db-112">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="992db-112">Teams desktop client</span></span>  |<span data-ttu-id="992db-113">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="992db-113">Teams mobile client</span></span> |
|---------|---------|
|![显示团队桌面客户端的屏幕截图](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![显示团队移动客户端的屏幕截图](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="992db-116">在 Microsoft 团队管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="992db-116">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="992db-117">你可以使用全局 (组织范围默认) 策略或创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="992db-117">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="992db-118">除非你创建并分配自定义策略, 否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="992db-118">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="992db-119">你可以编辑全局策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-119">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="992db-120">如果要为组织中的不同组用户自定义团队, 请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="992db-120">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="992db-121">如果向用户分配了自定义策略, 则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="992db-121">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="992db-122">如果未向用户分配自定义策略, 则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="992db-122">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

![显示应用设置策略页面的屏幕截图](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="992db-124">如果你有团队教育版, 请务必了解, 默认情况下, 作业应用固定在全局策略中, 即使当前, 你也看不到全局策略中列出了该应用。</span><span class="sxs-lookup"><span data-stu-id="992db-124">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="992db-125">它将是团队客户端上的固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="992db-125">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="992db-126">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-126">Create a custom app setup policy</span></span>

<span data-ttu-id="992db-127">你可以使用 Microsoft 团队管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="992db-127">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="992db-128">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="992db-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="992db-129">选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="992db-129">Select **New policy**.</span></span>
3. <span data-ttu-id="992db-130">输入策略的描述性名称, 然后单击 "**添加应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="992db-130">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="992db-131">打开或关闭 "**允许上载自定义应用**", 具体取决于是否希望允许用户将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="992db-131">Turn on or turn off **Allow uploading custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span>
5. <span data-ttu-id="992db-132">在 "**添加固定的应用**" 窗格中, 搜索要添加的应用, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="992db-132">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="992db-133">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="992db-133">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="992db-134">选择应用列表后, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="992db-134">When you've chosen your list of apps, click **Add**.</span></span>

     ![显示 "添加固定应用" 窗格的屏幕截图](media/app-setup-policies-add-apps.png)

6. <span data-ttu-id="992db-136">按希望在团队中显示的顺序排列应用, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="992db-136">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![显示 "固定的应用" 部分的屏幕截图](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="992db-138">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-138">Edit an app setup policy</span></span>

<span data-ttu-id="992db-139">你可以使用 Microsoft 团队管理中心编辑策略, 包括全局 (组织范围默认) 策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="992db-139">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="992db-140">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="992db-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="992db-141">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="992db-141">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="992db-142">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="992db-142">From here, make the changes that you want.</span></span> <span data-ttu-id="992db-143">你可以添加、删除和更改应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="992db-143">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="992db-144">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="992db-144">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="992db-145">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-145">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="992db-146">你可以使用 Microsoft 团队管理中心向单个用户或 Skype for business PowerShell 模块分配自定义策略, 以将自定义策略分配给用户组, 如安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="992db-146">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="992db-147">我们建议仅使用 PowerShell 为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="992db-147">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="992db-148">使用 Microsoft 团队管理中心创建、编辑和管理策略。</span><span class="sxs-lookup"><span data-stu-id="992db-148">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="992db-149">向单个用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-149">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="992db-150">在 Microsoft 团队管理中心的左侧导航中, 转到 "**用户**", 然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="992db-150">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="992db-151">在 "**分配的策略**" 旁边, 选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="992db-151">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="992db-152">在 "**团队应用设置策略**" 下, 选择要分配的应用设置策略, 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="992db-152">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![显示 "编辑用户策略" 窗格的屏幕截图](media/app-setup-policies-assign-policy.png)

<span data-ttu-id="992db-154">你还可以将应用设置策略分配给一个或多个用户, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="992db-154">You can also assign an app setup policy to one or more users as follows:</span></span>

1. <span data-ttu-id="992db-155">转到**Microsoft 团队管理中心** > **团队应用** > **设置策略**。</span><span class="sxs-lookup"><span data-stu-id="992db-155">Go to **Microsoft Teams admin center** > **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="992db-156">通过单击策略名称的左侧, 选择策略。</span><span class="sxs-lookup"><span data-stu-id="992db-156">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="992db-157">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="992db-157">Select **Manage users**.</span></span>
4. <span data-ttu-id="992db-158">在 "**管理用户**" 窗格中, 按 "显示名称" 或 "按用户名搜索用户", 选择名称, 然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="992db-158">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="992db-159">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="992db-159">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="992db-160">完成添加用户后, 请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="992db-160">When you are finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="992db-161">为组中的用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-161">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="992db-162">你可能需要将自定义应用设置策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="992db-162">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="992db-163">例如, 你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="992db-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="992db-164">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="992db-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="992db-165">有关使用 PowerShell 管理团队的详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="992db-165">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="992db-166">在此示例中, 我们为 Contoso 制药人力资源项目组中的所有用户分配一个名为 "HR App Setup 策略" 的自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="992db-166">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="992db-167">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤, 确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="992db-167">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="992db-168">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="992db-168">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="992db-169">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="992db-169">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="992db-170">将组中的所有用户分配到特定应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="992db-170">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="992db-171">在此示例中, 它是 HR 应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="992db-171">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="992db-172">此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="992db-172">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="992db-173">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="992db-173">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="992db-174">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="992db-174">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="992db-175">Microsoft 团队管理中心中包括哪些内置应用设置策略？</span><span class="sxs-lookup"><span data-stu-id="992db-175">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="992db-176">**全局 (组织范围默认值)**: 此默认策略适用于你组织中的所有用户, 除非你分配其他策略。</span><span class="sxs-lookup"><span data-stu-id="992db-176">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="992db-177">编辑全局策略以固定对你的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-177">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="992db-178">**FirstLineWorker**: 此政策适用于一线工作者。</span><span class="sxs-lookup"><span data-stu-id="992db-178">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="992db-179">你可以将其分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="992db-179">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="992db-180">请务必知道, 例如你创建的自定义策略, 你必须将策略分配给用户才能使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="992db-180">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="992db-181">有关详细信息, 请转到本文的 "向[用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users)" 部分。</span><span class="sxs-lookup"><span data-stu-id="992db-181">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="992db-182">为什么我无法在 "添加固定的应用" 窗格中找到应用？</span><span class="sxs-lookup"><span data-stu-id="992db-182">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="992db-183">并非所有应用都可以通过应用设置策略固定到团队。</span><span class="sxs-lookup"><span data-stu-id="992db-183">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="992db-184">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="992db-184">Some apps may not support this functionality.</span></span> <span data-ttu-id="992db-185">若要查找可固定的应用, 请在 "**添加固定的应用**" 窗格中搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="992db-185">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="992db-186">具有个人作用域 (静态选项卡) 和机器人的选项卡可以固定到团队桌面客户端, 并且这些应用在 "**添加固定应用**" 窗格中可用。</span><span class="sxs-lookup"><span data-stu-id="992db-186">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="992db-187">请记住, "团队" 应用商店将列出所有团队应用, 而 "**添加固定的应用**" 窗格仅包括可通过策略固定到团队的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-187">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="992db-188">我是教育版管理员的团队。我需要了解有关团队教育版中的应用设置策略的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="992db-188">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

- <span data-ttu-id="992db-189">"呼叫" 应用在教育版团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="992db-189">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="992db-190">创建新的自定义应用设置策略时, 将在应用列表中显示调用应用。</span><span class="sxs-lookup"><span data-stu-id="992db-190">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="992db-191">但是, 应用不会固定到团队客户端和团队, 教育用户将看不到团队中的 "调用" 应用。</span><span class="sxs-lookup"><span data-stu-id="992db-191">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

- <span data-ttu-id="992db-192">当前, 团队中的团队针对教育版应用中的用户不会反映策略更改。</span><span class="sxs-lookup"><span data-stu-id="992db-192">Currently, policy changes aren't reflected for Teams for Education users on the Teams Android app.</span></span> <span data-ttu-id="992db-193">我们正在致力于支持适用于教育团队的策略更改的新版本应用。</span><span class="sxs-lookup"><span data-stu-id="992db-193">We're working on a new version of the app that supports policy changes for Teams for Education.</span></span>

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="992db-194">可以向策略添加多少个应用？</span><span class="sxs-lookup"><span data-stu-id="992db-194">How many apps can be added to a policy?</span></span>

<span data-ttu-id="992db-195">必须将两个应用中的至少一个应用固定到团队移动客户端 (iOS 和 Android)。</span><span class="sxs-lookup"><span data-stu-id="992db-195">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="992db-196">如果策略的应用少于两个, 则移动客户端不会反映策略设置, 而是将继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="992db-196">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="992db-197">策略更改需要多长时间才能生效？</span><span class="sxs-lookup"><span data-stu-id="992db-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="992db-198">编辑全局策略或分配策略后, 所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="992db-198">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="992db-199">用户体验</span><span class="sxs-lookup"><span data-stu-id="992db-199">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="992db-200">用户如何能够查看团队中的所有固定应用？</span><span class="sxs-lookup"><span data-stu-id="992db-200">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="992db-201">若要查看为用户固定的所有应用, 用户可能需要执行以下操作, 具体取决于已安装应用的数量以及其团队客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="992db-201">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="992db-202">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="992db-202">Teams desktop client</span></span> |<span data-ttu-id="992db-203">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="992db-203">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="992db-204">在团队侧面的应用栏中, 单击 **.。。更多应用**。</span><span class="sxs-lookup"><span data-stu-id="992db-204">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="992db-205">在团队底部附近的应用栏中, 向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="992db-205">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![在团队桌面客户端中显示更多应用的屏幕截图](media/app-setup-policies-desktop-more-apps.png)<br>   |![在团队移动客户端中显示更多应用的屏幕截图](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="992db-208">我需要了解有关团队移动体验的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="992db-208">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="992db-209">团队移动客户端 (iOS 和 Android) 目前不支持带有静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="992db-209">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="992db-210">根据策略中设置的应用, 固定到团队桌面客户端的应用可能不会显示在团队移动客户端中。</span><span class="sxs-lookup"><span data-stu-id="992db-210">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="992db-211">在移动客户端上, 个人机器人仍将显示在聊天中。</span><span class="sxs-lookup"><span data-stu-id="992db-211">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="992db-212">通过团队移动客户端, 用户将看到核心团队应用 (如活动、聊天和团队), 并且你可以固定 Microsoft 的一些第三方应用, 例如倒班。</span><span class="sxs-lookup"><span data-stu-id="992db-212">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span> 

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="992db-213">用户是否可以更改通过策略固定的应用顺序？</span><span class="sxs-lookup"><span data-stu-id="992db-213">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="992db-214">当前, 用户可以更改团队移动客户端上的固定应用的顺序, 但不能更改团队桌面或 web 客户端上的应用。</span><span class="sxs-lookup"><span data-stu-id="992db-214">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="992db-215">自定义团队应用</span><span class="sxs-lookup"><span data-stu-id="992db-215">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="992db-216">我的组织构建了一个自定义团队应用, 并已将其发布到 AppSource 或租户应用目录, 但当应用固定到团队中的应用栏时, 应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="992db-216">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="992db-217">如何解决此问题？</span><span class="sxs-lookup"><span data-stu-id="992db-217">How do I fix it?</span></span> 

<span data-ttu-id="992db-218">在提交应用之前, 请确保遵循徽标指南。</span><span class="sxs-lookup"><span data-stu-id="992db-218">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="992db-219">若要了解详细信息, 请参阅[卖方仪表板提交清单](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)。</span><span class="sxs-lookup"><span data-stu-id="992db-219">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="992db-220">相关主题</span><span class="sxs-lookup"><span data-stu-id="992db-220">Related topics</span></span>
- [<span data-ttu-id="992db-221">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="992db-221">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="992db-222">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="992db-222">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="992db-223">在 Teams 中管理自定义应用策略和设置</span><span class="sxs-lookup"><span data-stu-id="992db-223">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="992db-224">从团队客户端将应用发布到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="992db-224">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
