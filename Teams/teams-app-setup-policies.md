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
description: 了解如何在应用程序中为Microsoft Teams用户使用和管理应用设置策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059196"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="870bc-103">在 Microsoft Teams 中管理应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="870bc-104">作为管理员，可以使用应用设置策略执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="870bc-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="870bc-105">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="870bc-106">选择要固定的应用并设置它们显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="870bc-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="870bc-107">固定应用允许你展示组织中用户所需的应用，包括由第三方或你组织的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="870bc-108">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="870bc-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="870bc-109">代表用户安装应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-109">Install apps on behalf of users.</span></span> <span data-ttu-id="870bc-110">选择在用户启动应用时默认安装哪些Teams。</span><span class="sxs-lookup"><span data-stu-id="870bc-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="870bc-111">请记住，如果分配给用户的应用权限策略允许，用户仍然可以[](teams-app-permission-policies.md)自行安装应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="870bc-112">对于管理员安装的应用，用户无法卸载这些应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="870bc-113">应用固定到应用栏，应用栏位于 Teams 桌面客户端一侧，位于 Teams 移动客户端 (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="870bc-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="870bc-114">Teams桌面客户端</span><span class="sxs-lookup"><span data-stu-id="870bc-114">Teams desktop client</span></span>  |<span data-ttu-id="870bc-115">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="870bc-115">Teams mobile client</span></span> |
|---------|---------|
|![Teams桌面客户端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams移动客户端](media/mobile-app-ui.png)      |

<span data-ttu-id="870bc-118">若要查看管理员安装的应用，请在应用栏中 **选择"...桌面** 和Teams客户端中的更多应用，在移动客户端中向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="870bc-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="870bc-119">在管理中心内管理Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="870bc-120">使用全局 (组织范围的默认) 策略，或者创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="870bc-121">除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="870bc-122">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="870bc-123">编辑全局策略中的设置，以包含需要的应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="870bc-124">若要为Teams组用户自定义策略，请创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

!["应用设置策略"页](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="870bc-126">如果你拥有Teams应用，必须知道"作业"应用默认已固定在全局策略中，即使当前未在全局策略中列出该应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="870bc-127">它将是客户端上已固定应用列表中的第四Teams应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="870bc-128">创建自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-128">Create a custom app setup policy</span></span>

<span data-ttu-id="870bc-129">可以使用 Microsoft Teams 管理中心创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="870bc-130">在管理中心的左侧导航Microsoft Teams，转到"Teams **设置**  >  **策略"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="870bc-131">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="870bc-131">Select **Add**.</span></span>

   !["添加应用设置策略"页](media/app-setup-policies-add.png)

3. <span data-ttu-id="870bc-133">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="870bc-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="870bc-134">打开或 **关闭Upload应用**，具体取决于是否要让用户将自定义应用上传到Teams。</span><span class="sxs-lookup"><span data-stu-id="870bc-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="870bc-135">如果在组织范围的应用设置 中关闭"允许第三方应用"，[则不能更改此设置](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="870bc-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="870bc-136">打开或关闭 **"允许用户** 固定"，具体取决于是否要让用户通过将应用固定到应用栏来个性化其应用栏。</span><span class="sxs-lookup"><span data-stu-id="870bc-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="870bc-137">Microsoft 365 政府社区云 (GCC) 环境 (GCC、GCC High 和 DoD) 中的 Teams 管理中心中提供了"允许用户固定"设置，但目前不起作用。</span><span class="sxs-lookup"><span data-stu-id="870bc-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="870bc-138">若要为用户安装应用，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="870bc-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="870bc-139">在 **"已安装的应用"** 下，选择 **"添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="870bc-140">在 **"添加已安装的应用**"窗格中，搜索希望用户在启动应用时自动安装Teams。</span><span class="sxs-lookup"><span data-stu-id="870bc-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="870bc-141">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="870bc-142">选择应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-142">When you've chosen your list of apps, select **Add**.</span></span>

       !["添加已安装的应用"窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="870bc-144">若要固定应用，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="870bc-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="870bc-145">在 **"固定的应用"下**，选择"**添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="870bc-146">在"**添加固定的应用"** 窗格中，搜索要添加的应用，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="870bc-147">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="870bc-148">选择要固定的应用列表后，选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       !["添加固定的应用"窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="870bc-150">按照希望应用在应用中显示的顺序排列Teams，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       !["固定的应用"部分](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="870bc-152">编辑应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-152">Edit an app setup policy</span></span>

<span data-ttu-id="870bc-153">可以使用 Microsoft Teams 管理中心编辑策略，包括 (组织范围的) 策略和自定义策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="870bc-154">在管理中心的左侧导航Microsoft Teams，转到"Teams **设置**  >  **策略"。**</span><span class="sxs-lookup"><span data-stu-id="870bc-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="870bc-155">通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="870bc-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="870bc-156">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="870bc-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="870bc-157">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="870bc-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="870bc-158">向用户分配自定义应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="870bc-159">常见问题</span><span class="sxs-lookup"><span data-stu-id="870bc-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="870bc-160">使用应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="870bc-161">应用管理中心包含哪些内置应用Microsoft Teams策略</span><span class="sxs-lookup"><span data-stu-id="870bc-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="870bc-162">**全局 (组织范围内的** 默认) ：此默认策略适用于组织中的所有用户，除非分配了其他策略。</span><span class="sxs-lookup"><span data-stu-id="870bc-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="870bc-163">编辑全局策略以固定对用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="870bc-164">**FrontlineWorker：** 此策略适用于前端工作人员。</span><span class="sxs-lookup"><span data-stu-id="870bc-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="870bc-165">你可以将其分配给你组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="870bc-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="870bc-166">必须知道，与创建的自定义策略一样，必须向用户分配策略，使设置处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="870bc-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="870bc-167">有关详细信息，请转到本文的向用户分配 [自定义](#assign-a-custom-app-setup-policy-to-users) 应用设置策略部分。</span><span class="sxs-lookup"><span data-stu-id="870bc-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="870bc-168">为什么在"添加固定的应用"窗格中找不到应用</span><span class="sxs-lookup"><span data-stu-id="870bc-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="870bc-169">并非所有应用都可以通过应用设置Teams固定到其他应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="870bc-170">某些应用可能不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="870bc-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="870bc-171">若要查找可固定的应用，请搜索"添加固定的应用" **窗格中的应用** 。</span><span class="sxs-lookup"><span data-stu-id="870bc-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="870bc-172">具有个人范围的选项卡 (静态选项卡) 和机器人可以固定到 Teams 桌面客户端，这些应用在"添加固定应用"**窗格中可用。**</span><span class="sxs-lookup"><span data-stu-id="870bc-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="870bc-173">请记住，应用商店Teams列出所有Teams应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="870bc-174">"**添加固定应用"** 窗格仅包含可以通过策略固定Teams应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="870bc-175">我是教育Teams管理员。在适用于教育的 Teams 中，我需要了解哪些应用设置策略</span><span class="sxs-lookup"><span data-stu-id="870bc-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="870bc-176">呼叫应用在教育Teams不可用。</span><span class="sxs-lookup"><span data-stu-id="870bc-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="870bc-177">创建新的自定义应用设置策略时，"呼叫"应用会显示在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="870bc-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="870bc-178">但是，该应用未固定到Teams客户端，Teams教育用户不会在应用中看到"呼叫"Teams。</span><span class="sxs-lookup"><span data-stu-id="870bc-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="870bc-179">可以将多少个固定应用添加到策略</span><span class="sxs-lookup"><span data-stu-id="870bc-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="870bc-180">必须将至少两个应用固定到 iOS Teams Android (移动客户端) 。</span><span class="sxs-lookup"><span data-stu-id="870bc-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="870bc-181">如果策略的应用少于两个，移动客户端不会反映策略设置，而是继续使用现有配置。</span><span class="sxs-lookup"><span data-stu-id="870bc-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="870bc-182">可以添加到策略的固定应用数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="870bc-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="870bc-183">策略更改生效需要多久</span><span class="sxs-lookup"><span data-stu-id="870bc-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="870bc-184">编辑或分配策略后，更改可能需要几个小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="870bc-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="870bc-185">用户体验</span><span class="sxs-lookup"><span data-stu-id="870bc-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="870bc-186">用户如何在应用中查看其所有固定Teams</span><span class="sxs-lookup"><span data-stu-id="870bc-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="870bc-187">若要查看为用户固定的所有应用，用户可能需要执行以下操作，具体取决于已安装的应用数及其Teams窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="870bc-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="870bc-188">Teams桌面客户端</span><span class="sxs-lookup"><span data-stu-id="870bc-188">Teams desktop client</span></span> |<span data-ttu-id="870bc-189">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="870bc-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="870bc-190">在应用栏的"应用Teams，选择 **"...更多应用**。</span><span class="sxs-lookup"><span data-stu-id="870bc-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="870bc-191">在屏幕底部附近的应用Teams向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="870bc-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![桌面客户端中的Teams应用](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams移动客户端中的更多应用](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="870bc-194">关于移动体验，Teams哪些信息</span><span class="sxs-lookup"><span data-stu-id="870bc-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="870bc-195">iOS Teams Android (移动客户端) 静态选项卡支持个人应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="870bc-196">固定到 Teams 桌面客户端的应用将显示在Teams客户端中。</span><span class="sxs-lookup"><span data-stu-id="870bc-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="870bc-197">个人机器人将显示在移动客户端上的聊天中。</span><span class="sxs-lookup"><span data-stu-id="870bc-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="870bc-198">可以从应用商店 (下载的第三方Teams应用) 在移动设备上显示之前需要获得批准。</span><span class="sxs-lookup"><span data-stu-id="870bc-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="870bc-199">如果管理员固定应用（未经 Microsoft 移动版批准）将在桌面Teams上显示，但不在移动设备上显示。</span><span class="sxs-lookup"><span data-stu-id="870bc-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="870bc-200">有关详细信息 [，请参阅](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="870bc-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="870bc-201">使用 Teams 移动客户端，用户将看到核心 Teams 应用，如活动、聊天和 Teams，并且你可以固定来自 Microsoft 的一些第一方应用，例如 Shifts。</span><span class="sxs-lookup"><span data-stu-id="870bc-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="870bc-202">用户能否更改通过策略固定的应用的顺序</span><span class="sxs-lookup"><span data-stu-id="870bc-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="870bc-203">如果"允许用户固定"选项打开，用户可以在桌面Teams移动客户端上更改其固定应用的顺序。</span><span class="sxs-lookup"><span data-stu-id="870bc-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="870bc-204">用户不能更改其固定应用在 Web 客户端上Teams的顺序。</span><span class="sxs-lookup"><span data-stu-id="870bc-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="870bc-205">用户固定是否优先</span><span class="sxs-lookup"><span data-stu-id="870bc-205">Does user pinning take precedence</span></span>

<span data-ttu-id="870bc-206">管理图钉始终优先。</span><span class="sxs-lookup"><span data-stu-id="870bc-206">Admin pins always take precedence.</span></span> <span data-ttu-id="870bc-207">如果 **"允许用户固定"** 选项已打开，则用户将保留其固定应用在管理员固定应用下方。</span><span class="sxs-lookup"><span data-stu-id="870bc-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="870bc-208">如果 **"允许用户固定"** 选项已关闭，则用户将丢失其预先存在的固定项，并且应用栏中将只显示管理员固定的应用。</span><span class="sxs-lookup"><span data-stu-id="870bc-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="870bc-209">自定义Teams应用</span><span class="sxs-lookup"><span data-stu-id="870bc-209">Custom Teams apps</span></span>

<span data-ttu-id="870bc-210">我的组织构建了Teams应用并发布到 AppSource 或租户应用目录，但在应用固定到 Teams 中的应用栏时，应用图标不会按预期显示。</span><span class="sxs-lookup"><span data-stu-id="870bc-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="870bc-211">如何修复它</span><span class="sxs-lookup"><span data-stu-id="870bc-211">How do I fix it</span></span>

<span data-ttu-id="870bc-212">在提交应用之前，请确保遵循徽标准则。</span><span class="sxs-lookup"><span data-stu-id="870bc-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="870bc-213">有关详细信息，请参阅卖方 [仪表板提交清单](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="870bc-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="870bc-214">相关主题</span><span class="sxs-lookup"><span data-stu-id="870bc-214">Related topics</span></span>

[<span data-ttu-id="870bc-215">Teams 中应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="870bc-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="870bc-216">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="870bc-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
