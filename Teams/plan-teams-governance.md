---
title: 团队-Microsoft 团队中的治理规划
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 了解如何规划团队中实现调控功能。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 048b9dd09e9309c4aaaf1af3b92d7e24f280d088
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883249"
---
# <a name="plan-for-governance-in-teams"></a>团队中的治理规划

团队提供了一组丰富的工具，以实现您的组织可能需要任何管理功能。 本文指导 IT 专业人员提出正确的问题，以确定他们的调控和如何满足这些要求。 

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>组和团队创建、 命名、 分类和来宾访问

您的组织可能要求您实现严格控制如何命名和分类团队、 是否可以作为工作组成员添加来宾和谁可以创建团队。 您可以使用 Azure Active Directory (Azure AD) 配置每个区域。 

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>您的组织是否需要为团队的特定命名约定？</li><li>团队创建者是否需要能够向工作组分配特定于组织的分类？</li><li>您是否需要限制将来宾添加到每个团队基于团队的功能？</li><li>贵组织需要限制哪些人可以创建团队？</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档的团队创建、 命名、 分类和来宾访问组织的要求。</li><li>按计划实现这些要求作为您的团队推出的一部分。</li><li>通信和发布您的策略以向团队用户告知他们可以预期的行为。</li></ul>|

> [!TIP]
下表用于捕获贵组织的要求。
|功能 |详细信息 |Azure AD Premium <br> 所需的许可证 |决策 |
|---------|---------|---------|---------|
|团队命名策略 | 使用基于前缀后缀、 自定义已阻止单词。 |P1 |TBD |
|团队分类 |向工作组分配分类。 |P1 |TBD |
|团队来宾访问 |允许或阻止来宾添加到团队。 |否 |TBD |
|团队创建 |限制向管理员团队创建。 |否 |TBD|
|团队创建 |限制团队创建安全组成员。 |P1 |TBD|

> [!NOTE]
> 可帮助您规划提前，[了解更多有关这些策略设置和哪些所需的许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。

> [!NOTE]
> 限制组和团队创建会降低用户工作效率，因为许多 Office 365 服务需要服务的函数创建的组。 有关其他信息，导航到，展开[为什么控制谁创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他信息

您已确定您的要求后，您可以使用 Azure AD 控件来实现它们。 有关如何实施这些设置的技术指导信息，请参阅：

-   [配置组设置的 azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

-   [强制在 Azure Active Directory 中的 Office 365 组命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

-   [Office 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>组和团队过期、 保留和存档

您的组织可能已设置的到期日期保留策略的其他要求和存档团队团队需要数据。 可以配置组过期策略，以自动管理生命周期的组和保留策略保留或删除的信息，根据需要且可以存档团队 （将它们设置为只读模式） 若要保留的时间点视图的工作组的不再处于活动状态。

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>贵组织需要指定团队的到期日期？</li><li>贵组织需要的特定数据保留策略应用于工作组？</li><li>您的组织是否希望需要能够存档非活动团队保留只读状态中的内容？</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>文档团队过期、 数据保留和存档的组织的要求。</li><li>按计划实现这些要求您的团队推出的一部分。</li><li>通信和发布您的策略以向团队用户告知他们可以预期的行为。</li></ul>|

> [!TIP]
下表用于捕获贵组织的要求。
|功能 |详细信息 |Azure AD Premium <br>所需的许可证 |决策 |
|---------|---------|---------|---------|
|过期策略 |通过设置过期策略管理 Office 365 组的生命周期。 |P1 |TBD|
|保留策略 |保留还是删除在特定时间段内的数据 （团队通道消息和频道文件），通过为团队的保留策略设置中的安全性和合规性中心。 **注意**： 使用此功能要求许可或以上的 Office 365 企业版 E3。 |否 |TBD |
|存档和还原 |存档团队不再处于活动状态时，但您希望保留其周围的引用或将来重新激活。 |否 |TBD |

> [!Note]
> 组到期时间是 Azure AD Premium 功能。 能够使用此功能，您的租户必须为配置的设置和受影响的组的成员的管理员具有订阅 Azure AD Premium 和许可证。

#### <a name="additional-information"></a>其他信息

有关如何实施这些设置的技术指导信息，请参阅：

-   [设置 Office 365 组过期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。

-   [设置团队保留策略](security-compliance-overview.md#retention-policies)。

-   [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。


## <a name="teams-feature-management"></a>团队功能管理

治理和生命周期管理团队的另一个重要方面是控制哪些功能您的用户将可以访问的能力。 您可以管理消息、 会议、 和呼叫功能，可以在 Office 365 租户级别或每个用户。 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>贵组织需要整个租户限制团队功能？</li><li>贵组织需要限制为特定用户的工作组功能？</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>文档的限制团队功能在租户和用户级别的组织的要求。</li><li>按计划实现您的特定要求您的团队推出的一部分。</li><li>通信和发布您的策略以向团队用户告知他们可以预期的行为。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>团队功能管理会议状态中心区域

团队提供精细的控制消息、 会议、 呼叫，和实时事件功能及其他内容，通过策略功能。 默认情况下或每个用户根据您的组织的需要，可以向所有用户应用不同的策略。 

所有设置，包括有关如何为您的组织，实现这些技术指南的详细列表，请参阅以下文章：

-   [管理 Office 365 组织中的 Microsoft 团队功能](enable-features-office-365.md)
-   [转换为新的 Microsoft 团队和业务管理中心的 Skype 的过程管理团队](manage-teams-skypeforbusiness-admin-center.md)
-   [管理团队中的会议策略](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>安全性和遵从性

团队基于的高级的安全和 Office 365 合规性功能和支持审核和报告、 合规性内容搜索、 电子发现、 法律挂起和保留策略。 

> [!Important]
> 如果您的组织具有合规性和安全要求，查看有关本主题[概述安全性和合规性中的 Microsoft 团队](security-compliance-overview.md)一文中提供的深入内容。

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->