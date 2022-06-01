---
title: Microsoft Teams|操作服务管理|质量
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Teams服务管理所需的任务和活动，包括监视服务运行状况以及评估和确保网络质量和使用情况
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 925ab3c7ab6889651e9e66e0b38266f7dbe17e7a
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823231"
---
# <a name="operate-your-service"></a>运行服务

![升级旅程图，强调卓越运营阶段。](media/upgrade-banner-op-excellence.png "升级过程的各个阶段，重点是“卓越运营”阶段")

本文是升级过程的“卓越运营”阶段的一部分，从Skype for Business升级到Teams后立即开始。

本文概述了升级后组织成功运行Teams的要求。 通过正确运行Teams服务，可以确保为组织提供高质量、可靠的体验。

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介

操作指南概述了作为Microsoft Teams服务管理功能的一部分所需的所有任务和活动。

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams服务包括Microsoft 365或Office 365以及部署在本地 (的基础结构组件，例如网络) 。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实现了与现有服务关联的进程和任务。 也就是说，在计划当前的服务管理以支持将来的Teams时，你或许可以增加当前流程。

服务管理包括管理端到端Teams涉及的所有活动和流程。 如前所述，服务管理的某些组件（Microsoft 365或Office 365服务本身构成的基础结构）由 Microsoft 负责，而客户则对用户负责管理你提供的Teams、网络和终结点的各个方面。

本指南中的任务和活动分为八个类别，如下图所示。 以下各部分将扩展其中的每个类别。

![描述任务和活动的类别列表的图表。](media/operate-my-service-image1.png "描述服务管理Teams包含的任务和活动的类别列表的图表。该图还描述了服务管理在很大程度上是一项客户任务。")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定如何为Teams实现操作。</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>全面查看操作指南。</li><li>实施符合组织目标的操作策略，以提供Teams工作负荷的质量和可靠性。</li><li>查看体验质量评审指南。</li><li> 实施操作策略，定期执行体验质量评审，以确保Teams部署在其最高峰时运行。</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>可操作的角色映射

在构想阶段执行的操作计划至关重要，因为操作活动将在启用第一批试点用户时开始。 本指南列出了必须每天、每周、每月或根据需要执行的活动和任务，以维护高质量的Teams部署。 本指南提供有关如何执行这些关键活动和任务的知识和指导。

成功部署的一个关键组成部分是确保在构想阶段早期执行的规划包括确定谁将负责执行特定活动。 确定哪些任务和活动适用于部署后，需要了解这些任务和活动，然后再了解分配给他们的组或个人。

标识的每个团队都必须查看并就确定的任务和责任达成一致，并开始准备。 这可能包括培训和就绪情况、提供人员配置计划的更新，或确保外部提供商已准备好交付。

本指南中定义的活动和角色在大多数情况下应该有效，但每个Teams部署都是唯一的;因此，可以使用本指南作为起点自定义活动和默认角色以满足你的需求。

确保每个负责的团队都能很好地了解运行服务所需的活动。 在第一次试点开始前，每个团队都必须接受并注销组织中的责任。

协议达成后，相应的团队应开始操作其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td>
<td><ul><li>使用本文档可促进操作角色映射练习。</li><li>与相应的支持团队会面，为所需活动列表中的每个项分配名称。</li><li>获取已分配角色的接受或注销。</li><li>确保相应的团队具有适当的培训、准备情况和资源来完成所需的活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams服务依赖项

Microsoft Teams将跨Microsoft 365和Office 365的技术汇集在一起，为团队合作提供中心。 示例包括：

- Azure Active Directory (Azure AD) 为Teams提供身份验证和授权服务。

- Exchange Online提供法律保留和电子发现等高级功能。

- SharePoint联机提供了在频道中共享文件的功能，OneDrive for Business提供了在私人聊天中共享文件的机制。

组织还可以利用本地基础结构的现有投资。 例如，现有本地 Active Directory帐户可以使用 Azure AD 连接进行身份验证。 某些版本的Exchange Server可用于代替Exchange Online。

这些技术汇集在一起，为用户提供丰富、协作和智能的通信套件。 这种紧密集成是Teams的主要优势，但它也推动了在这些技术中进行服务管理的要求。

本指南介绍管理Teams服务的重点领域。 很可能，你已针对Teams依赖的支持技术制定了服务管理计划。 否则，还需要为这些技术组件制定适当的服务管理计划， (本地和联机) 。 这将有助于确保用户在Teams中享受高质量、可靠的体验。

#### <a name="references"></a>References

[Microsoft Teams 概述](teams-overview.md)

[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

[Microsoft Teams和Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南活动

以下部分概述了成功运行Microsoft Teams服务所需的活动。 它们包括对工具、上下文信息和其他内容的引用，以帮助你了解活动并协助准备计划。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监视服务运行状况

请务必了解Microsoft Teams服务的整体运行状况，以便可以主动提醒组织中其他人任何影响服务的事件。 如前所述，Teams依赖于其他Microsoft 365和Office 365服务，如 Azure Active Directory、Exchange Online、SharePoint Online 和OneDrive for Business。 因此，监视依赖服务的运行状况同样重要。

将此活动合并到事件管理过程中，主动通知用户、支持人员和运营团队准备处理用户升级。

以下部分介绍可用于监视影响Teams[服务的服务事件](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1)的工具。 下表中包含每个工具的优点摘要，以及何时应使用每个工具。

| 监视工具 | 优点 | 何时使用 |
|---|---|---|
| Microsoft 365 管理中心 | 可从具有受支持浏览器的任何设备获得。 | 无需实时通知时使用。 |
| Microsoft 365 管理应用 | 向移动设备提供推送通知。 | 在外出时需要收到服务事件通知时使用。 |
| Microsoft System Center | 与 Microsoft System Center集成。 | 需要高级监视功能和通知支持时使用。 |
| Microsoft 365服务通信 API | 以编程方式访问Microsoft 365或Office 365服务运行状况。 | 需要与第三方监视工具集成或想要生成自己的解决方案时使用。 |

> [!NOTE]
> 只有分配有 **全局管理员** 或 **服务管理员** 角色的个人才能查看服务运行状况。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 管理中心进行监视

[Microsoft 365 管理中心](https://portal.office.com/)提供了[一个服务运行状况仪表板](https://portal.office.com/adminportal/home#/servicehealth)，除了依赖服务之外，还可以在其中查看Teams服务的当前运行状况。

### <a name="monitoring-with-the-mobile-app"></a>使用移动应用进行监视

Microsoft 365 管理应用在 Apple iOS、Android 和Windows (电脑和移动) 上提供。 该应用向管理员提供有关服务运行状况和即将进行的更改的信息。 应用支持推送通知，这些通知几乎可以在发布通知后立即发出警报。 这有助于你随时了解服务的状态、运行状况以及即将发生的任何更改。 通知支持使其成为管理员建议的监视工具。 有关详细信息，请参阅：

[Microsoft 365 管理移动应用](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载Microsoft 365 管理移动应用](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center 进行监视

Microsoft System Center是一个集成管理平台，可帮助你管理数据中心、客户端设备和混合云 IT 环境。 使用System Center的Microsoft 365或Office 365管理员现在可以选择导入管理包，这使他们能够在 System Center 中查看 Operations Manager 中的所有服务通信。 使用此工具可以访问订阅服务的状态、活动和已解决的服务事件，以及消息中心通信 (即将发生的更改) 。 有关详细信息，请参阅以下[博客帖子](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/)。

如果利用System Center监视Teams服务运行状况 (和依赖服务) ，则可以进一步自定义管理包，以提醒或通知已确定对事件做出反应的特定组或个人。
这些组可以包括服务所有者、支持人员、二级和三级支持组，以及组织中的事件管理器。

### <a name="monitoring-for-advanced-scenarios"></a>针对高级方案的监视

可以通过利用服务通信 API 以编程方式访问服务运行状况和更改，监视服务运行状况和即将发生的更改。 使用此 API 创建自己的监视工具，或将现有监视工具连接到Microsoft 365或Office 365服务通信，从而可能简化环境监视方式。 有关详细信息，请参阅[Enterprise开发人员的Microsoft 365或Office 365](/office/developer-program/microsoft-365-developer-program-faq)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 监视服务运行状况 | 使用可用的工具主动监视Microsoft Teams服务运行状况、 (和依赖服务) 。 依赖服务包括：Exchange Online、SharePoint联机、OneDrive for Business、Azure Active Directory。 | 实时 | |
| 事件通知 | 通知内部利益干系人影响Teams服务的事件。 内部利益干系人可以包括用户、支持人员和事件管理者。 | 根据需要 | |

### <a name="references"></a>References

[如何检查Microsoft 365或Office 365服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[服务运行状况和连续性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理组织更改

Microsoft Teams是基于云的服务。 随之而来的是快速提供新功能和功能的能力。 提供持续创新可为组织带来明显的好处，但这些更改需要在组织内得到适当的管理，以避免用户抵制或升级到支持人员。

Teams更新会自动向用户推出。 用户将始终拥有最新的客户端和Teams服务中提供的功能。 无法管理向用户推出Teams更新，因此，通过有效的通信、培训和采用计划管理更改至关重要。 如果你的用户意识到了这一变化，了解了好处，并有权利用新功能&mdash;，他们将能够更快地适应并欢迎更改。

### <a name="monitoring-for-change"></a>监视更改

更改管理的第一步是监视为Teams计划进行的更改。 监视这些更改的最佳来源是[Microsoft 365路线图](https://www.microsoft.com/microsoft-365/roadmap)，其中列出了当前正在开发、正在向客户推出或已完全启动的功能。 可以使用提供的筛选器搜索特定于Teams的功能，也可以将路线图下载到Excel文件进行进一步分析。 对于每个功能，路线图提供简短的说明以及预期的发布日期。

在[Microsoft Teams博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)中，可以了解有关Teams产品更新的最佳做法、趋势和新闻。 期望在此处找到要宣布Teams的主要功能更新。 还可以通过 RSS 源订阅博客。 然后，可以将 [RSS 源](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)直接添加到Teams通道中，以便所有重要新闻都直接在Teams内部传递。

已发布的所有功能都记录在[Microsoft Teams发行说明](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)中。
在这里，你将找到针对桌面、Web 和移动设备发布的功能列表。 “[帮助](get-help-in-microsoft-teams.md)”中的“新增功能”选项卡上也提供了同 **一** 组发行说明。

熟悉可用的资源，并确保分配适用的所有者来监视更改。

### <a name="planning-for-change"></a>规划更改

现在，你已意识到即将对Teams服务进行更改，下一步是进行相应的准备和计划。 评估每个更改，以确定哪些更改需要与用户沟通、认知活动、支持团队或用户的培训，或功能评估和采用活动。 这是更改管理团队在组织中的主要角色。 下面是可帮助你规划更改的示例表的集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：云录制 (发布日期：2018 年 1 月) 

**常规轨道**

| 更改就绪情况 | 地位 | 备注/后续步骤 | 所有者 |
|---|---|---|---|
| 法律审查 | 完成 | 此功能是加入训练团队的先决条件。 | Project团队 |

**技术更改管理**

| 更改就绪情况 | 地位 | 备注/后续步骤 | 所有者 |
|---|---|---|---|
| 需要 IT 更改 | 是 | 管理员需要仅为标识的用户启用录制。 | 支持团队 |
| 技术就绪情况完成 | 是 | | 支持团队 |
| | | | |

**用户更改管理**

| 更改就绪情况 | 地位 | 备注/后续步骤 | 所有者 |
|---|---|---|---|
| 用户影响 | 低 | | |
| 需要用户就绪 | 是 | | |
| 通信准备就绪 | 否 | 已起草通信电子邮件 - 待审阅。 | 通信团队 |
| 训练准备就绪 | 是 | 培训将利用现有的 Microsoft 视频。 | 培训团队 |

**状态跟踪**

| 更改就绪情况 | 地位 | 备注/后续步骤 | 所有者 |
|---|---|---|---|
| 发布状态 | 正在进行中 | 由执行发起人等待评审。 | 更改管理团队 |
| 发布登录 | | | |
| 发布日期 | | | |

有关使用Teams规划更改管理的详细信息，请[参阅为Microsoft Teams创建更改管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动| 说明| 节奏| 分配的团队 |
|---|---|---|---|
| 监视更改| 监视即将对Microsoft Teams服务所做的更改。| 每天||
| 规划更改| 评估并规划新功能和功能，包括通信计划、认知活动和培训。| 根据需要 ||
| 用户就绪情况| 执行有针对性的通信、感知或培训活动，以确保用户已准备好迎接即将到来的更改。| 根据需要 ||
| 支持团队就绪情况 | 执行有针对性的沟通、感知或培训活动，以确保支持团队已准备就绪。 支持团队可以包括“白手套”团队、支持人员、第 2 层或第 3 层支持、外部合作伙伴等。 | 根据需要 ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估Teams使用情况

初始试点开始后，必须建立一个定期的节奏来测量实际Teams使用情况。 这使组织能够深入了解实际使用情况如何与你在构想阶段预测的使用情况保持一致。 虽然本部分重点介绍Teams使用情况，但这应该是衡量和评估总体Microsoft 365或Office 365使用情况的更广泛努力的一部分。

在部署早期频繁查看使用情况可让你有机会：

- 验证用户是否正在使用Teams。

- 在在整个组织中创建关键问题之前，确定潜在的采用挑战。

- 了解构想阶段要求与实际使用情况之间是否存在差异。

如果使用情况不是你所期望的，这可能是由于部署问题，或者采用计划未正确执行或其他问题。 根据低使用率背后的实际原因，管理员必须与相关团队协作，以帮助消除使用障碍。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 管理中心度量使用情况

报表仪表板中提供了来自Teams的使用情况数据。 Teams使用情况数据可以在三个不同的报表中找到。 第一个报表提供了用户如何通过在Microsoft 365或Office 365中使用各种服务进行通信和协作的跨产品视图。 可在此处找到此报表：[Microsoft 365管理中心中的报表 - 活动用户](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他两个报表Teams特定，它们从用户和设备的角度提供有关Teams使用情况的更多详细信息。 可在此处找到这两个报表：

[Microsoft Teams 设备使用情况报告](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Microsoft Teams 用户活动报告](/microsoft-365/admin/activity-reports/microsoft-teams-user-activity-preview)

#### <a name="required-permissions"></a>所需权限

管理员中心中的使用情况报告可由已分配 **全局管理员角色或** 产品特定管理员角色的人员访问， (**Exchange管理员**、**Skype for Business管理员****、SharePoint管理员**) 。

此外， **报表读取者** 角色适用于需要访问报表但不执行任何需要管理员级权限的任务的用户。 你将此角色分配给任何利益干系人提供使用情况报告，以监视和推动采用。 有关可用的不同角色的详细信息，[请参阅关于Microsoft 365管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

使用“报告”仪表板测量使用情况后，请务必将测量使用情况与在项目构想阶段定义的任何关键成功指标 (KSI) 进行比较。 可以定义可能定义为活动使用情况的 KSI，或间接链接到活动使用情况的 KSI。

在恢复向其他网站或用户推出之前，请务必确定实际使用情况和计划使用情况之间的任何差异。 你可能会将组织学习确定为此活动的一部分，你可以利用这些学习来确保下一批网站或用户不会遇到相同的问题。

首先，确定这是采用问题还是技术问题。 首先，请调查以下项，以确定问题所在位置。

1. 通过执行 [体验质量评审](upgrade-monitor-quality.md)来验证质量。

2. 与支持团队合作，检查是否有阻止用户访问或使用服务的趋势技术问题。 如果问题趋势确实存在，请使用本文后面的 [终结点故障排除](#endpoint-troubleshooting) 部分，尝试在获得支持之前解决问题。

3. 请与培训和采用团队合作，收集用户的直接反馈 (请参阅本文后面) 评估 [用户情绪](#assess-user-sentiment) ，并检查认知和采用活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 度量使用情况 (启用阶段)  | 在启用阶段继续载入站点时，测量和评估Teams使用情况。 根据需要解决使用问题。 | 每周 | |
| 度量值使用情况 | ) 完成部署后，在驱动器值阶段 (度量和评估Teams使用情况。 根据需要解决使用问题。 | Biweekly | |
|  (驱动器值阶段)  | | | |
| 更新采用计划 | 根据测量的使用情况与规划目标的比较，更新采用计划。 | 根据需要 | |

### <a name="references"></a>References

[关于Microsoft 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 管理中心中的活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户情绪

了解用户情绪可以作为衡量Teams部署成功的关键指标。 用户反馈可以推动组织中的更改;这可能包括对通信计划、培训计划或向用户提供支持的方式的更改。

请务必尽早获得反馈，并继续评估整个项目生命周期及更高版本的用户情绪。 使用以下指南确定组织寻求反馈的时间间隔：

- **项目开头**：通过在项目开始时评估用户情绪，可以提前了解用户对其Teams体验的感受。

- **在重大里程碑之后**：通过在整个项目生命周期中收集反馈，可以持续评估用户情绪并根据需要进行更改。 这在重大里程碑之后特别有用。

- **Project结论**：在项目结束时评估用户情绪会告诉你你做得有多好，工作在哪里仍需要完成，并允许你将结果与上一次调查进行比较。

- **持续**：继续无限期地衡量用户情绪。 用户情绪的变化可能是由于组织环境的变化或Teams服务的变化。 通过定期衡量用户情绪，可以了解服务管理团队的性能以及组织如何响应Teams服务中的更改。

可以通过许多不同的方法评估用户情绪。 这些可以包括电子邮件调查、亲自或电话式访谈，或者只是在Teams或Yammer中创建反馈频道。 有关详细信息，请参阅[Microsoft Teams中用户反馈方法的最佳做法](best-practices-feedback.md)。

还可以使用全行业的方法来评估名为“net promotor score”的用户情绪 (NPS) ，如下一部分所述。

### <a name="nps"></a>NPS

NPS)  (净促进者分数是全行业客户忠诚度指标，也是用于评估用户情绪的好方法。 可以通过提出两个问题来计算 NPS：“你向同事推荐Teams的可能性有多大？”

NPS 是一个从 –100 到 100 不等的索引，用于衡量客户推荐公司产品或服务的意愿。 NPS 基于通过电子邮件或其他电子方式传递给用户的匿名调查。 NPS 衡量提供商与使用者之间的忠诚度。 它只包含一个问题，要求用户对其体验从 1 到 10 进行评分，并选择提供其他注释。 然后根据以下分级对用户进行分类：

- 9 或 10 是推广者：忠诚的爱好者，他们将促进你的服务和燃料他人。

- 7 或 8 是被动的：满足但不热情，容易受到其他服务或产品/服务的影响。

- 从 1 到 6 是诋毁者：不愉快的客户可能会损害你的服务并阻碍增长。

![演示 NPS 缩放的图表。](media/operate-my-service-image2.png "此图演示 NPS 规模。它显示 0 到 6 的排名是诋毁者，7 到 8 是被动的，9 到 10 是推广者。")

尽管基本 NPS 数非常有用，但分析用户注释可以获得最大的价值。 它们将帮助你了解用户为何 (或不) 向其他人推荐Teams。 这些意见可以提供有价值的反馈，帮助项目或服务管理团队了解提供优质服务所需的调整。

若要向组织提供 NPS 调查，可以利用你喜欢的在线调查工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 评估用户情绪 | 使用调查或访谈，或通过Teams或Yammer的反馈渠道捕获和评估用户情绪。 | 根据需要 | |
| 更新采用计划 | 根据用户反馈在组织中推动更改;这可以包括对通信计划、培训计划或向用户提供支持的方式的更改。 | 根据需要 | |

### <a name="references"></a>References

[Net Promoter 分数](https://en.wikipedia.org/wiki/Net_Promoter)

[使用Yammer收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈的最佳做法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心规划元素将进入优化、调整大小和修正网络基础结构，以确保获得高质量、高效的Microsoft Teams服务路径。 我们的 [网络就绪](prepare-network.md) 指南介绍了规划任务和要求。 由于升级、扩展或其他业务要求，网络通常会随时间推移而发展。 请务必考虑网络规划活动中Teams的要求。

尽管网络规划是Teams部署的一个关键方面，但同样重要的是，根据不断变化的业务或技术要求，确保网络保持正常运行并保持最新状态。

为了确保网络的运行状况，需要定期执行许多操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 监视Microsoft 365或Office 365 IP 和 URL | 使用提供的 [RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)监视[对Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)的任何更改，并启动对适用网络组的更改请求。 | 每天 | |
| 根据对Microsoft 365或Office 365 IP 和 URL 的更改更新网络 |  (防火墙、代理服务器、VPN、客户端防火墙等) 对适用的网络组件进行更新，以反映[对Office 365 URL 和 IP 地址范围的](/microsoft-365/enterprise/urls-and-ip-address-ranges)更改。 | 根据需要 | |
| 提供生成数据 | 向质量冠军 (或相关利益干系人) 提供更新的子网信息，以确保 [CQD 中的生成定义](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 保持最新。 | 根据需要 | |
| 实现更改 | 在网络上实施更改，以支持更改Teams业务和技术要求。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线网络和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul> | 根据需要 | |
| 网络监视和报告 | 使用网络提供商提供的现有第三方网络管理工具和报告功能来监视网络端到端的可用性、利用率和容量趋势。 使用趋势数据进行网络容量规划。 | 每日、每周、每月 | |
| 容量规划 | 与Teams服务所有者协作，了解可能推动其他容量更改的业务和技术要求的变化。  | 根据需要 | |
| 网络故障排除和修正 | 协助Teams支持人员、服务所有者和关键利益干系人排查和修正与Teams连接、可靠性或质量相关的问题。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线网络和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul> | 根据需要 | |
| 灾难恢复和高可用性测试 | 定期在网络基础结构上执行高可用性和灾难恢复测试，以确保它符合 (SLA) 或服务级别协议 (SLA) Teams服务的既定服务级别目标。 | 每月 | |

### <a name="references"></a>References

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[生成数据架构](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估并确保质量

所有组织都需要一个组或个人来负责质量。 这是服务管理中最重要的角色。 质量冠军角色分配给对用户体验充满热情的人员或组。
此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的规模和复杂性，这可能是任何热衷于确保高质量用户体验的人员或组。

质量冠军利用现有的工具和记录的流程，例如呼叫质量仪表板 (CQD) 和[改进和监视Teams的呼叫质量](monitor-call-quality-qos.md)，监视用户体验、确定质量趋势，并在需要时驱动修正。
质量冠军应与各自的团队合作，推动补救行动，并向指导委员会报告进度和任何公开问题。

[改进和监视Teams的呼叫质量](monitor-call-quality-qos.md)包括在对改善用户体验影响最大的关键领域评估和提供修正指导的活动。 《质量体验评审指南》中提供的指南重点介绍如何使用 CQD Online 作为报告和调查每个领域的主要工具，重点是音频以最大限度地利用和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议你尽早提名质量冠军。 被提名后，他们应该开始熟悉[改进和监视Teams](monitor-call-quality-qos.md)和相关培训材料的通话质量中的内容。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 已分配团队 |
|---|---|---|---|
| 提名和训练质量冠军 ()  | 提名并训练质量冠军。 | 根据需要 | |
| 执行体验质量评审 (QR)  | 执行 QER 来确定质量和可靠性趋势，针对定义的目标进行审查，并向组织中的关键利益干系人报告。 | 部署期间每周每月 ()  | |
| 驱动器修正 | 根据 QER 评估和结果协调整个组织的修正工作。 | 根据需要 | |
| 更新 CQD 中的生成数据 | 对网络进行更改时，请更新或添加 CQD 中的新生成定义 (请[参阅Upload生成信息](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)) 。 | 根据需要 | |
| 填写质量冠军角色 | 组织中质量的端到端责任。 这包括：<ul><li>确保定期执行 QER。</li><li>向主要利益干系人报告质量状态。</li><li>确保生成数据定义是最新的。</li><li>协调整个组织的修正工作，确保用户具有高质量的Teams体验。</li></ul> | 每天 | |

### <a name="references"></a>References

[Upload生成信息](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[改进和监视Teams的呼叫质量](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

Microsoft Teams终结点可以定义为任何电脑、Mac、平板电脑或移动 (或运行Teams客户端的任何其他) 设备。 术语 *终结点* 不仅包括设备本身，还包括用户如何连接到设备，例如，使用设备的内置麦克风或扬声器、耳塞或优化的耳机。 部署终结点后，不能忘记终结点。 Teams终结点需要持续的护理和维护。 以下部分介绍要关注的特定区域。

### <a name="endpoint-requirements"></a>终结点要求

Teams的主要优势之一是客户端自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。 Teams移动应用通过各自的应用存储保持最新状态。

Teams客户端在基础软件平台方面具有最低要求。 这些要求可能会随时间推移而变化，因此监视这些要求以进行更改非常重要。 例如，Teams客户端具有最小iOS版本。 如果客户端使用 Internet 浏览器，则浏览器也需要保持最新状态。 可在 [Get 客户](get-clients.md)端中找到支持Microsoft Teams平台的列表。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙可能会影响呼叫质量，甚至会阻止建立呼叫。 配置客户端防火墙上的适当排除项后，需要根据[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的信息保持最新。 第三方供应商将提供有关如何更新排除项的具体指导。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

Wi-Fi驱动程序可能会有问题。 例如，驱动程序在访问点之间可能具有非常激进的漫游行为，这可能会导致不必要的访问点切换，导致调用质量不佳。 性能不佳的Wi-Fi驱动程序可能通过体验质量评审发现 (请参阅[改进和监视Teams的呼叫质量](monitor-call-quality-qos.md)，以获取更多详细信息) 。 必须实施质量驱动过程，监视新的Wi-Fi驱动程序，并确保在部署到一般用户群体之前对其进行测试。

### <a name="endpoint-management"></a>终结点管理

应提供和维护支持的终结点和接口设备的目录 (，例如耳机) 。 此目录将包括作为构想和载入阶段的一部分选择和验证的已批准设备的列表。 通常，为组织中的每个角色类型选择特定设备以满足该角色属性的需求。 所有终结点都有生命周期，你需要管理与这些设备关联的供应商合同、保修、更换、分发和修复策略。

### <a name="endpoint-troubleshooting"></a>终结点故障排除

即使你遵循了前面的指南，组织中的用户仍可能会遇到Teams问题。 尽管问题可能与终结点本身不相关，但问题症状通常通过客户端向用户显示。 以下指南旨在提供解决该问题的一般步骤;这不是一个全面的故障排除指南。 这些步骤按特定顺序提供，但不必显式执行，也可能不适用，具体取决于问题的性质。

1. **验证服务运行状况：** 用户可能遇到的问题可能与对Teams服务或其依赖服务产生负面影响的事件相关。 作为第一步，我们建议确认没有活动服务问题。 请参阅[如何检查Microsoft 365服务运行状况](/office365/enterprise/view-service-health)。 请记住检查依赖服务的状态 (例如，Exchange、SharePoint、OneDrive for Business) 。 上一部分的“ [监视服务运行状况”](#monitor-service-health)更详细地讨论了对服务运行状况的监视。

2. **验证客户端连接：** 连接问题会导致Teams中的功能或登录问题。 我们建议 (，尤其是对于验证与服务连接) 的新站点或位置。 确保针对每个站点遵循以下[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)指南。 可以利用 [Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)执行连接测试，以验证是否已正确打开媒体端口以实现Teams功能。 [网络就绪](prepare-network.md)指南中提供了有关如何运行连接测试的详细步骤。

3. **检查已知问题列表：** 请 [参阅Teams疑难解答](/MicrosoftTeams/troubleshoot/teams)，以确定用户是否受到其中一个问题的负面影响。 如果有一个) 来解决问题，请按照 (提供的解决方法进行操作。

4. **访问Microsoft Teams社区：**[Microsoft Teams社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)为Teams提供专用空间。 Teams社区提供以Teams为中心的讨论列表、博客文章和公告。 可以帖子问题，或者搜索之前的讨论以找到问题的解决方案。

5. **联系Microsoft 支持部门：** 可以联系Microsoft 支持部门在线或通过电话Teams的问题。 有关信息，请参阅[业务产品的联系人支持 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)。 对于顶级客户，可按照联系[支持Microsoft Teams (顶级客户) ](https://support.microsoft.com/premier/contacts)指南启动支持请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 终结点要求 | 确保Teams终结点继续满足 Get [客户](get-clients.md)端中列出Microsoft Teams Teams的所有软件要求。 | 每月 | |
| 终结点防火墙 | 根据Office 365 [URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的信息，在终结点防火墙上维护适当的排除项。 第三方供应商将提供有关如何维护排除项的具体指导。 订阅 [RSS 源](https://support.office.com/o365ip/rss) 以自动收到更改通知。 | 根据需要 | |
| Wi-Fi 驱动程序 | 在电脑上测试和更新Wi-Fi驱动程序。 使用 CQD 验证结果 ([改进和监视Teams) 的调用质量](monitor-call-quality-qos.md)。 | 根据需要 | |
| 终结点管理 | 维护支持的终结点和接口设备的目录 (如耳机) 。 管理供应商合同、保修、分发、更换和修复策略。 | 每月 | |
| 终结点故障排除 | 故障排除任务可以包括验证连接性、咨询已知问题列表、日志收集、分析以及向Microsoft 支持部门或第三方供应商升级。 | 根据需要 | |

### <a name="references"></a>References

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[获取 Microsoft Teams 客户端](get-clients.md)

[Microsoft Teams社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[联系商业版产品的支持人员 - 管理员帮助](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[联系顶级支持人员](https://support.microsoft.com/premier/contacts)

[Teams视频疑难解答](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署Microsoft Teams服务后，需要执行多个与其管理相关的活动。 活动范围从管理服务和个人用户到容量规划和预配许可和电话号码。 以下部分介绍了其中一些常见的管理任务。

### <a name="service-administration"></a>服务管理

Teams服务具有多个可在租户范围内配置的设置。
对租户设置所做的更改会影响已启用Teams的所有用户。 有关这些设置的详细列表，请参阅[组织管理Microsoft Teams设置](enable-features-office-365.md)。

### <a name="user-administration"></a>用户管理

为了支持用户，组织可能需要任意数量的相关任务 - 特定任务因一个组织而异。 最终，这些任务需要由分配了这些操作职责的支持团队管理。 通常需要执行以下任务来支持Teams中的用户。

#### <a name="general-tasks"></a>常规任务

[管理 Microsoft Teams 的用户访问](user-access.md)

### <a name="team-creation-optional"></a>团队创建 (可选) 

默认情况下，具有邮箱Exchange Online的所有用户都有权创建Microsoft 365组，因此，Microsoft Teams中的团队。 如果希望更严格地控制和[限制新团队](assign-roles-permissions.md#permissions-to-create-teams) (的创建，从而) 创建新的Microsoft 365组，则可以将组创建和管理权限委托给一组管理员。 如果你的组织想要执行此选项，请参阅本文中所述的过程，以允许用户提交由分配的团队处理的请求。

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要的任务

| 活动 | 说明 | 节奏 | 分配的团队 |
|---|---|---|---|
| 服务管理 | 管理租户范围的Teams设置。 | 根据需要 | |
| 用户管理 | 管理Teams中基于用户的设置和许可。 | 根据需要 | |
| 许可证管理 | 利用 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 和 [PSTN 分钟池](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 报表，规划用户和基于消耗的许可 (呼叫计划和通信额度) 当前和未来需求。 | 每周 | |
| 电话号码管理 | 管理可用于未来增长的电话号码，并根据组织需求调整库存级别。 | 每周 | |
| 团队创建 (可选)  | 查看并处理团队创建请求。 | 根据需要 | |

<!--ENDOFSECTION-->