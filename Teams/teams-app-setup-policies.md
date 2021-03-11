---
title: 在 Microsoft Teams 中管理应用设置策略
author: cichur
ms.author: v-cichur
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
description: 了解如何在 Microsoft Teams 中为贵组织的用户使用和管理应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a58cbf682760249ee3b269d1765a265cc58d3022
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615088"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="18f1b-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="18f1b-104">如果启用了组织范围应用设置"允许与自定义应用交互"，则你可能尚未在 Microsoft Teams 管理中心看到应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you might not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="18f1b-105">它目前正在推出，即将在你的组织中推出。</span><span class="sxs-lookup"><span data-stu-id="18f1b-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="18f1b-106">作为管理员，可以使用应用设置策略执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="18f1b-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="18f1b-107">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="18f1b-108">选择要固定的应用并设置它们显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="18f1b-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="18f1b-109">使用固定应用可以展示组织中用户所需的应用，包括由第三方或组织中开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="18f1b-110">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="18f1b-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="18f1b-111">代表用户安装应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-111">Install apps on behalf of users.</span></span> <span data-ttu-id="18f1b-112">用户启动 Teams 时，可以选择默认安装哪些应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="18f1b-113">请记住，如果分配给用户的应用权限策略允许，用户仍然可以[](teams-app-permission-policies.md)自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="18f1b-114">对于管理员安装的应用，用户无法卸载这些应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-114">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="18f1b-115">应用固定到应用栏，应用栏位于 Teams 桌面客户端的一侧，位于 Teams 移动客户端底部， (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="18f1b-115">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="18f1b-116">Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="18f1b-116">Teams desktop client</span></span>  |<span data-ttu-id="18f1b-117">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="18f1b-117">Teams mobile client</span></span> |
|---------|---------|
|![Teams 桌面客户端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 移动客户端](media/mobile-app-ui.png)      |

<span data-ttu-id="18f1b-120">若要查看管理员安装的应用，请在应用栏中选择 **...Teams 桌面** 和 Web 客户端中的更多应用，在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="18f1b-120">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="18f1b-121">在 Microsoft Teams 管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="18f1b-122">使用全局 (组织范围内的默认) 策略，或创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-122">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="18f1b-123">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="18f1b-124">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="18f1b-125">编辑全局策略中的设置，以包含需要的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-125">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="18f1b-126">若要为组织中不同用户组自定义 Teams，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-126">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

!["应用设置策略"页](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="18f1b-128">如果你有 Teams 教育，必须知道"作业"应用默认固定在全局策略中，即使当前未看到它列在全局策略中。</span><span class="sxs-lookup"><span data-stu-id="18f1b-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="18f1b-129">它将是 Teams 客户端上已固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="18f1b-130">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-130">Create a custom app setup policy</span></span>

<span data-ttu-id="18f1b-131">可以使用 Microsoft Teams 管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="18f1b-132">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="18f1b-133">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="18f1b-133">Select **Add**.</span></span>

   !["添加应用设置策略"页](media/app-setup-policies-add.png)

3. <span data-ttu-id="18f1b-135">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="18f1b-135">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="18f1b-136">打开或关闭" **上传自定义应用**"，具体取决于是否要允许用户将自定义应用上传到 Teams。</span><span class="sxs-lookup"><span data-stu-id="18f1b-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="18f1b-137">如果在组织范围内的应用设置中关闭"允许第三方应用"，[则不能更改此设置](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="18f1b-137">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="18f1b-138">打开或关闭"允许用户 **固定**"，具体取决于是否要让用户通过将应用固定到应用栏来个性化应用栏。</span><span class="sxs-lookup"><span data-stu-id="18f1b-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="18f1b-139">Microsoft  365 政府社区云 (GCC) 环境 (GCC、GCC High 和 DoD) 中的 Teams 管理中心提供"允许用户固定"设置，但目前不起作用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-139">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="18f1b-140">若要为用户安装应用，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="18f1b-140">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="18f1b-141">在 **"已安装的应用"** 下，选择 **"添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-141">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="18f1b-142">在" **添加已安装的应用"** 窗格中，搜索用户启动 Teams 时要自动安装的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-142">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="18f1b-143">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-143">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="18f1b-144">选择应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-144">When you've chosen your list of apps, select **Add**.</span></span>

       !["添加已安装的应用"窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="18f1b-146">若要固定应用，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="18f1b-146">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="18f1b-147">在 **"固定应用"下**，选择 **"添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-147">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="18f1b-148">在"**添加固定的应用"** 窗格中，搜索要添加的应用，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-148">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="18f1b-149">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-149">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="18f1b-150">选择要固定的应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-150">When you've chosen your list of apps to pin, select **Add**.</span></span>

       !["添加固定的应用"窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="18f1b-152">按照希望应用在 Teams 中显示的顺序排列应用，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-152">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       !["固定应用"部分](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="18f1b-154">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-154">Edit an app setup policy</span></span>

<span data-ttu-id="18f1b-155">可以使用 Microsoft Teams 管理中心编辑策略，包括 (组织范围的) 策略和自定义策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-155">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="18f1b-156">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="18f1b-157">单击策略名称左侧选择策略，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-157">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="18f1b-158">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="18f1b-158">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="18f1b-159">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-159">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="18f1b-160">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-160">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="18f1b-161">常见问题</span><span class="sxs-lookup"><span data-stu-id="18f1b-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="18f1b-162">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="18f1b-163">Microsoft Teams 管理中心包含哪些内置应用设置策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-163">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="18f1b-164">**全局 (组织范围内的默认**) ：此默认策略适用于组织中的所有用户，除非分配了其他策略。</span><span class="sxs-lookup"><span data-stu-id="18f1b-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="18f1b-165">编辑全局策略以固定对用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-165">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="18f1b-166">**FrontlineWorker：** 此策略适用于前端工作程序。</span><span class="sxs-lookup"><span data-stu-id="18f1b-166">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="18f1b-167">可以将它分配给组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="18f1b-167">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="18f1b-168">必须知道，与创建的自定义策略一样，必须向用户分配策略，使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="18f1b-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="18f1b-169">有关详细信息，请转到本文的"向用户分配 [自定义](#assign-a-custom-app-setup-policy-to-users) 应用设置策略"部分。</span><span class="sxs-lookup"><span data-stu-id="18f1b-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="18f1b-170">为什么在"添加固定的应用"窗格中找不到应用</span><span class="sxs-lookup"><span data-stu-id="18f1b-170">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="18f1b-171">并非所有应用都可以通过应用设置策略固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="18f1b-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="18f1b-172">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="18f1b-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="18f1b-173">若要查找可固定的应用，请搜索"添加固定的应用" **窗格中的应用** 。</span><span class="sxs-lookup"><span data-stu-id="18f1b-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="18f1b-174">具有个人范围的选项卡 (静态选项卡) 和机器人可以固定到 Teams 桌面客户端，这些应用在"添加固定应用"**窗格中可用。**</span><span class="sxs-lookup"><span data-stu-id="18f1b-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="18f1b-175">请记住，Teams 应用商店列出了所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-175">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="18f1b-176">" **添加固定的应用"** 窗格仅包含可以通过策略固定到 Teams 的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-176">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="18f1b-177">我是 Teams 教育管理员。我需要了解 Teams 教育应用设置策略的哪些信息</span><span class="sxs-lookup"><span data-stu-id="18f1b-177">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="18f1b-178">"呼叫"应用在 Teams for Education 中不可用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-178">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="18f1b-179">创建新的自定义应用设置策略时，"呼叫"应用会显示在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="18f1b-179">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="18f1b-180">但是，该应用未固定到 Teams 客户端，Teams 教育用户不会在 Teams 中看到"呼叫"应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-180">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="18f1b-181">可以将多少个固定应用添加到策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-181">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="18f1b-182">必须将至少两个应用固定到 iOS 和 Android (Teams 移动) 。</span><span class="sxs-lookup"><span data-stu-id="18f1b-182">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="18f1b-183">如果策略的应用少于两个，移动客户端不会反映策略设置，而是继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="18f1b-183">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="18f1b-184">可以添加到策略的固定应用数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="18f1b-184">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="18f1b-185">策略更改生效需要多久</span><span class="sxs-lookup"><span data-stu-id="18f1b-185">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="18f1b-186">编辑或分配策略后，更改可能需要几个小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="18f1b-186">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="18f1b-187">用户体验</span><span class="sxs-lookup"><span data-stu-id="18f1b-187">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="18f1b-188">用户如何在 Teams 中查看其所有固定应用</span><span class="sxs-lookup"><span data-stu-id="18f1b-188">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="18f1b-189">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装的应用数及其 Teams 客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="18f1b-189">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="18f1b-190">Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="18f1b-190">Teams desktop client</span></span> |<span data-ttu-id="18f1b-191">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="18f1b-191">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="18f1b-192">在 Teams 一侧的应用栏中，选择 **...更多应用**。</span><span class="sxs-lookup"><span data-stu-id="18f1b-192">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="18f1b-193">在 Teams 底部附近的应用栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="18f1b-193">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams 桌面客户端中的更多应用](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 移动客户端中的更多应用](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="18f1b-196">我需要了解哪些 Teams 移动体验</span><span class="sxs-lookup"><span data-stu-id="18f1b-196">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="18f1b-197">iOS (Android) Teams 移动客户端目前不支持使用静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-197">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="18f1b-198">固定到 Teams 桌面客户端的应用可能不会显示在 Teams 移动客户端中，具体取决于策略中设置的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-198">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="18f1b-199">个人机器人仍将显示在移动客户端上的聊天中。</span><span class="sxs-lookup"><span data-stu-id="18f1b-199">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="18f1b-200">使用 Teams 移动客户端，用户将看到核心 Teams 应用，如活动、聊天和 Teams，并且你可以固定 Microsoft 的一些第一方应用，例如 Shifts。</span><span class="sxs-lookup"><span data-stu-id="18f1b-200">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="18f1b-201">用户能否更改通过策略固定的应用的顺序</span><span class="sxs-lookup"><span data-stu-id="18f1b-201">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="18f1b-202">如果启用"允许用户固定"选项，用户可以在 Teams 桌面和移动客户端上更改其固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="18f1b-202">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="18f1b-203">用户不能更改 Teams Web 客户端上固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="18f1b-203">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="18f1b-204">用户固定是否优先</span><span class="sxs-lookup"><span data-stu-id="18f1b-204">Does user pinning take precedence</span></span>

<span data-ttu-id="18f1b-205">如果将分配给用户的应用设置策略更改为阻止用户应用固定，Teams 将删除固定到应用栏的任何应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-205">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="18f1b-206">如果更改策略以允许用户应用固定，用户必须重新固定其以前固定的应用。</span><span class="sxs-lookup"><span data-stu-id="18f1b-206">If the policy is then changed to allow user app pinning, users must repin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="18f1b-207">自定义 Teams 应用</span><span class="sxs-lookup"><span data-stu-id="18f1b-207">Custom Teams apps</span></span>

<span data-ttu-id="18f1b-208">我的组织构建了自定义 Teams 应用，并且已发布到 AppSource 或租户应用目录，但在将应用固定到 Teams 中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="18f1b-208">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="18f1b-209">如何修复它</span><span class="sxs-lookup"><span data-stu-id="18f1b-209">How do I fix it</span></span>

<span data-ttu-id="18f1b-210">在提交应用之前，请确保遵循徽标准则。</span><span class="sxs-lookup"><span data-stu-id="18f1b-210">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="18f1b-211">若要了解有关详细信息，请参阅["卖家仪表板提交清单"。](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="18f1b-211">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18f1b-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="18f1b-212">Related topics</span></span>

[<span data-ttu-id="18f1b-213">Teams 中应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="18f1b-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="18f1b-214">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="18f1b-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
