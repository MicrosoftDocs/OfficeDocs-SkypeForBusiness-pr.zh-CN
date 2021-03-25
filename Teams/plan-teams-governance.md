---
title: 在 Teams 中规划管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 本文将了解如何规划在 Teams 中实现治理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab70daffa91b534f15b032cd0c137efe89abb438
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117810"
---
# <a name="plan-for-governance-in-teams"></a>在 Teams 中规划管理

Teams 提供了一组丰富的工具，用于实现组织可能需要的任何管理功能。 本文指导 IT 专业人员提出正确的问题，以确定其监管要求以及如何满足这些要求。 

> [!Tip] 
> 观看以下会话，详细了解 Microsoft Teams 中的治理[：Microsoft Teams](https://aka.ms/teams-governance)中的治理、管理和生命周期

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>组和团队创建、命名、分类和来宾访问

组织可能要求对团队的命名和分类方式、来宾是否可以添加为团队成员以及可以创建团队的严格控制。 可以使用 Azure Active Directory 和 Azure AD (和敏感度) 配置这些区域。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |决策点|<ul><li>组织是否需要团队的特定命名约定？</li><li>团队创建者是否需要能够将组织特定的分类分配给团队？</li><li>是否需要限制按团队将来宾添加到团队的能力？</li><li>组织是否需要限制可以创建团队的人？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|后续步骤|<ul><li>记录组织对团队创建、命名、分类和来宾访问的要求。</li><li>计划在 Teams 推出过程中实施这些要求。</li><li>沟通并发布策略，告知 Teams 用户他们预期的行为。</li></ul>|

> [!NOTE]
> 为帮助你提前规划， [请详细了解如何设置这些策略及其需要哪些许可证](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制组和团队创建可能会降低用户的工作效率，因为许多 Microsoft 365 和 Office 365 服务要求创建组才能让服务正常工作。 有关其他信息，请导航到 并展开["为什么控制谁创建 Microsoft 365 组"。](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>其他信息

确定要求后，可以使用 Azure AD 控件实现它们。 有关如何实现这些设置的技术指南，请参阅：

- [用于配置组设置的 Azure Active Directory cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [对 Azure Active Directory 中的 Microsoft 365 组强制实施命名策略](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [组、团队和 Yammer 的生命周期结束选项](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>组和团队过期、保留和存档

组织可能还需要设置过期、保留和存档团队的策略，以及将团队数据 (频道消息和频道) 。 可以将组过期策略配置为自动管理组的生命周期和保留策略以根据需要保留或删除信息，也可以存档团队 (将其设置为只读模式) 以保留不再处于活动状态的团队的时间点视图。 请注意，存档的团队将继续应用过期策略，除非排除或续订，否则可能会被删除。

|-          |-           |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>组织是否需要为团队指定到期日期？</li><li>组织是否需要对团队应用特定的数据保留策略？</li><li>您的组织是否期望能够存档非活动团队，以将内容保留为只读状态？</li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织对团队过期、数据保留和存档的要求。</li><li>计划在 Teams 推出过程中实施这些要求。</li><li>沟通并发布策略，告知 Teams 用户他们预期的行为。</li></ul>|

> [!TIP]
> 使用下表捕获组织的要求。

|功能 |详细信息 |需要 Azure AD Premium 许可证 |决定 |
|---------|---------|---------|---------|
|过期策略 |通过设置过期策略来管理 Microsoft 365 组的生命周期。 |P1 |TBD|
|保留策略 |在安全与合规中心为 Teams 设置保留策略，保留&删除数据。 **注意**：使用此功能需要获得 Microsoft 365 或 Office 365 企业版 E3 或以上版的许可。 |否 |TBD |
|存档和还原 |当团队不再处于活动状态，但你想要保留该团队供参考或将来重新激活时，请将其存档。 |否 |TBD |

> [!Note]
> 组过期是一项 Azure AD Premium 功能。 若要提供此功能，租户必须具有 Azure AD Premium 订阅，以及配置设置和受影响组成员的管理员的许可证。

#### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [设置 Microsoft 365 组过期 。](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [设置 Teams 保留策略](retention-policies.md)。

- [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>组和团队成员身份管理

对于需要快速载入和下载或用户和来宾的团队来说，必须一致地管理基于项目的成员或受限组的成员。 您的组织可能还需要确保所有当前成员都有在团队中的业务理由。 管理成员可能比较困难，因为团队所有者可以离开，并且用户在项目结束时或更改角色时通常不会自行离开组。 管理组成员身份（允许用户根据需要获取访问权限，但确保组没有不当访问风险）最好的方法是通过两个区域流程：权利管理和访问评审。

[权利](/azure/active-directory/governance/entitlement-management-overview) 管理允许您委派给项目经理等人员，以将所需的所有资源（包括团队成员身份）收集到单个包中。 他们还可以定义谁可以提出请求：租户中的用户或其他连接的组织的用户。 项目经理将在电子邮件中收到访问请求，在 MyAccess 门户中批准或拒绝请求。 管理员可以配置访问条件，以包括过期日期或期限，除非续订访问权限，否则将用户或来宾从团队中删除。 管理员还可以设置与团队关联的组，以参与访问评审。 对于 [访问评审](/azure/active-directory/governance/access-reviews-overview)，组所有者将收到定期提醒，提醒他们审阅团队成员。 访问评审包括建议，使组所有者可以更轻松地完成其常规证明过程。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 决策点 | 组织是否需要一致的流程来管理一个或多个团队的成员身份？ <br> 组织是否需要所有者或成员本身定期证明他们持续成为一个或多个团队的成员身份的理由？ <br> 您的组织是否需要审批用户和来宾来请求访问团队、组、SharePoint 网站和应用等资源？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 下一步？ | 记录每个团队或特定团队的成员资格到期的组织要求。<br>规划组织如何在访问包中将团队、组、SharePoint 网站和应用捆绑在一起。<br>规划哪些人员（例如请求者经理、项目经理、已连接组织的发起人或组织中安全主管）需要批准或拒绝访问请求。 |

> [!TIP]
> 使用下表捕获组织的要求。

| 功能 | 详细信息 | 需要 Azure AD Premium 许可证 | 决定 |
|:-|:-|:-|:-|
| 访问评审 | 设置访问评审，定期重新认证特定团队的成员身份 | P2 | TBD |
| 权利管理 | 设置访问包以允许用户和来宾请求访问团队 | P2 | TBD |

> [!NOTE]
> 为帮助你提前规划 [，请详细了解他们需要哪些许可证](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [权利管理](/azure/active-directory/governance/entitlement-management-overview)
- [访问评审](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 功能管理

Teams 治理和生命周期管理的另一个重要方面是能够控制用户有权访问的功能。 可在 Microsoft 365 或 Office 365 组织级别或每个用户管理消息传递、会议以及呼叫功能。


|-        |-        |
|---------|---------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>组织是否需要限制整个租户的 Teams 功能？</li><li>组织是否需要限制特定用户的 Teams 功能？</li></ul>|
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织在租户和用户级别限制 Teams 功能的要求。</li><li>计划在 Teams 推出过程中实现特定要求。</li><li>沟通并发布策略，告知 Teams 用户他们预期的行为。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams 功能管理重点区域

Teams 通过策略提供精细的功能来控制消息传递、会议、通话和实时事件功能等。 默认情况下，可以按组织要求将不同的策略应用到所有用户或按用户应用。 

有关所有设置的详细列表，包括有关如何为组织实施这些设置的技术指南，请参阅以下文章：

- [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)
- [在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams 中的私人频道](private-channels.md)
- [管理 Teams 中的会议策略](meeting-policies-in-teams.md)
- [在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)
- [在 Microsoft Teams 管理中心管理应用](manage-apps.md)

此外，您可以为频道设置审查，并授予特定用户的审查方功能，以便他们可以控制谁可以创建频道帖子并回复他们。 有关详细信息 [，请参阅在 Microsoft Teams 中](manage-channel-moderation-in-teams.md) 设置和管理频道审核。

## <a name="security-and-compliance"></a>安全性和合规性

Teams 基于 Microsoft 365 和 Office 365 的高级安全性和符合性功能构建，支持审核和报告、符合性内容搜索、电子发现、法定保留和保留策略。

> [!Important]
> 如果你的组织有合规性和安全性要求，请查看 Microsoft Teams 中的安全性和符合性概述一文中提供的有关此主题 [的深入内容](security-compliance-overview.md)。

## <a name="related-topics"></a>相关主题

[Teams 的管控快速入门](teams-adoption-governance-quick-start.md)

[Microsoft 365 安全与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->