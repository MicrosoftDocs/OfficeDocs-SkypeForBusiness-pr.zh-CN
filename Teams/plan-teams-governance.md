---
title: 在 Teams 中规划管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，你将了解如何规划如何在团队中实施管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416914"
---
# <a name="plan-for-governance-in-teams"></a>在 Teams 中规划管理

团队提供了一组丰富的工具来实施你的组织可能需要的任何监管功能。 本文指导 IT 专业人员提出正确的问题来确定他们对公司治理的要求以及如何满足这些要求。 

> [!Tip] 
> 观看以下会话以了解有关 Microsoft 团队中的管理的详细信息： [Microsoft 团队中的管理、管理和生命周期](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>组和团队创建、命名、分类和来宾访问

你的组织可能要求你实施严格的控制来控制团队的命名方式和分类方式，是否可以将来宾添加为团队成员以及谁可以创建团队。 你可以通过使用 azure Active Directory (Azure AD) 和灵敏度标签来配置这些区域。 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |决策点|<ul><li>您的组织是否需要针对团队的特定命名约定？</li><li>团队创建者是否需要将组织特定的分类分配给团队的能力？</li><li>是否需要限制按团队为团队添加来宾的能力？</li><li>您的组织是否需要限制哪些人可以创建团队？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|后续步骤|<ul><li>记录组织对团队创建、命名、分类和来宾访问的要求。</li><li>计划在团队推出过程中实施这些要求。</li><li>传达和发布你的策略以通知团队用户他们所期望的行为。</li></ul>|

> [!TIP]
> 使用下表来捕获组织的要求。

|功能 |详细信息 |Azure AD Premium <br> 需要许可证 |作出 |
|---------|---------|---------|---------|
|团队命名策略 | 使用基于前缀的后缀、自定义阻止的字词。 |P1 |TBD |
|团队分类 |为团队分配分类。 |P1 |TBD |
|团队来宾访问 |允许或阻止将来宾添加到团队。 |否 |TBD |
|团队创建 |将团队创建限制为管理员。 |否 |TBD|
|团队创建 |将团队创建限制为安全组成员。 |P1 |TBD|
|灵敏度标签|配置隐私和来宾共享|否|TBD|

> [!NOTE]
> 为了帮助您提前计划，请 [了解有关设置这些策略以及所需的许可证的详细信息](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制组和团队创建会降低用户的工作效率，因为许多 Microsoft 365 和 Office 365 服务都需要创建组才能使服务正常工作。 有关其他信息，请导航到并展开 [控制创建 Microsoft 365 组的人员的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。


#### <a name="additional-information"></a>其他信息

确定你的要求后，你可以使用 Azure AD 控件实现它们。 有关如何实现这些设置的技术指南，请参阅：

- [用于配置组设置的 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [在 Azure Active Directory 中强制使用 Microsoft 365 组的命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [使用敏感度标签保护 Microsoft 团队、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [组、团队和 Yammer 的生命周期选项结束](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>组和团队过期、保留和存档

你的组织可能对为过期、保留和存档团队和团队数据 (通道消息和频道) 文件设置策略的其他要求。 你可以将组过期策略配置为自动管理组和保留策略的生命周期，以根据需要保留或删除信息，你可以将团队存档 (将其设置为只读模式) 以保留不再处于活动状态的团队的时间点视图。 请注意，已存档的团队将继续应用过期策略，并且可能会删除，除非已排除或已续订。

|           |            |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>您的组织是否需要为团队指定到期日期？</li><li>您的组织是否需要向团队应用特定的数据保留策略？</li><li>您的组织是否希望能够将非活动团队存档以使内容保持为只读状态？</li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织对团队过期、数据保留和存档的要求。</li><li>计划在团队推出过程中实现这些要求。</li><li>传达和发布你的策略以通知团队用户他们所期望的行为。</li></ul>|

> [!TIP]
> 使用下表来捕获组织的要求。

|功能 |详细信息 |需要 Azure AD Premium 许可证 |作出 |
|---------|---------|---------|---------|
|过期策略 |通过设置过期策略来管理 Microsoft 365 组的生命周期。 |P1 |TBD|
|保留策略 |通过在安全 & 合规中心设置团队的保留策略来保留或删除特定时间段内的数据。 **注意**：使用此功能需要 Microsoft 365 或 Office 365 Enterprise E3 或更高版本的许可。 |否 |TBD |
|存档和还原 |如果团队不再处于活动状态，而您想要保留它以供参考或在将来重新激活，请存档团队。 |否 |TBD |

> [!Note]
> 组过期是 Azure AD Premium 功能。 为使此功能可用，你的租户必须对用于配置受影响组的设置和成员的管理员的 Azure AD Premium 和许可证进行订阅。

#### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [设置 Microsoft 365 组过期时间](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。

- [设置团队保留策略](retention-policies.md)。

- [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>组和团队成员身份管理

对需要快速加入和脱离或用户和来宾的团队而言，一致地管理基于项目的成员或受限组是必需的。 您的组织可能还需要确保所有当前成员在团队中具有业务理由。 管理成员可能很难，因为团队所有者可以离开，并且用户通常不会在项目结束或更改角色时退出组。 管理组成员身份的最佳方式允许用户在需要时获取访问权限，但确保组不会有不当的访问权限是通过两个地区流程：权利管理和访问评论。

[权利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 允许你委托给某人（如项目经理），以将所有需要的资源（包括团队成员）收集到单个程序包中。 他们还可以定义哪些人可以发出请求：租户中的用户或来自其他连接的组织的用户。 项目经理将在其电子邮件中接收访问请求，并在 MyAccess 门户中批准或拒绝请求。 管理员可以将 access 的条件配置为包括过期日期或时间段，除非续订了 access，否则将从团队中删除用户或来宾。 管理员还可以设置与团队相关联的组，以参与访问评论。 对于 [access 审阅](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，组所有者将收到定期提醒以查看团队成员。 Access 评论包括建议，使组所有者可以更轻松地完成常规证明过程。

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 决策点 | 您的组织是否需要一个一致的流程来管理一个或多个团队的成员身份？ <br> 您的组织是否需要所有者或成员自己来定期调整一个或多个团队的持续成员身份？ <br> 你的组织是否需要批准用户和来宾请求对资源（包括团队、组、SharePoint 网站和应用）的访问权限？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 后续步骤？ | 为每个团队或特定团队的成员资格到期记录您的组织要求。<br>规划你的组织可以如何将团队、组、SharePoint 网站和应用捆绑到 access 程序包中。<br>规划请求者的经理（如请求者的经理、项目经理、已连接组织的主办方或组织中的安全主管）将需要批准或拒绝访问请求。 |

> [!TIP]
> 使用下表来捕获组织的要求。

| 功能 | 详细信息 | 需要 Azure AD Premium 许可证 | 作出 |
|:-|:-|:-|:-|
| 访问评论 | 设置访问权限审阅 recertify 特定团队的成员身份按固定间隔 | 又 | TBD |
| 权利管理 | 设置访问程序包以允许用户和来宾请求对团队的访问权限 | 又 | TBD |

> [!NOTE]
> 为了帮助您提前计划，请 [了解有关他们需要哪些许可证的详细信息](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [权利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [访问评论](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>团队功能管理

团队管理和生命周期管理的另一个重要方面是控制你的用户有权访问的功能的能力。 您可以在 Microsoft 365 或 Office 365 组织级别或按用户管理邮件、会议和呼叫功能。


|         |         |
|---------|---------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>您的组织是否需要针对您的整个租户限制团队功能？</li><li>您的组织是否需要针对特定用户限制团队功能？</li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织在租户和用户级别限制团队功能的要求。</li><li>计划在团队推出过程中实施特定要求。</li><li>传达和发布你的策略以通知团队用户他们所期望的行为。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>团队功能管理重点领域

团队通过策略提供精确的功能，用于控制消息、会议、通话和实时事件功能等。 默认情况下，可根据组织的需要将不同的策略应用于所有用户。 

有关所有设置的详细列表，包括有关如何为你的组织实施它们的技术指南，请参阅以下文章：

- [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)
- [在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams 中的私人频道](private-channels.md)
- [管理团队中的会议策略](meeting-policies-in-teams.md)
- [在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)
- [在 Microsoft 团队管理中心中管理你的应用](manage-apps.md)

此外，你可以为频道设置裁决，并向特定用户提供审阅者的功能，以便他们可以控制哪些人可以创建频道发布和答复他们。 有关详细信息，请参阅 [在 Microsoft 团队中设置和管理通道裁决](manage-channel-moderation-in-teams.md) 。

## <a name="security-and-compliance"></a>安全性和合规性

团队基于 Microsoft 365 和 Office 365 的高级安全和合规性功能构建，并支持审核和报告、合规性内容搜索、电子发现、法律封存和保留策略。

> [!Important]
> 如果您的组织具有合规性和安全要求，请查看本文中提供的有关 [Microsoft 团队安全性和合规性概述](security-compliance-overview.md)中的本主题的深入内容。

## <a name="related-topics"></a>相关主题

[Teams 的管控快速入门](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
