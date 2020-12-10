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
ms.openlocfilehash: a23d9f5196f2d537e00c6e049377f9a7d7488654
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611596"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="2e60e-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="2e60e-104">如果启用了组织范围的应用设置， **允许与自定义应用交互**，则你可能看不到 Microsoft 团队管理中心中的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2e60e-105">它目前正在推出，即将在您的组织中提供。</span><span class="sxs-lookup"><span data-stu-id="2e60e-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="2e60e-106">作为管理员，你可以使用应用设置策略执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2e60e-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="2e60e-107">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="2e60e-108">你可以选择要固定的应用，并设置它们的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="2e60e-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="2e60e-109">固定应用允许你展示你的组织需要的用户所需的应用，包括由第三方或你组织中的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="2e60e-110">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="2e60e-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="2e60e-111">**在预览) 中** 代表用户安装应用 (。</span><span class="sxs-lookup"><span data-stu-id="2e60e-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="2e60e-112">在用户启动团队时，选择默认为用户安装的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="2e60e-113">请记住，如果分配给应用的 [应用权限策略](teams-app-permission-policies.md) 允许，用户仍然可以自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="2e60e-114">应用程序将固定到应用栏，它是团队桌面客户端和团队移动客户端 (iOS 和 Android) 的栏。</span><span class="sxs-lookup"><span data-stu-id="2e60e-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="2e60e-115">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="2e60e-115">Teams desktop client</span></span>  |<span data-ttu-id="2e60e-116">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="2e60e-116">Teams mobile client</span></span> |
|---------|---------|
|![团队桌面客户端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![团队移动客户端](media/mobile-app-ui.png)      |

<span data-ttu-id="2e60e-119">若要查看其预安装应用，请在应用栏中，用户选择 **.。。** 团队桌面和 web 客户端中的更多应用，并在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="2e60e-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="2e60e-120">在 Microsoft 团队管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2e60e-121">使用全局 (组织范围默认) 策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="2e60e-122">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2e60e-123">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="2e60e-124">编辑全局策略中的设置以包括所需的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="2e60e-125">若要为组织中不同组的用户自定义团队，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![应用设置策略页面](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="2e60e-127">如果你有团队教育版，请务必了解，默认情况下，作业应用固定在全局策略中，即使当前，你也看不到全局策略中列出了该应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="2e60e-128">它将是团队客户端上的固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="2e60e-129">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-129">Create a custom app setup policy</span></span>

<span data-ttu-id="2e60e-130">你可以使用 Microsoft 团队管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="2e60e-131">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="2e60e-132">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="2e60e-132">Select **Add**.</span></span>

   !["添加应用设置策略" 页面](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="2e60e-134">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2e60e-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="2e60e-135">打开或关闭 " **上载自定义应用程序**"，具体取决于是否希望允许用户将自定义应用程序上载到团队。</span><span class="sxs-lookup"><span data-stu-id="2e60e-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="2e60e-136">如果 " **允许第三方应用** " 在 [组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)中处于关闭状态，则不能更改此设置。</span><span class="sxs-lookup"><span data-stu-id="2e60e-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="2e60e-137">打开或关闭 " **允许用户固定**"，具体取决于是否希望让用户通过将应用固定到应用栏来对其应用栏进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="2e60e-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2e60e-138">Microsoft 365 政府社区中的 " **允许用户固定** " 设置适用于 Microsoft 政府社区中的团队管理中心 (gcc) 环境 (GCC、gcc 高和 DoD) ，但当前它不起作用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="2e60e-139">若要为用户安装应用 **(在 "预览) 中**，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2e60e-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="2e60e-140">在 " **已安装的应用**" 下，选择 " **添加应用**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="2e60e-141">在 " **添加已安装的应用** " 窗格中，搜索你希望在用户启动团队时为用户自动安装的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="2e60e-142">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="2e60e-143">选择应用列表后，选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-143">When you've chosen your list of apps, select **Add**.</span></span>

       !["添加已安装的应用" 窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="2e60e-145">若要固定应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2e60e-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="2e60e-146">在 " **固定应用**" 下，选择 " **添加应用**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="2e60e-147">在 " **添加固定的应用** " 窗格中，搜索要添加的应用，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="2e60e-148">你还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="2e60e-149">选择要固定的应用列表后，选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       !["添加固定的应用" 窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="2e60e-151">按希望在团队中显示的顺序排列应用，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       !["固定应用" 部分](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="2e60e-153">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-153">Edit an app setup policy</span></span>

<span data-ttu-id="2e60e-154">你可以使用 Microsoft 团队管理中心编辑策略，包括全局 (组织范围的默认) 策略和你创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="2e60e-155">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="2e60e-156">单击策略名称左侧的 "选择"，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="2e60e-157">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="2e60e-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="2e60e-158">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2e60e-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="2e60e-159">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="2e60e-160">常见问题</span><span class="sxs-lookup"><span data-stu-id="2e60e-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="2e60e-161">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2e60e-162">Microsoft 团队管理中心中包含哪些内置应用设置策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="2e60e-163">**全局 (组织范围默认)**：此默认策略适用于你的组织中的所有用户，除非你分配其他策略。</span><span class="sxs-lookup"><span data-stu-id="2e60e-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="2e60e-164">编辑全局策略以固定对你的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="2e60e-165">**FirstLineWorker**：此政策适用于一线工作者。</span><span class="sxs-lookup"><span data-stu-id="2e60e-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="2e60e-166">你可以将其分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="2e60e-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="2e60e-167">请务必知道，例如你创建的自定义策略，你必须将策略分配给用户才能使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2e60e-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="2e60e-168">有关详细信息，请转到本文的 "向 [用户分配自定义应用设置策略](#assign-a-custom-app-setup-policy-to-users) " 部分。</span><span class="sxs-lookup"><span data-stu-id="2e60e-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="2e60e-169">为什么在 "添加固定的应用" 窗格中找不到应用</span><span class="sxs-lookup"><span data-stu-id="2e60e-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="2e60e-170">并非所有应用都可以通过应用设置策略固定到团队。</span><span class="sxs-lookup"><span data-stu-id="2e60e-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="2e60e-171">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="2e60e-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="2e60e-172">若要查找可固定的应用，请在 " **添加固定的应用** " 窗格中搜索该应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="2e60e-173">具有个人作用域 (静态选项卡) 和机器人的选项卡可以固定到团队桌面客户端，并且这些应用在 " **添加固定应用** " 窗格中可用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="2e60e-174">请记住，"团队" 应用商店将列出所有团队应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="2e60e-175">" **添加固定的应用** " 窗格仅包括可通过策略固定到团队的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="2e60e-176">我是教育版管理员的团队。我需要了解有关团队教育版中的应用设置策略的哪些信息</span><span class="sxs-lookup"><span data-stu-id="2e60e-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="2e60e-177">"呼叫" 应用在教育版团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="2e60e-178">创建新的自定义应用设置策略时，将在应用列表中显示调用应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="2e60e-179">但是，应用不会固定到团队客户端和团队，教育用户将看不到团队中的 "调用" 应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="2e60e-180">可将多少个固定应用添加到策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="2e60e-181">必须将两个应用中的至少一个应用固定到团队移动客户端 (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="2e60e-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="2e60e-182">如果策略的应用数少于两个，则移动客户端不会反映策略设置，而是将继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="2e60e-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="2e60e-183">对于可添加到策略的固定应用的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="2e60e-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="2e60e-184">策略更改需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="2e60e-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="2e60e-185">编辑或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="2e60e-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="2e60e-186">用户体验</span><span class="sxs-lookup"><span data-stu-id="2e60e-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="2e60e-187">用户如何能够查看团队中的所有固定应用</span><span class="sxs-lookup"><span data-stu-id="2e60e-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="2e60e-188">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装应用的数量以及其团队客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="2e60e-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="2e60e-189">团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="2e60e-189">Teams desktop client</span></span> |<span data-ttu-id="2e60e-190">团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="2e60e-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="2e60e-191">在团队侧面的应用栏中，选择 **.。。更多应用**。</span><span class="sxs-lookup"><span data-stu-id="2e60e-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="2e60e-192">在团队底部附近的应用栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="2e60e-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![团队桌面客户端中的更多应用](media/app-setup-policies-desktop-more-apps.png)<br>   |![团队移动客户端中的更多应用](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="2e60e-195">我需要了解有关团队移动体验的哪些信息</span><span class="sxs-lookup"><span data-stu-id="2e60e-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="2e60e-196"> (iOS 和 Android) 的团队移动客户端当前不支持具有静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="2e60e-197">根据策略中设置的应用，固定到团队桌面客户端的应用可能不会显示在团队移动客户端中。</span><span class="sxs-lookup"><span data-stu-id="2e60e-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="2e60e-198">在移动客户端上，个人机器人仍将显示在聊天中。</span><span class="sxs-lookup"><span data-stu-id="2e60e-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="2e60e-199">通过团队移动客户端，用户将看到核心团队应用（如活动、聊天和团队），并且你可以固定 Microsoft 的一些第三方应用，例如倒班。</span><span class="sxs-lookup"><span data-stu-id="2e60e-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="2e60e-200">用户能否更改通过策略固定的应用的顺序</span><span class="sxs-lookup"><span data-stu-id="2e60e-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="2e60e-201">如果启用了 " **允许用户固定** " 选项，用户可以更改团队桌面和移动客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="2e60e-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="2e60e-202">用户无法更改团队 web 客户端上的固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="2e60e-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="2e60e-203">用户固定优先</span><span class="sxs-lookup"><span data-stu-id="2e60e-203">Does user pinning take precedence</span></span>

<span data-ttu-id="2e60e-204">如果分配给用户的应用设置策略被更改为阻止用户应用固定，团队会删除固定到应用栏的任何应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="2e60e-205">如果随后将策略更改为允许用户应用固定，则用户必须重新固定其以前固定的应用。</span><span class="sxs-lookup"><span data-stu-id="2e60e-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="2e60e-206">自定义团队应用</span><span class="sxs-lookup"><span data-stu-id="2e60e-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="2e60e-207">我的组织构建了一个自定义团队应用，并已将其发布到 AppSource 或租户应用目录，但当应用固定到团队中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="2e60e-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="2e60e-208">如何修复</span><span class="sxs-lookup"><span data-stu-id="2e60e-208">How do I fix it</span></span>

<span data-ttu-id="2e60e-209">在提交应用之前，请确保遵循徽标指南。</span><span class="sxs-lookup"><span data-stu-id="2e60e-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="2e60e-210">若要了解详细信息，请参阅 [卖方仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="2e60e-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e60e-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="2e60e-211">Related topics</span></span>

[<span data-ttu-id="2e60e-212">Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="2e60e-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="2e60e-213">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="2e60e-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
