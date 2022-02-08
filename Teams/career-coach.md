---
title: 购买、配置和启用职业指导配置Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何为用户购买、配置和职业指导Microsoft Teams。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f2698f668f33f078988b4c9ff1967a07c6765d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389764"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>购买、配置和启用职业指导配置Microsoft Teams

职业指导是一Microsoft Teams 教育版由 LinkedIn 支持的应用，它为更高层次的学生提供个性化指导，帮助其导航其职业之旅。 职业指导为教育机构提供统一的职业发展解决方案，使学生能够发现其职业路径、发展实际技能，并全部在一个地方构建其网络。

## <a name="supported-languages"></a>支持的语言

职业指导以下语言本地化：

- 中文 (简体中文，中国大陆) 
- 繁 (繁体中文、台湾) 
- 英语 (US)
- 英语 (UK)
- 加拿大 (法语) 
- 法语 (法国) 
- 德国 (德语) 
- 日语 (日本) 
- 巴西 (葡萄牙语) 
- 西班牙语 (西班牙) 
- 西班牙语 (墨西哥) 

详细了解[职业指导。](https://aka.ms/career-coach)

> [!TIP]
> 使用本指南中的最佳实践和有用提示，为学生职业指导和教职员工启用协作功能。 请参阅 [快速规划指南](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) 一文。

## <a name="review-the-requirements"></a>查看要求

若要职业指导机构启用应用，请查看启动并运行应用所需的内容。

**技术要求**

- Office 365租户Azure Active Directory。

- Microsoft Teams。

- Azure Active Directory 中的 LinkedIn 帐户Azure Active Directory。

**许可证**

- 教职员工

- 学生

> [!IMPORTANT]
> 必须将职业指导许可证分配给完成配置的 IT 管理员。

**来自教育机构的数据和文件**

- 教育机构徽标和所需格式的图形资产。

- 课程目录数据。

- 提供的研究领域列表。

- 教育机构的 [LinkedIn 页面](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

- 教育机构的隐私策略 URL。

- 教育机构链接到职业相关资源，例如职业服务和学生作业 (可选) 。

- LinkedIn Learning学校订阅 (首选) 。

## <a name="purchase-the-career-coach-licenses"></a>购买职业指导许可证

职业指导 通过教育版解决方案注册)  (EES) 、云服务提供商 (CSP) 和 Microsoft 365 管理中心 (Web direct) 在全球 (（中国和俄罗斯除外）提供，适用于符合条件的教育机构作为附加许可证。 作为Microsoft Teams应用，租户必须具有 Microsoft 365 A3/A5 或 Office 365 A1/A3/A5 才能购买附加职业指导许可证。 为学生和教职员工用户提供单独的许可证。

标准 90 天免费试用版适用于 25 名学生和 25 名教职员工许可证。 有资格购买试用版许可证Microsoft 365 管理中心租户从 职业指导。

### <a name="assign-app-licenses-to-users"></a>向用户分配应用许可证

有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="turn-on-linkedin-account-connections"></a>打开 LinkedIn 帐户连接

职业指导 **要求教育机构** 的用户能够将其 Microsoft 365 帐户连接到其 LinkedIn 帐户，职业指导。

1. 使用 Azure AD 组织的全局[](https://aad.portal.azure.com/)管理员帐户登录到 Azure AD 管理中心。

2. 选择" **用户"**。

3. 在" **用户"** 页上，选择" **用户设置"**。

4. **LinkedIn 帐户连接** 必须设置为"是"或"已选择"**组职业指导正确** 配置。

   ![在组织中集成 LinkedIn 帐户连接](/azure/active-directory/enterprise-users/media/linkedin-integration/linkedin-integration.png)

   > [!NOTE]
   > 在用户同意连接其帐户之前，不会共享任何数据。

   - 选择 **"** 是"，为教育机构中的所有用户启用该服务。

   - 选择 **"所选** 组"，仅为教育机构中的一组选定用户启用该服务。

有关详细信息，请参阅 Azure Active Directory 中的 [LinkedIn 帐户Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)。

## <a name="access-the-career-coach-app-settings"></a>访问职业指导应用设置

使用Microsoft Teams管理中心职业指导为教育机构配置应用，并让用户启用它。

> [!IMPORTANT]
> 必须是全局管理员或Teams管理员才能访问页面。

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

2. 在左侧导航栏中，选择"**Teams管理** > **[应用"](https://admin.teams.microsoft.com/policies/manage-apps)**。  

3. 搜索 **或浏览职业指导**。  

4. 选择 **职业指导**，然后选择"设置 **"**。  

    ![显示选中职业指导应用，设置选项。](media/career-coach-app.png)

## <a name="configure-the-career-coach-app-settings"></a>配置 职业指导 应用设置

职业指导有五个配置类别：

- [品牌和首选项](#brand-and-preferences) - 必需

- [LinkedIn 连接](#linkedin-connection) - 必需

- [课程目录](#course-catalog) - 必需

- [研究领域](#fields-of-study) - 必需

- [自定义](#customization)

> [!IMPORTANT]
> 品牌和首选项、LinkedIn 配置、课程目录和研究领域是必需的，才能有效地为学生和教职员工启用该应用。

### <a name="brand-and-preferences"></a>品牌和首选项

自定义职业指导，以匹配教育机构的品牌。 您有责任尊重其他人的权利，包括版权和商标权利。

> [!IMPORTANT]
> 这是必填部分 - 职业指导提交品牌和首选项的情况下无法启用。

![管理职业指导的"品牌"部分。](media/career-coach-brand.png)

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

2. 选择 **Teams管理** > **[应用职业指导](https://admin.teams.microsoft.com/policies/manage-apps)** >  > **品牌和首选项**。

3. Upload **教育机构图标**。 图标用于整个职业指导标识您的教育机构独有的内容、整个应用中的课程目录资源，以及仪表板的实际体验部分。 图标的格式最好为：

    - 透明 PNG
    - 纵横比为 1：1
    - 最大大小为 64 px x 64 px

4. Upload **教育机构缩略图**。 当特定图像不可用于课程时，缩略图将用于整个应用中的课程目录资源。 缩略图的格式最好为：

    - A PNG
    - 纵横比为 16：9
    - 最大大小为 360 px x 200 px

5. 添加 **教育机构的隐私策略 URL**。 如果已添加，则学校的隐私策略可供学生在应用职业指导审阅。

6. 选择" **提交"**。

### <a name="linkedin-connection"></a>LinkedIn 连接

LinkedIn 配置将 职业指导与来自 LinkedIn 的公共毕业生数据连接。

> [!IMPORTANT]
> 这是必填职业指导 - 在未验证 LinkedIn 页面连接的情况下无法启用。

#### <a name="add-the-linkedin-page"></a>添加 LinkedIn 页面
  
1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

2. 选择 **Teams管理** > **[应用](https://admin.teams.microsoft.com/policies/manage-apps)** > **职业指导** > **LinkedIn 连接**。

3. 通过搜索 LinkedIn 并选择"学校"筛选器来查找 LinkedIn **页面。** 或者与职业服务员工联系，以确定要使用正确的 LinkedIn 学校页面。 有关详细信息，请参阅 [如何识别 LinkedIn 页面](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

    ![linkedin 搜索学校。](media/career-coach-school-search.png)

4. 添加 LinkedIn 学校页面 URL。 URL 必须是学校页面，而不是公司页面，并且通常格式为 `https://www.linkedin.com/school/willow-university/`。

   ![linkedin 学校页面示例。](media/career-coach-linkedin-page-url.png)

5. 选择" **提交"**。
#### <a name="verify-the-linkedin-page"></a>验证 LinkedIn 页面 

> [!IMPORTANT]
> 验证必须由教育机构的 LinkedIn 页面超级管理员完成。

1. 如果成功提交，页面将更新以显示"验证 **"链接和** " **验证"链接过期**。 验证链接在 30 天后过期。

   ![职业指导应用的链接连接。](media/career-coach-linked-in.png)  

2. 复制验证链接，并与教育机构的 LinkedIn 页面超级管理员共享。在 LinkedIn 页面管理员文档中详细了解 [LinkedIn 页面超级管理员角色](https://www.linkedin.com/help/linkedin/answer/102672)。

3. LinkedIn 页面超级管理员将使用唯一验证链接将职业指导学校页面关联。 有关详细信息 [，请参阅有关 LinkedIn 页面验证](https://www.linkedin.com/help/linkedin/answer/102672) 的其他文档。

   ![linkedin 开发人员门户中的 linkedin 页面验证。](media/career-coach-linkedin-verification.png)

### <a name="course-catalog"></a>课程目录

课程目录表示教育机构为学生提供的课程和课程。

> [!IMPORTANT]
> 这是必填部分 - 职业指导目录无法启用。

这些课程在应用内用于两个方面：

- 课程作为学习资源的一部分返回。  

- 课程和课程元数据（如说明）用于帮助学生在上传脚本时识别其技能。  

若要创建课程目录，请汇集在教育机构中教授的所有课程的列表，并将其上传为 CSV 文件。 该应用从课程目录中进行绘制，以识别学生的脚本技能，并建议要参加的课程。

#### <a name="add-the-course-catalog"></a>添加课程目录

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

1. 在 **Teams目录中** &gt; **[选择"管理职业指导](https://admin.teams.microsoft.com/policies/manage-apps)** &gt; **设置** &gt;  &gt;**应用"**。  

2. Upload包含所需列的 CSV 格式课程：courseId、title 和 sourceLink。 每行必须包含每个所需列的数据。 _包含建议的字段可返回更好的搜索结果和技能标识，从而改善学生的体验。_

4. 选择" **提交"**。

   ![职业指导应用的课程目录部分。](media/course-catalog.png)

#### <a name="course-catalog-document-format-and-schema"></a>课程目录文档格式和架构

文档需要采用 CSV 格式，最大大小为 18 MB。 文档必须包含必填字段 **课程标题**、 **课程 ID** 和 **课程 URL**。 

> [!TIP]
> 从示例 [课程目录文档]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) 开始，确保设置正确的格式。 _包含建议的字段可返回更好的搜索结果和技能标识，从而改善学生的体验。_

下表显示了要包括在课程目录中的项目：

| 名称             | 状态      | 类型   | 说明                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | 必需    | string | 课程 ID 通常 (映射到脚本脚本中生成的内容) 。 |
| title            | 必需    | string | 通常是课程标题。                                                      |
| sourceLink       | 必需    | URL    | 课程页面的网站链接。                                               |
| description      | 推荐 | string | 课程简介文本。                                              |
| 语言         | 推荐 | string | 课程的语言。 使用标准语言代码。                           |
| format           | 推荐 | string | 在线、 (在线、视频、个人或个人) 。                                   |
| thumbnailLink    | 推荐 | URL    | 指向课程图像的缩略图链接。                                            |
| thumbnailAltText | 推荐 | string | 图像的辅助功能替换文字                                           |
| educationLevel   | 推荐 | string | 学习级别，例如 公司/毕业生。                                       |
| 主题           | 推荐 | string | 与课程所教技能相关的主题或标记。          |

### <a name="fields-of-study"></a>研究领域

研究领域与感兴趣的主要领域、学术专业和程度同义。 这些游戏在学生开始使用应用并开始设置其个性化个人资料时被学生引用。

> [!IMPORTANT]
> 这是必填职业指导 - 如果没有研究领域列表，无法启用此部分。

#### <a name="add-the-fields-of-study"></a>添加研究领域

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。
1. 选择 **Teams"管理** &gt; **[应用"职业指导](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  &gt; **设置**&gt;**"研究领域"**。  

2. Upload CSV 格式的研究领域。

3. 选择" **提交"**。

#### <a name="fields-of-study-document-format-and-schema"></a>研究领域文档格式和架构

添加学生可用的所有研究领域，如工程、英语、商业等。 字段列表允许学生发现可能感兴趣的研究领域，并将其添加到其个人资料中。

> [!TIP]
> 从研究领域 [示例文档开始](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) ，确保设置正确的格式。

下表显示了要包括在研究领域中的项目：

| 名称          | 状态   | 类型   | 说明                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | 必需 | string | 研究领域的名称 |

### <a name="customization"></a>自定义

职业指导自定义为对教育机构是唯一的。 自定义支持将体验添加到仪表板。 建议添加指向职位委员会、活动、职业服务办公室、职业相关活动、学生俱乐部和任何其他可帮助学生获得实际经验的资源的链接。

#### <a name="add-customized-experiences"></a>添加自定义体验

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

1. 选择 **Teams应用管理** &gt; **[应用职业指导](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  > **设置** &gt; **自定义"**。

2. 添加每个标题、URL 和简短说明。  
  
3. 选择" **提交"**。

## <a name="making-career-coach-available-to-your-organization"></a>使职业指导可供组织使用

现在职业指导为组织配置了该配置。 请按照以下步骤操作，确保职业指导组织可以使用Microsoft Teams。

### <a name="enable-the-app"></a>启用应用

完成配置后，为学生和许可用户启用应用，以便他们有权访问职业指导。  
  
> [!IMPORTANT]
> 必须具有全局或Teams管理员角色权限。

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

1. 选择 **Teams应用管理** &gt; **[应用职业指导](https://admin.teams.microsoft.com/policies/manage-apps)** &gt; **。**

2. 将"状态"切换开关移动到" **允许"**。  

   > [!NOTE]
   > **允许** 意味着该应用可供教育机构中的用户使用。 被阻止意味着该应用对学生不可用。

### <a name="add-career-coach-as-an-installed-app"></a>将职业指导添加为已安装的应用

> [!IMPORTANT]
> 此步骤可确保职业指导正确配置你的组织，并确保学生职业指导。

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

2. 选择 **Teams设置** &gt; **策略"**，然后选择首选策略。
如果不确定要使用哪个策略，可以参考 Microsoft Teams [策略管理](/microsoftteams/policy-packages-edu)文档，或利用教育策略向导为策略配置Microsoft Teams。[](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings)

3. 在"已安装的应用"下，选择 **"添加应用"**。

4. 在"添加已安装的应用"窗格中，搜索希望用户在启动应用时自动安装Teams。 还可以按应用权限策略筛选应用。 选择应用列表后，选择"添加 **"**。

5. 选择“**保存**”。

> [!NOTE]
> 编辑或分配策略可能需要几个小时，更改才能生效。 在职业指导完成之前，Microsoft Teams应用在应用中不可用。

### <a name="pin-the-app"></a>固定应用

固定职业指导会使应用更易于访问，并且对学生可见。

1. 登录到 Teams **[管理中心](https://admin.teams.microsoft.com)**。

2. 选择 **Teams设置** &gt; **策略"**，然后选择首选策略。
如果不确定要使用哪个策略，可以参考 Microsoft Teams [策略管理](/microsoftteams/policy-packages-edu)文档，或利用教育策略向导为策略配置Microsoft Teams。[](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings)

3. 在 **"固定的应用"下**，选择" **添加应用"**。

4. 搜索"**职业指导**"，然后选择"添加 **"**。

5. 选择显示应用的顺序，然后选择"保存 **"**。

> [!NOTE]
> 学生将收到已Microsoft Teams职业指导通知。

有关 [更多详细信息，请参阅在 Microsoft 中](/microsoftteams/teams-app-setup-policies) 管理应用设置策略。

## <a name="career-coach-settings-status"></a>职业指导设置状态

管理职业指导中心中的Teams设置"页提供状态报告，其中显示配置应用的不完整、挂起、完成和失败步骤。 这些状态可帮助你确定是否职业指导配置正确并且已准备好释放到租户。

### <a name="configuration-status"></a>配置状态

应用设置页面的配置状态部分将显示当前状态。

![职业指导应用的配置状态部分。](media/career-coach-config-status.png)

| 类别              | 状态                    | 说明                                                 |
| --------------------- | ------------------------- | ----------------------------------------------------------- |
| 服务预配  | Pending                   | 正在将应用添加到租户。 无需进一步的操作。 |
| 服务预配  | 完成                  | 准备让 IT 管理员提交设置。                      |
| 品牌和首选项 | 未启动               | 设置提交。                              |
| 品牌和首选项 | 缺少 _必填字段_ | IT 管理员需要添加或上传缺少的字段。         |
| 品牌和首选项 | 完成                  | 无需进一步的操作。                                   |
| 课程目录        | 未启动               | 需要提交目录。                              |
| 课程目录        | 不完整                | 查看"输入状态"，详细了解如何解决此问题。   |
| 课程目录        | 完成                  | 无需进一步的操作。                                   |
| LinkedIn 连接   | 未启动               | 需要提交 LinkedIn 学校页面 URL。             |
| LinkedIn 连接   | Pending                   | 正在等待 LinkedIn 学校页面管理员批准。               |
| LinkedIn 连接   | 完成                  | 无需进一步的操作。                                   |
| 研究领域       | 未启动               | 需要提交文档。                             |
| 研究领域       | 完成                  | 无需进一步的操作。                                   |

> [!NOTE]
> 所有步骤都标记为完成后，应用可以成功释放到租户，并职业指导许可证。 有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)。

### <a name="course-catalog-status"></a>课程目录状态

上传文档后，课程目录状态会显示在"课程目录设置"页面上，提供文档上传和处理的详细信息。


![职业指导应用的课程目录上传状态。](media/career-coach-course-catalog-status.png)

| 列           | 值     | 说明                                                                                        |
| ---------------- | --------- | -------------------------------------------------------------------------------------------------- |
| 上传时间    | 时间戳 | IT 管理员上传文档的日期和时间。                                                     |
| 完成时间   | 时间戳 | 文档完全处理的日期和时间。                                               |
| 上传的课程 | 整型   | 在文档中找到的课程数。                                                           |
| Ingestion status | Pending   | 队列中要处理的文档。                                                                  |
| Ingestion status | 正在运行   | 当前正在处理文档。 此过程最多可能需要 60 分钟。                        |
| Ingestion status | 成功   | 完全配置后，将完成 Ingestion 过程和课程，并可在应用中使用。 |
| Ingestion status | 失败    | 检查文档格式并重新加载。                                                            |
| 重复项       | 整型   | 在文档中找到的重复课程数。                                                 |

> [!NOTE]
> 如果列为空，则当前正在处理文档，并且这些值不可用。 处理文档后，将填充这些值。 可以刷新页面以检查更新。

## <a name="troubleshooting"></a>疑难解答

- 如果在 职业指导 应用中看到"职业指导当前正在设置，供你使用"，则所需部分 __尚未完成__。 以下 __部分需要完成__ 才能使用职业指导：品牌和首选项、[LinkedIn 连接](#linkedin-connection)、[](#brand-and-preferences)课程目录和 [研究领域](#fields-of-study)。 [](#course-catalog)

- 课程目录和研究领域的VS 具有所需的格式，最大大小为 18 MB。 参考职业指导[目录文档架构和](#course-catalog-document-format-and-schema)职业指导[领域文档架构](#fields-of-study-document-format-and-schema)以确保正确配置。

- 在包含必填字段的设置页面上，如果字段未完成，则页面不会提交。 你将不会看到警告消息;页面不会提交。

- 首次配置职业指导时，可能会显示一个错误横幅，指出"无法更新应用的设置。 请重试。" 这很可能是因为租户预配了 职业指导 应用，这最多可能需要 15 分钟。 如果发生这种情况，请等待 15 分钟，然后再次提交。

- 如果职业指导应用未显示在Microsoft Teams中，则策略更改可能尚未生效。 策略更改可能需要几个小时才能更新。 在职业指导完成之前，Microsoft Teams应用在应用中不可用。

## <a name="removing-your-tenant-data"></a>删除租户数据

租户数据包括作为应用程序配置的一部分上传或生成的信息。 若要删除租户职业指导数据，请让租户的全局管理员打开支持票证，请求永久删除该[](https://edusupport.microsoft.com/support?product_id=career_coach)租户的数据。 请注意，此过程是不可逆的。 删除数据完成后，职业指导 应用程序将恢复为所有用户预配置的非个性化状态，Teams 管理员需要再次设置应用程序才能继续使用该应用程序。

下面介绍了删除过程：

- 租户全局管理员必须提交支持票证，明确表明要永久删除租户数据的请求。 **无法限制删除的数据集或时间窗口**。

- 提交后，支持票证将在一周后解决，以满足合规性的最短保留策略。 在此期间，可以取消操作。

- 一周后，职业指导团队确保删除与租户相关的所有数据。 Microsoft 支持人员会监视票证，删除过程完成后（不超过 30 天）会 **通知你**。


## <a name="resources"></a>资源

以下资源将帮助你规划职业指导应用。

- [欢迎使用 Microsoft Teams](Teams-overview.md)

- [如何部署 Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Microsoft Teams 中的团队和频道概述](teams-channels-overview.md)

- [在管理中心Microsoft Teams应用](manage-apps.md)

- [联机虚拟方向工具包](https://www.microsoft.com/education/remote-learning/virtual-orientation)

- [通道的限制Teams规范](limits-specifications-teams.md)

- [适用于管理员的管理员培训Microsoft Teams](ITAdmin-readiness.md)

- [Teams 疑难解答](/microsoftteams/troubleshoot/teams-welcome)

- [在 Microsoft Teams 中管理应用权限策略](teams-app-permission-policies.md)
