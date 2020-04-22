---
title: 在 Microsoft Teams 中管理应用设置策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中为你的组织中的用户使用和管理应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 55b43e9fe156a2b3707cb5e99c57239345bf031e
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749819"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="bf9c4-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="bf9c4-104">如果启用了组织范围的应用设置，**允许与自定义应用交互**，则你可能看不到 Microsoft 团队管理中心中的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bf9c4-105">它目前正在推出，即将在您的组织中提供。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="bf9c4-106">作为管理员，你可以使用应用设置策略执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf9c4-106">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="bf9c4-107">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="bf9c4-108">你可以选择要固定的应用，并设置它们的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="bf9c4-109">通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-109">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="bf9c4-110">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="bf9c4-111">代表用户安装应用 **（在预览中）**。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="bf9c4-112">在用户启动团队时，选择默认为用户安装的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="bf9c4-113">请记住，如果分配给应用的[应用权限策略](teams-app-permission-policies.md)允许，用户仍然可以自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="bf9c4-114">将应用程序固定到应用栏。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-114">Apps are pinned to the app bar.</span></span> <span data-ttu-id="bf9c4-115">这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-115">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="bf9c4-116">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="bf9c4-116">Teams desktop client</span></span>  |<span data-ttu-id="bf9c4-117">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="bf9c4-117">Teams mobile client</span></span> |
|---------|---------|
|![显示团队桌面客户端的屏幕截图](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![显示团队移动客户端的屏幕截图](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="bf9c4-120">若要查看其预安装应用，请在应用栏中单击 " **..."** 团队桌面和 web 客户端中的更多应用，并在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-120">To see their pre-installed apps, in the app bar, users click **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="bf9c4-121">在 Microsoft 团队管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bf9c4-122">可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-122">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="bf9c4-123">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="bf9c4-124">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="bf9c4-125">你可以编辑全局策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-125">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="bf9c4-126">如果要为组织中的不同组用户自定义团队，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-126">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="bf9c4-127">如果向用户分配了自定义策略，则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-127">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="bf9c4-128">如果未向用户分配自定义策略，则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-128">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

![显示应用设置策略页面的屏幕截图](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="bf9c4-130">如果你有团队教育版，请务必了解，默认情况下，作业应用固定在全局策略中，即使当前，你也看不到全局策略中列出了该应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-130">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="bf9c4-131">它将是团队客户端上的固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-131">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="bf9c4-132">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-132">Create a custom app setup policy</span></span>

<span data-ttu-id="bf9c4-133">你可以使用 Microsoft 团队管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-133">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="bf9c4-134">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="bf9c4-135">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-135">Click **Add**.</span></span>
    <span data-ttu-id="bf9c4-136">![显示 "添加应用设置策略" 页面的屏幕截图](media/app-setup-policies-add.png)</span><span class="sxs-lookup"><span data-stu-id="bf9c4-136">![Screenshot showing the Add app setup policies page](media/app-setup-policies-add.png)</span></span>
3. <span data-ttu-id="bf9c4-137">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-137">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="bf9c4-138">打开或关闭 "**上载自定义应用程序**"，具体取决于是否希望允许用户将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-138">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="bf9c4-139">如果 "[组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)" 中的 "**允许第三方应用**" 处于关闭状态，则不能更改此设置。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-139">You won't be able to change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>
5. <span data-ttu-id="bf9c4-140">打开或关闭 "**允许用户固定**"，具体取决于是否希望让用户通过将应用固定到应用栏来对其应用栏进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-140">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>
6. <span data-ttu-id="bf9c4-141">若要为用户安装应用 **（在预览中）**，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bf9c4-141">To install apps for users **(in preview)**, do the following:</span></span>

    1. <span data-ttu-id="bf9c4-142">在 "**已安装的应用**" 下，单击 "**添加应用**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-142">Under **Installed apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="bf9c4-143">在 "**添加已安装的应用**" 窗格中，搜索你希望在用户启动团队时为用户自动安装的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-143">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="bf9c4-144">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-144">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="bf9c4-145">选择应用列表后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-145">When you've chosen your list of apps, click **Add**.</span></span>

        ![显示 "添加已安装的应用" 窗格的屏幕截图](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="bf9c4-147">若要固定应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bf9c4-147">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="bf9c4-148">在 "**固定应用**" 下，单击 "**添加应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-148">Under **Pinned apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="bf9c4-149">在 "**添加固定的应用**" 窗格中，搜索要添加的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-149">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="bf9c4-150">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-150">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="bf9c4-151">选择要固定的应用列表后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-151">When you've chosen your list of apps to pin, click **Add**.</span></span>

         ![显示 "添加固定应用" 窗格的屏幕截图](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="bf9c4-153">按希望在团队中显示的顺序排列应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-153">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

        ![显示 "固定的应用" 部分的屏幕截图](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="bf9c4-155">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-155">Edit an app setup policy</span></span>

<span data-ttu-id="bf9c4-156">你可以使用 Microsoft 团队管理中心编辑策略，包括全局（组织范围默认）策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-156">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="bf9c4-157">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-157">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="bf9c4-158">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-158">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="bf9c4-159">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-159">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="bf9c4-160">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-160">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="bf9c4-161">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-161">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="bf9c4-162">你可以使用 Microsoft 团队管理中心向单个用户或 Skype for business PowerShell 模块分配自定义策略，以将自定义策略分配给用户组，如安全组或通讯组。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-162">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="bf9c4-163">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-163">Assign a custom app setup policy to users</span></span>

1. <span data-ttu-id="bf9c4-164">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="bf9c4-165">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bf9c4-165">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="bf9c4-166">在 "**应用设置策略**" 下，选择要分配的应用设置策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-166">Under **App setup policy**, select the app setup policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="bf9c4-167">若要将策略一次性分配给多个用户，请参阅[批量编辑 Teams 用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-167">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="bf9c4-168">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf9c4-168">Or, you can also do the following:</span></span>

1. <span data-ttu-id="bf9c4-169">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-169">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="bf9c4-170">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bf9c4-171">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="bf9c4-172">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bf9c4-173">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bf9c4-174">添加完用户后，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-174">After you finish adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="bf9c4-175">为组中的用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-175">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="bf9c4-176">你可能需要将自定义应用设置策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-176">You may want to assign a custom app setup policy to multiple users that you've already identified.</span></span> <span data-ttu-id="bf9c4-177">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="bf9c4-178">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="bf9c4-179">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="bf9c4-180">在此示例中，我们为 Contoso 制药人力资源项目组中的所有用户分配一个名为 "HR App Setup 策略" 的自定义应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-180">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="bf9c4-181">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="bf9c4-182">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-182">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="bf9c4-183">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-183">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="bf9c4-184">将组中的所有用户分配到特定应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-184">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="bf9c4-185">在此示例中，它是 HR 应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-185">In this example, it's HR App Setup Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="bf9c4-186">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="bf9c4-187">常见问题</span><span class="sxs-lookup"><span data-stu-id="bf9c4-187">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="bf9c4-188">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="bf9c4-188">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf9c4-189">Microsoft 团队管理中心中包括哪些内置应用设置策略？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-189">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="bf9c4-190">**全局（组织范围默认值）**：此默认策略适用于你组织中的所有用户，除非你分配其他策略。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-190">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="bf9c4-191">编辑全局策略以固定对你的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-191">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="bf9c4-192">**FirstLineWorker**：此政策适用于一线工作者。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-192">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="bf9c4-193">你可以将其分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-193">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="bf9c4-194">请务必知道，例如你创建的自定义策略，你必须将策略分配给用户才能使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-194">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="bf9c4-195">有关详细信息，请转到本文的 "向[用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users)" 部分。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-195">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="bf9c4-196">为什么我无法在 "添加固定的应用" 窗格中找到应用？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-196">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="bf9c4-197">并非所有应用都可以通过应用设置策略固定到团队。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-197">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="bf9c4-198">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-198">Some apps may not support this functionality.</span></span> <span data-ttu-id="bf9c4-199">若要查找可固定的应用，请在 "**添加固定的应用**" 窗格中搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-199">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="bf9c4-200">具有个人作用域（静态选项卡）和机器人的选项卡可以固定到团队桌面客户端，并且这些应用在 "**添加固定应用**" 窗格中可用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-200">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="bf9c4-201">请记住，"团队" 应用商店将列出所有团队应用，而 "**添加固定的应用**" 窗格仅包括可通过策略固定到团队的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-201">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="bf9c4-202">我是教育版管理员的团队。我需要了解有关团队教育版中的应用设置策略的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-202">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="bf9c4-203">"呼叫" 应用在教育版团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-203">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="bf9c4-204">创建新的自定义应用设置策略时，将在应用列表中显示调用应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-204">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="bf9c4-205">但是，应用不会固定到团队客户端和团队，教育用户将看不到团队中的 "调用" 应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-205">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="bf9c4-206">可以向策略添加多少个固定的应用？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-206">How many pinned apps can be added to a policy?</span></span>

<span data-ttu-id="bf9c4-207">必须将两个应用中的至少一个应用固定到团队移动客户端（iOS 和 Android）。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-207">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="bf9c4-208">如果策略的应用少于两个，则移动客户端不会反映策略设置，而是将继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-208">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="bf9c4-209">对于可添加到策略的固定应用的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-209">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="bf9c4-210">策略更改需要多长时间才能生效？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-210">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="bf9c4-211">编辑全局策略或分配策略后，所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-211">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="bf9c4-212">用户体验</span><span class="sxs-lookup"><span data-stu-id="bf9c4-212">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="bf9c4-213">用户如何能够查看团队中的所有固定应用？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-213">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="bf9c4-214">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装应用的数量以及其团队客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-214">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="bf9c4-215">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="bf9c4-215">Teams desktop client</span></span> |<span data-ttu-id="bf9c4-216">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="bf9c4-216">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="bf9c4-217">在团队侧面的应用栏中，单击 **.。。更多应用**。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-217">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="bf9c4-218">在团队底部附近的应用栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-218">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![显示团队桌面客户端中的更多应用的屏幕截图](media/app-setup-policies-desktop-more-apps.png)<br>   |![在团队移动客户端中显示更多应用的屏幕截图](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="bf9c4-221">我需要了解有关团队移动体验的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-221">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="bf9c4-222">团队移动客户端（iOS 和 Android）目前不支持带有静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-222">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="bf9c4-223">根据策略中设置的应用，固定到团队桌面客户端的应用可能不会显示在团队移动客户端中。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-223">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="bf9c4-224">在移动客户端上，个人机器人仍将显示在聊天中。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-224">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="bf9c4-225">通过团队移动客户端，用户将看到核心团队应用（如活动、聊天和团队），并且你可以固定 Microsoft 的一些第三方应用，例如倒班。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-225">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="bf9c4-226">用户是否可以更改通过策略固定的应用顺序？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-226">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="bf9c4-227">如果启用了 "**允许用户固定**" 选项，用户可以更改团队桌面和移动客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-227">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="bf9c4-228">用户无法更改团队 web 客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-228">Users can't change the order of their pinned apps on Teams web clients.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="bf9c4-229">自定义团队应用</span><span class="sxs-lookup"><span data-stu-id="bf9c4-229">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="bf9c4-230">我的组织构建了一个自定义团队应用，并已将其发布到 AppSource 或租户应用目录，但当应用固定到团队中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-230">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="bf9c4-231">如何解决此问题？</span><span class="sxs-lookup"><span data-stu-id="bf9c4-231">How do I fix it?</span></span>

<span data-ttu-id="bf9c4-232">在提交应用之前，请确保遵循徽标指南。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-232">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="bf9c4-233">若要了解详细信息，请参阅[卖方仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="bf9c4-233">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="bf9c4-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="bf9c4-234">Related topics</span></span>

- [<span data-ttu-id="bf9c4-235">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="bf9c4-235">Admin settings for apps in Teams</span></span>](admin-settings.md)
