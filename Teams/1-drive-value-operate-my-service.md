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
description: 管理服务管理Teams和活动，包括监视服务运行状况，以及评估和确保网络质量和使用情况。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8376f6d2c385f2c7feee3c7051d7978e1deb04b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633446"
---
# <a name="operate-my-service"></a>操作服务

本文概述了为组织成功运行云语音服务的要求。 通过正确操作云语音服务，你可以确保为组织提供高质量、可靠的体验。

## <a name="introduction-to-the-operations-guide"></a>《操作指南》简介

操作指南概述了作为服务管理功能的一部分所需的所有任务和活动，Microsoft Teams。

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams服务包括Microsoft 365或Office 365部署在本地的基础结构组件，例如 (网络) 。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已实现与现有服务关联的进程和任务。 也就是说，如果现在计划进行服务管理以支持将来的服务管理，Teams当前进程。

服务管理包含端到端管理Teams的所有活动和流程。 如前所述，服务管理的一些组件（Microsoft 365 或 Office 365 服务本身包含的基础结构）由 Microsoft 负责，而客户负责管理 Teams、网络和提供的终结点的各个方面。

本指南中的任务和活动分为八个类别，如下图所示。 以下各节将扩展其中每个类别。

![描述任务和活动类别列表的图表](media/operate-my-service-image1.png "一个图表，描绘了服务管理部门所构成的任务和活动Teams列表。该图还描绘了服务管理在很大程度上是一项客户任务。")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定如何为任务实现Teams。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>完整查看操作指南。</li><li>实施与组织的目标相一致的运营策略，以提供云语音工作负荷的质量和可靠性。</li><li>查看["监视呼叫质量"。](monitor-call-quality-qos.md)</li><li> 实施运营策略，定期执行体验质量评审，确保云语音部署以峰值功能运行。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>可操作的角色映射

在"构想"阶段对操作进行规划至关重要，因为操作活动在启用第一个试点用户时开始。 本指南列出了必须每天、每周、每月或根据需要执行的活动和任务，以保持高质量的Teams部署。 本指南提供有关如何执行这些关键活动和任务的知识和指导。

成功部署的一个重要组成部分是确保在"构想"阶段早期进行的计划包括确定谁将负责执行特定活动。 确定哪些任务和活动适用于部署后，需要理解这些任务和活动，并关注分配给这些任务和活动的组或个人。

你标识的每个团队必须审阅并同意确定的任务和责任并开始准备。 这可能包括培训和准备情况、提供人员配备计划的更新，或确保外部提供商已准备好交付。

本指南中定义的活动和角色在大多数方案中都应有效，但每个Teams都是唯一的;因此，可以使用本指南作为起点来自定义活动和默认角色以满足需求。

确保每个负责团队对运行服务所需的活动有一个很好的了解。 第一次试点开始前，每个团队必须接受并签署组织中的责任，这一点至关重要。

协议到位后，相应的团队应开始实施其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td>
<td><ul><li>使用本文档促进操作角色映射练习。</li><li>与相应的支持团队会面，为所需活动列表中的每个项目分配名称。</li><li>接受或签收已分配的角色。</li><li>确保相应的团队具有适当的培训、准备情况和资源，以完成所需的活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams服务依赖项

Microsoft Teams将跨团队或Microsoft 365技术Office 365为团队合作提供中心。 示例包括：

-   Azure Active Directory (Azure AD) 为用户提供身份验证和授权Teams。

-   Exchange Online提供高级功能，例如法定保留和电子发现。

-   SharePointOnline 提供在频道中共享文件的能力，OneDrive for Business提供在私人聊天中共享文件的机制。

组织还可以利用本地基础结构的现有投资。 例如，可以使用现有的本地 Active Directory 帐户通过利用 Azure AD 连接。 某些版本的Exchange Server可用于Exchange Online。

这些技术共同为用户提供丰富、协作和智能的通信套件。 这种紧密的集成是服务Teams的主要优势，但它也驱动了对这些技术的服务管理的要求。

本指南介绍管理服务服务的主要Teams领域。 很可能，你已针对所依赖的支持技术Teams计划。 如果没有，则还需要为本地和联机服务 (技术组件建立) 计划。 这将帮助确保你的用户享受使用 Teams 的高质量、可靠的体验。

#### <a name="references"></a>References 

[Microsoft Teams 概述](teams-overview.md)

[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

[Microsoft Teams和Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南活动

以下部分概述了成功运行 Microsoft Teams 服务所需的活动。 其中包括对工具、上下文信息和其他内容的引用，以帮助你了解活动并帮助完成准备计划。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监视服务运行状况

必须了解服务的总体运行状况Microsoft Teams，以便可以主动提醒组织中其他人任何影响该服务的事件。 如上所述，Teams依赖于其他 Microsoft 365 或 Office 365 服务，例如 Azure Active Directory、Exchange Online、SharePoint Online OneDrive for Business。 因此，监视依赖服务的运行状况也同样重要。

将此活动纳入事件管理流程，主动通知用户、支持人员和运营团队，准备处理用户升级。

以下部分介绍可用于监视影响服务服务的服务Teams的工具。 [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) 下表汇总了每个工具的好处，以及何时应该使用每个工具。

| 监视工具                       | 优点                                            | 何时使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 管理中心                     | 可从具有受支持浏览器的任何设备使用。 | 在不需要实时通知时使用 。                                          |
| Microsoft 365 或 Office 365 Admin 应用                  | 向移动设备提供推送通知。  | 在需要获得服务事件通知时，使用 。                  |
| Microsoft System Center               | 与 Microsoft System Center 集成。           | 当需要高级监视功能和通知支持时，请使用 。                       |
| Microsoft 365或 Office 365 Service Communications API | 以编程方式Microsoft 365或Office 365运行状况。   | 当需要集成第三方监视工具或想要构建自己的解决方案时，请使用 。 |

> [!NOTE]
> 只有分配有全局管理员 **或** 服务管理员角色 **的个人** 可以查看服务运行状况。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用监视Microsoft 365 管理中心

该[Microsoft 365 管理中心](https://portal.office.com/)提供了[一个](https://portal.office.com/adminportal/home#/servicehealth)服务运行状况仪表板，可在其中查看除依赖服务Teams服务当前运行状况。

### <a name="monitoring-with-the-mobile-app"></a>使用移动应用进行监视

Apple Microsoft 365 或 Office 365 Admin 应用在 Apple iOS、Android 和 Windows (电脑和移动设备上) 。 该应用向服务管理员提供有关服务运行状况和即将进行的更改的信息。 该应用支持推送通知，在发布公告后几乎可以立即提醒你。 这可帮助你随时了解状态、运行状况以及即将对服务进行的任何更改。 通知支持使它成为建议管理员的监视工具。 有关详细信息，请参阅：

[Office 365 Admin移动应用](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载 Office 365 Admin 移动应用](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center 进行监视

Microsoft System Center 是一个集成式管理平台，可帮助你管理数据中心、客户端设备和混合云 IT 环境。 Office 365管理员System Center现在可以选择导入 Office 365 Management Pack，这样他们可以查看 System Center 中的 Operations Manager 内的所有服务通信。 使用此工具可以访问已订阅服务的状态、活动和已解决的服务事件，以及消息中心通信 (更改) 。 有关详细信息，请参阅以下 [博客文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果利用 System Center 监视 Teams 服务运行状况 (和从属服务) ，可以进一步自定义管理包，以提醒或通知已识别为对事件做出响应的特定组或个人。
这些组可能包括服务所有者、支持人员、二级和三级支持组，以及组织中事件管理员。

### <a name="monitoring-for-advanced-scenarios"></a>监视高级方案

可以监视服务运行状况和即将进行的更改，Office 365服务通信 API 以编程Office 365访问服务运行状况和更改。 使用此 API 创建自己的监视工具，或连接现有的监视工具Office 365服务通信，这可能会简化监视环境的方法。 有关详细信息，请参阅适用于[Office 365开发人员Enterprise应用](https://developer.microsoft.com/office)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动               | 说明                                                                                                                                                                                                               | 节奏   | 团队分配 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视服务运行状况 | 使用可用Microsoft Teams主动 (服务运行状况) 服务运行状况和依赖服务。 从属服务包括：Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory。 | 实时 |               |
| 事件通知  | 向内部利益干系人通知影响服务Teams的事件。 内部利益干系人可以包括用户、支持人员以及事件管理员。                                                                          | 根据需要 |               |

### <a name="references"></a>References 

[如何检查Office 365运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[服务运行状况和连续性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理组织更改

Microsoft Teams是基于云的服务。 因此，能够快速提供新功能。 持续创新为组织带来了明显的好处，但需要在组织内部适当管理这些更改，以避免用户受到用户的影响或向支持人员升级。

更新Teams自动向用户推出。 用户始终拥有最新的客户端和功能，这些功能在 Teams服务中。 无法管理向用户推出 Teams更新，因此通过有效的通信、培训和采用计划管理更改至关重要。 如果你的用户了解变化、了解好处并能够利用新功能，他们将能够更快适应并 &mdash; 欢迎更改。

### <a name="monitoring-for-change"></a>监视更改

更改管理的第一步是监视计划用于管理Teams。 监视这些更改的最佳来源是Office 365路线图，其中[](https://products.office.com/business/office-365-roadmap)列出了当前处于开发阶段、正在向客户推出或已完全启动的功能。 可以使用提供的筛选器Teams特定功能，也可以将路线图下载到 Excel文件进行进一步分析。 对于每个功能，路线图提供了简短说明以及预期的发布日期。

在[Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)博客中，您可以了解有关产品更新的最佳实践、趋势Teams新闻。 希望在此处找到要Teams的主要功能更新。 您也可以通过 RSS 源订阅博客。 然后，您可以将[RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)源直接添加到Teams频道，以便所有重要新闻都直接在 Teams。

发布的所有功能都记录在 Microsoft Teams[发行说明中](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)。
可在此处找到针对桌面、Web 和移动设备发布的功能列表。 帮助 中的"新增功能"选项卡上也提供了相同的发行[说明集](get-help-in-microsoft-teams.md)。

熟悉可用的资源，并确保分配相应的所有者来监视更改。

### <a name="planning-for-change"></a>规划更改

现在，你已了解即将对 Teams 服务所做的更改，下一步是进行相应的准备和规划。 评估每项更改，确定哪些更改需要与用户沟通、进行认知活动、为支持团队或用户进行培训，或者进行功能评估和采用活动。 这是组织中更改管理团队的主要角色。 下面是可帮助你规划更改的示例表集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：云录制 (发布日期：2018 年 1 月) 

**常规曲目**

| 更改准备情况 | 状态   | 说明/下一步 | 所有者 |
|----|----|----|-----|
| 法律审查   | 已完成     | 此功能是加入培训团队的先决条件。 | Project团队  |

**技术更改管理**

|       更改准备情况       | 状态 |                      说明/下一步                      |    所有者     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     需要 IT 更改      |  是   | 管理员只需为标识的用户启用录制。 | 支持团队 |
| 技术准备完成 |  是   |                                                            | 支持团队 |
|                              |        |                                                            |              |

**用户更改管理** 

| 更改准备情况 | 状态   | 说明/下一步 | 所有者 |
|----|----|----|-----|
| 用户影响                  | 低                  |                                                                 |                        |
| 需要用户就绪性      | 是                  |                                                                 |                        |
| 通信就绪         | 否                   | 通信电子邮件已草拟-待审阅。            | 通信团队    |
| 培训就绪               | 是                  | 培训将利用现有的 Microsoft 视频。                | 培训团队          |

**状态跟踪**

| 更改准备情况 | 状态   | 说明/下一步 | 所有者 |
|----|----|----|-----|
| 发布状态               | 正在进行          | 待执行发起人审阅。               | 更改管理团队 |
| 发布签单             |                      |                                                                 |                        |
| 发布日期                 |                      |                                                                 |                        |

有关使用更改管理规划Teams，请参阅为用户创建[更改管理Microsoft Teams。](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动               | 说明                                                                                                                                                                                                                | 节奏   | 团队分配 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视更改     | 监视即将对服务Microsoft Teams更改。                                                                                                                                                                   | 每天     |               |
| 规划更改    | 评估和规划新功能，包括通信计划、意识活动和培训。                                                                                                     | 根据需要 |               |
| 用户就绪性             | 执行有针对性的沟通、认知或培训活动，确保用户已准备好进行即将到来的更改。                                                                                                        | 根据需要 |               |
| 支持团队准备情况 | 执行有针对性的沟通、意识或培训活动，确保支持团队准备就绪。 支持团队可以包括"白种人"团队、支持人员、第 2 层或第 3 层支持人员、外部合作伙伴等。 | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估Teams使用情况

初始试点开始后，必须建立一个定期的节奏来测量实际Teams使用情况。 这使组织能够深入了解实际使用情况如何与"构想"阶段预测的使用情况保持一致。 虽然本部分重点介绍Teams使用情况，但是，这应该是测量和评估整体使用情况的Office 365工作的一部分。

在部署早期经常查看使用情况提供了以下机会：

-   验证用户是否正在使用Teams。

-   确定潜在的采用挑战，然后再在整个组织中创建关键问题。

-   了解"构想"阶段要求与实际使用情况之间是否存在差异。

如果使用量不是预期，这可能是由于部署问题、采用计划未正确执行或其他一些问题。 根据使用率低的实际原因，服务管理员必须与相关团队协作，帮助消除使用障碍。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用指标测量Microsoft 365 管理中心

"报告"Teams中提供了来自报表的使用情况数据。 Teams使用情况数据可在三个不同的报告中找到。 第一份报告提供跨产品视图，其中显示用户如何使用 Office 365 中的各种服务进行通信和Office 365。 可在此处找到此报告[：Office 365活动用户报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

另外两个报告Teams，它们从用户和设备的角度提供有关Teams使用情况的更多详细信息。 可在此处找到这两个报告：

[Microsoft Teams 设备使用情况报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams 用户活动报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>所需权限

分配有全局管理员角色或产品特定管理员角色的用户（ (Exchange 管理员、Skype for Business管理员、SharePoint 管理员）可以访问管理中心中的 **使用情况) 。**  

此外，报表 **读取** 者角色适用于需要访问报表，但不执行任何需要管理员级权限的任务的用户。 可分配此角色，向利益干系人提供使用情况报告，以监视和推动采用。 有关可用不同角色的信息，请参阅[关于Office 365角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

使用"报告"仪表板测量使用情况后，将测量的使用情况与在项目的"构想"阶段定义的任何关键 (KSIS) 进行比较，这一点很重要。 可以定义可定义为活动使用情况的 KSI，或间接链接到活动使用情况的 KSI。

在向其他网站或用户恢复推出之前，必须确定实际使用情况和计划使用情况之间的任何差异。 你很可能会将组织学习识别为此活动的一部分，你可以利用这些知识来确保下一批网站或用户不会遇到相同的问题。

首先，查明这是采用还是技术问题。 首先调查以下各项，以便确定问题所在。

1.  通过执行体验质量评审来验证质量 (请参阅[改进](monitor-call-quality-qos.md)和监视 Teams 呼叫质量) 。

2.  请与支持人员团队合作，检查是否不存在阻止用户访问或使用该服务的热门技术问题。 如果存在问题趋势，请在获得支持之前[](#endpoint-troubleshooting)，使用本文稍后的终结点故障排除部分尝试解决问题。

3.  请与培训和采用团队合作，从用户收集直接反馈 (请参阅本文稍后的"[](#assess-user-sentiment)评估用户情绪) ，并检查认知和采用活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动                         | 说明                                                                                                                      | 节奏   | 团队分配 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 度量 (启用阶段)  | 在启用Teams继续载入网站时，测量和评估网站使用情况。 按需要解决使用问题。 | 每周    |               |
| 测量 (驱动器值阶段)                            | 在部署完成后Teams"驱动器值"阶段 (评估) 。 按需要解决使用问题。 | Biweekly  |               |
| 更新采用计划             | 根据衡量的使用情况与规划目标的比较情况更新采用计划。                                         | 根据需要 |               |

### <a name="references"></a>References 

[关于Microsoft 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

["活动报告"Microsoft 365 管理中心](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户情绪

了解用户情绪可以充当衡量部署成功的关键Teams指标。 用户反馈可以推动组织中的变化;这可能包括对通信计划、培训计划或你为用户提供支持的方式的更改。

必须尽早获得反馈，并在整个项目生命周期及以后持续评估用户情绪。 使用以下指南来确定组织寻求反馈的时间间隔：

-   **项目开始时**：通过评估项目开始时的用户情绪，可以提前了解用户对用户体验Teams情况。

-   **重要里程碑之后**：通过收集整个项目生命周期的反馈，可以持续评估用户情绪，并根据需要进行更改。 这一点在主要里程碑之后特别有用。

-   **Project：** 在项目结束时评估用户情绪将告诉你完成得如何以及需要在哪里完成工作，并允许你将结果与上一个调查进行比较。

-   **持续**：继续无限期测量用户情绪。 用户情绪的变化可能是由于组织环境的变化或用户服务Teams更改。 通过定期测量用户情绪，可以了解服务管理团队的表现以及组织如何响应服务Teams变化。

可以通过许多不同的方法评估用户情绪。 这些方式可能包括电子邮件调查、当场或电话式面试，或者直接在客户或Teams Yammer。 有关详细信息，请参阅中[用户反馈方法Microsoft Teams。](best-practices-feedback.md)

还可使用全行业方法评估名为 net promotor score (NPS) 的用户情绪，如下一部分所述。

### <a name="nps"></a>NPS 

NPS (者分数) 是一个全行业客户会员指标，也是评估用户情绪的一个好方法。 可通过提出两个问题计算 NPS："你向同事推荐Teams的可能性有多大？"，后跟自由格式问题"为什么？"

NPS 是范围从 –100 到 100 的索引，它衡量客户推荐公司产品或服务的意愿。 NPS 基于通过电子邮件或其他电子方式传递给用户的匿名调查。 NPS 度量提供商与使用者之间的会员。 它只包含一个问题，该问题要求用户从 1 到 10 进行体验评分，并提供其他评论。 然后，根据以下分级对用户进行分类：

-   9 或 10 是推动者：将推广你的服务和为他人提供燃料的忠实爱好者。

-   7 或 8 是被动的：满足但不可接受，容易受到其他服务或产品/服务的影响。

-   从 1 到 6 是"破坏者"：使客户感到不满意，他们可能会损害你的服务并阻碍增长。

![演示 NPS 缩放的示意图](media/operate-my-service-image2.png "此图演示了 NPS 规模。它显示 0 到 6 的排名是攻击者，7 到 8 是被动的，9 到 10 是推动者。")

虽然基本 NPS 编号很有用，但从分析用户评论中可以获取最大的价值。 它们可帮助你了解用户为何会 (或不推荐) 向Teams用户。 这些评论可以提供有价值的反馈，帮助项目或服务管理团队了解提供高质量服务所需的调整。

若要向组织提供 NPS 调查，可以利用最喜欢的在线调查工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动              | 说明                                                                                                                                                                         | 节奏   | 团队分配 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 评估用户情绪 | 使用调查或访谈，或者通过反馈渠道或反馈渠道捕获和评估用户Teams或Yammer。                                                                 | 根据需要 |               |
| 更新采用计划 | 根据用户反馈推动组织中的变化;这可能包括更改通信计划、培训计划或你为用户提供支持的方式。 | 根据需要 |               |

### <a name="references"></a>References 

[Net 提升者分数](https://en.wikipedia.org/wiki/Net_Promoter)

[使用Yammer收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈最佳做法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心规划元素都进入优化、调整大小以及修正网络基础结构，以确保获得高质量、Microsoft Teams路径。 我们的网络准备指南中介绍了规划 [任务和](3-envision-evaluate-my-environment.md#network-readiness) 要求。 由于升级、扩展或其他业务要求，网络通常会随着时间的推移而发展。 在网络规划活动中，Teams要求非常重要。

尽管网络规划是网络部署Teams一个重要方面，但根据不断变化的业务或技术要求，确保网络保持正常运行并保持最新也同样重要。

为了确保网络的运行状况，需要定期执行一些操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动                                                       | 说明                                                                                                                                                                                                                                                                                                                                                                 | 节奏                | 团队分配 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 监视Office 365 IP 和 URL                                | 使用提供的[RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) [源Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) URL 和 IP 地址范围的任何更改，并启动对适用网络组的更改请求。                                                                                                                                | 每天                  |               |
| 根据对 IP 和 URL Office 365更新网络 | 更新适用的网络组件 (防火墙、代理服务器、VPN、客户端防火墙等) 以反映对 Office 365 URL 和[IP 地址范围的更改](/microsoft-365/enterprise/urls-and-ip-address-ranges)。                                                                                                                                                              | 根据需要              |               |
| 提供建筑物数据                                          | 向质量负责人或相关利益干系 (提供更新的子网信息) 以确保 [CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 中的建筑物定义保持最新。 | 根据需要              |               |
| 实施更改                                               | 在网络中实施更改，以支持更改Teams要求。 网络元素可以包括：<ul><li>防火墙</li><li>VPN</li><li>有线和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>     | 根据需要              |               |
| 网络监视和报告                               | 使用网络提供商提供的现有第三方网络管理工具和报告功能，端到端地监视网络的可用性、利用率和容量趋势。 使用趋势数据进行网络容量规划。                                                                                                            | 每日、每周、每月 |               |
| 容量规划                                              | 与服务Teams协作，了解可能推动额外容量更改的业务和技术要求的变化。                                | 根据需要              |               |
| 网络故障排除和修正                        | 帮助Teams支持人员、服务所有者和关键利益干系人排查和解决与连接、Teams或质量相关的问题。 网络元素可以包括：<ul><li>防火墙</li><li>VPN</li><li>有线和Wi-Fi网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul>    | 根据需要              |               |
| 灾难恢复和高可用性测试                | 在网络基础结构上定期执行高可用性和灾难恢复测试，以确保它满足针对 Teams 服务的服务级别目标 (SLA) 或服务级别协议 (SLA) 。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>References 

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[生成数据架构](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估和确保质量 

所有组织都需要一个小组或个人对质量负责。 这是服务管理中最重要的角色。 "质量保证者"角色分配给对用户体验充满热情的人或组。
此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的规模和复杂程度，这可能是任何一个致力于确保高质量用户体验的人或组。

质量保证者利用现有工具和记录的流程（例如呼叫质量仪表板 (CQD) ）来监视用户体验、识别质量趋势，并根据需要推动修正。
质量冠军应该与相应的团队协作，推动补救措施，并报告进度和任何未解决问题的引导委员会。

请阅读[改进和](monitor-call-quality-qos.md)监视 Teams 质量，其中介绍了在对改善用户体验影响最大的主要领域评估和提供修正指导的活动。 本文中提供的指南侧重于使用 CQD 作为主要工具来报告并调查每个区域，并侧重于音频，以最大限度地提高采用和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议你尽早提名质量冠军。 获得提名后，他们应开始熟悉监视呼叫 [质量](monitor-call-quality-qos.md) 内容和关联的培训材料。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动                               | 说明                                                                                                                                                                                                                                                                                                 | 节奏                             | 团队分配 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名并训练质量 ()  | 提名并训练质量冠军。                                                                                                                                                                                                                                                                   | 根据需要                           |               |
| 执行体验质量评审 (QR)      | 执行 QER 以确定质量和可靠性的趋势，针对定义的目标进行评审，并报告给组织中的关键利益干系人。                                                                                                                            | 部署 (每月)  |               |
| 驱动器修正                      | 根据 QER 评估和结果在整个组织中协调补救工作。                                                                                                                                                                                                           | 根据需要                           |               |
| 更新 CQD 中的建筑物数据            | 对网络进行更改时，在 CQD 中更新或添加新的建筑物定义 (请参阅Upload[信息) 。](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | 根据需要                           |               |
| 填充"质量冠军"角色      | 组织中质量的端到端责任。 这包括：<ul><li>确保定期进行 QER。</li><li>向关键利益干系人报告质量状态。</li><li>确保建筑物数据定义是最新的。</li><li>在整个组织中协调补救工作，确保用户拥有高质量的Teams。</li></ul>          | 每天                               |               |



### <a name="references"></a>References 


[Upload CQD 中的租户和建筑物数据](CQD-upload-tenant-building-data.md)

[改进和监视呼叫质量Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

Microsoft Teams终结点可以定义为任何 PC、Mac、平板电脑或移动设备 (运行) 客户端Teams设备。 术语 *终结点* 不仅包括设备本身，还包括用户如何连接到设备，例如，使用设备的内置麦克风或扬声器、耳机或优化耳机。 部署终结点后，不得忘记终结点。 终结点Teams需要持续维护。 以下部分介绍要关注的特定领域。

### <a name="endpoint-requirements"></a>终结点要求

应用程序的主要优势Teams之一是客户端自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。 移动应用Teams通过其各自的应用商店保持最新。

客户端Teams基础软件平台的最低要求。 这些要求可能会随着时间的推移而改变，因此，必须监视它们以发现更改。 例如，Teams客户端具有最低 iOS 版本。 如果客户端使用 Internet 浏览器，则浏览器也需要保持最新。 可以在获取客户端中找到支持的平台列表[，Microsoft Teams。](get-clients.md)

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙可能会影响呼叫质量，甚至会阻止建立呼叫。 在客户端防火墙上配置适当的排除项后，需要根据 URL 和 IP 地址范围 Office 365[信息保持最新](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 第三方供应商将获得有关如何更新排除项的具体指导。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

Wi-Fi驱动程序可能有问题。 例如，驱动程序可能在接入点之间具有非常激进的漫游行为，这会引发不必要的接入点切换，从而导致通话质量差。 性能不佳Wi-Fi驱动程序可能通过体验质量评审发现 (请参阅改进和监视 Teams 呼叫质量，了解) 。 [](monitor-call-quality-qos.md) 必须实施质量驱动的流程，监视新的用户Wi-Fi，并确保在将新驱动程序部署到一般用户群体之前已经过测试。

### <a name="endpoint-management"></a>终结点管理

应提供和维护受支持的终结点和 (设备（) 耳机）目录。 此目录将包括已选择并验证为"构想"和"载入"阶段一部分的批准设备的列表。 通常，为组织中每种人员类型选择特定设备以满足该人员属性的需求。 所有终结点都有生命周期，需要管理与这些设备关联的供应商合同、保修、更换、分发和修复策略。

### <a name="endpoint-troubleshooting"></a>终结点故障排除

即使你遵循了前面的指导，你组织中用户仍可能遇到与Teams。 尽管问题可能并不存在于终结点本身，但该问题的症状通常通过客户端向用户显示。 以下指南旨在提供解决问题时可以采取常规步骤;它并不是全面的故障排除指南。 这些步骤按特定顺序提供，但它们不必明确执行，并且可能不适用，具体取决于问题的性质。

1.  **验证服务运行状况：** 用户可能遇到的问题可能与对服务Teams服务产生负面影响的事件相关。 第一步，建议确认没有活动的服务问题。 请参阅[如何检查Office 365运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    请记得检查从属服务的状态 (例如，Exchange、SharePoint OneDrive for Business) 。 上一部分监视服务运行状况中更详细地讨论了 [服务运行状况的监视](#monitor-service-health)。

2.  **验证客户端连接：** 连接问题会导致服务中的功能或登录Teams。 我们建议 (新站点或) 验证服务连接的位置。 确保每个[Office 365遵循](/microsoft-365/enterprise/urls-and-ip-address-ranges)以下 URL 和 IP 地址范围指南。 可以利用 Microsoft [网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) 执行连接测试，验证媒体端口已正确打开，以便实现云语音功能。 网络就绪性指南中提供了有关如何运行连接测试 [的详细](3-envision-evaluate-my-environment.md#network-readiness) 步骤。

3.  **检查已知问题列表：** 请参阅 [Teams故障排除](/MicrosoftTeams/troubleshoot/teams)"，确定用户是否受到这些问题之一的负面影响。 如果只有一 (解决此问题，请按照) 解决方法。

4.  **请访问Microsoft Teams社区：** 社区 [Microsoft Teams为](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)社区提供专用Teams。 该Teams社区提供一个讨论列表、博客文章和围绕Teams。 可以发布问题或搜索之前的讨论，以查找问题的解决方案。

5.  **联系 Microsoft 支持部门：** 你可以在线或通过电话联系 Microsoft 支持Teams问题。 有关信息，请参阅 [联系商业产品支持人员](/microsoft-365/admin/contact-support-for-business-products)。
    对于顶级客户，可以按照联系顶级客户的支持人员Microsoft Teams ([提出支持) 。 ](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动                 | 说明                                                                                                                                                                                                                                                                                                                                                                     | 节奏   | 团队分配 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 终结点要求    | 确保Teams终结点继续满足获取客户端 Teams 中列出的所有[软件Microsoft Teams。](get-clients.md)                                                                                                                                                                                       | 每月   |               |
| 终结点防火墙       | 根据 URL 和 IP 地址范围 中的信息，在终结点防火墙Office 365[排除项](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 第三方供应商将就如何维护排除项提供具体的指导。 订阅 [RSS 源](https://support.office.com/o365ip/rss) ，以自动收到更改通知。 | 根据需要 |               |
| Wi-Fi 驱动程序            | 测试和Wi-Fi电脑上的驱动程序。 使用 CQD 验证结果 (改进和监视[Teams) 。](monitor-call-quality-qos.md)                                                                                                                                                                                                                                                                   | 根据需要 |               |
| 终结点管理      | 维护受支持的终结点和接口设备的目录， (耳机和) 。 管理供应商合同、保修、分发、更换和修复策略。                                                                                                                                                                                                        | 每月   |               |
| 终结点故障排除 | 故障排除任务可能包括验证连接、咨询已知问题列表、日志收集、分析和向 Microsoft 支持或第三方供应商升级。                                                                                                                                                                                               | 根据需要 |               |

### <a name="references"></a>References 

[Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[获取 Microsoft Teams 客户端](get-clients.md)

[Microsoft Teams社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[联系商业版产品的支持人员 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products)

[联系顶级支持人员](https://support.microsoft.com/premier/contacts)

[视频Teams故障排除](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署Microsoft Teams服务后，需要执行多个与管理相关的活动。 活动范围从管理服务和单个用户到容量规划和预配许可和电话号码。 以下部分介绍其中一些常见的管理任务。

### <a name="service-administration"></a>服务管理

该Teams服务具有多个可在租户范围内配置的设置。
对租户设置所做的更改会影响已启用租户设置的Teams。 有关这些设置的详细列表，请参阅[管理Microsoft Teams组织设置](enable-features-office-365.md)。

### <a name="user-administration"></a>用户管理

为了支持用户，组织可能需要执行任意数目的相关任务，具体任务因组织而异。 最终，这些任务需要由分配有这些运营职责的支持团队管理。 通常需要以下任务才能支持 Teams。

#### <a name="general-tasks"></a>常规任务

[管理 Microsoft Teams 的用户访问](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>常见任务电话系统

[为用户分配、更改或删除电话号码](./assign-change-or-remove-a-phone-number-for-a-user.md)

[为用户分配或更改紧急地址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[为你的组织添加、更改或删除紧急位置](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[创建并管理拨号计划](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>音频会议常见任务

[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)

[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>许可证管理

随着组织的发展或合约，必须规划许可以满足当前和未来的需求。 除了云语音Teams许可证外， (电话系统音频会议) 。 [](here-s-what-you-get-with-phone-system.md) [](https://products.office.com/skype-for-business/audio-conferencing)

对于Teams，电话系统许可证需要关联的[呼叫计划](calling-plan-landing-page.md)许可证。 呼叫计划许可使您能够拨打和接听国内和/或国际电话呼叫。 这些计划基于使用情况，并且具有与之关联的分钟池。 预配 [通信信用额度](what-are-communications-credits.md) 将确保永远不会用完服务。

音频会议允许使用收费电话拨入式会议和国内电话拨入式会议服务。 免费电话拨入式会议或非国内拨出方案可能会导致产生额外的 [通信积分费用](what-are-communications-credits.md) 。

通信积分可以补充通话计划和音频会议许可证。 呼叫计划许可证和通信信用额度均基于使用情况，因此需要相应地进行监视和预配。

可以利用 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 来帮助监视呼叫计划分钟数和通信信用额度的使用情况。 根据此活动的结果，可以相应地调整许可。 即将推出，我们将提供 [PSTN 分钟池报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) ，以更有效地协助完成此任务。

### <a name="telephone-number-management"></a>电话号码管理

可通过两种方法在 Teams中获取号码：可以移植来自其他提供商的电话号码，也可以直接从 Microsoft 的号码清单中预配号码。 获取用户的电话号码 [中介绍了这两种方法](getting-phone-numbers-for-your-users.md)。

你可以从 Microsoft 的号码清单中预配的电话号码数有限制。 限制由一些因素决定，详详于 ["可以获取多少电话号码？"中](how-many-phone-numbers-can-you-get.md)。
限制取决于号码类型-免费服务号码、收费服务号码和订阅者 (用户) 号码。 每个都有自己的限制，并且必须独立管理。 如果即将达到限制 (已达到限制) ，可以申请递增到限制。 上一段中的文章介绍了此过程。

有时，在服务可用的区域可能无法预配数字。 有关请求号码的过程的信息，请参阅 [管理组织的电话号码](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>团队创建 (可选) 

默认情况下，邮箱在 Exchange Online 的所有用户都有权创建Microsoft 365组，因此，拥有 Microsoft Teams。 如果要更严格控制并限制新团队[ (因此](assign-roles-permissions.md#permissions-to-create-teams)要创建新的 Microsoft 365 组) ，可以将组创建和管理权限委派给一组管理员。 如果你的组织想要使用此选项，请参阅本文中所述的过程，以允许用户提交由分配的团队处理的请求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/根据需要任务

| 活动                    | 说明                                                                                                                                                                                                                                                                                                                                                                                                             | 节奏   | 团队分配 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服务管理      | 管理租户范围的Teams设置。                                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 用户管理         | 管理基于用户的设置和在 Teams。                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 许可证管理          | 利用 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 使用情况报表和 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 分钟池报告 (计划和通信信用额度) 用户和基于使用情况的许可的当前和未来需求。 | 每周    |               |
| 电话号码管理 | 管理可用于未来增长的电话号码，并调整库存级别以满足组织需求。                                                                                                                                                                                                                                                                                                | 每周    |               |
| 团队创建 (可选)     | 查看并处理团队创建请求。                                                                                                                                                                                                                                                                                                                                                                          | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>改进和监视呼叫质量

[改进和](monitor-call-quality-qos.md)监视Teams包括一组活动，这些活动在对改善用户体验影响最大的关键领域进行评估和提供补救指导，如下图所示。

![体验质量评审期间要检查的区域示意图](media/plan-my-service-management-image2.png "在体验质量评审期间要检查的关键方面：音频、可靠性和用户测试结果。")

通过持续评估和修正本指南中所述的区域，可以减少它们可能对用户体验造成负面影响的可能性。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

改进和监视[Teams](monitor-call-quality-qos.md)的呼叫质量中提供的指南侧重于使用呼叫质量仪表板 (CQD) Online 作为主要工具来报告并调查所述的每个领域，并侧重于音频，以最大限度地提高采用和影响。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

我们强烈建议你尽早提名质量冠军。 提名后，他们应开始熟悉改进和监视呼叫质量中的内容，以便[Teams。](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->