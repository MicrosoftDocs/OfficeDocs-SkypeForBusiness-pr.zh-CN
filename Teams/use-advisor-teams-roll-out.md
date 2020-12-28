---
title: 使用 Advisor for Teams 帮助你推出 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: 使用 Advisor for Teams 帮助你计划和完成 Microsoft Teams 部署。
ms.openlocfilehash: e6c2fc2ee1eb08839817d3b8c1627582bb239bd8
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731130"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>使用 Advisor for Teams 帮助你推出 Microsoft Teams

Advisor for Teams 为你提供 Microsoft Teams 推出的分步指导。 它评估 Microsoft 365 组织环境，并确定成功推出 Teams 前可能需要更新或修改的最常见配置。 然后，Advisor for Teams 会创建一个部署团队（在 Teams 中），你要推出的每个工作负载都有对应的频道。部署团队中的每个工作负载都有一个综合 Planner 计划，其中包括每个工作负载的所有推出任务。  使用此 Planner 计划将任务分配给负责推出的每个阶段的人员 - 包括项目经理、Teams 服务管理员、支持人员以及你的采用和用户就绪性团队。 每个推出任务包含成功完成任务所需的所有指南和资源。

Advisor for Teams 是 [Teams管理中心](https://admin.teams.microsoft.com)的一部分。 至少必须有 Microsoft 365 商业基础版许可证，才能利用 Advisor for Teams 与 Forms 和 Planner 的集成。 若要开始使用 Teams 顾问，请在仪表板上的“**部署 Teams 工作负载**”小组件中单击“**启动**”按钮。 或者转到“**计划**” > “**Teams 顾问**”。

> [!IMPORTANT]
> Advisor for Teams 不适用于 Microsoft 365 政府版 - GCC High 或 DoD 部署。

有关 Teams 顾问体验的指导性概述，请查看 [Deploy & Configure Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) Microsoft Mechanics 视频。

## <a name="using-advisor-for-teams"></a>使用 Advisor for Teams

**必须要有 Teams、Forms 和 Planner 许可证才能使用 Teams 顾问。** 但是，要使用 Teams 顾问，不需要是 Teams 管理员 - 组织中的任何人都可使用它。 我们设置了特殊权限，使非管理员用户可以使用 Advisor for Teams，即使它位于团队管理中心，也是如此。 只有 Teams 管理员、Teams 服务管理员或全局管理员才能打开租户就绪性评估（这是因为特殊的非管理员角色无法访问位于评估底层的 Microsoft Graph API）。

> [!IMPORTANT]
> 如果 Teams 管理中心的“**计划**”下没有“**Teams 顾问**”，则意味着用户未获得 Teams 许可。

第一次使用 Teams 顾问时，它将在 Teams 中为你创建一个部署团队。 它为你选择的每个工作负载添加一个频道。

> [!IMPORTANT]
> 如果已创建部署团队，而另一个用户尝试创建该团队，他们将收到一条错误消息，告知他们联系支持团队。 这可防止 Teams 意外泄露关于现有团队及其成员的信息。 请让部署团队的所有者添加你，或与支持人员联系以获取帮助。

## <a name="available-advisor-for-teams-plans"></a>可用的 Teams 顾问计划

Advisor for Teams 当前提供以下计划：

1. 聊天、团队、频道和应用
    - 租户评估
    - Planner 计划，包括采用任务
    - Forms 用户调查
    - Teams 顾问机器人
1. 会话和会议
    - 租户评估
    - Planner 计划，包括采用任务
    - Forms 用户调查
    - Teams 顾问机器人
1. Skype for Business 升级
    - 租户评估
    - Planner 计划，包括采用任务
    - Forms 用户调查
    - Teams 顾问机器人
    - Skype for Business 升级计划专为当前正在使用 Skype for Business Online 或 Skype for business 本地环境的客户而设计，将帮助你摆脱升级旅程中的猜测。 通过利用经过验证的成功框架实施更改，无论是刚开始使用 Teams、已在 Skype for Business 中使用 Teams，还是已准备好升级，该计划都将指导你完成分步操作。 该计划还将连接到[联机指南和最佳实践](https://aka.ms/SkypeToTeams)、[可下载资产](https://aka.ms/UpgradeSuccessKit)、[实时 1：许多规划研讨会](https://aka.ms/UpgradeWorkshops)，以及支持成功的其他资源。

建议从“聊天、团队、频道和应用”计划开始。 该工作负载部署完成后，请返回到 Teams 顾问，然后选择“**添加频道**”以开始下一个工作负载。

## <a name="tenant-assessment"></a>租户评估

每个计划都包括租户就绪性评估，可用于在推出 Teams 前快速识别任何可能需要修正的环境问题。 评估包括先决条件和最佳做法。 每个评估测试都会显示绿色勾号或橙色警告三角形。

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>绿色勾号表示你的租户已通过特定测试。
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>橙色警告三角形表示我们建议你跟进，确定是否需要执行任何操作（例如，推荐使用 Microsoft 365 组过期策略，但不是必需的）。

> [!IMPORTANT]
> 拥有管理角色的用户启动 Teams 顾问后，所有评估都将在后台运行。 如果你进行某种更新或修正，这些内容可能在长达 24 小时内都不会反映到评估中。

下面各节将介绍每项评估，包括某一项是否是先决条件或最佳做法、每项评估检查所执行的操作和理由以及有关修正（如需要）的指导。

### <a name="assessment-tests-for-all-workloads"></a>针对所有工作负载的评估测试

|评估测试  |提供的信息  |
|---------|---------|
|已配置虚域     |是否为你的租户配置了非 @onmicrosoft.com 域（例如，@contoso.onmicrosoft.com）。 当然，你可以使用 @onmicrosoft.com 域，或者也可以配置虚域，由你选择。 有关详细信息，请阅读[将域添加到 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)。 |
|Teams 许可证     |这是先决条件；你 **必须具有** Teams 许可证才能推出 Teams。 此测试查询 Microsoft Graph 以了解你是否拥有 Teams 许可证（至少有一个许可证可供分配）。 有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。    |
|Exchange Online 许可证     |你是否有具有可用 Exchange Online 许可证的活动订阅 虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。 此测试查询 Microsoft Graph 以分析与租户关联的订阅并验证你是否有具有合格 Exchange Online 许可证的订阅（至少有一个可用的许可证可供分配）。 有关详细信息，请阅读 [Exchange 与 Teams 如何交互](exchange-teams-interact.md)。    |
|SharePoint Online 许可证     |你是否有具有可用 SharePoint Online 许可证的活动订阅。 建议采用基于每个用户的 SharePoint Online 许可证，以便提供 OneDrive for Business 在聊天中用于文件存储。 此测试查询 Microsoft Graph 以了解你是否拥有 SharePoint Online 许可证（至少有一个许可证可供分配）。 有关详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact)。    |
|已启用来宾访问     |是否已启用[来宾访问](guest-access.md)。 通过来宾访问可邀请外部用户加入你的团队。 请参阅“[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)”，了解在 Teams 中启用来宾访问的详细步骤；该检查表包含所需的 Azure AD 配置。 |
|已配置外部访问     |是否已启用[外部访问](manage-external-access.md)。 默认情况下会启用此项并采用开放式联合身份验证。 |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>有关聊天、团队、频道和应用的评估

除了[针对所有工作负载的评估测试](#assessment-tests-for-all-workloads)之外，还会针对聊天、团队、频道和应用工作负载运行以下额外评估：

|评估测试  |提供的信息  |
|---------|---------|
|已配置 Microsoft 365 组命名策略     |是否已为 Microsoft 365 组配置命名标准。 使用 Microsoft 365 组命名策略，组织可以对用户创建的团队应用一致的命名策略，并也能对其他组工作负载（包括 Outlook、SharePoint、Planner 和 Yammer）应用。 此测试通过 Microsoft Graph 查询 Azure AD，以检查是否有应用于 Microsoft 365 组的命名策略。 有关详细信息，请阅读[组命名策略](https://docs.microsoft.com/microsoft-365/admin/create-groups/groups-naming-policy)。    |
|已配置 Microsoft 365 组过期策略     |是否已为 Microsoft 365 组定义组过期策略。 这可让你的组织自动删除非活动状态的团队。 默认情况下处于禁用状态。 此测试通过 Microsoft Graph 查询 Azure AD，并报告是否已在默认值的基础上修改该值。 有关详细信息，请参阅 [Microsoft 365 组过期策略](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)。    |

### <a name="assessments-for-meetings-and-conferencing"></a>有关会话和会议的评估

除了[针对所有工作负载的评估测试](#assessment-tests-for-all-workloads)之外，还会针对会话和会议工作负载运行以下额外评估：

|评估测试  |提供的信息  |
|---------|---------|
|音频会议许可证    |你是否有具有音频会议许可证的活动订阅。 如果要部署音频会议网桥，那么这是先决条件。 此测试查询 Microsoft Graph 以了解你是否拥有音频会议许可证（至少有一个许可证可供分配）。有关详细信息，请阅读 [Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。    |
|Stream 许可证     |你是否有具有 Microsoft Stream 许可证的活动订阅。 如果你想要启用“会议录制”，那么这是先决条件。 此测试查询 Microsoft Graph 以了解你是否拥有 Microsoft Stream 许可证（至少有一个许可证可供分配）。 有关 Stream 及其启用方法的详细信息，请阅读 [Teams 云会议录制](cloud-recording.md)。

### <a name="assessments-for-skype-for-business-upgrade"></a>Skype for Business 升级评估

除了[针对所有工作负载的评估测试](#assessment-tests-for-all-workloads)，Skype for Business 升级还包括在会议和会议计划中使用的评估。

### <a name="advisor-for-teams-bot"></a>Teams 顾问机器人

Teams 顾问创建部署团队后，顾问机器人就会在“常规”频道中提供以下消息：

>**欢迎使用 Microsoft Teams 中的部署团队！**
>  
>此团队的目的是为你提供组织的 Teams 推出的分步指导，方法是为你提供所需的所有资源，并为项目团队提供协作空间。 使用 Advisor for Teams 创建的每个频道包括分步 Planner 计划和其他资源，例如可在整个推出过程中使用的 Forms 用户调查。 可随时返回并查看租户就绪性评估或使用 Teams 管理中心添加其他工作负载计划。
>
>**行动号召**
>
>- 如果你不熟悉 Teams 或 Planner，请查看我们的 [Teams 演练](https://teamsdemo.office.com/)并观看 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。
>- 转到 Teams 中的部署团队。 选择工作负载频道（例如，“聊天”、“团队”、“频道”和“应用”），选择“**Planner**”选项卡以开始使用。
>
>若要了解有关 Advisor for Teams 的详细信息，请参阅[使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。
>

> [!IMPORTANT]
> Advisor for Teams 机器人仅用于向部署团队发送欢迎消息。 不会收集额外的数据。

> [!IMPORTANT]
> 默认情况下会启用 Teams 顾问机器人。 如果你使用或计划使用 Teams 顾问，请不要将其禁用。

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Teams 顾问和 Microsoft 365 学习路径

[Microsoft 365 学习途径](https://docs.microsoft.com/office365/customlearning/)是一种按需学习解决方案，你可以自定义该解决方案来培训用户，并提高组织中 Teams 的使用率和采用率。 将学习途径与 Teams 顾问配合使用，让你的用户能够快速启动和运行，并推动采用。

学习途径为你提供了 SharePoint Online 网站模板，并让你能够轻松地为你的用户构建学习网站。 你可以自定义学习路径培训门户，以包含特定于用户需求的培训和支持内容。 使用 Microsoft 联机目录中的 Teams 播放列表并添加你自己的播放列表。

你可以在学习路径中构建学习网站，然后将其作为选项卡添加到 Teams 中的频道中，以便用户快速轻松地访问。

例如，将 Teams 顾问与学习途径结合使用，培训你的技术支持人员和支持者，然后让学习途径支持培训你的最终用户。 构建一个学习网站以帮助你的技术支持人员和支持者加入 Teams，然后将其作为选项卡添加到你正在推出的每个工作负载频道中。然后，你的技术支持人员和支持者可以在学习路径培训门户上创建一个包含链接和自定义播放列表的支持页面，从而为 Teams 上的用户提供支持。 此支持页面可以添加到任何团队的频道中，以帮助培训最终用户。

下面概述了如何将 Teams 顾问与学习途径一起使用。

### <a name="get-started-in-learning-pathways"></a>学习路径入门

若要开始使用学习途径，请查看[学习途径入门](https://docs.microsoft.com/office365/customlearning/)。

若要在你的环境中设置新的学习路径解决方案，请参阅[预配新的学习路径解决方案](https://docs.microsoft.com/office365/customlearning/custom_provision)。

### <a name="create-a-learning-plan"></a>创建学习计划

#### <a name="plan-your-learning-content"></a>规划学习内容

在通过学习途径构建网站之前，请花些时间来查看和收集可供你使用的学习资源和功能。 通过学习途径，你可以使用 Microsoft 365 培训页面中的内容，并添加你创建的内容，以根据你的独特需求定制网站。

若要了解详细信息，请参阅[规划学习路径内容](https://docs.microsoft.com/office365/customlearning/custom_plancontent)和[用于支持远程工作人员的资源](https://docs.microsoft.com/office365/customlearning/custom_plancontent_remoteresources)。

#### <a name="explore-teams-content-in-learning-pathways"></a>在学习路径中浏览 Teams 内容

学习途径为 SharePoint 网站提供了连接到联机目录的 Web 部件。 承载 Web 部件的 Microsoft 365 培训页面显示了学习途径中所有可用的培训。 四处看看，熟悉可用内容以及内容的组织方式。

[转到你的学习途径网站](https://docs.microsoft.com/office365/customlearning/custom_goto)，选择“**Microsoft 365 培训**”，然后选择“**Microsoft Teams**”，查看联机目录中的所有 Teams 培训播放列表。 选择一个播放列表，然后选择“**下一个**”和“**上一个**”按钮浏览它。 也可以单击向下箭头查看播放列表的内容并转到特定主题。

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>盘点你的组织中的 Teams 学习资源

查看你的组织中已提供的 Teams 学习内容。 例如，你可能已经为 Teams 开发了自定义加入、培训或支持内容。 可将你的现有 SharePoint 资产与播放列表中的 Microsoft 内容混合使用，以便为你的组织构建目标播放列表。

#### <a name="build-your-site-in-learning-pathways"></a>在学习途径中构建网站

学习途径中的[管理员成功中心](https://docs.microsoft.com/office365/customlearning/custom_successcenter)提供了指导和资源，可帮助你规划和自定义组织中的学习途径。 了解如何[自定义网站](https://docs.microsoft.com/office365/customlearning/custom_overview)、显示和隐藏内容、构建自定义播放列表等。

若要访问管理员成功中心，请在学习路径主页上，选择“**管理员成功中心**”。

#### <a name="add-your-site-to-teams"></a>将你的网站添加到 Teams

当你的网站准备就绪时，请将其添加到任何团队的频道，以便快速轻松地访问。

1. 在 Teams 中，转到该团队，然后选择一个频道。
2. 在频道页面顶部，选择 **+**(**添加选项卡**)。
3. 选择“**SharePoint 页面**”，然后选择“**从任何 SharePoint 网站添加页面**”。
4. 粘贴学习路径网站的 URL，然后选择“**保存**”。

若要了解详细信息，请参阅[将 SharePoint 页面或列表添加到 Teams 中的频道](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)。

### <a name="train-your-support-team"></a>培训你的支持团队

使用你的学习路径网站中的资源将你的技术支持人员和支持者加入 Teams。 让他们熟悉支持你的 Teams 用户所需的工具和信息。

有关为 Teams 准备技术支持人员和支持者的指导和资源，请参阅[培训你的组织](https://adoption.microsoft.com/microsoft-teams/#train-your-org)和[培养支持者](https://adoption.microsoft.com/microsoft-teams/#build-champions)。

作为你的用户“操作方法”问题的联系人，你的技术支持人员和支持者可以使用学习途径网站来培训用户以及作为创建支持服务票证的替代方法。 鼓励你的技术支持人员和支持者通过构建培训和支持页面来[自定义你的学习路径网站](https://docs.microsoft.com/office365/customlearning/)，然后[将其作为选项卡添加到团队中的频道](#add-your-site-to-teams)，以便用户自助服务。

### <a name="drive-adoption"></a>推动采纳

自定义你的网站并整理学习计划后，请考虑如何提高用户的认知，鼓励他们使用学习途径进行持续学习。

使用你的通信频道推广网站并提高认知。 例如，在与你的用户进行交流时，请加入标准标语，例如“查看我们的培训和支持网站，了解如何通过 Teams 提高工作效率”。

通过强调用户可以在 Teams 中协作的方式来吸引用户，然后引导他们进入学习路径网站以了解如何操作。

请查看这些资源，其中包括指导、采用工具包、最佳实践等，以帮助你实施成功的推广和采用计划。  

- [推动学习路径的采纳](https://docs.microsoft.com/office365/customlearning/driveadoption)
- [采用 Teams](adopt-microsoft-teams-landing-page.md)
- [Teams 的采用资源](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Teams 顾问 的许可要求是什么？

至少必须有 Microsoft 365 商业基础版，才能利用 Teams 顾问与 Forms 和 Planner 的集成。

### <a name="can-i-delete-the-deployment-team"></a>我是否可以删除部署团队

在 Advisor for Teams 创建部署团队后，可以像管理任何其他团队那样管理该团队，包括可以删除该团队。 请注意，如果不使用 Teams 管理中心删除该团队，Teams 管理中心将显示该团队仍然存在。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除频道

可以，创建部署团队后，你将按照管理任何其他团队的方式管理频道。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除项目团队成员

可以，创建部署团队后，你将按照管理任何其他团队的方式进行管理。

### <a name="can-i-modify-the-planner-plans"></a>能否修改 Planner 计划

可以，Advisor for Teams 创建部署团队后，你应更新 Planner 计划，使其可以为你的 Teams 推出提供最佳支持。 可以像任何其他 Planner 计划那样修改任何项 - 存储桶、任务和任务详细信息。

### <a name="can-i-modify-the-forms-survey"></a>能否修改 Forms 调查

可以，Advisor for Teams 创建部署团队后，可以按需修改 Forms 调查。

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>GCC 中的 Teams 顾问是否有任何差异

是的，用户调查 Forms 已创建，但未固定到计划频道中，因为 GCC 中当前未提供 Teams Forms 应用。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Teams 顾问会收集关于我的组织的什么信息

Advisor for Teams 请求你同意收集非 EUII（最终用户标识信息）。 收集的信息采用遥测的形式，用于向 Microsoft 提供有关 Advisor for Teams 在促进成功结果方面的作用以及需要改进之处的反馈。 此类数据用于帮助 Microsoft 识别与你的组织积极互动，从而为你的部署提供协助的机会。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>能否将 Teams 顾问与 FastTrack 配合使用

可以，针对希望部署 Teams 的所有客户，FastTrack 会利用 Advisor for Teams。 他们可以使用 Advisor for Teams（如果需要）协助部署团队进行初始设置，并在 Teams 推出期间根据需要就特定主题提供支持。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>能否在与合作伙伴协作的过程中使用 Teams 顾问

可以，在使用 Advisor for Teams 时，你也可以使用部署合作伙伴进行 Teams 部署。 如果你的合作伙伴是 CSP 并代表你管理租户，则他们可以使用 Advisor for Teams 来创建部署团队，并协助你执行整个项目。 此外，你还可以通过将各合作伙伴添加到你的部署团队来与他们一起工作，从而让他们作为整个项目团队的成员参与进来。

### <a name="how-do-i-use-planner"></a>如何使用 Planner

查看 [Microsoft Planner 帮助](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)和 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。

### <a name="how-do-i-use-forms"></a>如何使用 Forms

转到 [Forms 帮助中心](https://support.office.com/forms)。

## <a name="related-topics"></a>相关主题

[自定义 Teams 顾问](https://docs.microsoft.com/office365/customlearning/custom_teamsadvisor)

[如何部署 Teams](How-to-roll-out-teams.md)

[在 Teams 中组织团队的最佳做法](best-practices-organizing.md)

[用于许可的产品名称和服务计划标识符](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
