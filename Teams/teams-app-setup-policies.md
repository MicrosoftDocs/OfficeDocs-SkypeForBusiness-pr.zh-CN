---
title: 在 Microsoft Teams 中管理应用设置策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 2/11/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解 Microsoft 团队以及如何使用它们 pin 应用程序自定义您的组织中的用户的工作组中的应用程序设置策略。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e6ad41dac9021079bffa80284809733c39f3cc9
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205760"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="07ed7-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="07ed7-103">Manage app setup policies in Microsoft Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="07ed7-104">作为一名管理员，您可以使用应用程序设置策略自定义 Microsoft 团队以突出显示您的用户的最重要的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="07ed7-105">选择锁定并设置它们出现的顺序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="07ed7-106">应用程序安装策略允许您展示您的组织中的用户需要包括由第三方或由组织中的开发人员构建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="07ed7-107">您还可以使用应用程序安装策略管理如何内置功能显示。</span><span class="sxs-lookup"><span data-stu-id="07ed7-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="07ed7-108">应用程序被固定到应用程序栏。</span><span class="sxs-lookup"><span data-stu-id="07ed7-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="07ed7-109">这是一小组桌面客户端侧和底部的团队移动客户端 （iOS 和 Android） 的栏。</span><span class="sxs-lookup"><span data-stu-id="07ed7-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="07ed7-110">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="07ed7-110">Teams desktop client</span></span>  |<span data-ttu-id="07ed7-111">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="07ed7-111">Teams mobile client</span></span> |
|---------|---------|
|![app-setup-policies-desktop-app-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![app-setup-policies-mobile-app-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="07ed7-114">管理 Microsoft 团队管理中心中的应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="07ed7-115">您可以使用全局 （组织范围内默认值） 策略或创建自定义策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="07ed7-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="07ed7-116">您的组织中的用户将自动授予全局策略，除非您创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="07ed7-117">您可以编辑该全局策略中的设置，以包含所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="07ed7-118">如果您想要自定义为不同的组织中用户组的团队，创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![应用程序的安装程序 policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="07ed7-120">如果用户已分配的自定义策略，该策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="07ed7-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="07ed7-121">如果用户未分配的自定义策略，全局策略应用于用户。</span><span class="sxs-lookup"><span data-stu-id="07ed7-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="07ed7-122">创建自定义应用程序安装程序策略</span><span class="sxs-lookup"><span data-stu-id="07ed7-122">Create a custom app setup policy</span></span>

<span data-ttu-id="07ed7-123">您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-123">You can use the Microsoft Teams admin center or Windows PowerShell to create a custom policy.</span></span>

1. <span data-ttu-id="07ed7-124">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序设置策略**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-124">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>
2. <span data-ttu-id="07ed7-125">选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-125">Select **New policy**.</span></span>
3. <span data-ttu-id="07ed7-126">输入策略的描述性名称，然后单击**添加应用程序**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="07ed7-127">在**添加固定应用程序**窗格中，搜索要添加，然后单击**添加**的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-127">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span>  <span data-ttu-id="07ed7-128">若要查看所有应用程序的列表，请选中**团队应用程序存储**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-128">To see a list of all    apps, select **Teams app store**.</span></span> <span data-ttu-id="07ed7-129">您已选择您的应用程序的列表，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-129">When you've chosen your list of apps, click **Add**.</span></span>

     ![应用程序的安装程序的策略-添加-apps.png](media/app-setup-policies-add-apps.png)

5. <span data-ttu-id="07ed7-131">排列您所愿团队中显示，然后单击**保存**的顺序应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-131">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![app-setup-policies-new-policy-setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="07ed7-133">编辑应用程序安装程序策略</span><span class="sxs-lookup"><span data-stu-id="07ed7-133">Edit an app setup policy</span></span>

<span data-ttu-id="07ed7-134">您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 编辑策略，包括全局 （组织范围内默认值） 策略和您创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-134">You can use the Microsoft Teams admin center or Windows PowerShell to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="07ed7-135">在左窗格中的 Microsoft 团队管理中心，转到**团队应用程序** > **应用程序设置策略**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-135">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>
2. <span data-ttu-id="07ed7-136">选择您想要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-136">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="07ed7-137">从此处，进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="07ed7-137">From here, make the changes that you want.</span></span> <span data-ttu-id="07ed7-138">您可以添加、 删除和更改的应用程序的顺序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-138">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="07ed7-139">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="07ed7-139">Click **Save**.</span></span> 

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="07ed7-140">将自定义应用程序安装策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="07ed7-140">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="07ed7-141">您可以使用 Microsoft 团队管理中心自定义策略分配给单个用户或 Windows PowerShell，可以分配给用户，例如安全组的组或通讯组的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-141">You can use the Microsoft Teams admin center to assign a custom policy to individual users or Windows PowerShell to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="07ed7-142">自定义应用程序安装策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="07ed7-142">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="07ed7-143">在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。</span><span class="sxs-lookup"><span data-stu-id="07ed7-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click       the user.</span></span>
2. <span data-ttu-id="07ed7-144">旁边**分配策略**，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="07ed7-145">**团队应用程序设置策略**，下选择要分配的应用程序设置策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-145">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![应用程序的安装程序的策略-分配-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="07ed7-147">自定义应用程序安装策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="07ed7-147">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="07ed7-148">您可能想要为已识别的多个用户分配自定义应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-148">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="07ed7-149">例如，您可能要将策略分配给安全组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="07ed7-149">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="07ed7-150">您可以通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="07ed7-150">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="07ed7-151">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="07ed7-151">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="07ed7-152">本示例中，我们自定义应用程序安装程序将策略分配到 Contoso 药品 HR 项目组中的所有用户称为人力资源应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-152">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="07ed7-153">请确保您首次[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块的 Skype。</span><span class="sxs-lookup"><span data-stu-id="07ed7-153">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="07ed7-154">获取特定的组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="07ed7-154">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="07ed7-155">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="07ed7-155">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="07ed7-156">组中的所有用户都分配特定的应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-156">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="07ed7-157">本示例中，它是 HR 应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-157">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="07ed7-158">根据组中成员的数目，此命令可能需要几分钟才能执行。</span><span class="sxs-lookup"><span data-stu-id="07ed7-158">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="07ed7-159">常见问题</span><span class="sxs-lookup"><span data-stu-id="07ed7-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="07ed7-160">使用应用程序设置策略</span><span class="sxs-lookup"><span data-stu-id="07ed7-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="07ed7-161">内置应用程序安装程序将哪些策略都包含在 Microsoft 团队管理中心？</span><span class="sxs-lookup"><span data-stu-id="07ed7-161">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="07ed7-162">**全局 （组织范围内默认值）**： 此默认策略应用于组织中的所有用户，除非您将其他策略分配。</span><span class="sxs-lookup"><span data-stu-id="07ed7-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="07ed7-163">编辑您的用户的最重要的 pin 应用程序的全局策略。</span><span class="sxs-lookup"><span data-stu-id="07ed7-163">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="07ed7-164">**FirstLineWorker**： 此策略为 firstline 工作者。</span><span class="sxs-lookup"><span data-stu-id="07ed7-164">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="07ed7-165">您可以将其组织中分配给 firstline 工作者。</span><span class="sxs-lookup"><span data-stu-id="07ed7-165">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="07ed7-166">务必要了解，如您所创建的自定义策略，您必须将策略分配给用户处于活动状态的设置。</span><span class="sxs-lookup"><span data-stu-id="07ed7-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="07ed7-167">详细信息，请转到本文的[分配给用户的自定义应用程序设置策略](#assign-a-custom-app-setup-policy-to-users)一节。</span><span class="sxs-lookup"><span data-stu-id="07ed7-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="07ed7-168">为什么我无法在添加固定的应用程序窗格中查找应用程序</span><span class="sxs-lookup"><span data-stu-id="07ed7-168">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="07ed7-169">通过应用程序设置策略，可以向工作组固定并非所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="07ed7-170">某些应用程序可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="07ed7-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="07ed7-171">若要查找可以固定的应用程序，请搜索**添加固定应用程序**窗格中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="07ed7-172">具有个人范围 （静态选项卡） 和自动程序的选项卡可以固定到团队桌面客户端，这些应用程序也可在**添加固定应用程序**窗格中。</span><span class="sxs-lookup"><span data-stu-id="07ed7-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="07ed7-173">请记住，团队应用程序商店将列出所有团队应用程序，而**固定添加应用程序**窗格包括仅可以通过策略固定到团队的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-173">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="07ed7-174">我是团队教育管理员。我需要了解在面向教育机构的团队中的应用程序设置策略的哪些内容？</span><span class="sxs-lookup"><span data-stu-id="07ed7-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="07ed7-175">面向教育机构的团队中调用应用程序不可用。</span><span class="sxs-lookup"><span data-stu-id="07ed7-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="07ed7-176">创建新的自定义应用程序安装策略时，调用应用程序的应用程序列表中显示。</span><span class="sxs-lookup"><span data-stu-id="07ed7-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="07ed7-177">但是，应用程序不固定到团队客户端和团队的培训用户看团队中的呼叫应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="07ed7-178">可以向策略添加多少应用程序？</span><span class="sxs-lookup"><span data-stu-id="07ed7-178">How many apps can be added to a policy?</span></span>

<span data-ttu-id="07ed7-179">至少两个应用程序必须固定的团队移动客户端 （iOS 和 Android）。</span><span class="sxs-lookup"><span data-stu-id="07ed7-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="07ed7-180">如果策略具有少于两个应用程序，移动客户端不会反映的策略设置和改为将继续使用现有的配置。</span><span class="sxs-lookup"><span data-stu-id="07ed7-180">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="07ed7-181">如何长时间才会生效的策略更改？</span><span class="sxs-lookup"><span data-stu-id="07ed7-181">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="07ed7-182">编辑全局策略或分配策略后，可以最多 24 小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="07ed7-182">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="07ed7-183">用户体验</span><span class="sxs-lookup"><span data-stu-id="07ed7-183">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="07ed7-184">用户如何查看团队中的其固定应用程序？</span><span class="sxs-lookup"><span data-stu-id="07ed7-184">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="07ed7-185">若要查看固定的用户的所有应用程序，用户可能需要执行以下操作具体取决于已安装的应用程序的数目和其团队客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="07ed7-185">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="07ed7-186">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="07ed7-186">Teams desktop client</span></span> |<span data-ttu-id="07ed7-187">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="07ed7-187">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="07ed7-188">在工作组的一侧的应用程序栏中，单击 **...更多应用程序**。</span><span class="sxs-lookup"><span data-stu-id="07ed7-188">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="07ed7-189">在工作组底部附近的应用程序栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="07ed7-189">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![app-setup-policies-desktop-more-apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![app-setup-policies-mobile-more-apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="07ed7-192">了解团队移动体验时需要什么操作？</span><span class="sxs-lookup"><span data-stu-id="07ed7-192">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="07ed7-193">团队移动客户端 （iOS 和 Android） 当前不支持静态选项卡与个人应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-193">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="07ed7-194">在策略中设置的应用程序，根据固定到团队桌面客户端应用程序可能不出现在工作组移动客户端。</span><span class="sxs-lookup"><span data-stu-id="07ed7-194">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="07ed7-195">个人 bot 仍显示在聊天移动客户端上。</span><span class="sxs-lookup"><span data-stu-id="07ed7-195">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="07ed7-196">团队移动客户端，用户会看到如活动、 聊天和团队的核心团队应用程序，您可以锁定某些 microsoft，如班次的第一方应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-196">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="07ed7-197">用户可以更改的固定通过策略的应用程序的顺序？</span><span class="sxs-lookup"><span data-stu-id="07ed7-197">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="07ed7-198">目前，用户可以更改其固定的应用程序团队移动客户端上但团队桌面或 web 客户端的顺序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-198">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="07ed7-199">自定义团队应用程序</span><span class="sxs-lookup"><span data-stu-id="07ed7-199">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-through-appsource-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="07ed7-200">我的组织构建自定义的团队应用程序并将其发布到 AppSource 但预期时应用程序固定到应用程序栏团队中不显示的应用程序图标。</span><span class="sxs-lookup"><span data-stu-id="07ed7-200">My organization built a custom Teams app and published it through AppSource but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="07ed7-201">如何解决它？</span><span class="sxs-lookup"><span data-stu-id="07ed7-201">How do I fix it?</span></span> 

<span data-ttu-id="07ed7-202">请确保您遵循徽标准则之前提交应用程序。</span><span class="sxs-lookup"><span data-stu-id="07ed7-202">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="07ed7-203">若要了解详细信息，请参阅[卖方仪表板提交的清单](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)。</span><span class="sxs-lookup"><span data-stu-id="07ed7-203">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="07ed7-204">相关主题</span><span class="sxs-lookup"><span data-stu-id="07ed7-204">Related topics</span></span>
- [<span data-ttu-id="07ed7-205">从工作组客户端租户的应用程序目录发布应用程序</span><span class="sxs-lookup"><span data-stu-id="07ed7-205">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
