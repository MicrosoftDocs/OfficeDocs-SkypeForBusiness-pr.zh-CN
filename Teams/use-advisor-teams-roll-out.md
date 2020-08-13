---
title: 使用 Advisor for Teams 帮助你推出 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: 使用 Advisor for Teams 帮助你计划和完成 Microsoft Teams 部署。
ms.openlocfilehash: 72870eb94bc5bf19fce439c3607500eb688a291f
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648593"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>使用 Advisor for Teams 帮助你推出 Microsoft Teams

Advisor for Teams 为你提供 Microsoft Teams 推出的分步指导。 它评估 Microsoft 365 组织环境，并确定成功推出 Teams 前可能需要更新或修改的最常见配置。 然后，Advisor for Teams 会创建一个部署团队（在 Teams 中），你要推出的每个工作负载都有对应的频道。部署团队中的每个工作负载都有一个综合 Planner 计划，其中包括每个工作负载的所有推出任务。  使用此 Planner 计划将任务分配给负责推出的每个阶段的人员 - 包括项目经理、Teams 服务管理员、支持人员以及你的采用和用户就绪性团队。 每个推出任务包含成功完成任务所需的所有指南和资源。

Advisor for Teams 是 [Teams管理中心](https://admin.teams.microsoft.com)的一部分。 至少必须有 Microsoft 365 商业基础版许可证，才能利用 Advisor for Teams 与 Forms 和 Planner 的集成。 若要开始使用 Teams 顾问，请在仪表板上的“**部署 Teams 工作负载**”小组件中单击“**启动**”按钮。 或者转到“**计划**” > “**Teams 顾问**”。

> [!IMPORTANT]
> Advisor for Teams 不适用于 Microsoft 365 政府版 - GCC High 或 DoD 部署。

有关 Teams 顾问体验的指导性概述，请查看 [Deploy & Configure Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) Microsoft Mechanics 视频。

## <a name="using-advisor-for-teams"></a>使用 Advisor for Teams

**必须要有 Teams、Forms 和 Planner 许可证才能使用 Teams 顾问。** 但是，要使用 Teams 顾问，不需要是 Teams 管理员 - 组织中的任何人都可使用它。 我们设置了特殊权限，使非管理员用户可以使用 Advisor for Teams，即使它位于团队管理中心，也是如此。 只有 Teams 管理员、Teams 服务管理员或全局管理员才能打开租户就绪性评估（这是因为特殊的非管理员角色无法访问位于评估底层的 Microsoft Graph API）。 但是，要使用 Teams 顾问，不需要是 Teams 管理员 - 组织中的任何人都可使用它。 我们设置了特殊权限，使非管理员用户可以使用 Advisor for Teams，即使它位于团队管理中心，也是如此。 只有 Teams 管理员、Teams 服务管理员或全局管理员才能打开租户就绪性评估（这是因为特殊的非管理员角色无法访问位于评估底层的 Microsoft Graph API）。

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

建议从“聊天、团队、频道和应用”计划开始。 该工作负载部署完成后，请返回到 Teams 顾问，然后单击“**添加频道**”以开始下一个工作负载。

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
|Teams 许可证     |这是先决条件；你**必须具有** Teams 许可证才能推出 Teams。 此测试查询 Microsoft Graph 以了解你是否拥有 Teams 许可证（至少有一个许可证可供分配）。 有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。    |
|Exchange Online 许可证     |你是否有具有可用 Exchange Online 许可证的活动订阅 虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。 此测试查询 Microsoft Graph 以分析与租户关联的订阅并验证你是否有具有合格 Exchange Online 许可证的订阅（至少有一个可用的许可证可供分配）。 有关详细信息，请阅读 [Exchange 与 Teams 如何交互](exchange-teams-interact.md)。    |
|SharePoint Online 许可证     |你是否有具有可用 SharePoint Online 许可证的活动订阅。 建议采用基于每个用户的 SharePoint Online 许可证，以便提供 OneDrive for Business 在聊天中用于文件存储。 此测试查询 Microsoft Graph 以了解你是否拥有 SharePoint Online 许可证（至少有一个许可证可供分配）。 有关详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact)。    |
|已启用来宾访问     |是否已启用[来宾访问](guest-access.md)。 通过来宾访问可邀请外部用户加入你的团队。 请使用 [Teams 来宾访问清单](guest-access-checklist.md)了解在 Teams 中启用来宾访问的详细步骤；该清单包含所需的 Azure AD 配置。 |
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
|音频会议许可证    |你是否有具有音频会议许可证的活动订阅。 如果要部署音频会议网桥，那么这是先决条件。 此测试查询 Microsoft Graph 以了解你是否拥有音频会议许可证（至少有一个许可证可供分配）。有关详细信息，请阅读 [Teams 附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。    |
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
>- 如果你不熟悉 Teams 或 Planner，请查看我们的 [Teams 演练](https://teamsdemo.office.com/)并观看 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。 
>- 转到 Teams 中的部署团队。 选择工作负载频道（例如，“聊天”、“团队”、“频道”和“应用”），选择“**Planner**”选项卡以开始使用。
> 
>若要了解有关 Advisor for Teams 的详细信息，请参阅[使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。
>

> [!IMPORTANT]
> Advisor for Teams 机器人仅用于向部署团队发送欢迎消息。 不会收集额外的数据。

> [!IMPORTANT]
> 默认情况下会启用 Teams 顾问机器人。 如果你使用或计划使用 Teams 顾问，请不要将其禁用。

## <a name="frequently-asked-questions"></a>常见问题解答
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams 的许可要求是什么？
至少必须有 Microsoft 365 商业基础版，才能利用 Teams 顾问与 Forms 和 Planner 的集成。

### <a name="can-i-delete-the-deployment-team"></a>我是否可以删除部署团队？
在 Advisor for Teams 创建部署团队后，可以像管理任何其他团队那样管理该团队，包括可以删除该团队。 请注意，如果不使用 Teams 管理中心删除该团队，Teams 管理中心将显示该团队仍然存在。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除频道？
可以，创建部署团队后，你将按照管理任何其他团队的方式管理频道。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除项目团队成员？
可以，创建部署团队后，你将按照管理任何其他团队的方式进行管理。

### <a name="can-i-modify-the-planner-plans"></a>能否修改 Planner 计划？
可以，Advisor for Teams 创建部署团队后，你应更新 Planner 计划，使其可以为你的 Teams 推出提供最佳支持。 可以像任何其他 Planner 计划那样修改任何项 - 存储桶、任务和任务详细信息。

### <a name="can-i-modify-the-forms-survey"></a>能否修改 Forms 调查？
可以，Advisor for Teams 创建部署团队后，可以按需修改 Forms 调查。

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>GCC 中的 Advisor for Teams 是否有任何差异？
是的，用户调查 Forms 已创建，但未固定到计划频道中，因为 GCC 中当前未提供 Teams Forms 应用。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Advisor for Teams 会收集关于我的组织的什么信息？
Advisor for Teams 请求你同意收集非 EUII（最终用户标识信息）。 收集的信息采用遥测的形式，用于向 Microsoft 提供有关 Advisor for Teams 在促进成功结果方面的作用以及需要改进之处的反馈。 此类数据用于帮助 Microsoft 识别与你的组织积极互动，从而为你的部署提供协助的机会。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>能否将 Advisor for Teams 与 FastTrack 配合使用？
可以，针对希望部署 Teams 的所有客户，FastTrack 会利用 Advisor for Teams。 他们可以使用 Advisor for Teams（如果需要）协助部署团队进行初始设置，并在 Teams 推出期间根据需要就特定主题提供支持。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>能否在与合作伙伴协作的过程中使用 Advisor for Teams？
可以，在使用 Advisor for Teams 时，你也可以使用部署合作伙伴进行 Teams 部署。 如果你的合作伙伴是 CSP 并代表你管理租户，则他们可以使用 Advisor for Teams 来创建部署团队，并协助你执行整个项目。 此外，你还可以通过将各合作伙伴添加到你的部署团队来与他们一起工作，从而让他们作为整个项目团队的成员参与进来。

### <a name="how-do-i-use-planner"></a>如何使用 Planner？
查看 [Microsoft Planner 帮助](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)和 [Planner 快速入门视频](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。 

### <a name="how-do-i-use-forms"></a>如何使用 Forms？
转到 [Forms 帮助中心](https://support.office.com/forms)。

## <a name="related-topics"></a>相关主题

[如何部署 Teams](How-to-roll-out-teams.md)

[在 Teams 中组织团队的最佳做法](best-practices-organizing.md)

[用于许可的产品名称和服务计划标识符](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
