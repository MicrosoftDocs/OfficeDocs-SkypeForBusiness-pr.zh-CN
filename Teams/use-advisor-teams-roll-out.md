---
title: 使用 Advisor for Teams（预览版）帮助你推出 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: 使用 Advisor for Teams（预览版）帮助你计划和完成 Microsoft Teams 部署。
ms.openlocfilehash: f7de348c6f8ca60cc1d062fce79725b4b18d0350
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209188"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>使用 Advisor for Teams 帮助你推出 Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor for Teams（预览版）为你提供 Microsoft Teams 推出的分步指导。 它将评估 Office 365 租户环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。 然后，Advisor for Teams 会创建一个部署团队（在 Teams 中），你要推出的每个工作负载都有对应的频道。部署团队中的每个工作负载都有一个综合 Planner 计划，其中包括每个工作负载的所有推出任务。  使用此 Planner 计划将任务分配给负责推出的每个阶段的人员 - 包括项目经理、Teams 和 Office 365 管理员、支持人员以及你的采用和用户就绪性团队。 每个推出任务包含成功完成任务所需的所有指南和资源。

Advisor for Teams 是 [Teams管理中心](https://admin.teams.microsoft.com)的一部分。 若要首次使用 Advisor for Teams，请在仪表板上的“**部署 Teams 工作负载**”小组件中单击“**启动**”按钮。 或者转到“**计划**” > “**Advisor**”。

> [!IMPORTANT]
> Advisor for Teams 不适用于 Microsoft 365 政府版 - GCC High 或 DoD 部署。

## <a name="using-advisor-for-teams-preview"></a>使用 Advisor for Teams（预览版）

要使用 Advisor for Teams，不需要是 Teams 管理员 - 组织中的任何人都可使用它。 我们设置了特殊权限，使非管理员用户可以使用 Advisor for Teams，即使它位于团队管理中心，也是如此。 必须是 Teams 管理员、Teams 服务管理员或全局管理员才能打开租户就绪性评估。

第一次使用 Advisor for Teams 时，它将在 Teams 中为你创建一个部署团队。 它为你要推出的每个工作负载添加频道。 


## <a name="available-advisor-for-teams-plans"></a>可用的 Advisor for Teams 计划

在 Advisor for Teams 处于预览阶段时，我们提供以下两种计划：

1. 聊天、团队、频道和应用
    - 租户评估
    - Planner 计划，包括采用任务
    - Forms 用户调查
1. 会话和会议
    - 租户评估
    - Planner 计划，包括采用任务
    - Forms 用户调查

建议从“聊天”、“团队”、“频道”和“应用计划”开始。 工作负载部署完成后，请返回到 Advisor，然后单击“**添加频道**”以开始下一个工作负载。 

## <a name="tenant-assessment"></a>租户评估
每个计划都包括租户就绪性评估，可用于在推出 Teams 前识别并补救环境中的任何缺陷。 下面是每个评估的检查内容：

### <a name="chat-teams-channels-and-apps"></a>聊天、团队、频道和应用


|评估  |结果  |
|---------|---------|
|Teams 许可证     |你是否有具有可用 Teams 许可证的活动订阅 |
|Exchange 许可证     |你是否有具有可用 Exchange Online 许可证的活动订阅 虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。         |
|SharePoint Online 许可证     | 你是否有具有可用 SharePoint Online 许可证的活动订阅。 对于文件存储、频道协作和聊天，每个用户需要一个 SharePoint Online 许可证。 
|已启用来宾访问     |Teams 中的来宾访问是否已启用。 不会审核来宾访问的 Azure Active Directory 设置。   |
|已配置虚域     |是否为你的租户配置了非 @onmicrosoft.com 域  |
|已配置 Office 365 组命名标准     | 是否已为 Office 365 组配置命名标准        |
|已配置 Office 365 组到期     |  是否已为 Office 365 组定义组到期策略。 如果没有，则该值设置为“从不”。        |
|已配置外部访问     |如果已启用外部访问，则可与 Teams 中的外部组织进行通信。          |

### <a name="meetings-and-conferencing"></a>会话和会议


|评估  |结果  |
|---------|---------|
|Teams 许可证     |你是否有具有可用 Teams 许可证的活动订阅 |
|Exchange 许可证     |你是否有具有可用 Exchange Online 许可证的活动订阅 虽然 Exchange 不是基本 Teams 功能所必需的，但与 Exchange 的集成提供了一种最佳 Teams 体验。 |
|音频会议许可证    |你是否有具有音频会议许可证的活动订阅 |
|流式传输许可证     |你是否有具有流式传输许可证的活动订阅（如果需要会议录制可以使用此许可证）。 |
|来宾访问权限     |Teams 中的来宾访问是否已启用。 不会审核来宾访问的 Azure Active Directory 设置。|
|虚域     |是否为你的租户配置了非 @onmicrosoft.com 域。  |
|外部访问     |如果已启用外部访问，则可与 Teams 中的外部组织进行通信。 |


### <a name="advisor-bot"></a>Advisor 机器人
Advisor 创建部署团队后，Advisor 机器人就会发送以下消息。

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
> 默认情况下启用 Advisor for Teams。 如果你使用或计划使用 Advisor for Teams，请不要禁用此项。


## <a name="frequently-asked-questions"></a>常见问题解答
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams 的许可要求是什么？
除获得 Teams 许可之外，没有其他许可要求。

### <a name="can-i-delete-the-deployment-team"></a>我是否可以删除部署团队？
在 Advisor for Teams 创建部署团队后，可以像管理任何其他团队那样管理该团队，包括可以删除该团队。 请注意，如果不使用 Teams 管理中心删除该团队，系统将报告该团队存在。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除频道？
可以，创建部署团队后，你将按照管理任何其他团队的方式管理频道。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>我是否可以在部署团队中添加或删除项目团队成员？
可以，创建部署团队后，你将按照管理任何其他团队的方式进行管理。

### <a name="can-i-modify-the-planner-plans"></a>能否修改 Planner 计划？
可以，Advisor for Teams 创建部署团队后，你应更新 Planner 计划，使其可以为你的 Teams 推出提供最佳支持。 可以像任何其他 Planner 计划那样修改任何项 - 存储桶、任务和任务详细信息。


### <a name="can-i-modify-the-forms-survey"></a>能否修改 Forms 调查？
可以，Advisor for Teams 创建部署团队后，可以按需修改 Forms 调查。

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
