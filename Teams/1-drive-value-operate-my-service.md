---
title: Microsoft Teams 操作指南
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 04/12/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: 团队服务管理所需的任务和活动, 包括监视服务运行状况, 以及评估和确保网络质量和使用情况。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: d40bbeaf0876071502d187826ecc702c9175b2da
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494293"
---
# <a name="operate-my-service"></a>操作服务

本文概述了针对你的组织成功操作云语音服务的要求。 通过正确操作你的云语音服务, 你可以确保为你的组织提供优质、可靠的体验。

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介

操作指南概括介绍了 Microsoft 团队服务管理功能所需的所有任务和活动。

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams 服务包括 Microsoft Office 365 和在本地部署的基础结构组件（例如网络）。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实现了与现有服务相关联的流程和任务。 也就是说, 计划服务管理以便将来支持团队时, 您可能会增加当前流程。

服务管理包括管理团队结束的所有活动和过程。 如前面所述, 某些服务管理组件 (Office 365 服务本身所包含的基础结构) 是 Microsoft 的责任, 而你的客户对你的用户负责管理团队、网络的各个方面。以及你提供的终结点。

本指南中的任务和活动按下图所示分为八个类别。 这些类别中的每一个都将在以下部分展开。

![描述任务和活动类别列表的图表](media/operate-my-service-image1.png "描述团队服务管理所包含的任务和活动类别列表的图表。图表还描绘服务管理主要是客户任务。")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="Icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定将如何为团队实施操作。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="Icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>完整查看操作指南。</li><li>实现与你的组织的目标相协调的操作策略, 以提供云语音工作负荷的质量和可靠性。</li><li>查看体验质量评审指南。</li><li> 实施一种操作策略来定期执行体验检查质量, 以确保你的云语音部署在其峰值功能中运行。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>可操作的角色映射

规划你在构想阶段 undertook 的操作非常重要, 因为操作活动将在首次试用用户启用时开始。 本指南列出了必须按每天、每周、每月或按需执行的活动和任务, 以维护高质量的团队部署。 本指南提供有关如何执行这些关键活动和任务的知识和指南。

成功部署的一个重要部分是确保在构想阶段早期执行的规划包括确定负责执行特定活动的人员。 确定了哪些任务和活动适用于你的部署后, 需要先了解这些任务和活动, 然后再关注你分配给他们的组或个人。

您标识的每个团队都必须查看并同意标识的任务和职责, 并开始准备。 这可能包括培训和准备情况, 为人员配备计划提供更新或确保外部提供商已准备好交付。

本指南中定义的活动和角色在大多数情况下应是有效的, 但每个团队部署都是唯一的;因此, 你可以使用本指南作为自定义活动和默认角色的起始点, 以满足你的需求。

确保每个有责任的团队对运行服务所需的活动有一个很好的理解。 在第一个试点开始之前, 每个团队在您的组织中接受和签署自己的责任非常重要。

协议准备好后, 相应的团队应开始 operationalize 其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="Image depicting the next steps"/><br/>后续步骤</td>
<td><ul><li>使用此文档有助于操作角色映射练习。</li><li>与各自的支持团队会面, 为所需活动列表中的每个项目分配名称。</li><li>获取已分配角色的接受或注销。</li><li>确保相应的团队具有相应的培训、准备情况和资源来完成所需的活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>团队服务相关性

Microsoft 团队将跨 Office 365 的技术汇集在一起, 为团队协作提供中心。 示例包括:

-   Azure Active Directory (Azure AD) 为团队提供身份验证和授权服务。

-   Exchange Online 提供了一些高级功能, 如法律封存和电子发现。

-   SharePoint Online 提供了在频道中共享文件的功能, 而 OneDrive for business 提供了一种在私人聊天中共享文件的机制。

组织还可以利用本地基础架构中的现有投资。 例如, 可以利用 Azure AD Connect 将现有本地 Active Directory 帐户用于身份验证。 Exchange Server 的某些版本可用于代替 Exchange Online。

这些技术共同为用户提供丰富、协作和智能的通信套件。 这种紧密集成是团队的一个主要优点, 但它还可以促进跨这些技术对服务管理的要求。

本指南介绍了管理团队服务的主要关注领域。 最有可能的是, 您可以为团队所依赖的支持技术制定服务管理计划。 如果不是, 你将需要为这些技术组件 (本地和联机) 建立正确的服务管理计划。 这将帮助确保你的用户体验高质量、可靠的团队体验。

#### <a name="references"></a>References 

[Microsoft Teams 概述](teams-overview.md)

[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

[Microsoft 团队和 Skype for business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南活动

以下部分概述了成功操作 Microsoft 团队服务所需的活动。 它们包括对工具、上下文信息和其他内容的参考, 以帮助你理解活动并帮助准备就绪计划。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监视服务运行状况

了解 Microsoft 团队服务的整体运行状况非常重要, 这样你就可以在组织中向其他影响该服务的事件主动发出通知。 正如前面所述, 团队依赖于其他 Office 365 服务, 如 Azure Active Directory、Exchange Online、SharePoint Online 和 OneDrive for business。 因此, 监视相关服务的运行状况同样重要。

将此活动纳入你的事件管理流程, 以主动通知用户、帮助台和运营团队准备处理用户升级。

以下部分介绍了可用于监视影响团队服务的[服务事件](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1)的工具。 下表介绍了每个工具的优点摘要, 以及每个工具的用途。

| 监视工具                       | 优势                                            | 何时使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Office 365 门户                     | 在具有支持的浏览器的任何设备中可用。 | 在不需要实时通知时使用。                                          |
| Office 365 管理应用                  | 向移动设备提供推送通知。  | 当您在旅途中需要通知服务事件时, 请使用。                  |
| Microsoft System Center               | 与 Microsoft System Center 集成。           | 在需要高级监视功能和通知支持时使用。                       |
| Office 365 服务通信 API | 以编程方式访问 Office 365 服务运行状况。   | 在需要与第三方监视工具集成或希望构建自己的解决方案时使用。 |

> [!NOTE]
> 只有分配有**全局管理员**或**服务管理员**角色的人员才能查看服务运行状况。

### <a name="monitoring-with-the-office-365-portal"></a>通过 Office 365 门户进行监视

[Office 365 门户](https://portal.office.com/)提供了[服务运行状况仪表板](https://portal.office.com/adminportal/home#/servicehealth), 您可以在其中查看团队服务的当前运行状况以及相关服务。

### <a name="monitoring-with-the-mobile-app"></a>通过移动应用进行监控

Office 365 管理应用在 Apple iOS、Android 和 Windows (PC 和手机) 上可用。 该应用提供有关服务运行状况和即将进行的更改的服务管理员信息。 该应用支持推送通知, 在发布公告后几乎可以立即向您发出通知。 这可帮助你及时了解服务的状态、运行状况和任何即将到来的更改。 通知支持使其成为管理员推荐的监视工具。 有关详细信息, 请参阅:

[Office 365 管理员移动应用](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载 Office 365 管理移动应用](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>通过 Microsoft System Center 进行监控

Microsoft System Center 是一个集成的管理平台, 可帮助你管理数据中心、客户端设备和混合云 IT 环境。 使用 System Center 的 Office 365 管理员现在可以选择导入 Office 365 管理包, 从而使其能够查看 System Center 中 Operations Manager 内的所有服务通信。 使用此工具, 你可以访问已订阅服务的状态、活动和已解决的服务事件, 以及你的消息中心通信 (即将进行的更改)。 有关详细信息, 请参阅以下[博客文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果你利用 System Center 监视团队服务运行状况 (以及相关服务), 你可以进一步自定义管理包以通知或通知特定组或已标识为对事件做出反应的人员。
这些组可以包括服务所有者、支持人员、第二级和第三级支持组以及你的组织中的事件经理。

### <a name="monitoring-for-advanced-scenarios"></a>监视高级方案

通过利用 Office 365 服务通信 API 以编程方式访问 Office 365 服务运行状况和更改, 可以监视服务运行状况和即将进行的更改。 使用此 API 创建你自己的监视工具, 或将你的现有监视工具连接到 Office 365 服务通信, 从而可能简化你的环境监视方式。 有关详细信息, 请参阅[适用于企业开发人员的 Office 365](https://developer.microsoft.com/office)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                               | 节奏   | 分配的团队 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视服务运行状况 | 使用可用的工具主动监控 Microsoft 团队服务运行状况 (以及相关服务)。 相关服务包括: Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory。 | 实时 |               |
| 事件通知  | 将影响团队服务的事件通知给内部利益干系人。 内部利益干系人可以包括用户、服务中心和事件管理器。                                                                          | 根据需要 |               |

### <a name="references"></a>References 

[如何检查 Office 365 服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[服务运行状况和连续性](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理组织更改

Microsoft 团队是基于云的服务。 这使您能够以快速的步调提供新的功能和功能。 不断进行的创新为组织带来了明显的好处, 但需要在组织内适当地管理这些更改, 以避免用户对您的支持人员的抵抗或上报。

对团队的更新会自动向你的用户推出。 你的用户将始终拥有团队服务中提供的最新客户端和功能。 不能管理团队更新对你的用户的推出, 因此, 通过有效的通信、培训和采纳计划管理更改至关重要。 如果你的用户知道所做的更改、对好处的了解, 以及能够利用新功能&mdash;, 他们能够更快地适应所做的更改。

### <a name="monitoring-for-change"></a>监视更改

更改管理的第一步是监视为团队计划的更改。 监视这些更改的最佳来源是[Office 365 路线图](https://products.office.com/business/office-365-roadmap), 其中列出了当前正在开发、即将推出给客户的功能或已完全启动的功能。 你可以使用提供的筛选器搜索团队特定的功能, 也可以将路线图下载到 Excel 文件以进行进一步分析。 对于每个功能, 路线图将提供简短说明以及预计的发布日期。

在[Microsoft 团队博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)中, 你可以了解有关团队产品更新的最佳做法、趋势和新闻。 希望在此处找到要向团队发布的主要功能更新。 您也可以通过 RSS 源订阅博客。 然后, 您可以直接将[RSS 源](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)添加到团队频道, 以便所有重要新闻直接交付到团队内部。

[Microsoft 团队的发行说明](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)中记录了已发布的所有功能。
在此处, 你将找到针对桌面版、web 和移动设备发布的功能的列表。 "[帮助](get-help-in-microsoft-teams.md)" 的 "**新增功能**" 选项卡上也提供了相同版本的发行说明。

熟悉可用的资源, 并确保分配适用的所有者进行监视以进行更改。

### <a name="planning-for-change"></a>规划更改

现在, 你已了解团队服务即将进行的更改, 下一步是准备并相应规划。 评估每项更改以确定哪些更改需要与用户进行通信、认识市场活动、支持团队或用户培训、功能评估和采纳活动。 这是您的组织中的变更管理团队的主要角色。 下面是可帮助你规划更改的示例表的集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能: 云录制 (发布日期: 2018 年1月)

**常规跟踪**

| 更改准备情况 | 状态栏   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 法律评论   | 完     | 此功能是加入培训团队的先决条件。 | 项目团队  |

**技术变更管理**

|       更改准备情况       | 状态栏 |                      备注/后续步骤                      |    所有者     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     需要更改      |  是   | 管理员只需为识别用户启用录制。 | 支持团队 |
| 技术准备完成 |  是   |                                                            | 支持团队 |
|                              |        |                                                            |              |

**用户更改管理** 

| 更改准备情况 | 状态栏   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 用户影响                  | 低                  |                                                                 |                        |
| 需要用户准备就绪      | 是                  |                                                                 |                        |
| 通信就绪         | 否                   | 通信电子邮件已起草, 正在等待审阅。            | 通信团队    |
| 准备培训               | 是                  | 培训将利用现有的 Microsoft 视频。                | 培训团队          |

**状态曲目**

| 更改准备情况 | 状态栏   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 发布状态               | 正在进行          | 执行承办人待定的审阅。               | 更改管理团队 |
| 发布注销             |                      |                                                                 |                        |
| 发布日期                 |                      |                                                                 |                        |

有关规划团队变更管理的详细信息, 请参阅[创建 Microsoft 团队的更改管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                                | 节奏   | 分配的团队 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监控更改     | 监视 Microsoft 团队服务的即将进行的更改。                                                                                                                                                                   | 每天     |               |
| 规划更改    | 评估和规划新功能, 包括通信计划、意识活动和培训。                                                                                                     | 根据需要 |               |
| 用户准备就绪             | 执行目标通信、感知或培训活动, 以确保用户准备好进行即将进行的更改。                                                                                                        | 根据需要 |               |
| 支持团队准备情况 | 执行目标通信、感知或培训活动, 以确保支持团队做好准备。 支持团队可以包括 "白色 glove" 团队、支持人员、第2层或第3层支持、外部合作伙伴等。 | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估团队使用情况

初始试点开始后, 建立定期节奏来测量实际的团队使用情况非常重要。 这使你的组织能够深入了解实际使用情况如何与你在构想阶段中预测的用法保持一致。 虽然本部分重点介绍团队使用, 但这应该是衡量和评估 Office 365 总使用的更广泛的工作之一。

在部署早期查看使用情况使你有机会:

-   验证用户是否正在使用团队。

-   确定潜在的采纳挑战, 然后再在组织内创造关键问题。

-   了解构想阶段需求和实际使用情况之间是否存在差异。

如果使用不是你所期望的, 这可能是由于部署问题、未正确执行采纳的计划, 也可能是其他问题。 服务管理员必须与相关团队进行协作才能帮助删除使用障碍, 具体取决于低使用背后的实际原因。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心衡量使用情况

"报告" 仪表板中提供了来自团队的使用数据。 可在三个不同的报表中找到团队使用数据。 第一个报表提供有关用户如何使用 Office 365 中的各种服务进行通信和协作的交叉产品视图。 可在此处找到此报告: [Office 365 活动用户报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他两个报表是特定于团队的报表, 它们提供来自用户和设备的团队使用情况的进一步详细信息。 可在此处找到这两个报表:

[Microsoft Teams 设备使用情况报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams 用户活动报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>所需权限

管理员中心中的使用情况报告可由分配有**全局管理员**角色的人员或特定于产品的管理员角色 (**Exchange 管理员**、 **Skype for business 管理员**和 SharePoint) 访问。 **管理员**)。

此外,**报表读者**角色适用于需要访问报表的用户, 但不执行需要管理员级别权限的任何任务。 分配此角色以向任何有利益干系人的人员提供使用情况报告, 以监视和推动采纳。 有关可用的不同角色的详细信息, 请参阅[关于 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

使用报表仪表板测量使用率后, 请务必将测量的使用情况与项目的构想阶段中定义的任何关键成功指示器 (KSIs) 进行比较。 你可以定义可能定义为活动使用情况的 KSI, 也可以定义间接链接到活动使用情况的一个。

在恢复向其他网站或用户推出的功能之前, 请务必确定实际使用和计划使用情况之间的任何差异。 你可能会将组织发现标识为此活动的一部分, 你可以利用它来确保下一批网站或用户不会遇到相同的问题。

首先, 查明这是否是采纳或技术问题。 首先通过调查以下项目来确定问题所在。

1.  通过执行 "[体验质量检查](#quality-of-experience-review-guide)" 验证质量。

2.  与帮助台团队协作, 检查是否存在阻止用户访问或使用该服务的趋势技术问题。 如果问题的趋势确实存在, 请使用本文稍后部分的 "[终结点疑难解答](#endpoint-troubleshooting)" 部分尝试解决问题, 然后再参与支持。

3.  与培训和采纳团队协作, 收集用户的直接反馈 (请参阅本文后面的[评估用户情绪](#assess-user-sentiment)), 并查看知晓和采纳活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                         | 说明                                                                                                                      | 节奏   | 分配的团队 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 测量使用率 (启用阶段) | 在启用阶段继续 onboarded 时, 测量和评估团队使用情况。 根据需要解决使用问题。 | 每周    |               |
| 度量使用情况                    | 在 "驱动器价值" 阶段测量和评估团队的使用情况 (部署完成后)。 根据需要解决使用问题。 | 次  |               |
| (驱动器值阶段)              |                                                                                                                                  |           |               |
| 更新采纳计划             | 根据测量使用情况与计划目标的比较情况更新采纳计划。                                         | 根据需要 |               |

### <a name="references"></a>References 

[关于 Microsoft 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 管理中心中的活动报表](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户情绪

了解用户情绪可以充当评估团队部署成功的关键指示器。 用户反馈可推动组织中的更改;这可能包括对你的通信计划、培训计划的更改, 或为你的用户提供支持的方式。

尽早获取反馈并在项目的整个生命周期中继续评估用户情绪非常重要。 使用以下指南确定组织将寻求反馈的时间间隔:

-   **项目开始**: 在项目开始评估用户情绪时, 你可以快速了解用户对其团队体验的看法。

-   在**主要里程碑**: 通过在整个项目生命周期中收集反馈, 你可以连续测量用户情绪, 并根据需要进行更改。 这在主要里程碑后尤其有用。

-   **项目结论**: 评估用户在项目结束时的情绪将告诉你已完成的工作以及仍需要完成工作的位置, 并允许你将结果与以前的调查进行比较。

-   **持续**: 继续以无限衡量用户情绪。 用户情绪中的更改可能是由于组织的环境中的更改或团队服务中的更改所致。 通过以固定的时间间隔评估用户情绪, 你可以了解服务管理团队的执行情况以及你的组织如何响应团队服务中的更改。

用户情绪可以通过多种不同的方法进行评估。 其中包括电子邮件调查、人员或电话风格的面试, 或者仅在团队或 Yammer 中创建反馈频道。 有关详细信息, 请参阅[Microsoft 团队中用户反馈方法的最佳做法](best-practices-feedback.md)。

你还可以使用 industrywide 方法来评估名为 net promotor 评分 (NPS) 的用户情绪, 如下一节所述。

### <a name="nps"></a>NPS 

Net promoter 得分 (NPS) 是一种 industrywide 客户忠实度指标和一种用于评估用户情绪的好方法。 可以通过提出以下两个问题来计算 NPS: "向同事推荐团队的可能性有多大？", 后跟任意多边形问题 "为什么？"

NPS 是一个索引, 范围从-100 到 100, 用于衡量客户推荐公司产品或服务的意愿。 NPS 基于通过电子邮件或其他电子方式向用户发送的匿名调查。 NPS 测量提供商和使用者之间的忠诚度。 它只包含一个问题, 要求用户从1到10对其体验进行评级, 以及提供其他注释的选项。 然后, 根据以下分级对用户进行分类:

-   9或10是 Promoters: 将推动您的服务并燃料其他人的忠诚发烧。

-   7或8为被动: 满意但 unenthusiastic, 易受其他服务或服务的影响。

-   从1到6的 Detractors: 不满意的客户可能会损害您的服务并妨碍增长。

![演示 NPS 缩放的图表](media/operate-my-service-image2.png "此图演示了 NPS 的缩放。它显示0到6的排名是 detractors, 7 到8是被动的, 9 到10是 promoters。")

虽然基本 NPS 编号非常有用, 但你将获得分析用户意见的最大价值。 他们将帮助你了解用户为什么 (或不) 向其他人推荐团队的原因。 这些评论可提供有价值的反馈, 以帮助项目或服务管理团队了解提供优质服务所需的调整。

若要向您的组织提供 NPS 调查, 您可以利用您喜爱的在线调查工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>所需任务的每日/每周/每月/

| 活动              | 说明                                                                                                                                                                         | 节奏   | 分配的团队 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 评估用户情绪 | 通过使用调查或面试, 或通过团队或 Yammer 中的反馈频道来捕获和评估用户情绪。                                                                 | 根据需要 |               |
| 更新采纳计划 | 根据用户反馈对组织中的设备进行更改;这可能包括对你的通信计划、培训计划的更改, 或为你的用户提供支持的方式。 | 根据需要 |               |

### <a name="references"></a>References 

[净 Promoter 分数](https://en.wikipedia.org/wiki/Net_Promoter)

[使用 Yammer 收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈的最佳做法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心计划元素将进入优化、调整大小和修正你的网络基础结构, 以确保 Microsoft 团队服务的高质量、高效的路径。 规划任务和要求在我们的[网络准备](3-envision-evaluate-my-environment.md#network-readiness)指南中介绍。 由于升级、扩展或其他业务要求, 网络经常随着时间的推移而演化。 请务必考虑您的网络规划活动中团队的要求。

虽然网络规划是团队部署的一个重要方面, 但确保网络保持良好状态并保持最新是同等重要的, 具体取决于不断变化的业务或技术要求。

为了确保网络的运行状况, 需要定期执行许多操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                                                       | 说明                                                                                                                                                                                                                                                                                                                                                                 | 节奏                | 分配的团队 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 监视 Office 365 IPs 和 Url                                | 使用提供的[RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)监视对[Office 365 url 和 IP 地址范围](https://aka.ms/o365ips)所做的任何更改, 并启动对相应网络组的更改请求。                                                                                                                                | 每天                  |               |
| 基于 Office 365 IPs 和 Url 的更改更新网络 | 对适用的网络组件 (防火墙、代理服务器、Vpn、客户端防火墙等) 进行更新, 以反映[Office 365 url 和 IP 地址范围](https://aka.ms/o365ips)的更改。                                                                                                                                                              | 根据需要              |               |
| 提供建筑物数据                                          | 向质量专家 (或相关利益干系人) 提供更新的子网信息, 以确保[CQD 中的生成定义](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)保持最新状态。 | 根据需要              |               |
| 实施更改                                               | 实施对网络的更改以支持不断变化的团队业务和技术要求。 网络元素可以包括:<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wlan 网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>     | 根据需要              |               |
| 网络监控和报告                               | 通过使用您现有的第三方网络管理工具和您的网络提供商提供的报告功能, 监控网络端到端的可用性、利用率和容量趋势。 使用趋势数据进行网络容量规划。                                                                                                            | 每天、每周、每月 |               |
| 容量规划                                              | 与团队服务所有者协作, 以了解不断改变的业务和技术要求可能会增加额外的容量。 利用[网络 Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)的结果, 确保有足够的带宽可供 Microsoft 团队使用。                               | 根据需要              |               |
| 网络故障排除和修正                        | 帮助团队人员、服务所有者和关键利益干系人诊断和解决与团队连接性、可靠性或质量相关的问题。 网络元素可以包括:<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wlan 网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>    | 根据需要              |               |
| 灾难恢复和高可用性测试                | 在网络基础结构上执行常规高可用性和灾难恢复测试, 以确保它满足团队服务规定的服务级别目标 (Slo) 或服务级别协议 (Sla)。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>References 

[Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[构建数据架构](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估和确保质量 

所有组织都需要一个组或个人负责质量。 这是服务管理中最重要的角色。 质量拥护者角色分配给热心用户体验的人员或组。
此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的规模和复杂程度, 这可以是具有热情的人员或组, 可确保高质量的用户体验。

质量专家利用现有的工具和已记录的流程, 如通话质量仪表板 (CQD) 和体验检查指南, 用于监控用户体验、识别质量趋势和在需要的地方推动补救。
质量拥护者应与各个团队协作处理补救措施, 并向筹划指导委员会报告进度和任何打开的问题。

[体验质量检查指南](https://aka.ms/qerguide)包括在对改善用户体验有最大影响的关键领域中评估和提供补救指南的活动。 质量体验审核指南中提供的指南重点介绍如何使用 CQD Online 作为主要工具来报告和调查每个区域, 并重点介绍音频以最大程度地提高采纳和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议您提前提名本《质量专家提名。 在进行命名后, 他们应开始熟悉体验质量检查指南和相关培训资料中的内容。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                               | 说明                                                                                                                                                                                                                                                                                                 | 节奏                             | 分配的团队 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名和培训质量专家 | 提名和培训质量专家。                                                                                                                                                                                                                                                                   | 根据需要                           |               |
| 执行体验检查质量 (QERs)     | 执行 QER 以确定质量和可靠性的趋势, 针对已定义的目标进行评审, 并报告给组织中的关键利益干系人。                                                                                                                            | 每月 (在部署期间每周) |               |
| 驱动器修正                      | 基于 QER 评估和结果, 在组织内协调补救措施。                                                                                                                                                                                                           | 根据需要                           |               |
| 在 CQD 中更新构建数据            | 当对网络进行更改时, 在 CQD 中更新或添加新的生成定义 (请参阅[上载建筑物信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information))。 | 根据需要                           |               |
| 填写质量拥护者角色      | 组织中的质量的端到端责任。 这包括:<ul><li>确保定期执行 QER。</li><li>向关键利益干系人报告质量状况。</li><li>确保生成数据定义是最新的。</li><li>协调整个组织中的补救措施, 确保用户对团队具有优质的体验。</li></ul>          | 每天                               |               |



### <a name="references"></a>References 

[了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[上载租户数据信息](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)

[体验质量检查指南](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

Microsoft 团队终结点可以定义为任何运行团队客户端的 PC、Mac、平板电脑或手机 (或任何其他) 设备。 术语 "*终结点*" 不仅包括设备本身, 还包括用户如何连接到设备 (例如, 使用设备的内置麦克风或扬声器、earbuds 或优化的耳机)。 部署后, 必须忘记终结点。 团队终结点需要持续的护理和维护。 以下部分介绍了要关注的特定区域。

### <a name="endpoint-requirements"></a>终结点要求

团队的一个主要好处是客户自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。 团队移动应用将通过其各自的应用商店保持最新。

团队客户端在基础软件平台方面具有最低要求。 这些要求可能会随着时间的推移而更改, 因此, 监视它们的更改很重要。 例如, 团队客户端具有最低的 iOS 版本。 如果客户端使用 internet 浏览器, 则浏览器也需要保持最新。 可在[获取 Microsoft 团队的客户端](get-clients.md)中找到支持的平台列表。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙可能会影响呼叫质量, 甚至阻止建立通话。 在配置了客户端防火墙上的相应排除后, 需要根据[Office 365 url 和 IP 地址范围](https://aka.ms/o365ips)中的信息保持最新。 您的第三方供应商将提供有关如何更新排除项的特定指南。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

Wi-fi 驱动程序可能有问题。 例如, 驱动程序可能会导致访问点之间出现非常严重的漫游行为, 从而导致不必要的访问点切换, 从而导致通话质量较差。 性能较差的 Wlan 驱动程序可能会通过 "体验质量检查" (有关详细信息, 请参阅[体验查看指南的质量](https://aka.ms/qerguide)) 发现。 实施一个质量驱动的流程, 以监视新的 Wi-fi 驱动程序并确保在将其部署到一般用户群体之前对其进行了测试, 这一点非常重要。

### <a name="endpoint-management"></a>终结点管理

支持的终结点和接口设备 (如耳机) 的目录应该可用并保持。 此目录将包含已选择并验证为构想和板载阶段的一部分的已批准设备的列表。 通常, 为组织中的每个角色类型选择特定设备, 以满足该角色的属性的需要。 所有终结点都有一个生命周期, 您需要管理与这些设备相关联的供应商合同、保修、替换、分发和修复策略。

### <a name="endpoint-troubleshooting"></a>终结点疑难解答

即使您已遵循以前的指南, 组织中的用户仍可能会遇到团队问题。 尽管问题可能不与终结点本身有关, 但问题的症状通常通过客户端呈现给用户。 下面的指南旨在提供解决问题时可以采取的常规步骤;这并不是一种全面的故障排除指南。 这些步骤按特定顺序提供, 但不需要明确关注, 并且可能不适用, 具体取决于问题的性质。

1.  **验证服务运行状况:** 用户可能遇到的问题可能与对团队服务或其依赖服务产生负面影响的事件相关。 第一步, 我们建议您确认没有活动的服务问题。 请参阅[如何检查 Office 365 服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    请记住检查从属服务 (例如, Exchange、SharePoint、OneDrive for business) 的状态。 "监视服务运行状况" 将在上一节 "[监视服务运行状况](#monitor-service-health)" 中更详细地讨论。

2.  **验证客户端连接:** 连接问题导致团队中的功能或登录问题。 我们建议 (特别是对于新网站或位置) 验证与该服务的连接。 确保为每个网站遵循以下[Office 365 url 和 IP 地址范围](https://aka.ms/o365ips)指南。 你可以利用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)执行连接测试, 以验证是否已正确打开云语音功能的媒体端口。 有关如何运行连接测试的详细步骤在[网络准备情况](3-envision-evaluate-my-environment.md#network-readiness)指南中提供。

3.  **检查已知问题列表:** 查看[团队的已知问题列表](known-issues.md), 以确定用户是否已受到这些问题中的任何一项的不良影响。 按照提供的解决方法 (如果有) 解决问题。

4.  **访问 Microsoft 团队社区:**[Microsoft 团队社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)为团队提供专用空间。 团队社区围绕团队提供讨论列表、博客文章和公告。 你可以发布问题或搜索以前的讨论, 以查找你的问题的解决方案。

5.  **联系 Microsoft 支持人员:** 您可以与 Microsoft 支持部门联系, 以解决团队在线或手机出现的问题。 有关信息, 请参阅[联系业务产品支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。
    对于 Premier 客户, 可通过关注[Microsoft 团队的联系支持 (Premier 客户)](https://support.microsoft.com/premier/contacts)的指导启动支持请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                 | 说明                                                                                                                                                                                                                                                                                                                                                                     | 节奏   | 分配的团队 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 终结点要求    | 确保团队终结点继续满足[Microsoft 团队的获取客户端](get-clients.md)中列出的团队的所有软件要求。                                                                                                                                                                                       | 每月   |               |
| 终结点防火墙       | 基于[Office 365 url 和 IP 地址范围](https://aka.ms/o365ips)中的信息维护终结点防火墙上的相应排除项。 您的第三方供应商将提供有关如何维护排除项的特定指南。 订阅[rss 源](https://support.office.com/o365ip/rss)以自动收到更改通知。 | 根据需要 |               |
| Wi-Fi 驱动程序            | 在电脑上测试和更新 Wlan 驱动程序。 使用 "CQD" ([体验检查指南](https://aka.ms/qerguide)) 验证结果。                                                                                                                                                                                                                                                                   | 根据需要 |               |
| 终结点管理      | 维护支持的终结点和接口设备 (如耳机) 的目录。 管理供应商合同、保修、分发、更换和维修政策。                                                                                                                                                                                                        | 每月   |               |
| 终结点疑难解答 | 故障排除任务可以包括验证连接、咨询已知问题列表、记录收集、分析和上报给 Microsoft 支持或第三方供应商。                                                                                                                                                                                               | 根据需要 |               |

### <a name="references"></a>References 

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[获取 Microsoft Teams 的客户端](get-clients.md)

[Microsoft 团队社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Microsoft Teams 的已知问题](known-issues.md)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[联系商业版产品的支持人员 - 管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[联系 Premier 支持人员](https://support.microsoft.com/premier/contacts)

[团队视频疑难解答](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

在部署 Microsoft 团队服务之后, 你需要执行与其管理相关的多个活动。 活动范围从管理服务和单个用户到容量规划以及预配授权和电话号码。 以下部分介绍了一些常见的管理任务。

### <a name="service-administration"></a>服务管理

团队服务具有多个可在租户范围内配置的设置。
对租户设置所做的更改将影响已启用团队的所有用户。 有关这些设置的详细列表, 请参阅[管理你的组织的 Microsoft 团队设置](enable-features-office-365.md)。

### <a name="user-administration"></a>用户管理

为支持用户, 组织可能需要任意数量的相关任务, 具体任务因组织而异。 最终, 这些任务需要由已分配了这些操作责任的支持团队进行管理。 若要支持团队中的用户, 通常需要以下任务。

#### <a name="general-tasks"></a>常规任务

[管理 Microsoft Teams 的用户访问](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>电话系统的常见任务

[为用户分配、更改或删除电话号码](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)

[为用户分配或更改紧急地址](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[为你的组织添加、更改或删除紧急位置](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[创建并管理拨号计划](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>音频会议的常见任务

[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)

[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>许可证管理

当您的组织发展或发展合同时, 请务必为当前和未来需求计划许可。 除了授权使用云语音功能 ([电话系统](here-s-what-you-get-with-phone-system.md)和[音频会议](https://products.office.com/skype-for-business/audio-conferencing)) 外, 还有一个基本团队许可证。

对于团队, 电话系统许可证需要关联的[通话计划](calling-plan-landing-page.md)许可证。 通话计划许可使您能够拨打和接收国内和/或国际电话通话。 这些计划是基于使用的, 并且与它们关联的分钟池。 设置[通信信用点数](what-are-communications-credits.md)可确保您永远不会用尽服务。

音频会议允许 tolled 电话拨入式会议和国内拨出式会议服务。 免费电话拨入式会议或非国内拨出方案可能会导致您需要额外的费用, 以便[通信信用点数](what-are-communications-credits.md)是必需的。

通讯信用点数可以补充通话计划和音频会议许可证。 通话计划许可证和通讯信用点数都是基于使用的, 因此需要对其进行监视和设置。

你可以利用[PSTN 使用报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)帮助你监视通话计划分钟和通信信用点数的使用情况。 根据此活动的结果, 您可以相应地调整您的许可。 即将推出, 我们将提供[PSTN 分钟池](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report)报告, 以便更有效地帮助您完成此任务。

### <a name="telephone-number-management"></a>电话号码管理

可通过两种方法获取团队中的数字: 您可以从另一个提供商处移植电话号码, 也可以直接从 Microsoft 的号码清单中设置号码。 这两种方法在[获取用户的电话号码](getting-phone-numbers-for-your-users.md)中介绍。

您可以从 Microsoft 的编号清单中预配的电话号码数有限制。 这些限制取决于[您可以获取多少个电话号码](how-many-phone-numbers-can-you-get.md)的若干因素？。
限额取决于号码的类型-免费服务号码、收费服务号码和订阅者 (用户) 号码。 每个都有其自己的限制, 并且必须单独管理。 如果您接近限制 (或已达到限制), 则可以申请限制的增量。 此过程将在上一段的文章中介绍。

在服务可用的区域中, 可能会有一个数字不可用于设置。 有关申请号码的流程的信息, 请参阅[管理您的组织的电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>团队创建 (可选)

默认情况下, 在 Exchange Online 中具有邮箱的所有用户都具有创建 Office 365 组的权限, 因此是 Microsoft 团队中的团队。 如果你希望更严格地控制和[限制新团队的创建](assign-roles-permissions.md#permissions-to-create-teams)(从而创建新的 Office 365 组), 你可以将组创建和管理权限委派给一组管理员。 如果你的组织想要使用此选项, 请参阅本文中所述的过程, 以允许用户提交由分配的团队处理的请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                    | 说明                                                                                                                                                                                                                                                                                                                                                                                                             | 节奏   | 分配的团队 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服务管理      | 管理租户范围的团队设置。                                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 用户管理         | 在团队中管理基于用户的设置和授权。                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 许可证管理          | 通过利用[pstn 使用情况报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)和[pstn 分钟池](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report)报告, 规划基于用户和基于消费的许可 (呼叫计划和通讯信用点数) 的当前和未来需求。 | 每周    |               |
| 电话号码管理 | 管理可用于未来增长的电话号码, 并调整库存水平以满足组织的需求。                                                                                                                                                                                                                                                                                                | 每周    |               |
| 团队创建 (可选)    | 查看和处理团队创建的请求。                                                                                                                                                                                                                                                                                                                                                                          | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>体验质量检查指南

[体验质量检查指南](https://aka.ms/qerguide)包括一组活动, 这些活动在对改善用户体验有最大影响的关键领域中评估和提供补救指南, 如下所示。

![在体验质量评审期间要检查的区域示意图]在(media/plan-my-service-management-image2.png "体验质量评审期间要检查的关键方面: 音频、可靠性和用户调查结果。")

通过不断评估和修正指南中所述的区域, 你可以降低对用户体验产生负面影响的可能性。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

体验质量评审指南中提供的指南重点介绍如何使用呼叫质量仪表板 (CQD) 作为主要工具来报告和调查所述的每个区域, 并重点关注音频以最大程度地提高采纳和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议您提前提名本《质量专家提名。 在进行命名后, 他们应开始熟悉[体验质量审核指南](https://aka.ms/qerguide)中的内容。

<!--ENDOFSECTION-->
