---
title: Microsoft Teams 操作指南
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Teams 服务管理所需的任务和活动，包括监视服务运行状况，以及评估和确保网络质量和使用情况。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2cea73868bbd6a974242e2a6f8c3d31730e087
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019438"
---
# <a name="operate-my-service"></a>操作服务

本文概述了为组织成功操作云语音服务的要求。 通过正确操作云语音服务，可以确保为组织提供高质量、可靠的体验。

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介

操作指南概述了作为 Microsoft Teams 服务管理功能一部分所需的所有任务和活动。

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams 服务包含 Microsoft 365 或 Office 365 以及部署在本地 (的基础结构组件，例如网络) 。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实现了与现有服务关联的进程和任务。 也就是说，在计划当前服务管理以在将来支持 Teams 时，可以增强当前流程。

服务管理包括端到端管理 Teams 所涉及的所有活动和过程。 如前所述，服务管理的某些组件（Microsoft 365 或Office 365服务本身包含的基础结构）是 Microsoft 的责任，而你（客户）则负责管理 Teams、网络和提供的终结点的各个方面。

本指南中的任务和活动分为八个类别，如下图所示。 以下各节将扩展其中每个类别。

![描述任务和活动类别列表的关系图。](media/operate-my-service-image1.png "描述 Teams 服务管理包含的任务和活动类别列表的关系图。此图还描绘了服务管理主要是客户任务。")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>决定如何为 Teams 实现操作。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>完整查看操作指南。</li><li>实施符合组织目标的运营策略，以提供云语音工作负载的质量和可靠性。</li><li>查看 [监视通话质量](monitor-call-quality-qos.md)。</li><li> 实施运营策略，定期执行体验质量评审，以确保云语音部署在其功能高峰期运行。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>可操作的角色映射

在构想阶段对操作进行规划至关重要，因为操作活动在启用第一个试点用户时开始。 本指南列出了必须每天、每周、每月或根据需要执行才能维护高质量 Teams 部署的活动和任务。 本指南提供有关如何执行这些关键活动和任务的知识和指导。

成功部署的一个关键组成部分是确保你在“构想”阶段早期执行的规划包括确定谁将负责执行特定活动。 确定哪些任务和活动适用于你的部署后，需要了解这些任务和活动，然后是你分配给它们的组或个人。

你确定的每个团队都必须查看并就确定的任务和职责达成一致，并开始准备。 这可能包括培训和准备情况、提供人员配置计划的更新，或确保外部提供商已准备好交付。

本指南中定义的活动和角色在大多数情况下都应有效，但每个 Teams 部署都是唯一的：因此，可以使用本指南作为起点来自定义活动和默认角色以满足需求。

确保每个负责团队都充分了解运行服务所需的活动。 在开始第一个试点之前，每个团队必须接受并在组织中签出其责任，这一点至关重要。

协议到位后，相应的团队应开始实施其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td>
<td><ul><li>使用本文档可促进操作角色映射练习。</li><li>与相应的支持团队会面，为所需活动列表中的每个项目分配名称。</li><li>获取已分配角色的接受或注销。</li><li>确保相应的团队具有相应的培训、准备和资源，以完成所需的活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams 服务依赖项

Microsoft Teams 将 Microsoft 365 或 Office 365 中的技术汇集在一起，为团队合作提供中心。 示例包括：

-   Azure Active Directory (Azure AD) 为 Teams 提供身份验证和授权服务。

-   Exchange Online提供法律保留和电子发现等高级功能。

-   SharePoint Online 提供在频道中共享文件的功能，OneDrive for Business提供了在私人聊天中共享文件的机制。

组织还可以利用本地基础结构中的现有投资。 例如，现有本地 Active Directory帐户可以通过利用 Azure AD Connect 进行身份验证。 某些版本的Exchange Server可用于代替Exchange Online。

这些技术结合在一起，为用户提供丰富、协作和智能的通信套件。 这种紧密集成是 Teams 的主要优势，但它也推动了跨这些技术进行服务管理的要求。

本指南介绍了管理 Teams 服务的关键领域。 最有可能的是，你已为 Teams 所依赖的支持技术制定服务管理计划。 否则，还需要为本地和联机)  (这些技术组件制定适当的服务管理计划。 这有助于确保用户享受高质量、可靠的 Teams 体验。

#### <a name="references"></a>References 

[Microsoft Teams 概述](teams-overview.md)

[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

[Microsoft Teams 和Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南活动

以下部分概述了成功运行 Microsoft Teams 服务所需的活动。 它们包括对工具、上下文信息和其他内容的引用，以帮助你了解活动并协助准备计划。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监视服务运行状况

请务必了解 Microsoft Teams 服务的整体运行状况，以便可以主动向组织中的其他人发出任何影响服务的事件的警报。 如前所述，Teams 依赖于其他 Microsoft 365 或Office 365服务，例如 Azure Active Directory、Exchange Online、SharePoint Online 和 OneDrive for Business。 因此，监视依赖服务的运行状况同样重要。

将此活动纳入事件管理流程，主动通知用户、支持人员和运营团队准备处理用户升级。

以下部分介绍可用于监视影响 Teams [服务的服务事件](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) 的工具。 下表中汇总了每种工具的优点，以及何时应使用每个工具。

| 监视工具                       | 优点                                            | 何时使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 管理中心                     | 可通过支持浏览器的任何设备使用。 | 在不需要实时通知时使用。                                          |
| Microsoft 365 或 Office 365 Admin 应用                  | 向移动设备提供推送通知。  | 在外出时需要收到服务事件的通知时使用。                  |
| Microsoft System Center               | 与 Microsoft System Center 集成。           | 需要高级监视功能和通知支持时使用。                       |
| Microsoft 365 或 Office 365 服务通信 API | 以编程方式访问 Microsoft 365 或 Office 365 服务运行状况。   | 需要与第三方监视工具集成或想要生成自己的解决方案时使用。 |

> [!NOTE]
> 只有分配有 **全局管理员** 或服务 **管理员** 角色的个人才能查看服务运行状况。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 管理中心进行监视

[Microsoft 365 管理中心](https://portal.office.com/)提供了[一个服务运行状况仪表板](https://portal.office.com/adminportal/home#/servicehealth)，你可以在其中查看 Teams 服务的当前运行状况以及依赖服务。

### <a name="monitoring-with-the-mobile-app"></a>使用移动应用进行监视

Microsoft 365 或 Office 365 Admin 应用在 Apple iOS、Android 和 Windows (电脑和移动) 上可用。 应用向服务管理员提供有关服务运行状况和即将进行的更改的信息。 该应用支持推送通知，这些通知在发布公告后几乎可以立即发出警报。 这有助于你随时了解服务的状态、运行状况和任何即将进行的更改。 通知支持使其成为管理员建议的监视工具。 有关详细信息，请参阅：

[Office 365 Admin移动应用](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载Office 365 Admin移动应用](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center 进行监视

Microsoft System Center 是一个集成管理平台，可帮助你管理数据中心、客户端设备和混合云 IT 环境。 Office 365使用 System Center 的管理员现在可以选择导入 Office 365 管理包，这样他们就可以在 System Center 中查看 Operations Manager 中的所有服务通信。 使用此工具可以访问已订阅服务的状态、活动和已解决的服务事件，以及消息中心通信 (即将发生的更改) 。 有关详细信息，请参阅以下 [博客文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果利用 System Center 监视 Teams 服务运行状况 (和依赖服务) ，则可以进一步自定义管理包，以对事件做出响应的特定组或个人发出警报或通知。
这些组可以包括组织中的服务所有者、支持人员、二级和三级支持组以及事件经理。

### <a name="monitoring-for-advanced-scenarios"></a>高级方案的监视

可以通过利用Office 365服务通信 API 以编程方式访问Office 365服务运行状况和更改来监视服务运行状况和即将发生的更改。 使用此 API 创建自己的监视工具，或连接现有监视工具以Office 365服务通信，从而可能简化监视环境的方式。 有关详细信息，请参阅[面向企业开发人员的Office 365](https://developer.microsoft.com/office)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                               | 节奏   | 已分配团队 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视服务运行状况 | 使用可用的工具主动监视 Microsoft Teams 服务运行状况、 (和相关服务) 。 相关服务包括：Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory。 | 实时 |               |
| 事件通知  | 将影响 Teams 服务的事件通知内部利益干系人。 内部利益干系人可以包括用户、支持人员和事件经理。                                                                          | 根据需要 |               |

### <a name="references"></a>References 

[如何检查Office 365服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[服务运行状况和连续性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理组织变更

Microsoft Teams 是基于云的服务。 随之而来的是，能够快速提供新的特性和功能。 持续创新为组织提供了明显的优势，但需要在组织内部适当地管理这些更改，以避免用户抵制或上报到支持人员。

Teams 汇报会自动向用户推出。 你的用户将始终拥有 Teams 服务中提供的最新客户端和功能。 无法管理向用户推出的 Teams 更新，因此，通过有效的沟通、培训和采用计划来管理更改至关重要。 如果用户了解了更改，了解了权益，并且能够利用新功能&mdash;，他们将能够更快地适应和欢迎更改。

### <a name="monitoring-for-change"></a>监视更改

变更管理的第一步是监视为 Teams 计划的更改。 监视这些更改的最佳来源是[Office 365路线图](https://products.office.com/business/office-365-roadmap)，其中列出了当前正在开发、正在向客户推出或已完全启动的功能。 可以使用提供的筛选器搜索特定于 Teams 的功能，也可以将路线图下载到 Excel 文件进行进一步分析。 对于每个功能，路线图都会提供简短说明以及预期的发布日期。

在 [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)中，可以了解有关 Teams 产品更新的最佳做法、趋势和新闻。 可在此处找到要宣布的 Teams 的主要功能更新。 还可以通过 RSS 源订阅博客。 然后，可以将 [RSS 源](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) 直接添加到 Teams 频道，以便所有重要新闻直接在 Teams 中传递。

[Microsoft Teams 发行说明](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)中记录了已发布的所有功能。
在这里，你将找到针对桌面、Web 和移动设备发布的功能列表。 [“帮助](get-help-in-microsoft-teams.md)”中的“**新增功能**”选项卡上也提供了同一组发行说明。

熟悉可用的资源，并确保分配适用的所有者来监视更改。

### <a name="planning-for-change"></a>规划更改

现在你已了解 Teams 服务即将进行的更改，下一步是相应地准备和规划。 评估每项更改，以确定哪些更改需要与用户沟通、认知活动、支持团队或用户培训，或功能评估和采用活动。 这是组织中变更管理团队的主要角色。 下面是一组示例表，可帮助你规划更改。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：云录制 (发布日期：2018 年 1 月) 

**常规轨道**

| 更改就绪情况 | 地位   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 法律审查   | 完成     | 此功能是加入培训团队的先决条件。 | 项目团队  |

**技术变更管理**

|       更改就绪情况       | 地位 |                      备注/后续步骤                      |    所有者     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     需要 IT 更改      |  是   | 管理员仅需要为已识别的用户启用录制。 | 支持团队 |
| 技术就绪性完成 |  是   |                                                            | 支持团队 |
|                              |        |                                                            |              |

**用户更改管理** 

| 更改就绪情况 | 地位   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 用户影响                  | 低                  |                                                                 |                        |
| 需要用户就绪情况      | 是                  |                                                                 |                        |
| 通信就绪         | 否                   | 通信电子邮件已起草， 等待审阅。            | 通信团队    |
| 训练就绪               | 是                  | 培训将利用现有的 Microsoft 视频。                | 培训团队          |

**状态跟踪**

| 更改就绪情况 | 地位   | 备注/后续步骤 | 所有者 |
|----|----|----|-----|
| 发布状态               | 正在进行中          | 正在等待执行发起人的审查。               | 变更管理团队 |
| 发布注销             |                      |                                                                 |                        |
| 发布日期                 |                      |                                                                 |                        |

有关使用 Teams 规划变更管理的详细信息，请参阅 [为 Microsoft Teams 创建变更管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                                | 节奏   | 已分配团队 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视更改     | 监视 Microsoft Teams 服务即将进行的更改。                                                                                                                                                                   | 每天     |               |
| 规划更改    | 评估和规划新的特性和功能，包括沟通计划、宣传活动和培训。                                                                                                     | 根据需要 |               |
| 用户就绪情况             | 执行有针对性的沟通、认知或培训活动，以确保用户为即将到来的更改做好准备。                                                                                                        | 根据需要 |               |
| 支持团队就绪情况 | 执行有针对性的沟通、宣传或培训活动，以确保支持团队已准备就绪。 支持团队可以包括“白手套”团队、支持人员、第 2 层或第 3 层支持、外部合作伙伴等。 | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估 Teams 使用情况

初始试点开始后，建立定期的节奏来衡量实际 Teams 使用情况至关重要。 这使你的组织能够深入了解实际使用情况如何与在“设想”阶段预测的使用情况保持一致。 虽然本部分侧重于 Teams 使用情况，但这应是衡量和评估总体Office 365使用情况的更广泛工作的一部分。

在部署早期经常查看使用情况可让你有机会：

-   验证用户是否正在使用 Teams。

-   确定潜在的采用挑战，然后再在整个组织中产生关键问题。

-   了解“构想阶段要求”与“实际使用情况”之间是否存在差异。

如果使用情况不符合预期，则可能是由于部署问题、未正确执行采用计划或其他问题造成的。 根据低使用量背后的实际原因，服务管理员必须与相关团队协作，以帮助消除使用障碍。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 管理中心测量使用情况

报表仪表板中提供了来自 Teams 的使用情况数据。 可以在三个不同的报表中找到 Teams 使用情况数据。 第一个报表提供了跨产品视图，说明用户如何使用 Office 365 中的各种服务进行通信和协作。 可在此处找到此报告：[Office 365活动用户报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他两个报表特定于 Teams，它们从用户和设备的角度提供了有关 Teams 使用情况的进一步详细信息。 可在此处找到这两个报表：

[Microsoft Teams 设备使用情况报告](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Microsoft Teams 用户活动报告](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>所需权限

已分配有 **全局管理员** 角色的人员或产品特定的管理员角色（ (**Exchange 管理员**、**Skype for Business管理员**、**SharePoint 管理员**) ）可以访问管理中心中的使用情况报告。

此外， **报表读取者** 角色适用于需要访问报表，但不执行任何需要管理员级权限的任务的用户。 分配此角色以向利益干系人提供使用情况报告，以监视和推动采用。 有关可用不同角色的详细信息，请参阅[关于Office 365管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

使用“报告”仪表板衡量使用情况后，请务必将测量的使用情况与在项目“构想”阶段定义 (KCI) 的任何关键成功指标进行比较。 可以定义可定义为活动使用情况的 KSI，也可以定义一个间接链接到活动使用情况的 KSI。

在继续向其他站点或用户推出之前，请务必确定实际使用情况和计划使用情况之间的任何差异。 你可能会将组织学习确定为此活动的一部分，可以利用这些知识来确保下一批网站或用户不会遇到相同的问题。

首先，查明这是采用还是技术问题。 首先调查以下各项，以确定问题所在。

1.  通过执行体验质量评审来验证质量 (有关更多详细信息) ，请参阅 [改进和监视 Teams 的通话质量](monitor-call-quality-qos.md) 。

2.  请与支持团队协作，检查是否存在阻止用户访问或使用服务的趋势性技术问题。 如果问题趋势确实存在，请使用本文后面的 [终结点故障排除](#endpoint-troubleshooting) 部分，在吸引支持人员之前尝试解决问题。

3.  请与培训和采用团队协作，从用户那里收集直接反馈 (请参阅本文后面的 [评估用户情绪](#assess-user-sentiment)) ，并检查认知和采用活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                         | 说明                                                                                                                      | 节奏   | 已分配团队 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 度量使用情况 (启用阶段)  | 在启用阶段继续加入网站时，测量和评估 Teams 使用情况。 根据需要解决使用问题。 | 每周    |               |
| 衡量使用情况 (驱动价值阶段)                            | 在部署完成) 后，测量和评估“驱动器价值”阶段 (Teams 使用情况。 根据需要解决使用问题。 | 每两周  |               |
| 更新采用计划             | 根据衡量的使用情况与规划目标相比，更新采用计划。                                         | 根据需要 |               |

### <a name="references"></a>References 

[关于Microsoft 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 管理中心中的活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户情绪

了解用户情绪可以作为衡量 Teams 部署成功的关键指标。 用户反馈可以推动组织中的更改;这可能包括对通信计划、培训计划或向用户提供支持的方式的更改。

请务必尽早获得反馈，并在整个项目生命周期及以后继续评估用户情绪。 使用以下指南确定组织寻求反馈的间隔：

-   **项目开始**：通过在项目开始时评估用户情绪，你可以提前了解用户对其 Teams 体验的感受。

-   **完成主要里程碑后**：通过收集整个项目生命周期的反馈，可以持续衡量用户情绪并根据需要进行更改。 这在主要里程碑之后特别有用。

-   **项目结论**：在项目结束时评估用户情绪将告知你已完成的工作程度以及需要完成哪些工作，并允许你将结果与上一个调查进行比较。

-   **持续**：继续无限期地衡量用户情绪。 用户情绪的更改可能是由于组织环境的变化或 Teams 服务中的更改。 通过定期测量用户情绪，可以了解服务管理团队的表现以及组织如何响应 Teams 服务中的更改。

可以通过许多不同的方法评估用户情绪。 这些可以包括电子邮件调查、亲自或电话式面试，或者只是在 Teams 或 Yammer 中创建反馈通道。 有关详细信息，请参阅 [Microsoft Teams 中用户反馈方法的最佳做法](best-practices-feedback.md)。

还可以使用全行业方法评估称为 net promotor 分数 (NPS) 的用户情绪，这将在下一部分进行介绍。

### <a name="nps"></a>Nps 

净推广器分数 (NPS) 是一种全行业客户忠诚度指标，也是评估用户情绪的好方法。 可以通过提出两个问题来计算 NPS：“你向同事推荐 Teams 的可能性有多大？”，然后是任意格式问题“为什么？”

NPS 是一个从 –100 到 100 的索引，用于衡量客户推荐公司产品或服务的意愿。 NPS 基于通过电子邮件或其他电子方式发送给用户的匿名调查。 NPS 衡量提供商和使用者之间的忠诚度。 它只包含一个问题，要求用户从 1 到 10 对其体验进行评分，并可以选择提供其他注释。 然后，根据以下分级对用户进行分类：

-   9 或 10 是推广者：忠诚的爱好者，他们将推广你的服务和燃料其他人。

-   7 或 8 是被动的：满意但无动于衷，容易受到其他服务或产品/服务攻击。

-   从 1 到 6 是诋毁者：可能会损害服务并阻碍增长的不满客户。

![演示 NPS 缩放的示意图。](media/operate-my-service-image2.png "此图演示了 NPS 规模。它表明，排名 0 到 6 是批评者，7 到 8 是被动的，9 到 10 是发起人。")

尽管基 NPS 编号很有用，但分析用户注释可以获得最大的价值。 它们将帮助你了解为什么用户会 (或不) 向其他人推荐 Teams。 这些注释可以提供有价值的反馈，以帮助项目或服务管理团队了解提供优质服务所需的调整。

若要向组织提供 NPS 调查，可以利用你最喜欢的在线调查工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动              | 说明                                                                                                                                                                         | 节奏   | 已分配团队 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 评估用户情绪 | 通过使用调查或采访，或通过 Teams 或 Yammer 中的反馈渠道来捕获和评估用户情绪。                                                                 | 根据需要 |               |
| 更新采用计划 | 根据用户反馈推动组织中的变革;这可以包括对通信计划、培训计划或向用户提供支持的方式的更改。 | 根据需要 |               |

### <a name="references"></a>References 

[净推广器分数](https://en.wikipedia.org/wiki/Net_Promoter)

[使用 Yammer 收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈的最佳做法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心规划元素都用于优化、调整大小和修正网络基础结构，以确保 Microsoft Teams 服务的高质量、高效路径。 [网络就绪指南](3-envision-evaluate-my-environment.md#network-readiness)中介绍了规划任务和要求。 由于升级、扩展或其他业务需求，网络通常会随时间推移而发展。 请务必在网络规划活动中考虑对 Teams 的要求。

尽管网络规划是 Teams 部署的一个关键方面，但同样重要的是，根据不断变化的业务或技术要求，确保网络保持正常运行并保持最新状态。

为了确保网络的运行状况，需要定期执行许多操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                                                       | 说明                                                                                                                                                                                                                                                                                                                                                                 | 节奏                | 已分配团队 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 监视Office 365 IP 和 URL                                | 使用提供的 [RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)监视[对Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)所做的任何更改，并向适用的网络组发起更改请求。                                                                                                                                | 每天                  |               |
| 根据对Office 365 IP 和 URL 的更改更新网络 | 对适用的网络组件进行更新， (防火墙、代理服务器、VPN、客户端防火墙等) 以反映[对Office 365 URL 和 IP 地址范围的](/microsoft-365/enterprise/urls-and-ip-address-ranges)更改。                                                                                                                                                              | 根据需要              |               |
| 提供建筑数据                                          | ) 向质量支持者 (或相关利益干系人提供更新的子网信息，以确保 [CQD 中的生成定义](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 保持最新。 | 根据需要              |               |
| 实现更改                                               | 在网络上实施更改，以支持不断变化的 Teams 业务和技术要求。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>     | 根据需要              |               |
| 网络监视和报告                               | 使用网络提供商提供的现有第三方网络管理工具和报告功能，端到端监视网络的可用性、利用率和容量趋势。 使用趋势数据进行网络容量规划。                                                                                                            | 每日、每周、每月 |               |
| 容量规划                                              | 与 Teams 服务所有者协作，了解不断变化的业务和技术要求，这些要求可能会推动其他容量更改。                                | 根据需要              |               |
| 网络故障排除和修正                        | 协助 Teams 支持人员、服务所有者和关键利益干系人排查和修正与 Teams 连接、可靠性或质量相关的问题。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>    | 根据需要              |               |
| 灾难恢复和高可用性测试                | 对网络基础结构执行定期的高可用性和灾难恢复测试，以确保它满足 (SLO) 或服务级别协议 (Teams 服务的 SLA) 中所述的服务级别目标。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>References 

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[生成数据架构](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估和确保质量 

所有组织都需要一个组或个人对质量负责。 这是服务管理中最重要的角色。 质量拥护者角色分配给对用户体验充满热情的个人或组。
此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的规模和复杂性，这可能是任何对确保高质量用户体验充满热情的人或组。

质量支持者利用现有工具和记录的流程（如通话质量仪表板 (CQD) ）来监视用户体验、识别质量趋势，并在需要时推动修正。
质量支持者应与各自的团队合作，推动修正行动，并向指导委员会报告进度和任何悬而未决的问题。

阅读 [改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)，其中介绍了在对改善用户体验影响最大的关键领域评估和提供修正指导的活动。 本文中提供的指南重点介绍如何使用 CQD 作为报告和调查每个领域的主要工具，重点介绍音频以最大程度地提高采用率和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

强烈建议尽早提名质量冠军。 获得提名后，他们应开始熟悉 [监视通话质量](monitor-call-quality-qos.md) 内容和相关培训材料。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                               | 说明                                                                                                                                                                                                                                                                                                 | 节奏                             | 已分配团队 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名和培养质量冠军 ()  | 提名和培养质量冠军。                                                                                                                                                                                                                                                                   | 根据需要                           |               |
|  (QR) 执行体验质量评审     | 执行 QER 以确定质量和可靠性的趋势，根据定义的目标进行评审，并向组织中的关键利益干系人报告。                                                                                                                            | 部署期间每月 ()  |               |
| 驱动器修正                      | 根据 QER 评估和发现在整个组织中协调修正工作。                                                                                                                                                                                                           | 根据需要                           |               |
| 更新 CQD 中的生成数据            | 在对网络进行更改时，更新或添加新的 CQD 中的生成定义 (请参阅 [) 上传建筑物信息](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 。 | 根据需要                           |               |
| 填补质量冠军角色      | 组织中质量的端到端责任。 这包括：<ul><li>确保定期执行 QER。</li><li>向关键利益干系人报告质量状态。</li><li>确保生成数据定义是最新的。</li><li>协调整个组织的修正工作，以确保用户获得高质量的 Teams 体验。</li></ul>          | 每天                               |               |



### <a name="references"></a>References 


[在 CQD 中上传租户和生成数据](CQD-upload-tenant-building-data.md)

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

Microsoft Teams 终结点可以定义为任何电脑、Mac、平板电脑或移动 (，或者运行 Teams 客户端的任何其他) 设备。 术语 *终结点* 不仅包括设备本身，还包括用户连接到设备的方式，例如，通过使用设备的内置麦克风或扬声器、耳机或优化的头戴显示设备。 部署终结点后，不得忘记终结点。 Teams 终结点需要持续维护。 以下部分介绍了要关注的特定领域。

### <a name="endpoint-requirements"></a>终结点要求

Teams 的主要优势之一是客户端会自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。 Teams 移动应用通过各自的应用商店保持最新状态。

Teams 客户端对基础软件平台有最低要求。 这些要求可能会随着时间而变化，因此请务必监视这些要求的变化。 例如，Teams 客户端具有最低 iOS 版本。 如果客户端使用 Internet 浏览器，则浏览器也需要保持最新状态。 可以在 [获取 Microsoft Teams 的客户端](get-clients.md)中找到受支持的平台列表。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙可能会影响呼叫质量，甚至阻止建立呼叫。 在客户端防火墙上配置了相应的排除项后，需要根据[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的信息来使这些排除项保持最新。 第三方供应商将提供有关如何更新排除项的具体指南。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

Wi-Fi驱动程序可能存在问题。 例如，驱动程序可能在接入点之间具有非常激进的漫游行为，这可能会导致不必要的接入点切换，从而导致通话质量不佳。 可以通过体验质量评审发现性能不佳的Wi-Fi驱动程序 (请参阅 [改进和监视 Teams 的通话质量](monitor-call-quality-qos.md) ，了解更多详细信息) 。 必须实施质量驱动流程，以监视新的Wi-Fi驱动程序，并确保在部署到普通用户群体之前对其进行测试。

### <a name="endpoint-management"></a>终结点管理

应提供和维护受支持的终结点和接口设备 (目录，例如头戴显示设备) 。 此目录将包括已选择并验证为“构想”和“载入”阶段的一部分的已批准设备的列表。 通常，为组织中的每种角色类型选择特定设备，以满足该角色属性的需求。 所有终结点都有一个生命周期，你需要管理与这些设备关联的供应商合同、保修、更换、分发和维修策略。

### <a name="endpoint-troubleshooting"></a>终结点故障排除

即使已遵循前面的指南，组织中的用户仍可能会遇到 Teams 问题。 尽管问题可能不出在终结点本身，但问题的症状通常通过客户端显示给用户。 以下指南旨在提供解决问题时可以采取的一般步骤：它并不是一个全面的故障排除指南。 这些步骤按特定顺序提供，但不必显式遵循这些步骤，并且可能不适用，具体取决于问题的性质。

1.  **验证服务运行状况：** 用户可能遇到的问题可能与对 Teams 服务或其依赖服务产生负面影响的事件相关。 第一步，建议确认没有活动服务问题。 请参阅[如何检查Office 365服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    请记住检查依赖服务的状态 (例如 Exchange、SharePoint OneDrive for Business) 。 在上一节监视服务运行状况中更详细地讨论了 [对服务运行状况的监视](#monitor-service-health)。

2.  **验证客户端连接：** 连接问题会导致 Teams 中的功能或登录问题。 我们建议 (，特别是对于验证与服务的连接) 的新站点或位置。 确保为每个站点遵循以下[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)指南。 可以利用 [Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) 执行连接测试，以验证是否已为云语音功能正确打开媒体端口。 [网络就绪指南](3-envision-evaluate-my-environment.md#network-readiness)中提供了有关如何运行连接测试的详细步骤。

3.  **检查已知问题列表：** 请参阅 [Teams 故障排除](/MicrosoftTeams/troubleshoot/teams) ，以确定用户是否受到这些问题之一的负面影响。 如果存在一个) 来解决此问题，请遵循 (提供的解决方法。

4.  **访问 Microsoft Teams 社区：**[Microsoft Teams 社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)为 Teams 提供专用空间。 Teams 社区提供以 Teams 为中心的讨论列表、博客文章和公告。 可以发布问题或搜索以前的讨论，以获取问题的解决方案。

5.  **联系Microsoft 支持部门：** 如果 Teams 联机或电话出现问题，可以联系 Microsoft 支持部门。 有关信息，请参阅 [联系商业产品的支持人员](/microsoft-365/admin/contact-support-for-business-products)。
    对于顶级客户，可以按照 [联系 Microsoft Teams 支持 (顶级客户) ](https://support.microsoft.com/premier/contacts)中的指导启动支持请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                 | 说明                                                                                                                                                                                                                                                                                                                                                                     | 节奏   | 已分配团队 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 终结点要求    | 确保 Teams 终结点继续满足 [获取 Microsoft Teams 客户端](get-clients.md)中列出的 Teams 的所有软件要求。                                                                                                                                                                                       | 每月   |               |
| 终结点防火墙       | 根据[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的信息，在终结点防火墙上维护适当的排除项。 第三方供应商将有有关如何维护排除项的具体指导。 订阅 [RSS 源](https://support.office.com/o365ip/rss) ，以自动收到更改通知。 | 根据需要 |               |
| Wi-Fi 驱动程序            | 在电脑上测试和更新Wi-Fi驱动程序。 使用 CQD ([改进和监视 Teams) 的通话质量](monitor-call-quality-qos.md) 来验证结果。                                                                                                                                                                                                                                                                   | 根据需要 |               |
| 终结点管理      | 维护支持的终结点和接口设备的目录 (，例如头戴显示设备) 。 管理供应商合同、保修、分发、更换和维修策略。                                                                                                                                                                                                        | 每月   |               |
| 终结点故障排除 | 故障排除任务可能包括验证连接性、咨询已知问题列表、日志收集、分析和上报给Microsoft 支持部门或第三方供应商。                                                                                                                                                                                               | 根据需要 |               |

### <a name="references"></a>References 

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[获取 Microsoft Teams 客户端](get-clients.md)

[Microsoft Teams 社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[联系商业版产品的支持人员 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)

[联系顶级支持人员](https://support.microsoft.com/premier/contacts)

[Teams 故障排除视频](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署 Microsoft Teams 服务后，需要执行与其管理相关的多项活动。 活动范围从管理服务和单个用户到容量规划和预配许可和电话号码。 以下部分介绍其中一些常见管理任务。

### <a name="service-administration"></a>服务管理

Teams 服务具有多个可在租户范围内配置的设置。
对租户设置所做的更改会影响已启用 Teams 的所有用户。 有关这些设置的详细列表，请参阅 [管理组织的 Microsoft Teams 设置](enable-features-office-365.md)。

### <a name="user-administration"></a>用户管理

为了支持用户，组织可能需要任意数量的相关任务，具体任务因组织而异。 最终，这些任务需要由已分配了这些操作职责的支持团队管理。 支持 Teams 中的用户通常需要以下任务。

#### <a name="general-tasks"></a>常规任务

[管理 Microsoft Teams 的用户访问](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>电话系统的常见任务

[为用户分配、更改或删除电话号码](./assign-change-or-remove-a-phone-number-for-a-user.md)

[为用户分配或更改紧急地址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[为你的组织添加、更改或删除紧急位置](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[创建并管理拨号计划](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>音频会议的常见任务

[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)

[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>许可证管理

随着组织的发展或合同的发展，规划许可以满足当前和未来的需求非常重要。 除了云语音功能[电话系统和](here-s-what-you-get-with-phone-system.md)[音频会议](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing)许可外，还有一个基础 Teams 许可证。

对于 Teams，电话系统许可证需要关联的 [通话套餐](calling-plan-landing-page.md) 许可证。 通话套餐许可使你能够拨打和接听国内和/或国际电话。 这些计划基于使用情况，并具有与之关联的分钟池。 预配 [通信额度](what-are-communications-credits.md) 可确保服务永不耗尽。

音频会议允许收费电话拨入式会议和国内电话拨出式会议服务。 免费电话拨入式会议或非国内拨出方案可能会导致产生需要 [通信额度](what-are-communications-credits.md) 的额外费用。

通信额度可以补充通话套餐和音频会议许可证。 通话套餐许可证和通信额度都是基于使用情况的，因此需要相应地进行监视和预配。

可以利用 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 来监视通话套餐分钟数和通信额度的使用情况。 根据此活动的结果，可以相应地调整许可。 即将推出，我们将提供 [PSTN 分钟池](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 报告，以更有效地协助完成此任务。

### <a name="telephone-number-management"></a>电话号码管理

在 Teams 中获取号码有两种方法：可以从其他提供商转网电话号码，也可以直接从 Microsoft 的号码清单预配号码。 [获取用户的电话号码](getting-phone-numbers-for-your-users.md)中介绍了这两种方法。

可以从 Microsoft 的号码清单中预配的电话号码数量有限制。 这些限制由 [你可以获取多少个电话号码？](how-many-phone-numbers-can-you-get.md)中详述的许多因素决定。
限制取决于号码类型（免费服务号码、收费服务号码和订阅者 (用户) 号码）。 每个都有其自己的限制，必须独立管理。 如果接近限制 (或已达到限制) ，则可以申请限制的增量。 此过程在上一段的文章中介绍。

有时，在服务可用的区域中，可能无法预配数字。 有关请求号码的过程的信息，请参阅 [管理组织的电话号码](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>团队创建 (可选) 

默认情况下，邮箱位于 Exchange Online 的所有用户都有权创建 Microsoft 365 组，因此在 Microsoft Teams 中创建团队。 如果想要更严格地控制并 [限制 (创建新团队](assign-roles-permissions.md) ，从而) 创建新的 Microsoft 365 组，可以将组创建和管理权限委托给一组管理员。 如果你的组织想要使用此选项，请参阅本文中所述的过程，以允许用户提交由分配的团队处理的请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                    | 说明                                                                                                                                                                                                                                                                                                                                                                                                             | 节奏   | 已分配团队 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服务管理      | 管理租户范围的 Teams 设置。                                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 用户管理         | 在 Teams 中管理基于用户的设置和许可。                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 许可证管理          | 利用 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 和 [PSTN 分钟池](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 报告，) 规划基于用户和基于使用的许可 (通话套餐和通信额度的当前和未来需求。 | 每周    |               |
| 电话号码管理 | 管理可用于未来增长的电话号码，并调整库存级别以满足组织需求。                                                                                                                                                                                                                                                                                                | 每周    |               |
| 团队创建 (可选)     | 查看和处理团队创建请求。                                                                                                                                                                                                                                                                                                                                                                          | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>改进和监视通话质量

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md) 包括一组活动，这些活动在对改善用户体验影响最大的关键领域进行评估并提供修正指导，如下所示。

![在体验质量评审期间要检查的区域示意图。](media/plan-my-service-management-image2.png "在体验质量评审期间要检查的关键领域：音频、可靠性和用户调查结果。")

通过持续评估和修正指南中所述的领域，可以降低它们对用户体验产生负面影响的可能性。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

[改进和监视 Teams 的通话质量](monitor-call-quality-qos.md)中提供的指南侧重于使用通话质量仪表板 (CQD) Online 作为报告和调查所描述的每个领域的主要工具，并重点介绍音频以最大程度地提高采用率和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

强烈建议你尽早提名质量冠军。 获得提名后，他们应开始熟悉 [改进和监视 Teams 通话质量](monitor-call-quality-qos.md)中的内容。

<!--ENDOFSECTION-->