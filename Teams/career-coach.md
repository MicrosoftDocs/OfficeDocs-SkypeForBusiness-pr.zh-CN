---
title: 购买、配置和启用职业指导Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何购买、配置和启用职业指导Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2a5bc0f459bb9e7dac8878a5ad75911ba4b1b82
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628901"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="f1a2e-103">购买、配置和启用职业指导Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="f1a2e-104">职业指导是一Microsoft Teams由 LinkedIn 支持的应用，它为教育学生提供个性化指导，帮助其导航其职业之旅。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="f1a2e-105">职业指导为教育机构提供了统一的职业发展解决方案，学生可以发现其职业路径、发展实际技能，并全部在一个地方建立自己的网络。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="f1a2e-106">详细了解职业 [指导](https://aka.ms/career-coach)。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-107">使用本指南中的最佳实践和有用提示为学生和教职员工启用职业指导的功能。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="f1a2e-108">请参阅 [快速规划指南](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) 一文。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="f1a2e-109">查看要求</span><span class="sxs-lookup"><span data-stu-id="f1a2e-109">Review the requirements</span></span>

<span data-ttu-id="f1a2e-110">若要为教育机构启用职业指导，请查看启动和运行应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="f1a2e-111">**技术要求**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-111">**Technical requirements**</span></span>

  - <span data-ttu-id="f1a2e-112">Office 365租户Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1a2e-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="f1a2e-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-113">Microsoft Teams</span></span>

  - <span data-ttu-id="f1a2e-114">Azure Active Directory 中的 LinkedIn 帐户Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1a2e-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="f1a2e-115">**许可证**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-115">**Licenses**</span></span>

  - <span data-ttu-id="f1a2e-116">教职员工</span><span class="sxs-lookup"><span data-stu-id="f1a2e-116">Faculty</span></span> 

  - <span data-ttu-id="f1a2e-117">学生</span><span class="sxs-lookup"><span data-stu-id="f1a2e-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-118">必须为完成配置的 IT 管理员分配职业指导教职员工许可证。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="f1a2e-119">**来自教育机构的数据和文件**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="f1a2e-120">课程目录数据</span><span class="sxs-lookup"><span data-stu-id="f1a2e-120">Course catalog data</span></span>

  - <span data-ttu-id="f1a2e-121">提供的研究领域</span><span class="sxs-lookup"><span data-stu-id="f1a2e-121">Fields of study offered</span></span>

  - <span data-ttu-id="f1a2e-122">教育机构的 LinkedIn 页面</span><span class="sxs-lookup"><span data-stu-id="f1a2e-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="f1a2e-123">LinkedIn Learning campus 订阅 (首选) </span><span class="sxs-lookup"><span data-stu-id="f1a2e-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="f1a2e-124">购买职业指导许可证</span><span class="sxs-lookup"><span data-stu-id="f1a2e-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="f1a2e-125">通过教育解决方案注册 (EES) 、云服务提供商 (CSP) 和 Microsoft 365) 管理中心 (Web direct) ，可在全球 (（中国和俄罗斯除外）为符合条件的教育机构提供职业指导。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="f1a2e-126">作为Microsoft Teams应用，客户必须具有 Microsoft 365 A3/A5 或 Office 365 A1/A3/A5。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="f1a2e-127">向用户分配应用许可证</span><span class="sxs-lookup"><span data-stu-id="f1a2e-127">Assign app licenses to users</span></span>

<span data-ttu-id="f1a2e-128">有关分步说明，请参阅[向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-128">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="f1a2e-129">打开 LinkedIn 帐户连接</span><span class="sxs-lookup"><span data-stu-id="f1a2e-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="f1a2e-130">职业 **指导** 要求教育机构的用户能够将其个人帐户Microsoft 365其在职业指导中协助的 LinkedIn 帐户</span><span class="sxs-lookup"><span data-stu-id="f1a2e-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="f1a2e-131">使用 Azure [AD](https://aad.portal.azure.com/) 组织的全局管理员帐户登录到 Azure AD 管理中心。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="f1a2e-132">选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-132">Select **Users**.</span></span>

3. <span data-ttu-id="f1a2e-133">在"**用户"** 页上，选择"**用户设置"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="f1a2e-134">在 **"LinkedIn 帐户连接**"下，允许用户连接其帐户以在某些 Microsoft 应用中访问其 LinkedIn 连接。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="f1a2e-135">在用户同意连接其帐户之前，不会共享任何数据。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="f1a2e-136">选择 **"** 是"，为教育机构中的所有用户启用该服务</span><span class="sxs-lookup"><span data-stu-id="f1a2e-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="f1a2e-137">选择 **"所选** 组"，仅为教育机构中的一组选定用户启用该服务</span><span class="sxs-lookup"><span data-stu-id="f1a2e-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="f1a2e-138">选择 **"** 否"以撤消你的教育机构中所有用户的同意</span><span class="sxs-lookup"><span data-stu-id="f1a2e-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="f1a2e-139">了解如何将[LinkedIn 帐户连接集成到 Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="f1a2e-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="f1a2e-140">在管理中心Teams职业指导</span><span class="sxs-lookup"><span data-stu-id="f1a2e-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="f1a2e-141">使用管理中心中的Microsoft Teams设置，您可以为教育机构配置职业指导，并让用户启用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="f1a2e-142">访问职业指导应用设置</span><span class="sxs-lookup"><span data-stu-id="f1a2e-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="f1a2e-143">使用["管理应用](/microsoftteams/manage-apps)"Teams在教育机构的应用目录中查看应用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="f1a2e-144">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="f1a2e-145">在左侧导航栏中，选择  >  **Teams"管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="f1a2e-146">只有全局管理员或Teams才能访问页面。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="f1a2e-147">搜索或浏览"职业 **指导"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="f1a2e-148">选择 **"职业指导**"，然后选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![显示选中的"职业指导"应用，设置选项](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="f1a2e-150">配置职业指导应用设置</span><span class="sxs-lookup"><span data-stu-id="f1a2e-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="f1a2e-151">职业指导有五种配置类别：</span><span class="sxs-lookup"><span data-stu-id="f1a2e-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="f1a2e-152">品牌和首选项</span><span class="sxs-lookup"><span data-stu-id="f1a2e-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="f1a2e-153">LinkedIn 配置</span><span class="sxs-lookup"><span data-stu-id="f1a2e-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="f1a2e-154">课程目录</span><span class="sxs-lookup"><span data-stu-id="f1a2e-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="f1a2e-155">研究领域</span><span class="sxs-lookup"><span data-stu-id="f1a2e-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="f1a2e-156">自定义</span><span class="sxs-lookup"><span data-stu-id="f1a2e-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="f1a2e-157">品牌和首选项、LinkedIn 配置、课程目录和研究领域是必需的，才能有效地为学生和教职员工启用该应用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="f1a2e-158">品牌和首选项</span><span class="sxs-lookup"><span data-stu-id="f1a2e-158">Brand and preferences</span></span>

<span data-ttu-id="f1a2e-159">在品牌和首选项设置页面上设置教育机构的名称、徽标和默认语言。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![管理中心的"职业指导品牌"部分](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="f1a2e-161">教育机构图标</span><span class="sxs-lookup"><span data-stu-id="f1a2e-161">Educational institution icon</span></span>

<span data-ttu-id="f1a2e-162">在整个职业指导中，教育机构图标用于标识您的教育机构独有的内容、整个应用中的课程目录资源，以及仪表板的实际体验部分。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="f1a2e-163">图标的格式最好为：</span><span class="sxs-lookup"><span data-stu-id="f1a2e-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="f1a2e-164">透明 PNG</span><span class="sxs-lookup"><span data-stu-id="f1a2e-164">A transparent PNG</span></span>
 - <span data-ttu-id="f1a2e-165">纵横比为 1：1</span><span class="sxs-lookup"><span data-stu-id="f1a2e-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="f1a2e-166">最大大小为 64 px x 64 px。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="f1a2e-167">教育机构缩略图</span><span class="sxs-lookup"><span data-stu-id="f1a2e-167">Educational institution thumbnail</span></span>

<span data-ttu-id="f1a2e-168">当特定图像不可用于课程时，教育机构图标将在整个应用中用于课程目录资源。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="f1a2e-169">图标的格式最好为：</span><span class="sxs-lookup"><span data-stu-id="f1a2e-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="f1a2e-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="f1a2e-170">A PNG</span></span>
- <span data-ttu-id="f1a2e-171">纵横比为 16：9</span><span class="sxs-lookup"><span data-stu-id="f1a2e-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="f1a2e-172">最大大小为 360 px x 200 像素。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="f1a2e-173">LinkedIn 配置</span><span class="sxs-lookup"><span data-stu-id="f1a2e-173">LinkedIn configuration</span></span>

<span data-ttu-id="f1a2e-174">LinkedIn 配置将职业指导与来自 LinkedIn 的公共毕业生数据相连接。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-175">在未验证 LinkedIn 页面连接的情况下，无法启用职业指导。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="f1a2e-176">添加并确认 LinkedIn 页面</span><span class="sxs-lookup"><span data-stu-id="f1a2e-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="f1a2e-177">确定教育机构的 LinkedIn 页面。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="f1a2e-178">通过搜索 LinkedIn 或与职业服务职员联系来确定使用的正确页面，查找 LinkedIn 页面。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="f1a2e-179">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="f1a2e-180">选择 **"Teams应用**  >    >  **""管理应用""职业指导**  >  **LinkedIn 连接"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="f1a2e-181">输入教育机构的 LinkedIn 页面 URL。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="f1a2e-182">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-182">Select **Apply**.</span></span>

4. <span data-ttu-id="f1a2e-183">复制验证 URL，并与教育机构的 LinkedIn 页面管理员[LinkedIn 页面管理员文档共享。](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)</span><span class="sxs-lookup"><span data-stu-id="f1a2e-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="f1a2e-184">验证链接在 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-184">The verification link expires after 30 days.</span></span>  

   ![职业指导的链接设置](media/linkedin.png)  

#### <a name="course-catalog"></a><span data-ttu-id="f1a2e-186">课程目录</span><span class="sxs-lookup"><span data-stu-id="f1a2e-186">Course catalog</span></span>

<span data-ttu-id="f1a2e-187">课程目录表示教育机构为学生提供的课程和课程。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="f1a2e-188">这些课程在应用内用于两个方面：</span><span class="sxs-lookup"><span data-stu-id="f1a2e-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="f1a2e-189">课程作为学习资源的一部分返回。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="f1a2e-190">课程和课程元数据（如说明）用于帮助学生在上传脚本时识别其技能。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="f1a2e-191">若要创建课程目录，请汇集在教育机构中教授的所有课程的列表，并将其上传为 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="f1a2e-192">该应用从课程目录中进行绘制，以识别学生的脚本技能，并建议要参加的课程。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

> [!NOTE]
> <span data-ttu-id="f1a2e-193">有关[保护学生信息Teams](location-of-data-in-teams.md)[请参阅](security-compliance-overview.md)数据在安全与合规性中的位置。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-193">See [Location of data in Teams](location-of-data-in-teams.md) and [Security and compliance](security-compliance-overview.md) for information about protecting of student information.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="f1a2e-194">课程目录文档格式和架构</span><span class="sxs-lookup"><span data-stu-id="f1a2e-194">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="f1a2e-195">文档需要采用 CSV 格式，最大大小为 18 MB。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-195">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="f1a2e-196">文档必须包含必填字段 **课程标题**、**课程 ID** 和 **课程 URL。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-196">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="f1a2e-197">包含建议的字段可返回更好的搜索结果和技能标识，从而改善学生的体验。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-197">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-198">从示例 [课程目录文档]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) 开始入门。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-198">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

<span data-ttu-id="f1a2e-199">下表显示了要包括在课程目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="f1a2e-199">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="f1a2e-200">名称</span><span class="sxs-lookup"><span data-stu-id="f1a2e-200">Name</span></span>             | <span data-ttu-id="f1a2e-201">状态</span><span class="sxs-lookup"><span data-stu-id="f1a2e-201">Status</span></span>      | <span data-ttu-id="f1a2e-202">类型</span><span class="sxs-lookup"><span data-stu-id="f1a2e-202">Type</span></span>   | <span data-ttu-id="f1a2e-203">说明</span><span class="sxs-lookup"><span data-stu-id="f1a2e-203">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="f1a2e-204">courseId</span><span class="sxs-lookup"><span data-stu-id="f1a2e-204">courseId</span></span>         | <span data-ttu-id="f1a2e-205">必需</span><span class="sxs-lookup"><span data-stu-id="f1a2e-205">Required</span></span>    | <span data-ttu-id="f1a2e-206">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-206">string</span></span> | <span data-ttu-id="f1a2e-207">课程 ID 通常 (映射到脚本脚本中生成的内容) 。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-207">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="f1a2e-208">title</span><span class="sxs-lookup"><span data-stu-id="f1a2e-208">title</span></span>            | <span data-ttu-id="f1a2e-209">必需</span><span class="sxs-lookup"><span data-stu-id="f1a2e-209">Required</span></span>    | <span data-ttu-id="f1a2e-210">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-210">string</span></span> | <span data-ttu-id="f1a2e-211">通常是课程标题。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-211">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="f1a2e-212">sourceLink</span><span class="sxs-lookup"><span data-stu-id="f1a2e-212">sourceLink</span></span>       | <span data-ttu-id="f1a2e-213">必需</span><span class="sxs-lookup"><span data-stu-id="f1a2e-213">Required</span></span>    | <span data-ttu-id="f1a2e-214">URL</span><span class="sxs-lookup"><span data-stu-id="f1a2e-214">URL</span></span>    | <span data-ttu-id="f1a2e-215">课程页面的网站链接。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-215">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="f1a2e-216">description</span><span class="sxs-lookup"><span data-stu-id="f1a2e-216">description</span></span>      | <span data-ttu-id="f1a2e-217">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-217">Recommended</span></span> | <span data-ttu-id="f1a2e-218">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-218">string</span></span> | <span data-ttu-id="f1a2e-219">课程简介文本。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-219">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="f1a2e-220">语言</span><span class="sxs-lookup"><span data-stu-id="f1a2e-220">language</span></span>         | <span data-ttu-id="f1a2e-221">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-221">Recommended</span></span> | <span data-ttu-id="f1a2e-222">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-222">string</span></span> | <span data-ttu-id="f1a2e-223">课程的语言。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-223">Language of the course.</span></span> <span data-ttu-id="f1a2e-224">使用标准语言代码。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-224">Use standard language codes.</span></span>                           |
| <span data-ttu-id="f1a2e-225">format</span><span class="sxs-lookup"><span data-stu-id="f1a2e-225">format</span></span>           | <span data-ttu-id="f1a2e-226">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-226">Recommended</span></span> | <span data-ttu-id="f1a2e-227">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-227">string</span></span> | <span data-ttu-id="f1a2e-228">教学模式，例如在线、视频、个人。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-228">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="f1a2e-229">thumbnailLink</span><span class="sxs-lookup"><span data-stu-id="f1a2e-229">thumbnailLink</span></span>    | <span data-ttu-id="f1a2e-230">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-230">Recommended</span></span> | <span data-ttu-id="f1a2e-231">URL</span><span class="sxs-lookup"><span data-stu-id="f1a2e-231">URL</span></span>    | <span data-ttu-id="f1a2e-232">指向课程图像的缩略图链接。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-232">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="f1a2e-233">thumbnailAltText</span><span class="sxs-lookup"><span data-stu-id="f1a2e-233">thumbnailAltText</span></span> | <span data-ttu-id="f1a2e-234">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-234">Recommended</span></span> | <span data-ttu-id="f1a2e-235">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-235">string</span></span> | <span data-ttu-id="f1a2e-236">图像的辅助功能替换文字</span><span class="sxs-lookup"><span data-stu-id="f1a2e-236">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="f1a2e-237">educationLevel</span><span class="sxs-lookup"><span data-stu-id="f1a2e-237">educationLevel</span></span>   | <span data-ttu-id="f1a2e-238">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-238">Recommended</span></span> | <span data-ttu-id="f1a2e-239">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-239">string</span></span> | <span data-ttu-id="f1a2e-240">学习级别，例如</span><span class="sxs-lookup"><span data-stu-id="f1a2e-240">Study level, ex.</span></span> <span data-ttu-id="f1a2e-241">公司/毕业生。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-241">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="f1a2e-242">主题</span><span class="sxs-lookup"><span data-stu-id="f1a2e-242">topics</span></span>           | <span data-ttu-id="f1a2e-243">推荐</span><span class="sxs-lookup"><span data-stu-id="f1a2e-243">Recommended</span></span> | <span data-ttu-id="f1a2e-244">string</span><span class="sxs-lookup"><span data-stu-id="f1a2e-244">string</span></span> | <span data-ttu-id="f1a2e-245">与课程所教技能相关的主题或标记。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-245">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="f1a2e-246">添加课程目录</span><span class="sxs-lookup"><span data-stu-id="f1a2e-246">Add the course catalog</span></span>

1. <span data-ttu-id="f1a2e-247">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-247">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="f1a2e-248">选择 **"Teams应用** &gt; **管理应用** &gt; **""** 职业设置 &gt;  &gt; **课程目录"。**  </span><span class="sxs-lookup"><span data-stu-id="f1a2e-248">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="f1a2e-249">Upload CSV 格式的课程。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-249">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="f1a2e-250">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-250">Select **Apply**.</span></span>

   ![职业指导应用的课程目录部分](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="f1a2e-252">研究领域</span><span class="sxs-lookup"><span data-stu-id="f1a2e-252">Fields of study</span></span>

<span data-ttu-id="f1a2e-253">研究领域与感兴趣的主要领域、学术专业和程度同义。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-253">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="f1a2e-254">这些游戏在学生开始使用应用并开始设置其个性化个人资料时被学生引用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-254">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="f1a2e-255">添加学生可用的所有研究领域，如工程、英语、商业等。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-255">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="f1a2e-256">字段列表允许学生发现可能感兴趣的研究领域，并将其添加到其个人资料中。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-256">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-257">从研究领域 [示例文档](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) 开始。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-257">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="f1a2e-258">添加研究领域</span><span class="sxs-lookup"><span data-stu-id="f1a2e-258">Add the fields of study</span></span>

1. <span data-ttu-id="f1a2e-259">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-259">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="f1a2e-260">选择 **Teams应用** &gt; **管理** &gt; **应用职业** &gt;  &gt; **设置"研究领域"。**  </span><span class="sxs-lookup"><span data-stu-id="f1a2e-260">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="f1a2e-261">Upload CSV 格式的研究领域。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-261">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="f1a2e-262">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-262">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="f1a2e-263">自定义</span><span class="sxs-lookup"><span data-stu-id="f1a2e-263">Customization</span></span>

<span data-ttu-id="f1a2e-264">可以自定义职业指导，以在教育机构中独一无二。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-264">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="f1a2e-265">自定义支持将体验添加到仪表板。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-265">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="f1a2e-266">建议添加指向职位委员会、活动、职业服务办公室、职业相关活动、学生俱乐部和任何其他可帮助学生获得实际经验的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-266">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="f1a2e-267">添加自定义体验</span><span class="sxs-lookup"><span data-stu-id="f1a2e-267">Add customized experiences</span></span>

1. <span data-ttu-id="f1a2e-268">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-268">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="f1a2e-269">选择 **Teams应用** &gt; **管理** &gt; **应用""职业指导**  >  **设置** &gt; **自定义"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-269">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="f1a2e-270">添加每个 URL、标题和简短说明。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-270">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="f1a2e-271">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-271">Select **Apply**.</span></span>

## <a name="making-career-coach-available-to-your-organization"></a><span data-ttu-id="f1a2e-272">为组织提供职业指导</span><span class="sxs-lookup"><span data-stu-id="f1a2e-272">Making Career Coach available to your organization</span></span>

<span data-ttu-id="f1a2e-273">现在，已为组织配置了职业指导。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-273">Now that Career Coach has been configured for your organization.</span></span> <span data-ttu-id="f1a2e-274">请按照以下步骤确保职业指导可供组织在Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-274">Follow these steps to ensure that Career Coach is available to organization in Microsoft Teams.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="f1a2e-275">启用应用</span><span class="sxs-lookup"><span data-stu-id="f1a2e-275">Enable the app</span></span>

<span data-ttu-id="f1a2e-276">完成配置后，为学生和许可用户启用应用，以便他们有权访问职业指导。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-276">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1a2e-277">必须具有全局或Teams管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-277">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="f1a2e-278">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-278">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="f1a2e-279">选择 **"Teams** &gt; **应用""管理应用** &gt; **""职业指导"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-279">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="f1a2e-280">将"状态"切换开关移动到"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-280">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="f1a2e-281">允许意味着该应用可供教育机构中的用户使用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-281">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="f1a2e-282">被阻止意味着该应用对学生不可用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-282">Blocked means that the app isn't available to students.</span></span>

### <a name="add-career-coach-as-an-installed-app"></a><span data-ttu-id="f1a2e-283">将职业指导添加为已安装的应用</span><span class="sxs-lookup"><span data-stu-id="f1a2e-283">Add Career Coach as an installed app</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-284">此步骤可确保 1) 为组织正确配置职业指导 2) 学生找到职业指导。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-284">This step ensures 1) that Career Coach is properly configured for your organization 2) that students find Career Coach.</span></span>

1. <span data-ttu-id="f1a2e-285">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-285">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="f1a2e-286">选择 **Teams** &gt; **设置策略** &gt; *策略"。*</span><span class="sxs-lookup"><span data-stu-id="f1a2e-286">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="f1a2e-287">在"已安装的应用"下，选择"添加应用"。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-287">Under Installed apps, select Add apps.</span></span>

4. <span data-ttu-id="f1a2e-288">在"添加已安装的应用"窗格中，搜索希望用户在启动应用时自动安装Teams。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-288">In the Add installed apps pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="f1a2e-289">还可以按应用权限策略筛选应用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-289">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="f1a2e-290">选择应用列表后，选择"添加"。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-290">When you've chosen your list of apps, select Add.</span></span>

### <a name="pin-the-app"></a><span data-ttu-id="f1a2e-291">固定应用</span><span class="sxs-lookup"><span data-stu-id="f1a2e-291">Pin the app</span></span>

<span data-ttu-id="f1a2e-292">固定职业指导会使应用更易于访问，并且对学生可见。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-292">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="f1a2e-293">登录到管理 **Teams中心**。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-293">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="f1a2e-294">选择 **Teams** &gt; **设置策略** &gt; *策略"。*</span><span class="sxs-lookup"><span data-stu-id="f1a2e-294">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="f1a2e-295">在 **"固定的应用"下**，选择 **"添加应用"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-295">Under **Pinned apps**, choose **Add apps**.</span></span>

4. <span data-ttu-id="f1a2e-296">搜索"**职业指导"，** 然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-296">Search for **Career Coach**, and then select **Add**.</span></span>

5. <span data-ttu-id="f1a2e-297">选择显示应用的顺序，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="f1a2e-297">Choose the order for the app to appear and select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f1a2e-298">学生将收到职业Microsoft Teams已固定的通知。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-298">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>

<span data-ttu-id="f1a2e-299">有关 [更多详细信息，请参阅在 Microsoft 中](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) 管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-299">Reference [Manage app setup policies in Microsoft](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) for additional details.</span></span>

## <a name="resources"></a><span data-ttu-id="f1a2e-300">资源</span><span class="sxs-lookup"><span data-stu-id="f1a2e-300">Resources</span></span>

<span data-ttu-id="f1a2e-301">以下资源将帮助你规划职业指导应用。</span><span class="sxs-lookup"><span data-stu-id="f1a2e-301">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="f1a2e-302">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-302">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="f1a2e-303">如何部署 Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-303">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="f1a2e-304">Microsoft Teams 中的团队和频道概述</span><span class="sxs-lookup"><span data-stu-id="f1a2e-304">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="f1a2e-305">在管理中心Microsoft Teams应用</span><span class="sxs-lookup"><span data-stu-id="f1a2e-305">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="f1a2e-306">安全、隐私和合规性Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-306">Security, privacy, and compliance in Microsoft Teams</span></span>](security-compliance-overview.md)

- [<span data-ttu-id="f1a2e-307">联机虚拟方向工具包</span><span class="sxs-lookup"><span data-stu-id="f1a2e-307">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="f1a2e-308">通道的限制Teams规范</span><span class="sxs-lookup"><span data-stu-id="f1a2e-308">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="f1a2e-309">Microsoft Teams 中的数据位置</span><span class="sxs-lookup"><span data-stu-id="f1a2e-309">Location of data in Microsoft Teams</span></span>](location-of-data-in-teams.md)

- [<span data-ttu-id="f1a2e-310">适用于管理员的管理员培训Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1a2e-310">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="f1a2e-311">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="f1a2e-311">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="f1a2e-312">在 Microsoft Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="f1a2e-312">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
