---
title: 对于 Microsoft 小组的操作指南
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 04/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 任务和活动所需的团队服务管理，包括监视服务运行状况，评估并确保网络质量和使用情况。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d64da9bbe792031afbb3538020b7ff92fbaf493
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="operate-my-service"></a>使用我的服务

本文概述了成功运行云语音服务为您的组织的要求。 通过正确运行云语音服务，您可以确保您的组织为他们提供高质量、 可靠的体验。

## <a name="introduction-to-the-operations-guide"></a>操作指南简介

操作指南概述的所有任务和活动所需的服务管理功能的一部分作为 Microsoft 小组。

服务管理是一个宽泛的话题，涵盖日常操作 Microsoft 小组服务部署并为用户启用之后。 团队服务包括 Microsoft Office 365 和基础结构的组件部署内部 （如连网）。

服务管理的概念很可能不是大多数组织的一个新概念。 您可能已经实现了流程和与现有服务相关联的任务。 话虽如此，但今天在将来支持团队规划服务管理时，可能可以补充您当前的过程。

服务管理包括的所有活动和进程所涉及的管理端到端的团队。 如前文所述，服务管理的某些组件 — 包括 Office 365 提供服务本身的基础结构 — — 是 Microsoft 的责任，而您的客户，都对其负责的用户管理的团队，网络的各个方面和您提供的终结点。

任务和本指南中的活动分为八个类别如下面的关系图中所示。 上述每个类别将扩展在以下各节。

![A 图来描述任务和活动构成服务管理团队的类别的列表。该图还描述了服务管理是主要客户任务。](media/operate-my-service-image1.png "A 图来描述任务和活动构成服务管理团队的类别的列表。该图还描述了服务管理是主要客户任务。")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定操作对团队中的实现方式。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>查看完整的操作指南。</li><li>执行与您的组织的目标来提供的品质和可靠性的云语音工作负载对齐操作策略。</li><li>请查阅质量经验审查指南。</li><li> 实施定期执行质量经验审查以确保云语音部署运行于最佳功能的操作策略。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>操作角色映射

对于操作 undertook 在构想阶段的规划至关重要，因为运营活动开始时启用了第一个试验用户。 本指南列出了活动和维护高质量的团队部署的每日、 每周、 每月或根据需要基础必须执行的任务。 本指南提供的知识和如何执行这些重要活动和任务的指南。

成功部署的一个重要组成部分是确保，在构想阶段的初期执行的计划包括确定谁将负责执行特定的活动。 已经确定的任务和活动将应用于您的部署后，他们需要被理解后, 跟的组或个人分配给它们。

每个标识的团队必须检查和达成一致意见的任务和职责，确定和启动准备工作。 这可能包括培训和准备工作，提供更新的人员配备，或确保外部提供商就可以提供。

活动和本指南中定义的角色应该是在大多数情况下，有效，但每个小组部署是唯一的。因此，可用于本指南作为起始点的活动和默认角色，以满足您的需要自定义。

确保每个负责任的团队需要运行该服务的活动更好地理解。 这一点至关重要，每个小组接受，并在第一个试验开始前组织中其责任签署。

签订协议后，相应的团队应开始实施他们的角色。

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td>
<td><ul><li>使用本文档以便操作角色映射练习。</li><li>与各自的支持团队将名称分配给列表中的每个项的所需的活动。</li><li>获得认可或注销的分配角色。</li><li>确保相应的团队有适当的培训、 准备工作和资源来完成它们所需的活动。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>团队服务依存关系

Microsoft 小组汇集技术在 Office 365 提供中心的团队精神。 一些示例包括：

-   Azure 的 Active Directory 提供了身份验证和授权服务的团队。

-   Exchange Online 提供了高级的功能，如法律封存和电子发现。

-   SharePoint Online 提供共享频道中的文件的能力，OneDrive 为企业提供一种机制来共享文件内私人聊天。

企业还可以利用现有的内部部署基础结构投资。 例如，现有的内部部署 Active Directory 帐户还可以用于进行身份验证，通过利用 Azure AD 连接。 某些版本的 Exchange Server 可以代替 Exchange 联机。

这些技术聚在一起，为用户提供丰富、 协作式和智能通信套件。 这种紧密集成团队，一项关键好处，但也通过这些技术推动服务管理的要求。

该指南涵盖管理团队服务的重点关注领域。 很可能，取决于团队的支持性技术的地方中有服务管理计划。 如果不是这样，您将需要建立正确的服务管理计划，以这些技术组件 (内部部署和联机) 也。 这将有助于确保您的用户可以享受高质量、 可靠的团队掌握。

#### <a name="references"></a>引用 

[Microsoft Teams 概述](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

[如何交换和 Microsoft 小组进行交互](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact)

[SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact)

[Microsoft 的小组和 Skype 业务互操作性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>操作指南

以下各节概括了成功操作 Microsoft 小组服务所需的活动。 它们包括对引用工具、 上下文信息，以及可帮助您了解该活动，并协助准备工作计划的其他内容。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>监视服务运行状况

请务必了解 Microsoft 小组服务的整体健康状况，以便可以主动提醒其他人在您的组织的任何会影响服务的事件。 如上文所述，小组是依赖于业务 Azure Active Directory、 Exchange Online，SharePoint Online，和 OneDrive 等其他 Office 365 提供服务。 正因为如此，它是同样重要的是您监视相关服务的运行状况。

将此活动纳入到您的事件管理过程，以主动告知用户、 帮助台和运营团队准备来处理用户升级。

以下部分描述了这些工具，您可以利用它们来监视 [服务事故] (https://technet.microsoft.com/library/office-365-service-health.aspx?f=255&MSPPError=-2147217396#Service事件) 影响团队服务。 下表中包括的每个工具，并应使用每个优点总结。

| 监视工具                       | 优点                                            | 何时使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Office 365 门户                     | 可从任何支持的浏览器设备。 | 使用时不需要实时通知。                                          |
| Office 365 管理应用程序                  | 提供到您的移动设备的推式通知。  | 当同时在旅途中需要服务事件的通知。                  |
| 微软系统中心               | 与微软系统中心的集成。           | 您需要监视的高级的功能和通知支持。                       |
| Office 365 服务通信 API | 以编程方式访问 Office 365 提供服务的运行状况。   | 您需要与第三方监视工具的集成，或者希望构建自己的解决方案。 |

> [!NOTE]
> 只有**全局管理员**或**服务管理员**角色分配的人才可以查看服务的运行状况。

### <a name="monitoring-with-the-office-365-portal"></a>监视与 Office 365 门户

[Office 365 门户](https://portal.office.com/)提供了您可以在其中查看团队服务以及相关的服务的当前运行状况[服务运行状况的仪表板](https://portal.office.com/adminportal/home#/servicehealth)。

### <a name="monitoring-with-the-mobile-app"></a>使用移动应用程序监视

Office 365 管理应用程序可在苹果 iOS、 Android 和 Windows （PC 和移动）。 该应用程序提供服务管理员服务运行状况和即将进行的更改的信息。 该应用程序支持推送通知可以提醒您几乎可以立即通报过帐后。 这可以帮助您保持最新状态，健康，和服务对任何即将进行更改。 通知支持使其推荐使用的监视工具的管理员。 有关详细信息，请参阅：

[Office 365 管理移动应用程序](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下载 Office 365 管理移动应用程序](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>监视与微软系统中心

微软系统中心是帮助您管理数据中心、 客户端设备和混合云的 IT 环境的集成的管理平台。 现在使用 System Center office 365 管理员可以选择以使他们能够查看系统中心操作管理器中的所有服务通信 Office 365 管理包导入。 使用此工具使您可以访问您的订阅的服务、 活动和已解决的服务事故和邮件中心通信 （即将进行的更改） 的状态。 有关详细信息，请参阅下面的[博客文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果利用系统中心，以监视团队服务运行状况 （和相关服务），您可以进一步自定义管理包，提醒或通知特定的组或已确定对事故作出反应的个人。
这些组可以包括服务所有者、 支持人员、 二级和三级支持组和事件管理器在您的组织中。

### <a name="monitoring-for-advanced-scenarios"></a>对于高级方案监视

您可以利用 Office 365 服务通信 API 以编程方式访问 Office 365 服务运行状况和更改监视服务运行状况和即将进行的更改。 使用此 API 来创建自己的监视工具，或将您现有的监视工具连接到 Office 365 服务通信，有可能简化了如何监视您的环境。 有关详细信息，请参阅[Office 365 的企业开发人员](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                               | 节奏   | 分配团队 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 监视服务运行状况 | 通过使用可用的工具，可以主动监视 Microsoft 小组服务状况、 （和相关服务）。 依赖的服务包括： 为企业，Azure Active Directory Exchange 联机，SharePoint Online，OneDrive。 | 实时 |               |
| 事件通知  | 通知事件的影响团队服务的内部利益相关的者。 内部利益相关者可以包含用户、 支持人员和事件管理器。                                                                          | 根据需要 |               |

### <a name="references"></a>引用 

[如何检查 Office 365 服务运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[对于 Microsoft 小组验证服务运行状况](https://docs.microsoft.com/microsoftteams/service-health)

[服务运行状况和连续性](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理变革

Microsoft 的小组是一个基于云的服务。 伴随这种能够提供新的特性和功能，以快速的步调。 提供持续的技术创新提供明显的益处的组织，但需要组织为了避免用户的阻力或输送到您帮助台内适当地管理这些更改。

对团队的更新的推出会自动给您的用户。 您的用户总是会有最新的客户端和服务团队中可用的功能。 不能管理团队对您的用户推出，因此它是非常重要，要通过有效的沟通、 培训和采用程序的更改管理。 如果您的用户了解这些更改，教育的优点，并能够利用新的功能&mdash;他们将能够更快地适应，欢迎该更改。

### <a name="monitoring-for-change"></a>监视的更改

更改管理的第一步监视员计划的更改。 监视这些更改的最佳来源是[Office 365 的路线图](https://products.office.com/business/office-365-roadmap)，其中列出了当前正在开发，给客户，转出或已完全启动的功能。 您可以使用筛选器提供，搜索小组特定的功能或您可以下载到 Excel 文件供进一步分析的路线图。 对于每个功能，路线图提供简短的说明，以及预期的发行日期。

在[Microsoft 小组博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)，您可以了解有关最佳做法、 趋势和有关团队产品更新的新闻。 希望找到主要功能更新团队能够在这里宣布的。 您还可以订阅的 RSS 源通过博客。 可以将[RSS 源](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)直接集成到团队通道，以便直接在团队内交付所有重要的新闻。

[发行说明，了解 Microsoft 小组](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)中记录被释放的所有功能。
在此您将桌面、 web 和移动设备，找到发布的功能的列表。 一组相同的发行说明也是[Microsoft 小组 T Bot](https://docs.microsoft.com/microsoftteams/t-bot)的发行说明选项卡上。

熟悉的可用资源，并确保指定适用的所有者更改为监视。

### <a name="planning-for-change"></a>对更改的规划

现在，您已经知道即将做出的更改对小组服务下, 一步是准备并作出相应的计划。 评估每项更改，以便确定哪些更改需要给用户，认识活动培训的支持小组或用户或功能接受和评估市场活动的通信。 这是您的组织中的更改管理团队的主要作用。 下面是的示例表，可帮助您规划更改的集合。

[//]: # (列跨度和此表中的行跨度是可爱的但不支持在减价，至少 rowspan 是。这是关闭并无法得到。也许整件事都需要重新设计。)

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能： 云录制 (发布日期： 1 月 2018年)

**常规的轨道**
| 更改准备就绪 | 状态   | 注释/下一个步骤 | 所有者 |
|----|----|----|-----|
| 法律审查   | 完成     | 此功能是为服务培训团队的先决条件。 | 项目团队  |

**技术变更管理**
| 更改准备就绪 | 状态   | 注释/下一个步骤 | 所有者 |
|----|----|----|-----|
| 所需的 IT 更改          | 是                  | 管理员还必须能够为已识别的用户记录。      | 支持团队           |
| 技术准备工作完成 | 是                  |                                                                 | 支持团队  
         |
**用户更改管理** 
| 更改准备就绪 | 状态   | 注释/下一个步骤 | 所有者 |
|----|----|----|-----|
| 对用户的影响                  | 低                  |                                                                 |                        |
| 用户所需的准备工作      | 是                  |                                                                 |                        |
| 通信准备就绪         | 否                   | 通信电子邮件已在起草筹备，等待审核。            | 通信小组    |
| 培训准备               | 是                  | 培训将利用现有 Microsoft 视频。                | 培训团队          |

**状态跟踪**
| 更改准备就绪 | 状态   | 注释/下一个步骤 | 所有者 |
|----|----|----|-----|
| 发布状态               | 正在进行中          | 按上级主管的待定。               | 更改管理小组 |
| 发行签收             |                      |                                                                 |                        |
| 发行日期                 |                      |                                                                 |                        |

有关规划与团队的变更管理的详细信息，请参阅[创建用于 Microsoft 小组的变化管理策略](https://docs.microsoft.com/microsoftteams/change-management-strategy)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动               | 说明                                                                                                                                                                                                                | 节奏   | 分配团队 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 变更监视器     | 对即将到来的更改 Microsoft 小组服务监视器。                                                                                                                                                                   | 每天     |               |
| 对更改的规划    | 评估和规划的新特性和功能，包括沟通计划、 认识活动和培训。                                                                                                     | 根据需要 |               |
| 用户准备工作             | 执行目标的通信、 安全意识或培训活动，以确保用户准备即将到来的变化。                                                                                                        | 根据需要 |               |
| 支持团队准备工作 | 执行目标的通信、 安全意识或培训活动，以确保支持团队已准备就绪。 支持团队可以包括"白手套"团队、 支持人员、 第 2 层或第 3 层支持、 外部合作伙伴，依次类推。 | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>评估团队使用

初次试用中开始之后，建立用于测量实际的团队使用常规节奏至关重要。 这使，深入了解如何实际使用您的组织符合在构想阶段中预测的使用量。 虽然本节集中讲述有关小组的使用情况，这应该是衡量和评估 Office 365 使用整体更广泛努力的一部分。

查看部署中的使用经常提前为您提供机会：

-   验证是否用户使用团队。

-   之前他们在组织内创建关键问题识别潜在接受挑战。

-   了解是否有构想阶段要求和实际使用情况之间的差异。

如果使用不是您的期望，这可能是由于部署问题，或采用计划不被执行正确，或一些其它问题。 根据实际低使用率的背后原因，服务管理员必须与可帮助删除使用障碍的相关团队进行协作。

### <a name="measuring-usage-with-the-office-365-admin-center"></a>测定与 Office 365 管理中心的使用情况

从团队的使用率数据可用于报告仪表板。 在三个不同的报告中找不到团队使用情况数据。 第一份报告提供了跨产品视图的用户的通信和协作在 Office 365 中使用的各种服务方式。 此报表可以在以下位置找到： [Office 365 活动用户报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他两个报告是特定的团队，和他们提供进一步的详细信息有关小组的使用从用户和设备的角度来看。 可以在此处找到这两个报告：

[Microsoft 的小组的设备使用情况报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft 小组用户活动报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>所需的权限

管理中心中的使用率报表可以由**全局管理员**角色或特定于产品的管理角色 （**Exchange 管理员**、**企业管理员的 Skype**， **SharePoint 已分配的人管理员**)。

此外，**报告读者**角色仅供需要访问的报告，但不执行任何任务需要管理员级别权限的用户。 分配此角色提供使用率报告向利益相关者，显示器和驱动器采用任何人。 有关可用的不同角色的详细信息，请参阅[有关 Office 365 管理角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>评估使用情况

您已经使用报告仪表板测量使用情况之后，务必将根据您在项目的构想阶段定义任何关键的成功指标 (KSIs) 测得的使用情况进行比较。 您可以定义可能定义为活动使用，KSI 或一个是间接地链接到活动的用法。

请务必确定前继续推广到其他站点或用户的实际的和计划使用量之间的任何差异。 您可能要知道组织经验教训作为您可以利用以确保此活动一部分的下一批站点或用户不会遇到同样的问题。

首先，查明这是否采用和 （或） 技术的问题。 首先，研究之下，项目进行排序，以确定问题所在。

1.  通过执行[质量经验审查](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#quality-of-experience-review-guide)验证质量。

2.  若要检查有无趋势的技术问题，导致无法访问或使用服务的用户技术支持团队工作。 如果确实存在问题的趋势，使用本文内下文中的[终结点故障排除](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#endpoint-troubleshooting)部分来尝试支持先解决问题。

3.  工作与培训和采用团队收集的 （请参阅本文后面的[评估用户主观意图](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#assess-user-sentiment)） 的用户，直接的反馈，并检查接受和认知活动的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                         | 说明                                                                                                                      | 节奏   | 分配团队 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 度量值用法 （支持阶段） | 测量并评估站点继续进行 onboarded 的实现阶段，团队使用。 解决问题所需的使用问题。 | 每周    |               |
| 度量值使用                    | 测量并在驱动器值阶段 （完成部署） 后评估团队使用。 解决问题所需的使用问题。 | 半月刊  |               |
| （驱动器值阶段）              |                                                                                                                                  |           |               |
| 更新采用计划             | 采用计划根据如何测量使用率比较到您的规划目标。                                         | 根据需要 |               |

### <a name="references"></a>引用 

[有关 Office 365 管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Office 365 管理中心中的活动报告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>评估用户主观意图

了解用户观点可以作为用于测定团队部署成功的关键标志。 用户反馈可以驱动更改在您的组织;这可能包括对沟通计划、 培训计划或您向您的用户提供支持的方式。

请务必尽早获得反馈，并继续评估用户的整个生命周期的项目内外的主观意图。 使用以下指导来确定您的组织将在其中寻找反馈的时间间隔：

-   **项目的开始**： 通过评估用户主观意图在项目的开始，您可以尽早看到到您的用户如何看法他们团队的经验。

-   **后主要里程碑**： 通过收集反馈信息在整个项目生命周期，可以测量用户在连续的基础上的主观意图并根据需要进行更改。 这是主要的里程碑后尤其有用。

-   **项目总结**： 评估用户主观意图在项目的末尾将告诉您如何更好地所做的和在其中仍然需要工作来完成，并使您可以根据先前的调查结果进行比较。

-   **日常**： 继续无限期地测量用户主观意图。 用户主观意图的变化可能是由于您的组织环境中的更改或团队服务中的更改。 通过定期测定用户主观意图，您可以了解如何更好地执行您的服务管理团队，并组织响应团队服务中的更改。

可以通过许多不同的方法评估用户主观意图。 其中可以包括电子邮件调查、 当面或电话式面试，或者只在团队或 Yammer 创建反馈通道。 有关详细信息，请参阅[Microsoft 小组中的用户反馈方法的最佳做法](https://docs.microsoft.com/microsoftteams/best-practices-feedback)。

此外可以使用一种行业的方法来评估用户观点称为净 promotor 得分 (NPS)，即在下一节中所述。

### <a name="nps"></a>NPS 

净者均得分 (NPS) 是行业客户忠诚度公制单位和一个好的方法来使用它来评估用户主观意图。

NPS 可以计算方法提出两个问题:"可能性有多大是您推荐给同事团队？"，跟自由格式的问题，"为什么？"

NPS 是一个索引，范围从-100 到 100，衡量推荐公司的产品或服务的客户的意愿。 NPS 根据通过电子邮件或其他电子方式向用户提供匿名调查。 NPS 测量提供者和使用者之间的忠诚度。 它包含的只有一个问题，询问用户来评价他们的体验从 1 到 10，提供附加批注的选项。 用户然后分类基于以下分级：

-   9 或 10 的升级： 将升级您的服务和其他燃料的忠实爱好者。

-   7 或 8 是被动： 满意，但 unenthusiastic，容易受到另一个服务或产品。

-   从 1 到 6 是说三道四： 不满意的客户可以损坏您的服务并妨碍增长。

![此图演示 NPS 比例。它将显示 0-6 的排名会说三道四，7-8 是被动和 9-10 是升级。](media/operate-my-service-image2.png "此图演示 NPS 比例。它将显示 0-6 的排名会说三道四，7-8 是被动和 9-10 是升级。")

虽然 NPS 底数很有用，您将从分析用户意见获得最大价值。 他们将帮助您了解为什么用户会 （或不） 团队向其他人推荐。 这些注释可以提供有价值的反馈，以帮助项目或服务管理团队了解提供高质量的服务所必需的调整。

为了提供 NPS 为您的组织的调查，您可以利用您最喜爱的网上调查的工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/为所需的任务

| 活动              | 说明                                                                                                                                                                         | 节奏   | 分配团队 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 评估用户主观意图 | 捕获并评估用户主观意图，通过调查或面试，或通过在团队或 Yammer 反馈渠道。                                                                 | 根据需要 |               |
| 更新采用计划 | 根据用户反馈，则为您组织中的驱动器更改这可以包括对沟通计划、 培训计划或您向您的用户提供支持的方式。 | 根据需要 |               |

### <a name="references"></a>引用 

[净者均得分](https://en.wikipedia.org/wiki/Net_Promoter)

[使用 Yammer 收集反馈](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[用户反馈的最佳做法](https://docs.microsoft.com/microsoftteams/best-practices-feedback)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理网络质量

许多核心规划元素进入优化，校正规模并纠正网络基础结构以确保 Microsoft 小组服务高质量、 有效路径。 我们以前的[网络准备工作](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness)指南中介绍了规划的任务和要求。 网络经常随时间由于升级、 扩展或其他业务需求。 值得您考虑为您的团队要求网络规划活动中。

虽然网络规划团队部署的一个重要方面，是同样重要的是要确保网络保持健康和保持最新状态，根据不断变化的业务或技术要求。

若要确保您的网络的运行状况，需要定期执行大量操作活动。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                                                       | 说明                                                                                                                                                                                                                                                                                                                                                                 | 节奏                | 分配团队 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 监视 Office 365 的 IPs 和 Url                                | 使用[RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)提供监控到[Office 365 Url 和 ip 地址](https://aka.ms/o365ips)的任何更改并启动更改请求到适用的网络组。                                                                                                                                | 每天                  |               |
| 更新网络上对 Office 365 IPs 和 Url 的更改 | 对适用的网络组件 （防火墙、 代理服务器、 Vpn、 客户端的防火墙等） 来反映对[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)的更改进行更新。                                                                                                                                                              | 根据需要              |               |
| 提供构建数据                                          | 更新子网信息提供给质量冠军 （或利益相关者） 以确保[生成中 CQD 的定义](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)将保持为最新。 | 根据需要              |               |
| 实施更改                                               | 支持不断变化的团队业务和技术需求的网络上实施更改。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wi-Fi 网络</li><li>互联网连接和 ExpressRoute</li><li>DNS</li></ul>     | 根据需要              |               |
| 网络监视和报告                               | 通过使用您现有的第三方网络管理工具和报告功能可从您的网络提供商监控网络端到端的可用性、 利用率和容量趋势。 使用网络容量计划的趋势数据。                                                                                                            | 每天、 每周、 每月一次 |               |
| 容量规划                                              | 与团队服务所有者，了解不断变化的业务和技术要求，它们可能会促使更多容量的更改进行协作。 利用[网络计划](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)，以确保足够的带宽供 Microsoft 小组的结果。                               | 根据需要              |               |
| 网络故障诊断和修正                        | 协助团队支持人员、 服务所有者和主要的利益相关者进行故障排除和修正到团队连接性、 可靠性或质量相关的问题。 网络元素可以包括：<ul><li>防火墙</li><li>Vpn</li><li>有线和 Wi-Fi 网络</li><li>互联网连接和 ExpressRoute</li><li>DNS</li></ul>    | 根据需要              |               |
| 灾难恢复和高可用性测试                | 执行常规的高可用性和灾难恢复测试以确保它满足既定的服务级别目标 (Slo) 或为团队服务的服务等级协议 (Sla) 的网络基础结构。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>引用 

[网络规划器](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[构建数据架构](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>评估并确保质量 

所有组织都需要负责质量组或个人。 这是服务管理中最重要的角色。 质量拥护者角色分配给用户或组的致力于他们的用户体验。
此角色需要的技能来标识中的趋势的环境中和资助，以推动修正的其他小组的工作。 质量支持者的最佳候选人通常是客户服务所有者。 根据组织的规模和复杂性，这可能是任何用户组，以确保高质量用户体验的激情。

质量冠军利用现有工具和有案可稽的流程，如呼叫质量仪表板 (CQD) 并监视用户体验质量的经验审查指南 》，确定质量趋势，并推动补救措施在需要的地方。
质量冠军应使用驱动器的补救动作，各自团队和一个指导委员会报告进度和任何打开的问题有关。

[质量的经验审查指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)包括评估，并提供了补救措施指导对提高用户体验的影响大的关键领域中的活动。 质量经验审查指南 》 中提供的指南主要讲述如何使用联机 CQD 作为主要工具报告并调查每个区域中的，音频，以最大限度地采用和影响为重点。 为提高音频体验到网络所做的任何优化将还直接翻译为视频和桌面共享的改进。

我们强烈建议您尽早提名质量冠军。 在被提名后他们应该开始熟悉质量经验审查指南和相关的培训材料中的内容。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                               | 说明                                                                                                                                                                                                                                                                                                 | 节奏                             | 分配团队 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名和训练质量 champion(s) | 提名和训练质量 champion(s)。                                                                                                                                                                                                                                                                   | 根据需要                           |               |
| 质量的经验审查     | 向组织中的主要利益相关者执行质量经验审查 (QER)，以确定在质量和可靠性的发展趋势，审查对定义的目标，并报告。                                                                                                                            | 每月 （每周期间部署） |               |
| 驱动器的补救                      | 协调整个组织基于 QER 评估和调查结果的修正工作。                                                                                                                                                                                                           | 根据需要                           |               |
| 构建中 CQD 的数据更新            | 更新或添加新的生成定义中 CQD 时对网络进行更改, （请参阅[上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)）。 | 根据需要                           |               |
| 担任质量 Champion(s)      | 端到端组织中的质量责任。 这包括：<ul><li>确保定期进行 QER。</li><li>向质量状态的关键利益相关者报告。</li><li>确保定义是最新的生成数据。</li><li>协调整个组织，以确保用户可以与团队提供高品质的体验的补救工作。</li></ul>          | 每天                               |               |



### <a name="references"></a>引用 

[了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[上载的构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[质量的经验审查指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理终结点

可以将 Microsoft 小组终结点定义为任何 PC、 Mac、 平板电脑或移动 （或任何其他） 设备运行团队客户端。 术语*终结点*不只包括设备本身，但如何在用户连接到设备 — — 例如，通过使用该设备的内置麦克风或扬声器、 耳机或优化的头戴式耳机。 它们在部署后，必须不忘终结点。 团队终结点需要日常保养和维护。 以下各节介绍特定区域重点。

### <a name="endpoint-requirements"></a>终结点要求

团队的主要优点之一是，客户端最新的自动保持。 在 PC 和 Mac 上的客户端使用一个后台进程，检查新生成并下载新的客户端，当应用程序处于空闲状态更新。 移动应用程序通过其各自的应用程序商店将保留当前的团队。

小组客户端必须在基础软件平台方面的最低要求。 这些需求可能随着时间的推移发生变化，因此很重要的更改监视它们。 例如，团队客户端具有最小的 iOS 版本。 如果客户端使用 internet 浏览器，浏览器需要也会保持最新。 在[将客户端获取有关 Microsoft 小组](https://docs.microsoft.com/microsoftteams/get-clients)找不到受支持平台的列表。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验有很大的影响。
客户端防火墙可以影响通话质量，甚至导致在建立呼叫。 在配置客户端防火墙上了相应的排除项后，他们需要保留最新的基于[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息。 第三方供应商将有如何更新了排除项的具体指导。

### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

Wi-fi 驱动程序可能有问题。 例如，驱动程序可能必须访问点可以诱发不必要接入点切换，从而导致较差的呼叫质量之间的极具挑战性漫游行为。 可能通过质量经验审查发现差的 Wi-fi 驱动程序 （请参阅更详细[的经验审查指南的质量](https://aka.ms/qerguide)）。 实施监视新的 Wi-fi 驱动程序并确保他们正在测试然后再部署到的常规用户群体的质量驱动进程至关重要。

### <a name="endpoint-management"></a>终结点管理

提供和维护，应该是受支持的终结点和接口设备 （如耳机） 的目录。 此目录将包含一份批准的设备选择和验证的前景展望和服务阶段的一部分。 通常情况下，特定设备为您的组织中每个角色类型选择和满足该角色的属性。 所有终结点具有生命周期，并且没有需要管理供应商合同、 保修、 替换、 分发和维修这些设备与相关联的策略。

### <a name="endpoint-troubleshooting"></a>终结点进行故障排除

即使您已经遵循以前的指南，您组织中的用户仍然可能遇到问题的团队。 尽管问题可能不具有自身的终结点，此问题的症状是通常出来后通过客户端用户。 以下指南旨在提供常规步骤可以解决此问题;它并不是说要进行全面的故障排除指南。 按特定的顺序，提供的步骤，但没有明确遵守并可能不适用，这取决于问题的性质。

1.  **验证服务运行状况：**用户可能会遇到的问题可能与对团队服务或及其相关的服务产生负面影响的事件。 作为第一步，我们建议您确认没有主动服务的问题。 请查阅[如何检查 Office 365 提供服务的运行状况](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    记得要检查的状态相关的服务 （示例;交换，SharePoint，OneDrive 的业务)。 监视服务健康一节中更详细地讨论了对**监视服务健康。**

2.  **验证客户端连接：**连接问题导致团队中的功能或登录问题。 （尤其对于新的网站或位置） 我们建议您验证连接到该服务。 确保以下[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)指导后面的每个站点。 您可以利用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来执行连接测试，以验证正确已为云语音功能打开媒体端口。 在[网络准备](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness)指南提供了有关如何运行连接测试的详细的步骤。

3.  **检查已知的问题列表：**咨询[小组的已知问题列表](https://docs.microsoft.com/MicrosoftTeams/known-issues)以确定是否已被用户负面影响的问题之一。 请按照提供 （如果有） 来解决此问题的替代方法。

4.  **访问 Microsoft 技术社区：**[Microsoft 技术社区团队](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)的团队提供了专用的空间。 小组团体提供讨论列表、 博客张贴内容，并以团队为中心的公告。 可以将问题发布到或搜索上述讨论的解决方案与您的问题。

5.  **与 Microsoft 支持部门联系：**您可以与 Microsoft 技术支持团队在线或通过电话与问题。 有关信息，请参阅[Microsoft 小组的支持联系人](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。
    卓越的客户支持请求可以由以下[联系人](https://support.microsoft.com/premier/contacts)支持 Microsoft 小组 （高级客户） 的指导。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                 | 说明                                                                                                                                                                                                                                                                                                                                                                     | 节奏   | 分配团队 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 终结点要求    | 确保继续满足为团队[获得 Microsoft 小组客户端](https://docs.microsoft.com/microsoftteams/get-clients)的所有软件要求团队的终结点。                                                                                                                                                                                       | 每月   |               |
| 终结点防火墙       | 维护适当排除在终结点防火墙根据[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)的文章中的信息。 第三方供应商将有如何维护了排除项的具体指导。 订阅[RSS 源](https://support.office.com/en-us/o365ip/rss)进行的更改会自动通知。 | 根据需要 |               |
| Wi-fi 驱动程序            | 测试并更新计算机上的 Wi-fi 驱动程序。 通过使用 CQD （[经验审查指南的质量](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/CloudVoice-working/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)） 来验证结果。                                                                                                                                                                                                                                                                   | 根据需要 |               |
| 终结点管理      | 维护受支持的终结点和接口设备 （如耳机） 的目录。 管理供应商合同、 保修、 分布、 更换和修复策略。                                                                                                                                                                                                        | 每月   |               |
| 终结点进行故障排除 | 故障排除任务可以包括;验证连接性、 已知的问题列表、 日志收集、 分析和上报给 Microsoft 技术支持或第三方供应商咨询。                                                                                                                                                                                               | 根据需要 |               |

### <a name="references"></a>引用 

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)

[获取 Microsoft Teams 的客户端](https://docs.microsoft.com/microsoftteams/get-clients)

[Microsoft Teams 技术社区](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[对于 Microsoft 小组的已知的问题](https://docs.microsoft.com/MicrosoftTeams/known-issues)

[对于 Microsoft 小组验证服务运行状况](https://docs.microsoft.com/microsoftteams/service-health)

[与支持部门联系业务产品的管理帮助](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&rs=en-US&ad=US)

[联系人卓越](https://support.microsoft.com/premier/contacts)

[小组视频疑难解答](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理团队

在部署 Microsoft 小组服务后，您需要执行与管理有关的若干活动。 活动范围从管理服务和个人用户对容量规划和资源调配的授权和电话号码。 以下各节介绍其中的一些常见管理任务。

### <a name="service-administration"></a>服务管理

团队服务已可以设置组织范围内的多个设置。
为组织设置所做的更改会影响所有用户已启用为团队的。 有关这些设置的详细列表，请参阅[打开 Microsoft 小组 Office 365 提供组织中的功能](https://docs.microsoft.com/microsoftteams/enable-features-office-365)。

### <a name="user-administration"></a>用户管理

若要支持的用户，组织可能需要任意数量的相关任务 — — 特定任务因组织到下一个。 最终，这些任务需要由这些运营职责分配了一个支持团队来管理。 下列任务经常需要支持的团队中的用户。

#### <a name="general-tasks"></a>常规任务

[管理用户对 Microsoft 小组访问](https://docs.microsoft.com/microsoftteams/user-access)

#### <a name="common-tasks-for-phone-system"></a>电话系统的常见任务

[为用户分配、更改或删除电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)

[为用户分配或更改紧急地址](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[添加、 更改或删除您的组织紧急地点](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[创建并管理拨号计划](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

#### <a name="common-tasks-for-audio-conferencing"></a>音频会议的常规任务

[更改音频会议网桥的设置](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge)

[更改音频会议网桥的电话号码](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge)

[管理用户的音频会议设置](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/manage-the-audio-conferencing-settings-for-a-user)

[重置用户的音频会议 PIN](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/reset-the-audio-conferencing-pin-for-a-user)

### <a name="license-management"></a>许可证管理

随着您的组织成长或合同，值得您计划当前和未来需要的授权。 还有一个基本的团队许可证，除了云语音功能 （[电话系统](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system?ui=en-US&rs=en-US&ad=US)和[音频会议](https://products.office.com/skype-for-business/audio-conferencing)） 的授权。

对于团队，电话系统许可证要求相关[调用规划](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)许可证。 调用计划授权可拨打和接听国内和/或国际电话。 这些计划是基于使用的并具有每分钟池与它们相关联。 资源调配[通信贷](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)将确保永远不会运行停止服务。

音频会议允许拨入会议 tolled 和国内拨出的会议服务。 免费拨入会议或非国内拨出方案可能会使您的[通信贷](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)招来其他收费是必需的。

通信信用可以补充调用计划和音频会议的许可证。 调用规划许可证和通信贷都是基于使用情况的因此需要监视并相应地设置的。

您可以利用[PSTN 使用报表](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)来帮助监视您的调用计划分钟的使用率和通信贷。 根据该活动的结果，您可以调整相应许可证。 很快，我们将提供[PSTN 分钟池](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report)报表来更有效地帮助完成此任务。

### <a name="telephone-number-management"></a>电话号码管理

有两种方法来获取在团队中的数字： 可以移植从另一个提供商的电话号码或可以提供直接从 Microsoft 的数字库存数字。 这两种方法详见[获得为您的用户的电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)。

没有电话号码，可以提供从 Microsoft 的数字库存量的限制。 限制取决于多种因素，详细说明[您可以获得多少个电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)。
限制取决于类型的数字 — — 收费电话免费服务数字、 收费电话服务号码和订户 （用户） 号。 每有自己的局限性，必须单独管理。 如果您正在接近限制 （或已达到上限），您可以应用增量的限制。 上述文章中介绍此过程。

可能有大量不可可用于提供服务的区域中时的时间。 有关申请数字的过程的信息，请参阅[管理您的组织的电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>团队创建 （可选）

默认情况下，所有具有联机 Exchange 邮箱的用户有权创建 Office 365 组和工作组，因此，Microsoft 小组。 如果您想要有更严格的控制和[限制创建新团队](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions#permissions-to-create-teams)（以及创建新的 Office 365 组），您可以委派创建组和管理组的管理员权限。 如果您的组织想要开拓此选项，请参阅本文以允许用户提交的分配任务的工作组处理的请求中描述的过程。

<!--ENDOFSECTION-->

## <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每周/每月/按需任务

| 活动                    | 说明                                                                                                                                                                                                                                                                                                                                                                                                             | 节奏   | 分配团队 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服务管理      | 管理租户范围的团队设置。                                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 用户管理         | 基于用户的设置和在团队中授权管理。                                                                                                                                                                                                                                                                                                                                                           | 根据需要 |               |
| 许可证管理          | 通过利用[PSTN 使用情况报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)和[PSTN 分钟池](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report)报告计划当前和未来的需要，为用户和基于消耗的授权 （调用计划和通信贷）。 | 每周    |               |
| 电话号码管理 | 管理可用于未来的增长的电话号码，并调整库存水平，以满足您组织的需要。                                                                                                                                                                                                                                                                                                | 每周    |               |
| 团队创建 （可选）    | 团队创建的审查和处理请求。                                                                                                                                                                                                                                                                                                                                                                          | 根据需要 |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>质量的经验审查指南
质量经验审查指南有一套评估和提供补救措施指导对提高用户体验的影响最大，在下图中所示的关键领域中的活动。

![的关键领域，在质量检查体验评审： 音频、 可靠性和用户调查结果。](media/plan-my-service-management-image2.png "的关键领域，在质量检查体验评审： 音频、 可靠性和用户调查结果。")

通过不断地评估和纠正本文所述的区域，您可以减少他们可能会对用户体验产生负面影响。 在部署中遇到的大多数用户体验问题可以分为以下几类：

-   不完整的防火墙或代理服务器配置

-   较差的 Wi-fi 覆盖范围

-   没有足够的带宽

-   VPN

-   使用优化的还是内置的音频设备

-   有问题的子网或网络设备

使用的主要工具作为呼叫质量仪表板 (CQD) 联机报告并调查每个所述，音频，以最大限度地采用和影响为重点的区域重点质量经验审查指南 》 中提供的指导。 为提高音频体验到网络所做的任何优化将还直接翻译为视频和桌面共享的改进。

我们强烈建议您尽早提名质量冠军。 在被提名后他们应该开始熟悉[质量经验审查指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)中的内容。

<!--ENDOFSECTION-->