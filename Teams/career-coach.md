---
title: 购买、配置和启用职业教练Microsoft Teams 教育版
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何购买、配置和启用职业教练Microsoft Teams 教育版。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d6d3aed02c2f9eb9913a62ed502355590a5df4b
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494359"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>为 Microsoft Teams 购买、配置和启用职业教练

职业教练是一个Microsoft Teams 教育版应用，由LinkedIn提供个性化指导，让高等教育学生在职业旅程中导航。 职业教练为教育机构提供了一个统一的职业解决方案，让学生发现自己的职业道路，发展现实世界技能，并在一个地方建立他们的网络。

## <a name="supported-languages"></a>支持的语言

职业教练以以下语言进行本地化：

- 中国 (简体，中国大陆) 
- 中国 (传统，台湾) 
- 英语 (US)
- 英语 (UK)
- 法国 (加拿大) 
- 法国 (法国) 
- 德国 (德国) 
- 日本 (日本) 
- 葡萄牙 (巴西) 
- 西班牙 (西班牙) 
- 西班牙 (墨西哥) 

详细了解 [职业教练](https://aka.ms/career-coach)。

> [!TIP]
> 使用本指南中的最佳做法和有用的提示，为学生、教职员工启用职业教练功能。 请参阅 [快速规划指南](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) 文章。

## <a name="review-the-requirements"></a>查看要求

若要为教育机构启用职业教练，请查看启动和运行职业教练所需的内容。

### <a name="technical-requirements"></a>技术要求

- Office 365启用了LinkedIn帐户连接的 Azure Active Directory 租户。
- Microsoft Teams。
- LinkedIn学校页面。

### <a name="data-and-files-from-your-educational-institution"></a>来自教育机构的数据和文件

- 教育机构的徽标和图形资产 [采用所需的格式](#brand-and-preferences)。

- 课程目录数据。 [查看示例文件](https://aka.ms/career-coach/docs/it-admins/sample-catalog) 和 [文档格式](#course-catalog-document-format-and-schema)。

- 提供的研究领域列表。 [查看示例文件](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)。

- 教育机构的 [LinkedIn学校页面 URL](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

- 教育机构的隐私政策 URL。

- 教育机构链接到与职业相关的资源，如职业服务网站和学生职位发布 (可选) 。

## <a name="setup-checklist"></a>安装清单

为准备为租户发布职业教练，需要几个管理员角色。 这些角色和权限可以分配给一个人，或者可能需要与组织中的 IT 专业人员协作。 使用本指南可帮助确定完成所需任务所需的个人。

可以通过访问[Microsoft 365 管理中心 >用户>活动用户>](https://go.microsoft.com/fwlink/p/?linkid=834822)选择用户名来确认你的角色来检查帐户分配的角色。

详细了解[Microsoft 365 管理中心中的管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

### <a name="microsoft-365-admin-center"></a>[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)

角色： [全局管理员](/azure/active-directory/roles/permissions-reference#global-administrator) 职业教练任务：

- [购买许可证](#purchase-career-coach-licenses)
- [分配许可证](#assign-career-coach-licenses-to-users)

### <a name="azure-active-directory-admin-center"></a>[Azure Active Directory 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2067268)

角色： [全局管理员](/azure/active-directory/roles/permissions-reference#global-administrator) 职业教练任务：

- [打开LinkedIn帐户连接](#turn-on-linkedin-account-connections)

### <a name="teams-admin-center"></a>[Teams 管理中心](https://admin.teams.microsoft.com/dashboard)

角色： [Teams 管理员](/azure/active-directory/roles/permissions-reference#teams-administrator) 职业教练任务：

- [将职业教练添加为已安装的应用](#add-career-coach-as-an-installed-app)
- [配置职业教练应用设置](#configure-career-coach-settings)
  - [品牌和首选项](#brand-and-preferences) - 必需
  - [LinkedIn连接](#linkedin-connection) - 必需
  - [课程目录](#course-catalog) - 必需
  - [研究](#fields-of-study) 领域- 必需
  - [自定义](#customization) - 可选
- [设置策略](#setup-policies-and-pin-the-app)
- [固定应用](#setup-policies-and-pin-the-app)

### <a name="linkedin-developer-portal"></a>LinkedIn开发人员门户

角色：[LinkedIn学校页面超级管理员](https://www.linkedin.com/help/linkedin/answer/a541981)职业教练任务：

- [验证LinkedIn学校页面](#verify-the-linkedin-school-page)

## <a name="purchase-career-coach-licenses"></a>购买职业教练许可证

### <a name="license-types"></a>许可证类型

职业教练需要许可证才能访问应用程序。

有两种可用的许可证类型。

- **学生许可证** 是为学生设计的。
- **教师许可证** 专为参与使用职业教练支持学生的教职员工和 IT 专业人员设计。

> [!IMPORTANT]
> 必须向完成配置的 IT 管理员分配职业教练 **教职员工许可证** 。

### <a name="purchase-licenses"></a>购买许可证

除中国和俄罗斯外，除中国和俄罗斯外， (通过注册教育解决方案)  (EES) 、云服务提供商 (CSP) 以及Microsoft 365 管理中心 (Web 直接) ，将合格高等教育机构作为附加许可证提供职业教练。

作为 Microsoft Teams 应用，租户必须具有Microsoft 365 A3/A5 或Office 365 A1/A3/A5 才能购买加载项职业教练许可证。 为学生和教职员工用户提供单独的许可证。

### <a name="sign-up-for-a-free-trial"></a>注册免费试用版

标准的 90 天免费试用版适用于 25 名学生和 25 个教职员工许可证。 每个符合条件的租户都提供一个试用版。 有资格购买职业教练的租户可以从Microsoft 365 管理中心激活试用许可证。

若要试用，请登录[Microsoft 365 管理中心 >计费>购买服务>搜索职业教练](https://go.microsoft.com/fwlink/p/?linkid=868433)以查找[学生许可证试用](https://signup.microsoft.com/signup?OfferId=b3a40ff2-3d0d-481e-a0ed-f4de1069f201)版和[教职员工许可证试用](https://signup.microsoft.com/signup?OfferId=6f6e7db5-b9ab-4baa-86be-f13d0ae6a2c8)版。

## <a name="prepare-for-career-coach"></a>准备职业教练

### <a name="turn-on-linkedin-account-connections"></a>打开LinkedIn帐户连接

职业教练使用LinkedIn帐户连接有两种方法。

- 允许学生、教职员工将其 Microsoft 365 帐户连接到其LinkedIn帐户，并 [从职业教练发送LinkedIn邀请](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_connect_your_linkedin_account)。
- 使用来自LinkedIn的公共校友数据启用 [“构建网络](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) 和 [探索职业](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) ”功能。

1. 使用 [Azure AD](https://go.microsoft.com/fwlink/p/?linkid=2067268) 组织的 [全局管理员帐户](#setup-checklist) 登录到 Azure AD 管理中心。

2. 选择 **“用户**”。

3. 在 **“用户** ”页上，选择 **“用户设置**”。

4. **LinkedIn帐户连接** 必须设置为 **“是** ”或 **“选择”组** 才能正确配置职业教练。

   - 选择 **“是** ”可为教育机构中的所有用户启用该服务。
   - 选择 **“选定组** ”以仅为教育机构中的一组选定用户启用该服务。

有关详细信息，请参阅 [Azure Active Directory 中的LinkedIn帐户连接](/azure/active-directory/enterprise-users/linkedin-integration)。

> [!NOTE]
> 未经用户同意，不会共享任何数据。

### <a name="allow-microsoft-apps-in-teams"></a>在 Teams 中允许 Microsoft 应用

职业教练是 Microsoft 应用程序，因此必须在 Teams 应用权限策略中允许它。

1. 登录到 **[Teams 管理中心](https://admin.teams.microsoft.com)**。

2. 在左侧导航栏中，选择 **Teams 应用** > **[权限策略](https://admin.teams.microsoft.com/policies/manage-apps)**。

3. 选择首选策略。
    1. 如果不确定要使用哪个策略，请参阅 [Microsoft Teams 策略管理文档](policy-packages-edu.md) 或使用 [教育策略向导](easy-policy-setup-edu.md) 为 Microsoft Teams 配置策略。

详细了解如何 [配置权限策略](teams-app-permission-policies.md)。

### <a name="add-career-coach-as-an-installed-app"></a>将职业教练添加为已安装的应用

此步骤可确保为组织正确配置职业教练，并确保学生找到职业教练。

1. 登录 Teams [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。

2. 选择 **Teams 应用** > **设置策略**，然后选择首选策略。
    1. 如果不确定要使用哪个策略，请参阅 [Microsoft Teams 策略管理文档](policy-packages-edu.md) 或使用 [教育策略向导](easy-policy-setup-edu.md) 为 Microsoft Teams 配置策略。

3. 在 **“已安装的应用**”下，选择  **“+ 添加应用**”。

4. 在 **“添加已安装的应用** ”窗格中，搜索要在用户启动 Teams 时自动安装的应用。 还可以按应用权限策略筛选应用。

5. 选择应用列表后，选择 **“添加**”。

6. 选择  **“保存** > **确认**”。

> [!NOTE]
> 编辑或分配策略可能需要几个小时才能使更改生效。 在更改完成之前，职业教练在 Microsoft Teams 中不可用。

## <a name="configure-career-coach-settings"></a>配置职业教练设置

### <a name="access-the-career-coach-app-settings"></a>访问职业教练应用设置

若要配置职业教练设置并为用户启用它，必须是全局管理员或 Teams 服务管理员才能访问该页面。

1. 登录 Teams [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。
2. 在左侧导航栏中，选择 **“Teams 应用** > **管理应用**”。
3. 搜索或浏览 **职业教练**。
4. 选择 **职业教练**，然后 **选择“设置**”。

![显示已选中“设置”选项卡的职业教练应用。](media/career-coach-app-updated.png)

### <a name="career-coach-configuration-categories"></a>职业教练配置类别

若要有效地为学生、教职员工启用职业教练，需要以下设置：

- [品牌和首选项](#brand-and-preferences)
- [LinkedIn连接](#linkedin-connection)
- [课程目录](#course-catalog)
- [研究领域](#fields-of-study)

还可以设置可选的 [自定义](#customization) 设置。

> [!TIP]
> 通过选择位于页面顶部的格式`Manage apps\Career Coach\Setting label`**职业教练** 路径，快速从一个类别导航到另一个类别。

### <a name="brand-and-preferences"></a>品牌和首选项

自定义职业教练以匹配你的教育机构的品牌。 你负责尊重他人的权利，包括版权和商标权。

> [!IMPORTANT]
> 这是必需的部分。 没有品牌 **和首选项** 提交，就无法启用职业教练。

1. 登录 Teams **[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **管理应用** > **职业教练** > **设置** > **编辑品牌和首选项**。

3. 在 **“品牌”** 下，添加 **组织名称**。

4. 上传 **组织图标**。 在整个职业教练中，该图标用于标识教育机构独有的内容、整个应用的课程目录资源，以及仪表板的实际体验部分。

    图标的格式最好为：

    - 透明 PNG
    - 纵横比为 1：1
    - 最大大小为 64 px x 64 px

5. 上传 **Learning 内容缩略图**。 如果未为教育机构提供的课程指定特定映像，则缩略图将用于整个应用的课程目录学习资源。

    缩略图的格式最好为：

    - A PNG
    - 纵横比为 16：9
    - 最大大小为 360 px x 200 px

6. 添加 **组织隐私策略 URL**。 如果添加，该机构的隐私政策将可供学生在职业教练中审查。

7. 选择 **“提交**”。

8. 若要确认已成功提交设置，请检查[“完成”的职业教练配置状态](#configuration-status)。

![管理中心的职业教练品牌部分。](media/career-coach-brand-updated.png)

### <a name="linkedin-connection"></a>LinkedIn连接

LinkedIn连接设置将职业教练与来自你机构LinkedIn学校页面的公共校友数据连接起来。

只有 [在 Azure Active Directory 中启用了LinkedIn帐户连接](#turn-on-linkedin-account-connections)时，才能完成此步骤。 LinkedIn连接设置支持 [生成网络](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) 和 [探索职业](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) 功能。

> [!IMPORTANT]
> 这是必需的部分。 没有验证LinkedIn学校页面连接，就无法启用职业教练。

#### <a name="add-the-linkedin-school-page-url"></a>添加LinkedIn学校页面 URL

添加LinkedIn学校页面 URL 的过程由 Teams 管理员处理。 随后验证 URL 的步骤由教育机构的LinkedIn学校页面超级管理员完成。

1. 登录 Teams **[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **管理应用** > **职业教练** > **设置** > **LinkedIn连接**。

3. 选择 **“连接到LinkedIn**”。

4. 通过搜索LinkedIn并选择“学校”筛选器，查找机构的LinkedIn **学校** 页面。 或与贵机构的营销人员联系，以确定要使用的正确LinkedIn学校页面。 有关详细信息，请参阅 [如何标识LinkedIn页](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

    ![LinkedIn搜索学校。](media/career-coach-school-search-updated.png)

5. 添加 **LinkedIn学校页面 URL**。 URL 必须是 *学校页面*，而不能是 *公司页面*，并且通常设置为 `https://www.linkedin.com/school/willow-university/`格式。

   ![LinkedIn学校页面示例。](media/career-coach-linkedin-page-url-updated.png)

6. 选择 **“提交**”。

7. 成功提交 **LinkedIn学校页面 URL** 后，设置页将更新以显示  **验证链接** 和  **验证链接过期**。 验证链接在 30 天后过期。

8. 复制 **验证链接** ，并与教育机构的LinkedIn学校页面超级管理员共享。

9. LinkedIn学校页面超级管理员将使用唯一的验证链接来 [验证LinkedIn学校页面](#verify-the-linkedin-school-page) ，并将其与职业教练关联。

10. 若要确认验证和设置已成功提交，请检查 [职业教练配置状态](#configuration-status) 是否标记为 **“已完成**”。

#### <a name="verify-the-linkedin-school-page"></a>验证LinkedIn学校页面

LinkedIn学校页面验证必须由教育机构的 [LinkedIn学校页面超级管理员](https://www.linkedin.com/help/linkedin/answer/a541981)完成。

可以通过登录LinkedIn并访问教育机构的LinkedIn学校页面来检查LinkedIn帐户的管理员角色。 如果你的帐户被分配了超级管理员角色，你将在LinkedIn页上看到教育机构名称旁边列出的 **超级管理员视图** 。 如果看不到 **超级管理员视图** 标记，则您不是学校页面的超级管理员。

1. Teams 管理员提交 **LinkedIn学校页面 URL** 后，页面将显示 **验证链接** 和 **验证链接过期**。 验证链接在 30 天后过期。

   ![LinkedIn职业教练应用的连接。](media/career-coach-linkedin-updated.png)  

2. 复制验证链接并将其与LinkedIn学校页面超级管理员共享。

3. LinkedIn页超级管理员将打开验证链接，将职业教练与学校的页面相关联。 有关详细信息，请参阅 [有关LinkedIn页面验证的其他文档](https://www.linkedin.com/help/linkedin/answer/102672)。

4. 验证完成后，Teams 管理员可以通过检查 [职业教练配置状态](#configuration-status) 是否标记为 **“已完成**”来查看设置是否已成功提交。

   ![LinkedIn开发人员门户中的页面验证LinkedIn。](media/career-coach-linkedin-verification-updated.png)

### <a name="course-catalog"></a>课程目录

课程目录记录你的教育机构提供的课程和课程。

职业教练使用课程目录数据从成绩单中识别学生的技能，并建议学习课程。

> [!IMPORTANT]
> 这是必需的部分。 没有课程目录就无法启用职业教练。

这些课程在职业教练中用于两个方面：

- 课程作为 [学习资源](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_grow_real_world_skills)的一部分返回。  

- 课程和课程元数据（如课程标题和说明）用于帮助学生在 [上传脚本](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_Set_up_your_profile)时识别技能。

若要创建课程目录，请汇总在教育机构教授的所有课程的列表，并使用 [课程目录文档格式和架构](#course-catalog-document-format-and-schema)将其作为 CSV 文件上传。

> [!TIP]
> 从 [示例课程目录文](https://aka.ms/career-coach/docs/it-admins/sample-catalog) 档开始，以确保正确设置格式。还可以参考 [课程目录文档格式和架构](#course-catalog-document-format-and-schema) 部分，了解有关必需和建议字段的详细信息。

#### <a name="add-the-course-catalog"></a>添加课程目录

1. 登录 Teams **[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **管理应用** >搜索 **职业教练** > **设置** > **课程目录**。

3. 选择 **“上传课程目录** >使用必需列（courseId、标题和 sourceLink）的 CSV 格式上传课程。
    1. 每行必须包含每个必需列的数据。
    1. *包括推荐的字段可通过返回更好的搜索结果和技能识别来改善学生的体验。*

4. 将显示上传课程目录部分的预览，供参考。

5. 准备就绪时选择 **“提交** ”。

6. 已 [上传文档的状态](#course-catalog-status) 显示在设置页中。

7. 若要确认已成功提交设置，请检查 [职业教练配置状态](#configuration-status) 是否标记为 **“已完成**”。

> [!TIP]
> 若要上传新文件，请选择 (X) 关闭文档预览，确保清除最后一个文件。 此操作将允许再次显示 **“上传** ”按钮。

![职业教练应用的课程目录部分。](media/course-catalog-updated.png)

#### <a name="course-catalog-document-format-and-schema"></a>课程目录文档格式和架构

文档需要采用最大大小为 18 MB 的 CSV 格式。 大型文件应拆分为多个较小的文件，其中最多包含 15，000 行，以便成功处理。

文档必须包含必需的课程元数据： **课程标题**、 **课程 ID** 和  **课程 URL**。

> [!TIP]
> 从 [示例课程目录文]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) 档开始，以确保正确设置格式。 *包括推荐的字段可通过返回更好的搜索结果和技能识别来改善学生的体验。*

下表显示了要包含在课程目录中的项：

| 名称             | 地位      | 类型   | 说明                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | 必需    | 字符串 | courseId 映射到学生成绩单中生成的内容。             |
| 标题            | 必需    | 字符串 | 课程标题。                                                              |
| sourceLink       | 必需    | URL    | 指向课程页面的网站链接，了解有关课程和教学大纲的详细信息。   |
| 描述      | 推荐 | 字符串 | 介绍学习目标的课程简介文本。       |
| 语言         | 推荐 | 字符串 | 课程语言。 使用标准语言代码。                           |
| 格式           | 推荐 | 字符串 | 教学模式 (在线，视频，亲自) 。                                   |
| thumbnailLink    | 推荐 | URL    | 指向课程图像的缩略图链接。                                            |
| thumbnailAltText | 推荐 | 字符串 | 图像的辅助功能替换文字                                           |
| educationLevel   | 推荐 | 字符串 | 学习级别，前。 本科/研究生。                                       |
| 主题           | 推荐 | 字符串 | 与课程所教授的技能相关联的主题或标记。          |

### <a name="course-catalog-status"></a>课程目录状态

上传文档后，课程目录状态将显示在“课程目录设置”页上，提供文档上传和处理状态的详细信息。

在处理过程中，职业教练将分析文档中的重复项，通过从标题和说明中提取技能来规范化和丰富目录，并将其存储在“学习”页面和学生脚本上传期间用于技能识别。

![职业教练应用的课程目录上传状态。](media/career-coach-course-catalog-status-updated.png)

| 列           | 值     | 说明                                                                                        |
| ---------------- | --------- | -------------------------------------------------------------------------------------------------- |
| 上传的时间    | 时间 戳 | IT 管理员上传文档的日期和时间。                                                     |
| 已完成的时间   | 时间 戳 | 完全处理文档的日期和时间。                                               |
| 上传的课程 | 整型   | 在文档中找到的课程数。                                                           |
| 引入状态 | Pending   | 要处理的队列中的文档。                                                                  |
| 引入状态 | 运行   | 文档当前正在处理中。 此过程最多可能需要 6 小时，具体取决于文档的大小。 |
| 引入状态 | 成功   | 引入过程已完成，在配置所有必需设置后，课程将在职业教练中提供。 |
| 引入状态 | 失败    | 检查文档格式并重新加载。                                                           |
| 重复       | 整型   | 文档中找到的重复课程数。                                                 |

> [!NOTE]
> 如果课程目录状态中的列为空，则当前正在处理文档，并且这些值不可用。 此过程最多可能需要 6 小时，具体取决于目录的大小。 处理文档后，将填充值。 可以刷新页面以检查更新。

### <a name="fields-of-study"></a>研究领域

研究领域是关注的主要领域、学术专业和学位课程的同义词。 当学生开始使用职业教练并开始设置个性化的个人资料时，这些学习领域会被他们引用。

通过字段列表，学生可以发现可能令他们感兴趣的研究领域，并将计划内的学术焦点添加到他们在职业教练中的形象。

> [!IMPORTANT]
> 这是必需的部分。 没有学习领域列表，就无法启用职业教练。
>
> 向学生添加所有可用的学习领域，如工程学、英语、商业学等

#### <a name="add-the-fields-of-study"></a>添加研究字段

1. 登录到 **[Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **管理应用** >搜索 **职业教练** > **设置** >  **学习字段**。

3. 选择 **“上传** ”以 CSV 格式上传研究文件的字段。 将显示研究文档字段的预览。

4. 选择 **“提交**”。

5. 若要确认已成功提交设置，请检查 [职业教练配置状态](#configuration-status) 是否标记为 **“已完成**”。

#### <a name="fields-of-study-document-format-and-schema"></a>研究文档格式和架构的字段

文档需要采用最大大小为 18 MB 的 CSV 格式。 文档必须包含所需的元数据： **学习名称字段**。

下表显示了要包含在研究字段中的项：

| 名称          | 地位   | 类型   | 说明                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | 必需 | 字符串 | 研究领域的名称 |

### <a name="customization"></a>定制

自定义设置支持为教育机构为学生提供的仪表板添加获取真实体验的机会。

建议包含的链接是帮助学生获得真实体验的链接，例如工作板、活动、职业服务办公室、职业相关活动和学生俱乐部。

1. 登录 Teams **[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **管理应用** >搜索 **职业教练** > **设置**。

3. 选择 **“自定义体验****+ 添加**” > 

4. 在“选择 **应用**”>添加每个 **标题**、**URL** 和 **信息提示说明**。

5. 将显示已添加信息的预览。

6. 选择 **“提交**”。

## <a name="career-coach-settings-status"></a>职业教练设置状态

Teams 管理中心的“职业教练设置”页提供了配置职业教练的不完整、挂起、完成和失败的步骤的状态摘要。

状态消息可帮助你确定职业教练是否已正确配置并准备好发布到租户。

### <a name="configuration-status"></a>配置状态

应用设置页的配置状态部分将使用以下图例显示实时状态。

![职业教练应用的配置状态部分。](media/career-coach-config-status-updated.png)

| 类别                    | 地位                                        | 说明                                                 |
| --------------------------- | --------------------------------------------- | ----------------------------------------------------------- |
| 服务预配状态 | 职业教练正在初始化你的租户。     | 访问“职业教练设置”页时会自动进行服务预配。 在初始设置完成之前，不会接受配置更改。 服务预配的估计时间最长为 15 分钟。 |
| 服务预配状态 | 职业教练已经准备好配置了。       | 职业教练设置页面已准备好让 IT 管理员提交设置。 |
| 品牌和首选项       | 未启动                                   | 需要提交设置。 |
| 品牌和首选项       | 缺失：学习图标                        | 上传缺少的学习内容缩略图。 |
| 品牌和首选项       | 缺少：徽标                                 | 上传缺少的组织图标。 |
| 品牌和首选项       | 缺少：机构名称                     | 上传缺少的组织名称。 |
| 品牌和首选项       | 完成                                      | 无需采取进一步操作。 设置已完成。 |
| 课程目录上传       | 未启动                                   | 需要提交课程目录 CSV。 |
| 课程目录上传       | 缺少：成功上传课程目录   | 有关课程目录处理的详细信息，请查看课程目录状态。 |
| 课程目录上传       | 完成                                      | 无需采取进一步操作。 设置已完成。 |
| LinkedIn学校连接  | 未启动                                   | LinkedIn需要提交学校页面 URL。 |
| LinkedIn学校连接  | 缺少：已批准的LinkedIn学校页面 URL | 等待LinkedIn学校页面超级管理员验证批准。 |
| LinkedIn学校连接  | 完成                                      | 无需采取进一步操作。 设置已完成。 |
| 研究上传领域      | 未启动                                   | 需要提交研究领域 CSV。 |
| 研究上传领域      | 缺少：感兴趣的领域                    | 检查研究上传领域是否成功。 |
| 研究上传领域      | 完成                                      | 无需采取进一步操作。 设置已完成。 |

> [!NOTE]
> 将所有必需步骤标记为完成后，职业教练即可成功发布到租户。

## <a name="making-career-coach-available-to-your-organization"></a>使职业教练可供组织使用

此时，已为组织配置了职业教练。

接下来，请执行以下步骤，确保职业教练在 Microsoft Teams 中可供组织使用。

### <a name="assign-career-coach-licenses-to-users"></a>向用户分配职业教练许可证

有关分步说明，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="setup-policies-and-pin-the-app"></a>设置策略并固定应用

固定职业教练会将其添加到 Microsoft Teams 窗口的左侧栏杆中，使其更易于访问且对学生可见。 如果希望为部分用户固定职业教练，则需要实施包含该组的 [安装策略](teams-app-setup-policies.md) 。

1. 登录 Teams **[管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)**。

2. 选择 **Teams 应用** > **设置策略** 并选择首选策略。

    如果不确定要使用哪个策略，请参阅 [Microsoft Teams 策略管理文档](policy-packages-edu.md) 或使用 [教育策略向导](easy-policy-setup-edu.md) 为 Microsoft Teams 配置策略。

3. 在 **固定应用** 下，选择 **“添加应用**”。

4. **根据此应用权限策略选择“搜索”** 下的首选策略。

5. **在“按名称搜索**”下搜索 **职业教练**，然后选择  **“添加** > ”以关闭窗格。

6. 选择要显示的应用的顺序，然后选择 **“确认**”。

> [!NOTE]
> 在 Microsoft Teams 中，学生将收到职业教练已固定的通知。

## <a name="accessibility-in-career-coach"></a>职业教练中的辅助功能

职业教练有责任创建可供所有用户访问的体验。 职业教练符合 WCAG 2.1 A、AA 和 AAA，并采用所有全局辅助功能标准。

职业教练辅助功能包括：

- 一个逻辑标题结构和清晰的焦点指示器，用于支持鼠标、键盘或语音的导航。
- 跳过链接以使用户能够更快地访问重要功能。
- 清晰简洁的文本，使阅读和理解职业教练对所有用户都简单易懂。
- 颜色对比度与深色和高对比度模式，满足不同的需求和偏好。
- 使用 [第 508 部分受信任的测试人员](https://www.dhs.gov/trusted-tester) (电脑、Mac、Android 和 iPhone) 的所有格式验证的适当大小的用户体验。

## <a name="troubleshooting"></a>疑难解答

### <a name="missing-required-configuration-data"></a>缺少所需的配置数据

如果在职业教练体验中看到“职业教练当前正在设置以供你很快使用”， **则尚未添加所有必需的配置数据**。

在使用职业教练之前 **，必须完成以下部分** ：

- [品牌和首选项](#brand-and-preferences)
- [LinkedIn连接](#linkedin-connection)
- [课程目录](#course-catalog)
- [研究领域](#fields-of-study)

参考 [职业教练配置状态](#configuration-status) ，查看需要完成哪些设置。

### <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>课程目录或研究数据字段格式不正确

课程目录和研究领域的 CSV 具有必需格式，最大大小为 18 MB。

参考学习文档架构的职业教练 [课程目录文档架构](#course-catalog-document-format-and-schema) 和职业教练 [字段](#fields-of-study-document-format-and-schema) ，以确保正确配置。

此外，课程目录文件应不超过 15，000 行，以确保成功处理。

### <a name="missing-fields-in-career-coach-settings-pages"></a>职业教练设置页中缺少字段

职业教练设置页面具有必需字段。 如果必要字段未完成，页面将不会提交。

可能看不到警告消息;页面不会提交。

当你在页面顶部看到绿色横幅时，提交会成功。

### <a name="setup-policy-changes-arent-complete"></a>安装策略更改未完成

如果职业教练未在 Microsoft Teams 中为用户显示，则设置策略更改可能尚未生效。 在设置策略更改生效之前，不会为 Microsoft Teams 中的用户安装和固定职业教练。 策略更改可能需要几个小时才能生效。

但是，职业教练可以直接从 Microsoft Teams 应用商店安装。

- 如果用户在 Microsoft Teams 应用商店中找不到职业教练，请查看应用权限策略，并确保职业教练不是受阻止的应用。
- 职业教练是 Microsoft 应用，最佳做法是按权限策略允许 Microsoft 应用。 详细了解如何 [配置权限策略](teams-app-permission-policies.md)。

### <a name="career-coach-initialization-isnt-complete"></a>职业教练初始化未完成

你可能会遇到以下错误：“无法检索应用的设置。 再试一次。 如果仍遇到问题，请联系 Microsoft 客户支持人员。

在“职业教练设置”页上检查 **服务预配状态** 。

如果租户仍在初始化，请等待 15 分钟，然后重试。 如果仍收到错误，请打开支持票证。

## <a name="resources"></a>资源

以下资源将帮助你使用 Microsoft Teams 规划职业教练实现。

- [职业教练快速规划指南](https://support.microsoft.com/topic/career-coach-quick-planning-guide-c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)
- [面向学生的职业教练快速入门指南](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708)
- [让学生参与职业教练课程计划](https://support.microsoft.com/topic/get-started-with-career-coach-goals-and-activities-086ce412-05de-4259-a9fd-c96471cef1b0?preview=true)
- [欢迎使用 Microsoft Teams](Teams-overview.md)
- [如何部署 Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)
- [Microsoft Teams 中的团队和频道概述](teams-channels-overview.md)
- [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
- [Microsoft Teams 管理员培训入门](ITAdmin-readiness.md)
- [Teams 疑难解答](/microsoftteams/troubleshoot/teams-welcome)
- [在 Microsoft Teams 中管理应用权限策略](teams-app-permission-policies.md)
