---
title: 面向管理员的 Microsoft 教育版管理常见问题解答
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 使用 Teams 的 Microsoft 教育组的管理员的常见问题解答。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e64fad26d65eb1b7c96388a5f7d9a2f9c6655e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117820"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>面向管理员的 Microsoft 教育版管理常见问题解答

> [!Tip]
> 观看以下会话，详细了解 Microsoft Teams 中的管理：Microsoft Teams 中的监管、 [管理和生命周期](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何控制团队创建？ 我担心学生会创建不适宜的团队。

为了避免不恰当或误导性的名称，或只是为了提供团队命名方式的更多结构，可以使用 Microsoft 365 组命名策略 (当前处于预览状态) ：

-   **前缀后缀命名策略** 可以使用前缀或后缀来定义团队和组 (的) 约定，例如 **，GRP_US_My Group_Engineering。** 前缀和后缀可以是固定字符串或用户属性 (例如 **[Department]**) ，根据创建团队的用户添加到名称中。
-   **自定义阻止字词** 可以上传一组字词，阻止特定组织的用户使用他们创建的团队的名称。 例如，可以阻止 **将"CEO、****工资** 单"和 **"HR"** 术语用于不应用于的组的团队名称中。
-   **分类** 可以创建组织中用户在创建 Microsoft 365 组时可以设置的分类。 

> [!IMPORTANT]
> 使用 Microsoft 365 组命名策略需要每个唯一用户（即一个或多个 Microsoft 365 组的成员）的 Azure Active Directory Premium P1 许可证或 Azure AD Basic EDU 许可证。

有关详细说明，请参阅 [Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果使用另一个系统（例如 (学校数据同步) ）中的输入自动创建团队，请验证输入数据是否符合配置的命名策略;如果没有，团队创建将失败。

## <a name="can-i-see-who-created-a-team"></a>我能否查看团队的创建人？

若要了解创建特定团队的人，请参阅在 [Microsoft Teams 审核日志搜索活动](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>我能否控制谁可以创建团队？

一般情况下，我们建议防止任何人创建团队。 如果每个人都可以创建团队，则 Teams 更有可能被广泛采用。 教职员工、教师或学生可以使用 Teams 创建研究组或特殊兴趣组。 这有助于在课堂内外接受 Teams。

在我们的体验中，用户教育有助于确保负责的 Teams 使用情况。 一旦用户了解创建团队不是匿名的，他们就会理解不小心创建团队的影响，并且倾向于远离使用工具的错误。

如果确定要控制可以创建团队的人，请参阅管理可以创建 [Microsoft 365 组的人](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>在学年或季度开始时，如何自动为每个课程创建团队？

在每个学年或季度开始时，你需要一些新团队。 采用自动化方法自动创建这些团队、使用适当的用户填充这些团队并设置适当的权限可能很有意义：

-   学校数据同步可以创建适用于 Exchange Online 和 SharePoint Online 的 Microsoft 365 组、Microsoft Teams 和 OneNote 课堂笔记本的课堂团队、Intune 教育版学校组，以及适用于许多其他第三方应用程序的名单和单一登录 (SSO) 集成。 有关详细信息， [请通过学校数据同步概述了解](/schooldatasync/overview-of-school-data-sync)。
-   使用 PowerShell 可以创建团队和频道，并自动配置设置。 有关详细信息[，请参阅 Microsoft Teams PowerShell。](/powershell/module/teams/?view=teams-ps)
-   可以使用 Microsoft Graph API (beta 版) 创建、配置、克隆和存档团队。 有关详细信息 [，请参阅使用 Microsoft Graph API 与 Microsoft Teams](/graph/api/resources/teams-api-overview) 协作。

> [!TIP]
> 学校数据同步为同步的每个课堂创建 Microsoft 365 组，[](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)并启用隐藏的组成员身份，以便只有课堂中的教师和学生才能看到该课堂的成员。 如果使用不同的过程创建类组，请使用 New-UnifiedGroup cmdlet 的 HiddenGroupMembershipEnabled 参数来满足相同的隐私要求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>当季度或季度结束后，如何处理团队？

建议你首先考虑在学校学年或季度结束后如何处理 Teams 数据：是删除数据，还是使学生即使在完成课程后也能够使用这些数据。 你需要记住学校日历，这样你设置的任何策略都不要与假日冲突。 可以使用以下工具实现策略：

-   **保留策略：** 使用此功能删除超过指定年龄的所有数据，以确保从聊天中删除旧数据， (或部分用户的聊天) 和频道。 还可以将 Teams 配置为保留内容，以便无法将其删除。 有关详细信息，请参阅 [Microsoft Teams 的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **过期策略：** 将团队配置为在特定天数后过期。 在过期前 30 天，团队的所有所有者都将收到通知，告知其团队需要续订，否则将被删除 (但管理员可额外恢复已删除的团队 30 天) 。 此设置对于确保已禁用未使用的团队非常有用。 有关详细信息，请通过[Microsoft 365 组过期策略 。](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **存档团队：** 此设置将团队置于只读模式。 它们仍然可以浏览和搜索，但没有人可以添加任何新文章。 [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 介绍了团队所有者如何存档团队;团队所有者还可使用图形 [API ](/graph/api/resources/teams-api-overview) (beta) 存档或还原团队。
 
> [!IMPORTANT]
> 使用 Microsoft 365 组过期策略需要每个唯一用户（即一个或多个 Microsoft 365 组的成员）的 Azure Active Directory Premium P1 许可证。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>创建团队时，是否有供教职员工使用的团队模板？

是。 创建新 **团队时** ，用户可以从现有模板中选择"创建团队"，Teams 所有者还可使用图形 [API](/graph/api/resources/teams-api-overview) (beta) 从可用模板创建新团队。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>可以通过 PowerShell 或 Graph 自动执行哪些任务？

Microsoft [Graph API (beta) ](/graph/api/resources/teams-api-overview) 可以执行以下操作：

-   创建团队。
-   添加成员和所有者。
-   添加通道。
-   添加应用。
-   通过克隆现有团队来快捷方式这些步骤，并获取其选项卡。
-   为用户提供指向刚创建的团队的链接。
-   不再需要成员、所有者、通道和应用时，请将其删除。
-   当团队不再处于活动状态时将其存档。 
-   删除团队。
-   创建通道线程

[PowerShell](/powershell/module/teams/?view=teams-ps) 可以执行以下操作：

-   创建团队。
-   添加成员和所有者。
-   添加通道。
-   不再需要成员、所有者和频道时，请将其删除。
-   删除团队。

> [!TIP]
> 图形 API 和 PowerShell cmdlet 不断添加功能。 请务必经常查看 [Microsoft Graph API (beta ](/graph/api/resources/teams-api-overview) 版) [PowerShell](/powershell/module/teams/?view=teams-ps) 文章，了解功能增强功能。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>我能否控制教职员工和学生有权访问的 Teams 功能？

是。 可以使用策略来控制用户有权访问的特定消息传递、会议、呼叫和实时事件功能。 可以使用租户范围的设置将相同的设置应用到所有设置，或应用用户级策略（如果需要）。 

有关 Teams 策略的更多详细信息，请参阅 [管理组织的 Microsoft Teams 设置](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>我能否控制教职员工和学生与哪些外部方协作？

可以使用来宾访问权限邀请租户外部的用户，这可用于研究协作或来宾讲座：

-   使用域允许列表可基于来宾的域允许或阻止来宾。
-   为特定的 Microsoft 365 组和团队启用和关闭来宾访问，控制哪些团队可以 (哪些团队) 邀请来宾。
-   使用审核日志查看向受邀来宾发送了哪些警报。

有关详细信息，请参阅 [Microsoft 365 组的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>我可以查看有关现有团队的哪些信息？

可以检查审核日志以查看：

-   谁作为来宾受邀加入哪个团队。
-   创建哪个团队的人。

有关详细信息，请参阅在 Microsoft [Teams 审核日志搜索事件](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams 的发展速度非常快。 如何保持最新状态？

我们建议使用以下资源在 Teams 上获取最新更新：

-   [Microsoft Teams 中的新增功能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)