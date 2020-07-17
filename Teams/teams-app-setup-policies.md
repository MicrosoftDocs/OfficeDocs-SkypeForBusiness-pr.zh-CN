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
ms.openlocfilehash: 9ddbcd1a5110cff52ce518cf052279204fc8e2c9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938211"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="b1fe3-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="b1fe3-104">如果启用了组织范围的应用设置，**允许与自定义应用交互**，则你可能看不到 Microsoft 团队管理中心中的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1fe3-105">它目前正在推出，即将在您的组织中提供。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="b1fe3-106">作为管理员，你可以使用应用设置策略执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1fe3-106">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="b1fe3-107">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="b1fe3-108">你可以选择要固定的应用，并设置它们的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="b1fe3-109">通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-109">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="b1fe3-110">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="b1fe3-111">代表用户安装应用 **（在预览中）**。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="b1fe3-112">在用户启动团队时，选择默认为用户安装的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="b1fe3-113">请记住，如果分配给应用的[应用权限策略](teams-app-permission-policies.md)允许，用户仍然可以自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="b1fe3-114">将应用程序固定到应用栏。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-114">Apps are pinned to the app bar.</span></span> <span data-ttu-id="b1fe3-115">这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-115">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="b1fe3-116">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="b1fe3-116">Teams desktop client</span></span>  |<span data-ttu-id="b1fe3-117">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="b1fe3-117">Teams mobile client</span></span> |
|---------|---------|
|![显示团队桌面客户端的屏幕截图](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![显示团队移动客户端的屏幕截图](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="b1fe3-120">若要查看其预安装应用，请在应用栏中单击 " **..."** 团队桌面和 web 客户端中的更多应用，并在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-120">To see their pre-installed apps, in the app bar, users click **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="b1fe3-121">在 Microsoft 团队管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1fe3-122">你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-122">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="b1fe3-123">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="b1fe3-124">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="b1fe3-125">你可以编辑全局策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-125">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="b1fe3-126">如果要为组织中的不同组用户自定义团队，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-126">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![显示应用设置策略页面的屏幕截图](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="b1fe3-128">如果你有团队教育版，请务必了解，默认情况下，作业应用固定在全局策略中，即使当前，你也看不到全局策略中列出了该应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="b1fe3-129">它将是团队客户端上的固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="b1fe3-130">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-130">Create a custom app setup policy</span></span>

<span data-ttu-id="b1fe3-131">你可以使用 Microsoft 团队管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="b1fe3-132">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="b1fe3-133">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-133">Click **Add**.</span></span>
    <span data-ttu-id="b1fe3-134">![显示 "添加应用设置策略" 页面的屏幕截图](media/app-setup-policies-add.png)</span><span class="sxs-lookup"><span data-stu-id="b1fe3-134">![Screenshot showing the Add app setup policies page](media/app-setup-policies-add.png)</span></span>
3. <span data-ttu-id="b1fe3-135">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-135">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b1fe3-136">打开或关闭 "**上载自定义应用程序**"，具体取决于是否希望允许用户将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="b1fe3-137">如果 "[组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)" 中的 "**允许第三方应用**" 处于关闭状态，则不能更改此设置。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-137">You won't be able to change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>
5. <span data-ttu-id="b1fe3-138">打开或关闭 "**允许用户固定**"，具体取决于是否希望让用户通过将应用固定到应用栏来对其应用栏进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>
6. <span data-ttu-id="b1fe3-139">若要为用户安装应用 **（在预览中）**，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b1fe3-139">To install apps for users **(in preview)**, do the following:</span></span>

    1. <span data-ttu-id="b1fe3-140">在 "**已安装的应用**" 下，单击 "**添加应用**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-140">Under **Installed apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="b1fe3-141">在 "**添加已安装的应用**" 窗格中，搜索你希望在用户启动团队时为用户自动安装的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="b1fe3-142">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="b1fe3-143">选择应用列表后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-143">When you've chosen your list of apps, click **Add**.</span></span>

        ![显示 "添加已安装的应用" 窗格的屏幕截图](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="b1fe3-145">若要固定应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b1fe3-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="b1fe3-146">在 "**固定应用**" 下，单击 "**添加应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-146">Under **Pinned apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="b1fe3-147">在 "**添加固定的应用**" 窗格中，搜索要添加的应用，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-147">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="b1fe3-148">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="b1fe3-149">选择要固定的应用列表后，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-149">When you've chosen your list of apps to pin, click **Add**.</span></span>

         ![显示 "添加固定应用" 窗格的屏幕截图](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="b1fe3-151">按希望在团队中显示的顺序排列应用，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-151">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

        ![显示 "固定的应用" 部分的屏幕截图](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="b1fe3-153">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-153">Edit an app setup policy</span></span>

<span data-ttu-id="b1fe3-154">你可以使用 Microsoft 团队管理中心编辑策略，包括全局（组织范围默认）策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="b1fe3-155">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="b1fe3-156">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-156">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b1fe3-157">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-157">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="b1fe3-158">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="b1fe3-159">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="b1fe3-160">常见问题</span><span class="sxs-lookup"><span data-stu-id="b1fe3-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="b1fe3-161">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b1fe3-162">Microsoft 团队管理中心中包括哪些内置应用设置策略？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-162">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="b1fe3-163">**全局（组织范围默认值）**：此默认策略适用于你组织中的所有用户，除非你分配其他策略。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="b1fe3-164">编辑全局策略以固定对你的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-164">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="b1fe3-165">**FirstLineWorker**：此政策适用于一线工作者。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="b1fe3-166">你可以将其分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="b1fe3-167">请务必知道，例如你创建的自定义策略，你必须将策略分配给用户才能使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="b1fe3-168">有关详细信息，请转到本文的 "向[用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users)" 部分。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="b1fe3-169">为什么我无法在 "添加固定的应用" 窗格中找到应用？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-169">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="b1fe3-170">并非所有应用都可以通过应用设置策略固定到团队。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="b1fe3-171">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="b1fe3-172">若要查找可固定的应用，请在 "**添加固定的应用**" 窗格中搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="b1fe3-173">具有个人作用域（静态选项卡）和机器人的选项卡可以固定到团队桌面客户端，并且这些应用在 "**添加固定应用**" 窗格中可用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="b1fe3-174">请记住，"团队" 应用商店将列出所有团队应用，而 "**添加固定的应用**" 窗格仅包括可通过策略固定到团队的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-174">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="b1fe3-175">我是教育版管理员的团队。我需要了解有关团队教育版中的应用设置策略的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="b1fe3-176">"呼叫" 应用在教育版团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="b1fe3-177">创建新的自定义应用设置策略时，将在应用列表中显示调用应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="b1fe3-178">但是，应用不会固定到团队客户端和团队，教育用户将看不到团队中的 "调用" 应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="b1fe3-179">可以向策略添加多少个固定的应用？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-179">How many pinned apps can be added to a policy?</span></span>

<span data-ttu-id="b1fe3-180">必须将两个应用中的至少一个应用固定到团队移动客户端（iOS 和 Android）。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="b1fe3-181">如果策略的应用少于两个，则移动客户端不会反映策略设置，而是将继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-181">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="b1fe3-182">对于可添加到策略的固定应用的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="b1fe3-183">策略更改需要多长时间才能生效？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-183">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="b1fe3-184">编辑或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="b1fe3-185">用户体验</span><span class="sxs-lookup"><span data-stu-id="b1fe3-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="b1fe3-186">用户如何能够查看团队中的所有固定应用？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-186">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="b1fe3-187">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装应用的数量以及其团队客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-187">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="b1fe3-188">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="b1fe3-188">Teams desktop client</span></span> |<span data-ttu-id="b1fe3-189">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="b1fe3-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="b1fe3-190">在团队侧面的应用栏中，单击 **.。。更多应用**。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-190">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="b1fe3-191">在团队底部附近的应用栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![显示团队桌面客户端中的更多应用的屏幕截图](media/app-setup-policies-desktop-more-apps.png)<br>   |![在团队移动客户端中显示更多应用的屏幕截图](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="b1fe3-194">我需要了解有关团队移动体验的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-194">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="b1fe3-195">团队移动客户端（iOS 和 Android）目前不支持带有静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="b1fe3-196">根据策略中设置的应用，固定到团队桌面客户端的应用可能不会显示在团队移动客户端中。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="b1fe3-197">在移动客户端上，个人机器人仍将显示在聊天中。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="b1fe3-198">通过团队移动客户端，用户将看到核心团队应用（如活动、聊天和团队），并且你可以固定 Microsoft 的一些第三方应用，例如倒班。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="b1fe3-199">用户是否可以更改通过策略固定的应用顺序？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-199">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="b1fe3-200">如果启用了 "**允许用户固定**" 选项，用户可以更改团队桌面和移动客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="b1fe3-201">用户无法更改团队 web 客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="b1fe3-202">用户固定是否优先？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-202">Does user pinning take precedence?</span></span>

<span data-ttu-id="b1fe3-203">如果分配给用户的应用设置策略被更改为阻止用户应用固定，团队会删除固定到应用栏的任何应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-203">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="b1fe3-204">如果随后将策略更改为允许用户应用固定，则用户必须重新固定其以前固定的应用。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-204">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="b1fe3-205">自定义团队应用</span><span class="sxs-lookup"><span data-stu-id="b1fe3-205">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="b1fe3-206">我的组织构建了一个自定义团队应用，并已将其发布到 AppSource 或租户应用目录，但当应用固定到团队中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-206">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="b1fe3-207">如何解决此问题？</span><span class="sxs-lookup"><span data-stu-id="b1fe3-207">How do I fix it?</span></span>

<span data-ttu-id="b1fe3-208">在提交应用之前，请确保遵循徽标指南。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-208">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="b1fe3-209">若要了解详细信息，请参阅[卖方仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="b1fe3-209">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b1fe3-210">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1fe3-210">Related topics</span></span>

[<span data-ttu-id="b1fe3-211">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="b1fe3-211">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="b1fe3-212">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b1fe3-212">Assign policies to your users in Teams</span></span>](assign-policies.md)
