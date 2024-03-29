---
title: 在 Teams 中规划管理 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 本文介绍了如何规划在 Teams 中实现治理功能。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00a4fa6f2b0532ca0ff9837be4f3ee00f57662b0
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711296"
---
# <a name="plan-for-governance-in-teams"></a>在 Teams 中规划管理

Teams提供了一组丰富的工具，用于实现组织可能需要的任何管理功能。 本文指导 IT 专业人员提出正确的问题，以确定其监管要求以及如何满足这些要求。 

> [!Tip] 
> 观看以下会话，详细了解治理Microsoft Teams：治理、管理和[Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>组和团队创建、命名、分类和来宾访问

组织可能要求对团队的命名和分类方式、来宾是否可以添加为团队成员以及可以创建团队的严格控制。 可以使用敏感标签和敏感度标签Azure Active Directory (Azure AD) 这些区域。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |决策点|<ul><li>组织是否需要团队的特定命名约定？</li><li>团队创建者是否需要能够将组织特定的分类分配给团队？</li><li>是否需要限制按团队将来宾添加到团队的能力？</li><li>组织是否需要限制可以创建团队的人？</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|后续步骤|<ul><li>记录组织对团队创建、命名、分类和来宾访问的要求。</li><li>计划实施这些要求作为实施计划的一Teams部分。</li><li>传达并发布策略Teams告知用户预期的行为。</li></ul>|

> [!NOTE]
> 为帮助你提前规划， [请详细了解如何设置这些策略及其需要哪些许可证](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 限制组和团队创建可能会减慢用户的工作效率，因为许多 Microsoft 365 Office 365 服务需要创建组才能让服务正常运行。 有关其他信息，请访问[规划管理Teams](/microsoft-365/solutions/manage-creation-of-groups)。


#### <a name="additional-information"></a>其他信息

确定要求后，可以使用其他控件Azure AD这些要求。 有关如何实现这些设置的技术指南，请参阅：

- [Azure Active Directory用于配置组设置的 cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [对Microsoft 365组强制实施Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [使用敏感度标签保护网站Microsoft Teams、Microsoft 365组SharePoint内容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [组、团队和团队的生命周期结束选项Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>组和团队过期、保留和存档

组织可能还需要设置过期、保留和存档团队的策略，以及将团队数据 (频道消息和频道) 。 可以将组过期策略配置为自动管理组的生命周期和保留策略以根据需要保留或删除信息，也可以存档团队 (将其设置为只读模式) 以保留不再处于活动状态的团队的时间点视图。 请注意，存档的团队将继续应用过期策略，除非排除或续订，否则可能会被删除。

|-          |-           |
|-----------|------------|
| ![描述决策点的图标。](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>组织是否需要为团队指定到期日期？</li><li>组织是否需要对团队应用特定的数据保留策略？</li><li>您的组织是否期望能够存档非活动团队，以将内容保留为只读状态？</li></ul>|
| ![描述后续步骤的图标。](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织对团队过期、数据保留和存档的要求。</li><li>在推出新计划过程中，计划Teams这些要求。</li><li>传达并发布策略Teams告知用户预期的行为。</li></ul>|

> [!TIP]
> 使用下表捕获组织的要求。

|功能 |详细信息 |Azure AD Premium许可证 |决定 |
|---------|---------|---------|---------|
|过期策略 |通过设置过期Microsoft 365管理组生命周期。 |P1 |TBD|
|保留策略 |在安全与合规中心中为数据Teams保留策略，&数据。 **注意**：使用此功能需要获得 E3 Microsoft 365或Office 365 企业版许可。 |弱 |TBD |
|存档和还原 |当团队不再处于活动状态，但你想要保留该团队供参考或将来重新激活时，请将其存档。 |弱 |TBD |

> [!Note]
> 组过期是一项Azure AD Premium功能。 若要提供此功能，租户必须具有订阅，Azure AD Premium设置和受影响组成员的管理员的许可证和许可证。

#### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [设置Microsoft 365组过期。](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [设置Teams策略](retention-policies.md)。

- [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。

## <a name="group-and-team-membership-management"></a>组和团队成员身份管理

对于需要快速载入和下载或用户和来宾的团队，必须一致地管理基于项目的成员或受限组的成员。 您的组织可能还需要确保所有当前成员都有在团队中的业务理由。 管理成员可能比较困难，因为团队所有者可以离开，并且用户通常在项目结束时或更改角色时不自行离开组。 管理组成员身份（允许用户根据需要获取访问权限，但确保组没有不当访问风险）最好的方法是通过两个区域流程：权利管理和访问评审。

[权利](/azure/active-directory/governance/entitlement-management-overview) 管理允许您委派给项目经理等人员，以将所需的所有资源（包括团队成员身份）收集到单个包中。 他们还可以定义谁可以提出请求：租户中的用户或其他连接的组织的用户。 项目经理将在电子邮件中收到访问请求，在 MyAccess 门户中批准或拒绝请求。 管理员可以配置访问条件，以包括过期日期或期限，除非续订访问权限，否则将用户或来宾从团队中删除。 管理员还可以设置与团队关联的组，以参与访问评审。 对于 [访问评审](/azure/active-directory/governance/access-reviews-overview)，组所有者将收到定期提醒，提醒他们审阅团队成员。 访问评审包括建议，使组所有者可以更轻松地完成其常规证明过程。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 决策点 | 组织是否需要一致的流程来管理一个或多个团队的成员身份？ <br> 组织是否需要所有者或成员本身定期证明他们持续成为一个或多个团队的成员身份的理由？ <br> 组织是否需要用户和来宾批准，以请求访问团队、组、SharePoint和应用等资源？ |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 下一步？ | 记录每个团队或特定团队的成员资格到期的组织要求。<br>规划组织如何在访问包中将团队、组SharePoint网站和应用捆绑在一起。<br>规划哪些人员（例如请求者经理、项目经理、已连接组织的发起人或组织中安全主管）需要批准或拒绝访问请求。 |

> [!TIP]
> 使用下表捕获组织的要求。

| 功能 | 详细信息 | Azure AD Premium许可证 | 决定 |
|:-|:-|:-|:-|
| 访问评审 | 设置访问评审，定期重新认证特定团队的成员身份 | P2 | TBD |
| 权利管理 | 设置访问包以允许用户和来宾请求访问团队 | P2 | TBD |

> [!NOTE]
> 为帮助你提前规划 [，请详细了解他们需要哪些许可证](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>其他信息

有关如何实现这些设置的技术指南，请参阅：

- [权利管理](/azure/active-directory/governance/entitlement-management-overview)
- [访问评审](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams功能管理

治理和生命周期管理的另一个重要方面Teams是能够控制用户有权访问的功能。 您可以在组织级别或Microsoft 365或Office 365管理消息、会议以及呼叫功能。


|-        |-        |
|---------|---------|
| ![描述决策点的图标。](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>组织是否需要限制Teams租户的功能？</li><li>组织是否需要限制Teams特定用户的功能？</li></ul>|
| ![描述后续步骤的图标。](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录组织在租户和用户Teams限制功能的要求。</li><li>计划在推出计划过程中实现Teams要求。</li><li>传达并发布策略Teams告知用户预期的行为。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams管理重点区域

Teams通过策略提供精细的功能来控制消息传递、会议、呼叫和实时事件功能等。 默认情况下，可以按组织要求将不同的策略应用到所有用户或按用户应用。 

有关所有设置的详细列表，包括有关如何为组织实施这些设置的技术指南，请参阅以下文章：

- [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)
- [在过渡到全新的 Microsoft Teams 管理中心期间管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams 中的私人频道](private-channels.md)
- [共享频道Microsoft Teams](shared-channels.md)
- [管理 Teams 中的会议策略](meeting-policies-overview.md)
- [在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)
- [在管理中心内Microsoft Teams应用](manage-apps.md)

此外，您可以为频道设置审查，并授予特定用户的审查方功能，以便他们可以控制谁可以创建频道帖子并回复他们。 有关详细信息[，请参阅](manage-channel-moderation-in-teams.md)在 Microsoft Teams 中设置和管理频道审核。

## <a name="security-and-compliance"></a>安全性和合规性

Teams基于 Microsoft 365 和 Office 365 的高级安全性和符合性功能，并支持审核和报告、符合性内容搜索、电子发现、法定保留和保留策略。

> [!Important]
> 如果组织有合规性和安全性要求，请查看安全与合规概述一文提供的有关本主题的深入[Microsoft Teams](security-compliance-overview.md)。

## <a name="related-topics"></a>相关主题

[Teams 的管控快速入门](teams-adoption-governance-quick-start.md)

[Microsoft 365安全与合规的&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->