---
title: '安装、管理和分配 Teams Learning 应用的权限 (个人预览版) '
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: 使用 Microsoft Teams 学习应用创建一个中心，供员工在整个组织中共享、分配和学习内容库。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703401"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="42d97-103">安装、管理和分配 Teams Learning 应用的权限 (个人预览版) </span><span class="sxs-lookup"><span data-stu-id="42d97-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="42d97-104">*本文包含 Teams Learning 应用（个人预览版）的初步内容。*</span><span class="sxs-lookup"><span data-stu-id="42d97-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="42d97-105">Microsoft Teams Learning 应用 (个人预览版) 使组织中的团队和个人能够自然地学习。</span><span class="sxs-lookup"><span data-stu-id="42d97-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="42d97-106">该应用在 Teams 中创建了一个中心，员工可以在其中共享、分配内容以及从整个组织的内容库中学习。</span><span class="sxs-lookup"><span data-stu-id="42d97-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="42d97-107">管理员设置权限并允许学习应用的内容源。</span><span class="sxs-lookup"><span data-stu-id="42d97-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="42d97-108">学习内容可能包括 LinkedIn Learning、Microsoft Learn、Microsoft 365 培训、组织自己存储在 SharePoint Online 中的内容以及应用支持的第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="42d97-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="42d97-109">若要将 Teams Learning 应用 (个人预览版) ，需要涉及：</span><span class="sxs-lookup"><span data-stu-id="42d97-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="42d97-110">Teams 管理中心管理员</span><span class="sxs-lookup"><span data-stu-id="42d97-110">Teams admin center admin</span></span>
-   <span data-ttu-id="42d97-111">Microsoft 365 管理中心管理员 (，即全局管理员) </span><span class="sxs-lookup"><span data-stu-id="42d97-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="42d97-112">知识管理员 (Microsoft 365 管理中心中分配一个新角色，全局管理员 (也称为 IT 管理员或 Microsoft 365 管理员) 可分配给组织中任何人。</span><span class="sxs-lookup"><span data-stu-id="42d97-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="42d97-113">此角色通过 Microsoft 365 管理中心管理组织的学习内容源。) </span><span class="sxs-lookup"><span data-stu-id="42d97-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="42d97-114">在 Teams 管理中心 (Teams) 个人预览版</span><span class="sxs-lookup"><span data-stu-id="42d97-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="42d97-115">Teams 管理员从应用商店 (Teams 学习) 个人预览版，并通过 Teams 管理中心应用应用设置、管理和权限策略。</span><span class="sxs-lookup"><span data-stu-id="42d97-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="42d97-116">管理 Teams Learning 应用 (个人预览版) </span><span class="sxs-lookup"><span data-stu-id="42d97-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="42d97-117">若要管理应用的设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="42d97-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="42d97-118">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 管理中心中的左侧导航，显示 Teams 应用和"管理应用"部分](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="42d97-120">在"**管理应用"** 页面的搜索框中，键入学习内容以搜索 Teams Learning 应用 (个人预览) 。</span><span class="sxs-lookup"><span data-stu-id="42d97-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Teams 管理中心中的"管理应用"页面，显示搜索框](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="42d97-122">在" **学习"** 页上：</span><span class="sxs-lookup"><span data-stu-id="42d97-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="42d97-123">在 **"状态**" **下，选择** "允许"以打开应用。</span><span class="sxs-lookup"><span data-stu-id="42d97-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="42d97-124">在" **设置"** 选项卡上的"应用 **设置** "部分中，转到 Microsoft 365 管理中心以配置学习内容源。</span><span class="sxs-lookup"><span data-stu-id="42d97-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Teams 管理中心中的学习页面，显示"状态"和"应用设置"部分](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="42d97-126">管理 **应用设置** 后，转到"权限"和"设置"策略，向应有权访问应用（作为组织参与个人预览版一部分的员工）授予权限。</span><span class="sxs-lookup"><span data-stu-id="42d97-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="42d97-127">如果你的组织作为 Teams TAP100 计划的一部分进入 4.0 圈，你可能需要执行以下操作，使 3.0 圈中的获批用户能够访问 Teams Learning 应用 (个人预览版) 。</span><span class="sxs-lookup"><span data-stu-id="42d97-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="42d97-128">作为个人预览的一部分，Teams Learning 应用 (个人预览版) 3.0 圈中发布。</span><span class="sxs-lookup"><span data-stu-id="42d97-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="42d97-129">如果你的组织在 4.0 圈中，你将在应用商店中看不到该应用。</span><span class="sxs-lookup"><span data-stu-id="42d97-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="42d97-130">若要测试应用，需要创建自定义应用权限策略，将其设置为"允许 **所有** 应用"，并将其分配给 3.0 批准用户。</span><span class="sxs-lookup"><span data-stu-id="42d97-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TAP-AppsPermission-Plcy 页面，显示"允许选择所有应用"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="42d97-132">在 Microsoft 365 管理中心配置学习内容源</span><span class="sxs-lookup"><span data-stu-id="42d97-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="42d97-133">Microsoft 365 管理中心的管理员（自己或向组织中选定的个人分配知识管理员角色）可以管理与 Teams Learning 应用 (个人预览版) 相关的设置，并可以配置学习内容源。</span><span class="sxs-lookup"><span data-stu-id="42d97-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="42d97-134">知识管理员应具有中等技术水平，并且拥有现有的 SharePoint 管理员凭据，最好是熟悉组织教育、学习、培训或员工经验的人。</span><span class="sxs-lookup"><span data-stu-id="42d97-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="42d97-135">管理员选择哪些学习内容源 (如 LinkedIn Learning 或 SharePoint) 可在应用中使用。</span><span class="sxs-lookup"><span data-stu-id="42d97-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="42d97-136">然后，管理员配置这些源，以确保内容可用于搜索和发现，并且可供使用应用的员工浏览。</span><span class="sxs-lookup"><span data-stu-id="42d97-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="42d97-137">分配知识管理员角色 [可选]</span><span class="sxs-lookup"><span data-stu-id="42d97-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="42d97-138">这些步骤由 Microsoft 365 管理中心的管理员执行。</span><span class="sxs-lookup"><span data-stu-id="42d97-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="42d97-139">在 Microsoft 365 管理中心的左侧导航中，转到"**角色"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="42d97-140">在"**角色"** 页上的 **"Azure AD"** 选项卡上，选择 **"知识管理员"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="42d97-141">在"**知识管理员**"页的"**分配的** 管理员"部分中，选择"添加"，然后添加为角色选择的人。</span><span class="sxs-lookup"><span data-stu-id="42d97-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="42d97-142">为应用配置学习内容源的设置</span><span class="sxs-lookup"><span data-stu-id="42d97-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="42d97-143">这些步骤由 Microsoft 365 管理员或知识管理员执行。</span><span class="sxs-lookup"><span data-stu-id="42d97-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="42d97-144">在 Microsoft 365 管理中心的左侧导航中，转到"**设置**  >  **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="42d97-145">在"**设置"** 页上的"**服务&"** 选项卡上，选择 **"学习应用"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Microsoft 365 管理中心中的"设置"页，其中列出了学习应用](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="42d97-147">在 **"学习"** 应用面板中，选择要为组织配置的学习内容源，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Microsoft 365 管理中心中显示内容源选项的学习应用面板](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="42d97-149">在存在的所有学习源中，一些默认已启用。</span><span class="sxs-lookup"><span data-stu-id="42d97-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="42d97-150">其中包括：</span><span class="sxs-lookup"><span data-stu-id="42d97-150">These include:</span></span>

- <span data-ttu-id="42d97-151">LinkedIn Learning (免费内容) </span><span class="sxs-lookup"><span data-stu-id="42d97-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="42d97-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="42d97-152">Microsoft Learn</span></span>
- <span data-ttu-id="42d97-153">Microsoft 365 培训</span><span class="sxs-lookup"><span data-stu-id="42d97-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="42d97-154">如果您的组织具有 LinkedIn Learning Standard 或 Pro 订阅，将为您的组织中的员工解锁内容存储库。</span><span class="sxs-lookup"><span data-stu-id="42d97-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="42d97-155">只有具有权限的员工才能使用整个内容存储库。</span><span class="sxs-lookup"><span data-stu-id="42d97-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="42d97-156">其他源可能需要手动启用或配置。</span><span class="sxs-lookup"><span data-stu-id="42d97-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="42d97-157">非 Microsoft 的学习源在组织和第三方之间单独获得许可。</span><span class="sxs-lookup"><span data-stu-id="42d97-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="42d97-158">你需要验证你已注册供你和用户学习。</span><span class="sxs-lookup"><span data-stu-id="42d97-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="42d97-159">若要启用或禁用学习内容源，请选中源旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="42d97-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="42d97-160">如果启用了源，则显示一个选中标记。</span><span class="sxs-lookup"><span data-stu-id="42d97-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="42d97-161">将 SharePoint 配置为学习内容源</span><span class="sxs-lookup"><span data-stu-id="42d97-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="42d97-162">在 Microsoft 365 管理中心中将 SharePoint 配置为 Teams 学习应用 (个人) 预览版源。</span><span class="sxs-lookup"><span data-stu-id="42d97-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="42d97-163">概述</span><span class="sxs-lookup"><span data-stu-id="42d97-163">Overview</span></span>

<span data-ttu-id="42d97-164">知识管理员提供一个网站 URL，学习服务可在其中以结构化 SharePoint 列表的形式创建空的集中学习内容存储库。</span><span class="sxs-lookup"><span data-stu-id="42d97-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="42d97-165">组织可以使用此列表来存储指向包含学习内容的跨公司 SharePoint 文件夹的链接。</span><span class="sxs-lookup"><span data-stu-id="42d97-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="42d97-166">管理员负责收集和管理文件夹的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="42d97-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="42d97-167">这些文件夹应仅包含可在 Teams Learning 应用或个人预览版 (提供) 。</span><span class="sxs-lookup"><span data-stu-id="42d97-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="42d97-168">权限</span><span class="sxs-lookup"><span data-stu-id="42d97-168">Permissions</span></span>

<span data-ttu-id="42d97-169">可以从组织的任何 SharePoint 网站收集文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="42d97-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="42d97-170">这些文件夹中的任何内容都可以搜索，但只能使用单个员工具有权限的内容。</span><span class="sxs-lookup"><span data-stu-id="42d97-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="42d97-171">学习服务</span><span class="sxs-lookup"><span data-stu-id="42d97-171">Learning Service</span></span>

<span data-ttu-id="42d97-172">学习服务使用提供的文件夹 URL 从存储在这些文件夹中的所有内容获取元数据。</span><span class="sxs-lookup"><span data-stu-id="42d97-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="42d97-173">在集中式存储库中提供文件夹 URL 的 24 小时内，员工可以在应用中搜索和使用公司的内容。</span><span class="sxs-lookup"><span data-stu-id="42d97-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="42d97-174">目前不支持从存储库删除内容。</span><span class="sxs-lookup"><span data-stu-id="42d97-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="42d97-175">只有在 Microsoft 365 管理中心中提供新的 SharePoint 网站 URL，才能删除意外显示的内容。</span><span class="sxs-lookup"><span data-stu-id="42d97-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="42d97-176">将 SharePoint 配置为源</span><span class="sxs-lookup"><span data-stu-id="42d97-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="42d97-177">这些步骤由 Microsoft 365 管理员或知识管理员执行。</span><span class="sxs-lookup"><span data-stu-id="42d97-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="42d97-178">在 Microsoft 365 管理中心的左侧导航中，转到"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="42d97-179">在"**设置"** 页上的"**服务&"** 选项卡上，选择 **"学习应用"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Microsoft 365 管理中心中的"设置"页，其中列出了学习应用](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="42d97-181">在 **"学习"** 应用面板上，提供 SharePoint 网站的网站 URL，以便应用程序创建集中式存储库。</span><span class="sxs-lookup"><span data-stu-id="42d97-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Microsoft 365 管理中心中的学习应用面板，其中显示已选中 SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="42d97-183">SharePoint 列表在提供的组织的 SharePoint 网站中自动创建。</span><span class="sxs-lookup"><span data-stu-id="42d97-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="42d97-184">在 SharePoint 网站的左侧导航栏中，选择 **"学习应用内容存储库"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![SharePoint 中的左侧导航，显示"学习应用内容存储库"部分](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="42d97-186">在" **学习应用内容存储库"** 页上，使用学习内容文件夹的 URL 填充 SharePoint 列表。</span><span class="sxs-lookup"><span data-stu-id="42d97-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="42d97-187">选择 **"新建** "以查看 **"新建项目"** 面板。</span><span class="sxs-lookup"><span data-stu-id="42d97-187">Select **New** to view the **New item** panel.</span></span> 

   ![SharePoint 中显示"新建"选项的"学习应用内容存储库"页](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="42d97-189">在 **"新建项** "面板的"标题 **"字段中，** 添加选择的目录名称。</span><span class="sxs-lookup"><span data-stu-id="42d97-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="42d97-190">在 **"文件夹 URL"** 字段中，将 URL 添加到学习内容文件夹。</span><span class="sxs-lookup"><span data-stu-id="42d97-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="42d97-191">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="42d97-191">Select **Save**.</span></span>

   ![SharePoint 中的"新建项目"面板，显示"标题"和"文件夹 URL"字段](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="42d97-193">学习应用内容存储库页面使用新的学习内容进行更新。</span><span class="sxs-lookup"><span data-stu-id="42d97-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![SharePoint 中的"学习应用内容存储库"页，显示更新的信息](media/learning-app-content-repository-populated.png)


 


