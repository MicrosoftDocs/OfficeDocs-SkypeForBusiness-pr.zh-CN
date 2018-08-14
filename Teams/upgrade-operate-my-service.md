---
title: -Microsoft 团队的 Microsoft 团队的操作指南
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 任务和活动所需的团队服务管理，包括监视服务运行状况和评估并确保网络质量和使用情况
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad17668aba98c956aa1eda1c8df37dba0526ef06
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "20398066"
---
![升级旅程，重点强调卓越阶段的阶段](media/upgrade-banner-op-excellence.png "升级旅程，重点强调卓越阶段的阶段")

本文是您升级旅程，只要您已完成从 for Business 的 Skype 您升级到团队开始的卓越阶段的一部分。

# <a name="operate-my-service"></a>运行我的服务

本文概述了已升级后，在为组织成功操作团队的要求。 通过进行正确操作团队服务，您可以确保您正在为组织提供高质量、 可靠地体验。

## <a name="introduction-to-the-operations-guide"></a>操作指南简介

操作指南为您提供了所有的任务和活动所需的服务管理功能的一部分的 Microsoft 团队的概述。

服务管理是涵盖日常操作的 Microsoft 团队服务后已部署并为用户启用广泛主题。 团队服务包括 Microsoft Office 365 和本地部署的基础结构组件 （例如，网络）。

服务管理的概念很可能不是一个新的概念对于大多数组织。 您可能已经实现了进程和与现有服务相关联的任务。 也就是说，今天将来支持工作组规划服务管理时，您可能可以增大当前过程。

服务管理包括所有活动和进程涉及管理团队端到端。 如上文所述，某些组件服务管理-Office 365 服务本身包含的基础结构 — 是 Microsoft 的责任，而您客户，负责向用户管理团队，网络的各个方面和您提供的终结点。

任务和本指南中的活动分为八个类别下图中所示。 每个这些类别将展开时以下各节。

包含说明的任务和活动的服务管理团队的类别的列表的![A 图表。该图还描述了服务管理是很大程度客户任务。]包含说明的任务和活动的服务管理团队的类别的列表的(media/operate-my-service-image1.png "A 图表。该图还描述了服务管理是很大程度客户任务。")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>决定操作对团队的实现方式。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>查看全文操作指南。</li><li>实现与您的组织目标的质量和可靠性团队工作负荷提供对齐操作策略。</li><li>查看体验质量审查指南。</li><li> 实现定期执行质量的体验 reviews （英文） 以确保您的团队部署运行于其峰值功能的操作策略。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>操作的角色映射

规划操作 undertook 构想阶段很关键，因为操作活动开始时启用了第一个试点用户。 本指南列出的活动和必须在保持高质量团队部署的每日、 每周、 每月，或按需基础执行的任务。 本指南提供知识和有关如何执行这些关键活动和任务的指南。

成功部署一个关键组件是确保，在构想阶段的早期做好的规划步骤包括确定谁将负责执行特定活动。 您已经确定哪些任务和活动适用于您部署后，他们需要理解和被关注的组或个人您分配给它们。

确定每个工作组必须检查和达成一致的任务和标识的责任和开始准备。 这可能包括培训和准备，提供对人员配备计划，或确保外部提供程序已准备好进行传递的更新。

活动和本指南中定义的角色应在大多数情况下中, 有效，但每个团队部署是唯一的;因此，您可以使用作为起点本指南自定义活动和默认角色，以满足您需求。

确保每个无论如何工作组具有运行服务所需的活动很好地了解。 很关键，每个工作组接受和第一个试验开始之前您的组织中其责任签署。

协议位置后，应开始相应团队实施他们的角色。

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td>
<td><ul><li>使用本文档的操作角色映射练习。</li><li>会见各自的支持团队能够分配所需的活动的列表中的每个项的名称。</li><li>获得接受或注销分配角色上。</li><li>确保相应团队具有适当的培训、 准备、 和资源完成所需的这些活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>团队服务依赖项

Microsoft 团队汇集技术跨 Office 365 提供集线器团队协作。 示例包括：

-   Azure Active Directory (Azure AD) 提供团队的身份验证和授权服务。

-   Exchange Online 提供高级的功能，如合法保留和电子发现。

-   SharePoint Online 提供共享通道中的文件的功能和 OneDrive for Business 提供一种机制，共享私人聊天中的文件。

组织还可以利用现有的内部部署基础结构投资。 例如，现有的内部部署 Active Directory 帐户还可用于进行身份验证，通过利用 Azure AD 连接。 某些版本的 Exchange Server 可用于代替 Exchange Online。

这些技术更结合在一起，为用户提供丰富、 协作，且智能通信套件。 此紧密集成团队的主要优点，但它还驱动器分散在这些技术的服务管理的要求。

本指南介绍焦点来管理工作组服务的关键区域。 很可能必须服务管理计划中支持的技术取决于团队的位置。 如果不需要，您将需要建立这些技术组件的正确的服务管理计划 (在本地和联机) 以及。 这有助于确保您的用户体验高质量、 可靠地与团队。

#### <a name="references"></a>引用 

[Microsoft Teams 概述](teams-overview.md)

[Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)

[Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南活动

以下各节提供了概述成功运行的 Microsoft 团队服务所需的活动。 其中包括对引用工具、 上下文信息，以及可帮助您了解活动，并帮助在准备计划中的其他内容。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监控服务运行状况

务必您了解 Microsoft 团队服务的整体运行状况，以便可以主动通知其他人在您的组织的任何事件的影响的服务。 如前面所述，团队它依赖于在其他如 Azure Active Directory、 Exchange Online、 SharePoint Online 和 OneDrive for Business 的 Office 365 服务。 因此，很也相当重要您监视相关服务的运行状况。

将此活动合并到您的事件管理过程，主动告知用户、 帮助台和运营团队准备来处理用户升级。

以下各节介绍了工具，您可以利用要监视的[服务事件](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1)影响团队服务。 下表中包含的每个工具，以及何时应使用每个好处摘要。

| 监视工具                       | 优势                                            | 何时使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Office 365 门户                     | 可从任何设备支持的浏览器。 | 您无需实时通知时使用。                                          |
| Office 365 管理中心应用程序                  | 提供向您的移动设备的推送通知。  | 当您需要您外出时的服务事件通知时使用。                  |
| Microsoft System Center               | 与 Microsoft System Center 集成。           | 高级监控功能和通知支持您在需要时使用。                       |
| Office 365 服务通信 API | 对 Office 365 服务运行状况的编程访问权限。   | 当您需要与第三方监视工具的集成或想要生成您自己的解决方案时使用。 |

> [!NOTE]
> 只有分配了**全局管理员**或**服务管理员**角色的用户可以查看服务运行状况。

### <a name="monitoring-with-the-office-365-portal"></a>与 Office 365 门户监控

[Office 365 门户](https://portal.office.com/)提供[服务运行状况主控板](https://portal.office.com/adminportal/home#/servicehealth)从中可以查看相关服务除了团队服务的当前运行状况。

### <a name="monitoring-with-the-mobile-app"></a>使用移动应用程序监视

Apple iOS、 Android，和 Windows （PC 和移动设备） 都添加 Office 365 管理应用程序。 应用程序服务管理员提供有关服务运行状况和要做出的更改的信息。 应用程序支持推送通知的几乎可以立即通知您已发布 advisory 之后。 这有助于您了解最新状态、 运行状况，和服务的任何要做出的更改。 通知支持使其建议监视工具的管理员。 有关详细信息，请参阅：

[Office 365 管理移动应用程序](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载 Office 365 管理移动应用程序](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center 监视

Microsoft System Center 是帮助您管理数据中心、 客户端设备和混合云 IT 环境集成的管理平台。 现在使用 System Center office 365 管理员可以选择要导入 Office 365 管理包，这就使用户可以查看在 System Center Operations Manager 中的所有服务通信。 使用此工具可以访问您的订阅的服务、 活动和解决服务事件和消息中心通信 （要做出的更改） 的状态。 有关详细信息，请参阅以下[博客文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

使用 System Center 监视团队服务运行状况 （和相关服务） 时，您可以进一步自定义警报或通知特定组或已发现响应事件的个人的管理包。
这些组可以包括您的组织中的服务所有者、 支持人员、 第二级和第三级支持组和事件的经理。

### <a name="monitoring-for-advanced-scenarios"></a>监视的高级方案

您可以通过利用 Office 365 服务通信 API 以编程方式访问 Office 365 服务运行状况和更改监控服务运行状况和要做出的更改。 使用此 API 创建自己的监视工具，或连接到 Office 365 服务通信，可能简化如何监视您的环境的您现有的监视工具。 有关详细信息，请参阅[企业开发人员的 Office 365](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                               | 节奏   | 分配的工作组 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监控服务运行状况 | 使用可用的工具，主动监视的 Microsoft 团队服务运行状况，（和相关服务）。 相关服务包括： Exchange Online 中，SharePoint Online 的 OneDrive for Business，Azure Active Directory。 | 实时 |               |
| 事件通知  | 通知事件的影响团队服务的内部利益干系的人。 内部利益干系人可以包括用户、 支持人员和事件的经理。                                                                          | 根据需要 |               |

### <a name="references"></a>引用 

[如何检查 Office 365 服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[服务运行状况和连续性](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理组织的更改

Microsoft 团队是基于云的服务。 伴随这能够提供新特性和功能在较快的速度。 提供持续的创新提供组织，明显好处，但是这些更改需要以避免用户不愿意或升级至与技术支持人员贵组织中适当地管理。

向工作组的更新的推出自动为您的用户。 用户始终将具有的最新的客户端和团队服务中可用的功能。 不能管理团队更新您的用户的推出，因此是非常重要，来管理通过有效通信、 培训和应用程序的更改。 如果您的用户了解这些更改，教育的优势和权利用新的功能&mdash;他们将能够更快地调整和欢迎更改。

### <a name="monitoring-for-change"></a>更改监控

变更管理的第一步监控团队计划的更改。 监视这些更改的最佳源的是[Office 365 路线图](https://products.office.com/business/office-365-roadmap)，其中列出了当前正在开发，要推出的客户，或具有完全启动的功能。 您可以通过使用筛选器提供，搜索团队特定功能或可路线图下载到供进一步分析 Excel 文件。 为每个功能指南提供的简短说明，以及预期的发行日期。

在[Microsoft 团队博客 （英文）](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)，您可以了解有关最佳做法、 趋势和有关团队产品更新的新闻。 希望找到主要功能团队此处发布更新。 您还可以订阅通过 RSS 源的博客。 您然后可以直接将团队通道，添加[RSS 源](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)以便直接在工作组传递所有重要的新闻。

发布的所有功能均编都档在[Microsoft 团队的发行说明](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)。
此处您将发现已发布的功能的列表的桌面、 web 和移动设备。 一组相同的发行说明也是在[Microsoft 团队 T 自动程序](t-bot.md)发行说明选项卡上提供的。

熟悉的资源可用，并确保您分配适用所有者监视的更改。

### <a name="planning-for-change"></a>规划的更改

既然您知道要做出的更改到团队服务下, 一步是准备并相应做出计划。 评估每个更改以确定哪些更改需要向用户，认知 campaigns、 培训的支持团队或用户或功能评估和采用市场活动的通信。 这是您的组织中的更改管理工作组的主要角色。 下面是的示例表可帮助您规划的更改的集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能： 云录制 (发布日期： 年 1 月 2018年)

**常规跟踪**
| 更改准备 | 状态   | Notes/下一步步骤 | 所有者 |
|----|----|----|-----|
| 法律审阅   | 完成     | 此功能是入职培训培训团队的先决条件。 | 项目工作组  |

**技术变更管理**
| 更改准备 | 状态   | Notes/下一步步骤 | 所有者 |
|----|----|----|-----|
| 所需的 IT 更改          | 是                  | 管理员需要启用已识别的用户的记录。      | 支持团队           |
| 技术准备完成 | 是                  |                                                                 | 支持团队  
         |
**用户变更管理** 
| 更改准备 | 状态   | Notes/下一步步骤 | 所有者 |
|----|----|----|-----|
| 用户的影响                  | 低                  |                                                                 |                        |
| 所需的用户准备情况      | 是                  |                                                                 |                        |
| 准备好的通信         | 否                   | 通信电子邮件具有绘制 — 挂起的审阅。            | Communications 团队    |
| 培训就绪               | 是                  | 培训将利用现有的 Microsoft 视频。                | 培训团队          |

**状态跟踪**
| 更改准备 | 状态   | Notes/下一步步骤 | 所有者 |
|----|----|----|-----|
| 发布状态               | 正在进行中          | 通过执行发起人的等待审阅。               | 更改管理小组 |
| 注销发行版             |                      |                                                                 |                        |
| 发布日期                 |                      |                                                                 |                        |

有关与团队的变更管理规划的详细信息，请参阅[创建的 Microsoft 团队的变更管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动| 说明| 节奏| 分配的工作组 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 更改的监视器| 即将发布更改的 Microsoft 团队服务的监视器。| 每天||
| 规划的更改| 评估和规划的新特性和功能，包括通信计划、 认知 campaigns、 和培训。| 根据需要 ||
| 用户准备情况| 执行目标的通信、 认知度或培训活动，以确保用户可供即将发布的更改。| 根据需要 ||
| 支持团队准备 | 执行目标的通信、 认知度或培训活动，以确保支持团队已准备就绪。 支持团队可以包括"手套白色"团队、 支持人员，第 2 层或 3 层支持、 外部合作伙伴和等等。 | 根据需要 ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估团队使用率

初始试用开始之后，建立用于测量实际团队使用正则节奏至关重要。 这使您的组织深入了解如何实际使用与在构想阶段预测的使用情况。 本节重点介绍团队使用率，尽管这应该是衡量和评估 Office 365 使用率总体更广泛工作的一部分。

查看使用率经常早期部署中的为您提供机会：

-   验证是否用户使用团队。

-   他们在整个组织内创建严重问题之前，请识别潜在采用难题。

-   了解是否有构想阶段要求和实际使用率之间的差异。

如果使用率不是您的预期，这可能是因为部署问题，或者应用计划未被执行正常，或一些其他问题。 低使用率后面的实际原因，根据服务管理员必须与帮助删除使用率障碍相关团队协作。

### <a name="measuring-usage-with-the-office-365-admin-center"></a>测量用法与 Office 365 管理中心

从工作组的使用率数据位于报告仪表板中。 三个不同的报表中，可以找到团队使用率数据。 第一个报告提供跨产品视图的用户进行通信和协作使用 Office 365 中的各种服务的方式。 此报告可在此处找到： [Office 365 活动用户报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他两个报表是特定于团队的并提供更多有关团队使用情况的详细信息从用户和设备的角度来看。 可在此处找到两个报表：

[Microsoft 团队设备使用情况报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft 团队用户活动报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>所需的权限

在管理中心内的使用率报告可以访问的**全局管理员**角色或特定于产品的管理员角色 （**Exchange 管理员**、**业务管理员的 Skype**， **SharePoint 已分配的人员管理员**)。

此外，**报告读者**角色是可供用户需要访问的报告，但不执行任何需要管理员级权限的任务。 分配该角色提供使用率报告是利益干系人，监视器和驱动器应用到的任何人。 有关可用的不同角色的详细信息，请参阅[有关 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

您已使用报告仪表板测量使用率之后，务必比较根据项目的构想阶段定义任何关键成功指标 (KSIs) 的测量使用情况。 您可以定义可能定义为活动使用率 KSI 或间接链接到当前使用率。

非常重要确定实际的和计划继续向其他站点或用户推出之前的使用率之间的任何差异。 您可能将标识组织经验，您可以利用以确保此活动的一部分的站点或用户下一批不会遇到相同问题。

首先，查明这是采用还是技术问题。 首先调查下方，顺序，以确定问题所在的项目。

1.  通过执行[用户体验质量检查](upgrade-monitor-quality.md)来验证质量。

2.  使用检查不存在防止用户访问或使用服务趋势技术问题的帮助台团队。 如果存在问题趋势执行操作，使用本文后面的[终结点疑难解答](#endpoint-troubleshooting)一节尝试适当支持之前解决此问题。

3.  工作与培训和采用团队直接反馈收集 （请参阅本文后面的[评估用户观点](#assess-user-sentiment)） 的用户，并检查的知晓和采用活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动 | 说明 | 节奏 | 分配的工作组 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 度量使用率 （启用阶段） | 度量并为网站启用阶段是 onboarded 继续评估团队使用率。 地址所需的使用率问题。 | 每周 | |
| 度量使用率 | 度量并评估团队使用的驱动器值阶段 （后部署已完成）。 地址所需的使用率问题。 | 半月刊  | |
| （驱动器值阶段） | | | |
| 更新应用计划 | 应用计划基于如何测量的使用情况的更新将与您规划目标进行比较。 | 根据需要 | |

### <a name="references"></a>引用 

[有关 Office 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Office 365 管理中心中的活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户的观点

了解用户的观点可用作衡量团队部署成功的关键指标。 用户反馈可以在您的组织; 驱动器更改这可能包括更改沟通计划、 培训计划或向用户提供支持的方式。

务必早期获取反馈和继续评估用户的整个生命周期的项目及其他认证实战的观点。 使用以下指南以确定您的组织将在其中寻找反馈的间隔：

-   **项目的开始**： 通过评估项目的开始处的用户观点，您可以在早期视图到您的用户有关其团队体验的感觉如何。

-   **主要里程碑之后**： 通过收集整个项目生命周期的反馈，您可以测量连续逐个用户观点并根据需要进行更改。 这是后主要里程碑特别有用。

-   **项目结论**： 评估末尾的项目的用户观点会告诉您程度已完成，并且其中工时仍需要即可完成，并允许您针对以前调查结果进行比较。

-   **日常**： 继续无限期测量用户的观点。 更改用户的观点可能是由于在贵组织的环境中的更改或团队服务中的更改。 通过的时间间隔定期评估用户的观点，您可以了解程度执行您服务管理团队和组织响应团队服务中的更改。

可以通过多种不同的方法被评估用户的观点。 这包括电子邮件调查、 面对面或电话样式面试，或者只需在工作组或 Yammer 中创建的反馈通道。 有关详细信息，请参阅[Microsoft 团队中的用户反馈方法的最佳实践](best-practices-feedback.md)。

您还可以使用行业方法评估用户观点调用 net promotor 得分 (NPS)，即下节中所述。

### <a name="nps"></a>NPS 

Net 者均分数 (NPS) 是行业客户忠诚度指标和一个好方法用于评估用户的观点。 NPS 可以计算通过提出两个问题:"可能性有多大？ 您可以向同事推荐工作组"，"为什么？"后跟任意多边形的问题

NPS 是一个索引，为 100，介于-100 度量客户的通信意愿建议公司的产品或服务。 NPS 基于传递到用户可以通过电子邮件或其他电子方式匿名调查。 NPS 测量之间提供程序和使用者会员。 它包含只有一个问题，询问用户评价从 1 到 10，选项以提供其他注释其体验。 用户然后分类基于以下分级：

-   9 或 10 是升级： 尽力工作爱好者将推广您的服务和促进其他人。

-   7 或 8 是被动： 满足但 unenthusiastic，为其他服务或产品易受攻击。

-   介于 1 至 6 是说三道四： 可以损坏您的服务和妨碍增长客户满意度。

![此图演示的 NPS 刻度。显示的分级的 0 到 6 是说三道四、 7 至 8 是被动，和 9 到 10 的升级。](media/operate-my-service-image2.png "此图演示的 NPS 刻度。显示的分级的 0 到 6 是说三道四、 7 至 8 是被动，和 9 到 10 的升级。")

虽然 NPS 底数很有用，您将获得最大价值分析用户注释。 它们将帮助您了解为什么用户将 （或不） 建议团队向其他人。 这些注释可以提供有价值的反馈，以帮助项目或服务管理团队了解提供服务质量所必需的调整。

若要提供给组织的 NPS 调查，您可以利用您喜欢的在线调查的工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/根据需要任务

| 活动 | 说明 | 节奏   | 分配的工作组 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 评估用户的观点 | 捕获和评估用户的观点，使用调查或面试，或通过团队或 Yammer 中的反馈通道。 | 根据需要 | |
| 更新应用计划 | 驱动器根据用户反馈; 您组织中的更改这可以包括更改沟通计划、 培训计划或向用户提供支持的方式。 | 根据需要 | |

### <a name="references"></a>引用 

[Net 者均分数](https://en.wikipedia.org/wiki/Net_Promoter)

[使用 Yammer 收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈的最佳实践](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心规划元素转到优化，右大小调整和补救网络基础结构，以确保 Microsoft 团队服务的高质量、 高效路径。 在我们[网络准备](upgrade-prepare-environment-prepare-network.md)指南中介绍的规划任务和要求。 网络通常随时间由于升级、 扩展或其他业务需求。 非常重要规划活动网络中解决团队的要求。

尽管网络规划团队部署的一个重要方面，它是同等重要，以确保网络保持正常运行，并且保持最新状态，根据不断变化的业务和技术要求。

若要确保您的网络的运行状况，需要的时间间隔定期执行大量操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动 | 说明 | 节奏 | 分配的工作组 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 监控 Office 365 Ip 和 Url | 使用[RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)提供监视对[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)的任何更改，并启动到适用的网络组更改请求。 | 每天 | |
| 更新基于到 Office 365 Ip 和 Url 的更改网络 | 对适用的网络组件 （防火墙、 代理服务器、 Vpn、 客户端防火墙等） 以反映对[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)更改进行更新。 | 根据需要 | |
| 提供构建数据 | 更新子网信息提供给质量冠军 （或利益相关者），以确保[构建 CQD 中的定义](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)的速度将保持最新。 | 根据需要 | |
| 实现更改 | 实现支持不断变化的团队业务和技术要求在网络上的更改。 网络元素可能包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wi-fi 网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul> | 根据需要 | |
| 网络监控和报告 | 通过使用您现有的第三方网络管理工具和报告功能可从您网络提供程序来监控网络端到端的可用性、 利用率和容量趋势。 网络容量规划的使用趋势数据。 | 每日、 每周、 每月 | |
| 容量规划 | 与团队 service 所有者了解更改可能开车额外的容量更改的业务和技术要求进行协作。 利用[网络规划器](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)以确保足够的带宽适用于 Microsoft 团队的结果。 | 根据需要 | |
| 网络故障排除和修复 | 帮助团队支持人员、 服务所有者和主要利益干系人进行故障排除和修正问题到相关的团队连接、 可靠性或质量。 网络元素可能包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wi-fi 网络</li><li>Internet 连接和 ExpressRoute</li><li>DNS</li></ul> | 根据需要 | |
| 灾难恢复和高可用性测试 | 执行常规的高可用性和灾难恢复测试对网络基础结构，以确保它符合既定的服务级别目标 (Slo) 或团队服务的服务级别协议 (Sla)。 | 每月 | |

### <a name="references"></a>引用 

[网络计划程序](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[构建数据架构](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估，并确保质量 

所有组织都需要组或个人要负责质量。 这是在服务管理的最重要的角色。 质量冠军角色分配给用户或用户组属于热心有关其用户体验。
此角色需要确定中的趋势环境和赞助 ォ オ リ モ 驱动修正工作的技能。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的大小和复杂性，这可能是任何个人或组使用的确保高品质用户体验爱。

质量冠军利用现有的工具和记录操作过程中，如呼叫质量仪表板 (CQD) 和质量体验审阅指南，要监视的用户体验，请确定质量趋势和驱动器修正在需要时。
质量冠军应使用驱动器修正操作各自团队并向调控委员会进度并打开的任何问题有关的报告。

[质量体验审阅指南](https://aka.ms/qerguide)包括评估和修正指导对提高用户体验影响最大的主要区域中的活动。 使用 CQD Online 作为主要工具来报告和调查每个区域中，以最大限度地应用和影响的音频重点重点质量体验审阅指南中提供的指南。 对网络以提高音频体验任何优化还直接将翻译视频和桌面共享的改进。

我们强烈建议您在早期提名质量冠军。 正在提名之后, 他们应开始熟悉的用户体验质量审阅指南和关联的培训资料中的内容。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动 | 说明 | 节奏 | 分配的工作组 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名和培训质量 champion(s) | 提名和培训质量冠军。 | 根据需要 | |
| 执行质量体验评论 (QERs) | 执行 QER 以确定中的趋势质量和可靠性，针对定义目标、 查看和报告组织中的主要利益干系人。 | 每月 （每周过程中部署） | |
| 驱动器修正 | 基于 QER 评估和发现的组织中协调修复措施。 | 根据需要 | |
| 构建 CQD 中的数据的更新 | 更新或更改到网络时 CQD 中添加新的生成定义 （请参阅[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)）。 | 根据需要 | |
| 填充质量冠军角色 | 端到端负责组织中的质量。 这包括：<ul><li>确保定期召开 QER。</li><li>报告质量状态的主要利益干系人。</li><li>确保定义是最新的生成数据。</li><li>要确保用户具有与团队高质量体验的组织中协调修复措施。</li></ul> | 每天 | |

### <a name="references"></a>引用 

[了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[查看用户体验指南的质量](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

Microsoft 团队终结点可定义为任何 PC、 Mac、 平板电脑或运行团队客户端的移动 （或任何其他） 设备。 术语*终结点*而不是只包括设备本身，但用户如何连接到设备 — 例如，通过使用设备的内置麦克风或扬声器、 耳机或优化的耳麦。 他们正在部署后，必须不忘记终结点。 团队终结点需要持续医护和维护。 以下各节介绍重点关注的特定区域。

### <a name="endpoint-requirements"></a>终结点要求

一个团队的主要优点是，客户端保持最新自动。 PC 和 Mac 客户端是通过使用背景过程，为新的生成检查并下载新客户端应用程序空闲时进行了更新。 移动应用程序通过其各自的应用程序商店保留当前工作组。

团队客户端有基础软件平台方面的最低要求。 这些要求可能更改随时间推移，并因此很重要的更改监视它们。 例如，工作组客户端有最小 iOS 版本。 如果客户端使用 internet 浏览器，在浏览器需要以及保留当前。 [获取 Microsoft 团队的客户端](get-clients.md)中找不到支持的平台的列表。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验产生重大影响。
客户端防火墙可影响呼叫质量和甚至阻止呼叫的建立。 已配置合适对客户端防火墙排除后，他们需要保持最新的基于[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息。 您的第三方供应商会如何更新排除的特定指南。

### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

Wi-fi 驱动程序可能会出现问题。 例如，驱动程序可能有可能导致附不必要访问点切换，从而导致质量欠佳的呼叫质量的访问点之间的积极漫游行为。 佳的 Wi-fi 驱动程序可能会发现通过体验质量审查 （有关详细信息，请参阅[用户体验质量审阅指南](https://aka.ms/qerguide)）。 若要实现质量驱动采样新 Wi-fi 驱动程序，然后确保之前所要部署到的常规用户群体他们正在测试的过程至关重要。

### <a name="endpoint-management"></a>终结点管理

支持的终结点和接口设备 （如耳麦） 的目录应可用和维护。 此目录将包含已选定并验证的构想和 Onboard 阶段的一部分的批准设备的列表。 通常情况下，特定设备选择为您的组织中每个角色类型可以满足该角色的属性。 所有终结点具有生命周期中，并且您需要管理供应商合同、 担保、 替换、 通讯组，并修复这些设备相关联的策略。

### <a name="endpoint-troubleshooting"></a>终结点疑难解答

即使您已遵循前面的指南，您的组织中的用户仍可能会遇到问题团队中。 尽管此问题可能不与终结点本身，问题的症状通常显示通过客户端用户。 以下指南旨在提供解决问题; 您可以采取的常规步骤这不具有表示要全面的故障排除指南。 按特定顺序，提供的步骤，但无需显式后面，并且可能不适用，具体取决于问题的性质。

1.  **验证服务运行状况：** 用户可能遇到的问题可以与产生负面影响的团队服务或及其相关的服务事件。 第一步，我们建议您确认不存在活动服务问题。 请参阅[如何检查 Office 365 服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    请记住要检查的从属服务 (例如，Exchange、 SharePoint、 OneDrive for Business) 的状态。 监控服务运行状况是在上一节，[监控服务运行状况](#monitor-service-health)的更详细地讨论。

2.  **验证客户端连接：** 连接问题导致团队中的功能或登录问题。 （尤其是对于新的网站或位置） 我们建议您验证到服务的连接。 确保以下[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)指南后面的每个网站。 您可以利用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来执行验证正确已团队功能的打开的媒体端口的连接性测试。 [网络准备](upgrade-prepare-environment-prepare-network.md)指南中提供了有关如何运行连接测试的详细的步骤。

3.  **检查的已知的问题列表：** 请咨询[团队的已知问题的列表](known-issues.md)，以确定是否已被用户负面影响的这些问题之一。 按照提供 （如果有） 来解决该问题的解决方法。

4.  **访问的 Microsoft 团队社区：**[Microsoft 团队社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)团队提供专用的空格。 团队社区提供讨论列表、 博客帖子和团队为中心的通知。 可以将问题发布到或搜索解决方案的上述讨论与您的问题。

5.  **与 Microsoft 支持部门联系：** 您可以问题的团队联机或通过电话联系 Microsoft 支持。 有关信息，请参阅[支持的 Microsoft 团队的联系人](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。
    有关高级客户，可以执行在指南启动请求的支持[与支持部门联系的 Microsoft 团队 (高级客户)](https://support.microsoft.com/premier/contacts)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动 | 说明 | 节奏 | 分配的工作组 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 终结点要求 | 请确保终结点继续满足团队[获取 Microsoft 团队的客户端](get-clients.md)中列出的所有软件要求的团队。 | 每月 | |
| 终结点防火墙 | 维护相应排除在终结点防火墙中基于[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息。 您的第三方供应商会如何维护排除的特定指南。 订阅[RSS 源](https://support.office.com/en-us/o365ip/rss)以自动通知的更改。 | 根据需要 | |
| Wi-fi 驱动程序 | 测试和更新 PC 上的 Wi-fi 驱动程序。 使用 CQD （[用户体验质量审阅指南](https://aka.ms/qerguide)） 验证结果。 | 根据需要 | |
| 终结点管理 | 维护支持的终结点和接口设备 （如耳麦） 的目录。 管理供应商合同、 担保、 分发、 替换，并修复策略。 | 每月 | |
| 终结点疑难解答 | 故障排除任务可以包括验证咨询已知的问题列表、 收集日志、 分析和升级到 Microsoft 技术支持或第三方供应商的连接。 | 根据需要 | |

### <a name="references"></a>引用 

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[获取 Microsoft Teams 的客户端](get-clients.md)

[Microsoft 团队社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Microsoft Teams 的已知问题](known-issues.md)

[验证 Microsoft Teams 的服务运行状况](service-health.md)

[与支持部门联系业务产品的管理员帮助](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[联系人 Premier support](https://support.microsoft.com/premier/contacts)

[疑难解答团队视频](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理团队

已部署的 Microsoft 团队服务后，您需要执行与其管理相关的多个活动。 从管理服务和单独的用户容量规划和设置的许可和电话号码活动区域中。 以下各节介绍其中一些常见管理任务。

### <a name="service-administration"></a>服务管理

团队服务都有多个可以配置租户范围的设置。
租户设置所做的更改会影响所有用户已启用团队。 有关这些设置的详细列表，请参阅[Office 365 组织中的管理 Microsoft 团队功能](enable-features-office-365.md)。

### <a name="user-administration"></a>用户管理

若要支持用户，组织可能需要任意数量的相关任务 — 的特定任务因组织到下一步。 最终，这些任务需要由支持团队已分配这些操作的责任。 支持团队中的用户时，通常需要执行以下任务。

#### <a name="general-tasks"></a>常规任务

[管理对 Microsoft Teams 的用户访问](user-access.md)


### <a name="team-creation-optional"></a>团队创建 （可选）

默认情况下，与 Exchange Online 中邮箱的所有用户都有权在 Microsoft 团队中创建 Office 365 组和团队，因此。 如果您希望具有严格控制和[限制的新团队创建](assign-roles-permissions.md#permissions-to-create-teams)（以及创建新的 Office 365 组），您可以委派组创建和管理权限的管理员组。 如果您的组织希望使用此选项，请参阅本文以允许用户提交分配团队处理的请求中所述的过程。

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每天/每周/每月/按需任务

| 活动 | 说明 | 节奏 | 分配的工作组 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服务管理 | 租户范围的团队设置管理。 | 根据需要 | |
| 用户管理 | 基于用户的设置和许可团队中的管理。 | 根据需要 | |
| 许可证管理 | 规划用户和基于消耗的许可 （调用计划和通信字幕式） 的当前和将来需要通过利用[PSTN 使用率报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)和[PSTN minute 池](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report)报告。 | 每周    | |
| 电话号码管理 | 管理的电话号码用于未来增长，并调整库存水平，以满足您组织的需求。 | 每周 | |
| 团队创建 （可选）    | 团队创建的审阅和处理请求。 | 根据需要 | |

<!--ENDOFSECTION-->