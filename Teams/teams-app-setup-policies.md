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
description: 了解如何在 Microsoft Teams 中为组织的用户使用和管理应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697707"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="62184-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="62184-104">作为管理员，可以使用应用设置策略执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="62184-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="62184-105">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="62184-106">选择要固定的应用并设置它们显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="62184-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="62184-107">固定应用允许你展示组织中用户所需的应用，包括由第三方或你组织的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="62184-108">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="62184-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="62184-109">代表用户安装应用。</span><span class="sxs-lookup"><span data-stu-id="62184-109">Install apps on behalf of users.</span></span> <span data-ttu-id="62184-110">用户启动 Teams 时，可以选择默认安装哪些应用。</span><span class="sxs-lookup"><span data-stu-id="62184-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="62184-111">请记住，如果分配给用户的应用权限策略允许，用户仍然可以[](teams-app-permission-policies.md)自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="62184-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="62184-112">对于管理员安装的应用，用户无法卸载这些应用。</span><span class="sxs-lookup"><span data-stu-id="62184-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="62184-113">应用固定到应用栏，应用栏是 Teams 桌面客户端一侧的栏，位于 iOS 和 Android (Teams 移动) 。</span><span class="sxs-lookup"><span data-stu-id="62184-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="62184-114">Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="62184-114">Teams desktop client</span></span>  |<span data-ttu-id="62184-115">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="62184-115">Teams mobile client</span></span> |
|---------|---------|
|![Teams 桌面客户端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 移动客户端](media/mobile-app-ui.png)      |

<span data-ttu-id="62184-118">若要查看管理员安装的应用，请在应用栏中 **选择"...Teams 桌面** 和 Web 客户端中的更多应用，在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="62184-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="62184-119">在 Microsoft Teams 管理中心中管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="62184-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="62184-120">使用全局 (组织范围的默认) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="62184-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="62184-121">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="62184-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="62184-122">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="62184-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="62184-123">编辑全局策略中的设置，以包含需要的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="62184-124">若要为组织的不同用户组自定义 Teams，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="62184-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

!["应用设置策略"页](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="62184-126">如果你有 Teams for Education，则必须知道"作业"应用默认已固定在全局策略中，即使当前未看到它列在全局策略中。</span><span class="sxs-lookup"><span data-stu-id="62184-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="62184-127">它将是 Teams 客户端上已固定应用列表中的第四个应用。</span><span class="sxs-lookup"><span data-stu-id="62184-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="62184-128">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-128">Create a custom app setup policy</span></span>

<span data-ttu-id="62184-129">可以使用 Microsoft Teams 管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="62184-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="62184-130">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**</span><span class="sxs-lookup"><span data-stu-id="62184-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="62184-131">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="62184-131">Select **Add**.</span></span>

   !["添加应用设置策略"页](media/app-setup-policies-add.png)

3. <span data-ttu-id="62184-133">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="62184-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="62184-134">打开或关闭" **上传自定义应用**"，具体取决于是否要让用户将自定义应用上传到 Teams。</span><span class="sxs-lookup"><span data-stu-id="62184-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="62184-135">如果在组织范围的应用设置 中关闭"允许第三方应用"，[则不能更改此设置](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="62184-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="62184-136">打开或关闭 **"允许用户** 固定"，具体取决于是否要让用户通过将应用固定到应用栏来个性化其应用栏。</span><span class="sxs-lookup"><span data-stu-id="62184-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62184-137">Microsoft  365 政府社区云 (GCC) 环境 (GCC、GCC High 和 DoD) 中的 Teams 管理中心提供"允许用户固定"设置，但目前不起作用。</span><span class="sxs-lookup"><span data-stu-id="62184-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="62184-138">若要为用户安装应用，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="62184-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="62184-139">在 **"已安装的应用"** 下，选择 **"添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="62184-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="62184-140">在" **添加已安装的应用"** 窗格中，搜索希望用户在启动 Teams 时自动安装的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="62184-141">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="62184-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="62184-142">选择应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="62184-142">When you've chosen your list of apps, select **Add**.</span></span>

       !["添加已安装的应用"窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="62184-144">若要固定应用，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="62184-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="62184-145">在 **"固定的应用"下**，选择"**添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="62184-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="62184-146">在"**添加固定的应用"** 窗格中，搜索要添加的应用，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="62184-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="62184-147">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="62184-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="62184-148">选择要固定的应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="62184-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       !["添加固定的应用"窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="62184-150">按照希望应用在 Teams 中显示的顺序排列应用，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="62184-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       !["固定的应用"部分](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="62184-152">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-152">Edit an app setup policy</span></span>

<span data-ttu-id="62184-153">可以使用 Microsoft Teams 管理中心编辑策略，包括 (组织范围的) 策略和自定义策略。</span><span class="sxs-lookup"><span data-stu-id="62184-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="62184-154">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **设置策略"。**</span><span class="sxs-lookup"><span data-stu-id="62184-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="62184-155">通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="62184-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="62184-156">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="62184-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="62184-157">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="62184-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="62184-158">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="62184-159">常见问题</span><span class="sxs-lookup"><span data-stu-id="62184-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="62184-160">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="62184-161">Microsoft Teams 管理中心包含哪些内置应用设置策略</span><span class="sxs-lookup"><span data-stu-id="62184-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="62184-162">**全局 (组织范围内的** 默认) ：此默认策略适用于组织中的所有用户，除非分配了其他策略。</span><span class="sxs-lookup"><span data-stu-id="62184-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="62184-163">编辑全局策略以固定对用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="62184-164">**FrontlineWorker：** 此策略适用于前端工作人员。</span><span class="sxs-lookup"><span data-stu-id="62184-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="62184-165">你可以将其分配给你组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="62184-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="62184-166">必须知道，与创建的自定义策略一样，必须向用户分配策略，使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="62184-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="62184-167">有关详细信息，请转到本文的向用户分配 [自定义](#assign-a-custom-app-setup-policy-to-users) 应用设置策略部分。</span><span class="sxs-lookup"><span data-stu-id="62184-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="62184-168">为什么在"添加固定的应用"窗格中找不到应用</span><span class="sxs-lookup"><span data-stu-id="62184-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="62184-169">并非所有应用都可以通过应用设置策略固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="62184-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="62184-170">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="62184-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="62184-171">若要查找可固定的应用，请搜索"添加固定的应用" **窗格中的应用** 。</span><span class="sxs-lookup"><span data-stu-id="62184-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="62184-172">具有个人范围的选项卡 (静态选项卡) 和机器人可以固定到 Teams 桌面客户端，这些应用在"添加固定应用"**窗格中可用。**</span><span class="sxs-lookup"><span data-stu-id="62184-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="62184-173">请记住，Teams 应用商店列出了所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="62184-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="62184-174">" **添加固定的应用"** 窗格仅包含可通过策略固定到 Teams 的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="62184-175">我是 Teams 教育管理员。关于 Teams 教育中的应用设置策略，我需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="62184-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="62184-176">呼叫应用在 Teams 教育中不可用。</span><span class="sxs-lookup"><span data-stu-id="62184-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="62184-177">创建新的自定义应用设置策略时，"呼叫"应用会显示在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="62184-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="62184-178">但是，该应用未固定到 Teams 客户端，Teams 教育用户不会在 Teams 中看到"通话"应用。</span><span class="sxs-lookup"><span data-stu-id="62184-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="62184-179">可以将多少个固定应用添加到策略</span><span class="sxs-lookup"><span data-stu-id="62184-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="62184-180">必须至少将两个应用固定到 iOS 和 Android (Teams 移动) 。</span><span class="sxs-lookup"><span data-stu-id="62184-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="62184-181">如果策略的应用少于两个，移动客户端不会反映策略设置，而是继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="62184-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="62184-182">可以添加到策略的固定应用数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="62184-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="62184-183">策略更改生效需要多久</span><span class="sxs-lookup"><span data-stu-id="62184-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="62184-184">编辑或分配策略后，更改可能需要几个小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="62184-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="62184-185">用户体验</span><span class="sxs-lookup"><span data-stu-id="62184-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="62184-186">用户如何在 Teams 中查看其所有固定应用</span><span class="sxs-lookup"><span data-stu-id="62184-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="62184-187">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装的应用数及其 Teams 客户端窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="62184-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="62184-188">Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="62184-188">Teams desktop client</span></span> |<span data-ttu-id="62184-189">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="62184-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="62184-190">在 Teams 一侧的应用栏中，选择 **"...更多应用**。</span><span class="sxs-lookup"><span data-stu-id="62184-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="62184-191">在 Teams 底部附近的应用栏中，向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="62184-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams 桌面客户端中的更多应用](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 移动客户端中的更多应用](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="62184-194">关于 Teams 移动体验，我需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="62184-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="62184-195">iOS (Android) Teams 移动客户端目前不支持使用静态选项卡的个人应用。</span><span class="sxs-lookup"><span data-stu-id="62184-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="62184-196">固定到 Teams 桌面客户端的应用可能不会显示在 Teams 移动客户端中，具体取决于策略中设置的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="62184-197">个人机器人仍将显示在移动客户端上的聊天中。</span><span class="sxs-lookup"><span data-stu-id="62184-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="62184-198">使用 Teams 移动客户端，用户将看到核心 Teams 应用，如活动、聊天和 Teams，并且你可以固定 Microsoft 的一些第一方应用，例如 Shifts。</span><span class="sxs-lookup"><span data-stu-id="62184-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="62184-199">用户能否更改通过策略固定的应用的顺序</span><span class="sxs-lookup"><span data-stu-id="62184-199">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="62184-200">如果"允许用户固定"选项已打开，用户可以在 Teams 桌面和移动客户端上更改其固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="62184-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="62184-201">用户不能更改 Teams Web 客户端上固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="62184-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="62184-202">用户固定是否优先</span><span class="sxs-lookup"><span data-stu-id="62184-202">Does user pinning take precedence</span></span>

<span data-ttu-id="62184-203">管理图钉始终优先。</span><span class="sxs-lookup"><span data-stu-id="62184-203">Admin pins always take precedence.</span></span> <span data-ttu-id="62184-204">如果 **"允许用户固定"** 选项已打开，则用户将保留其固定应用在管理员固定应用下方。</span><span class="sxs-lookup"><span data-stu-id="62184-204">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="62184-205">如果 **"允许用户固定"** 选项已关闭，则用户将丢失其预先存在的固定项，并且应用栏中将只显示管理员固定的应用。</span><span class="sxs-lookup"><span data-stu-id="62184-205">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="62184-206">自定义 Teams 应用</span><span class="sxs-lookup"><span data-stu-id="62184-206">Custom Teams apps</span></span>

<span data-ttu-id="62184-207">我的组织构建了自定义 Teams 应用，并发布到 AppSource 或租户应用目录，但在应用固定到 Teams 中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="62184-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="62184-208">如何修复它</span><span class="sxs-lookup"><span data-stu-id="62184-208">How do I fix it</span></span>

<span data-ttu-id="62184-209">在提交应用之前，请确保遵循徽标准则。</span><span class="sxs-lookup"><span data-stu-id="62184-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="62184-210">有关详细信息，请参阅卖方 [仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="62184-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="62184-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="62184-211">Related topics</span></span>

[<span data-ttu-id="62184-212">Teams 中应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="62184-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="62184-213">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="62184-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
