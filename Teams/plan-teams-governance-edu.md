---
title: 面向 IT 专业人员的 Microsoft 教育版管理 FAQ - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 对使用团队的 Microsoft 教育组的管理员提出的常见问题的解答。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4faddea2a6d0366a45fab3667b781d9d1fe81f0b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573258"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>面向管理员的 Microsoft 教育版管理常见问题解答

> [!Tip]
> 观看以下会话以了解有关 Microsoft 团队中的管理的详细信息： [Microsoft 团队中的管理、管理和生命周期](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何控制团队创建？ 我担心学生将创建不恰当的团队。

为避免使用不适当或误导的名称，或者只是为团队命名方式提供更多的结构，您可以使用 Office 365 组命名策略（当前在预览中）：

-   **前缀-后缀命名策略**可以使用前缀或后缀定义团队（组）的命名约定，例如， **GRP_US_My Group_Engineering**。 前缀和后缀可以是固定字符串或用户属性（如 **[部门]**），这些属性根据创建团队的用户添加到名称。
-   **自定义阻止的字词**你可以上载特定组织中的用户在其创建的团队名称中阻止使用的一组字词。 例如，您可以阻止术语 " **CEO**"、"**工资单**" 和 "**人力资源**" 在不适用的组的团队名称中使用。
-   **分类**你可以创建你的组织中的用户在创建 Office 365 组时可以设置的分类。 

> [!IMPORTANT]
> 使用 Office 365 组命名策略要求属于一个或多个 Office 365 组成员的每个唯一用户的 Azure Active Directory Premium P1 许可证或 Azure AD 基本教育机构许可证。

有关详细说明，请参阅[Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果团队是使用来自其他系统（如学校数据同步）的输入自动创建的，请验证输入数据是否符合您配置的命名策略;如果不是，团队创建将失败。

## <a name="can-i-see-who-created-a-team"></a>是否可以查看团队的创建者？

若要了解创建特定团队的人员，请参阅[在 Microsoft 团队中搜索事件的审核日志](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>是否可以控制哪些人可以创建团队？

一般情况下，建议不要阻止任何人创建团队。 如果每个人都可以创建团队，则团队更有可能被广泛采纳。 教职员工、教师或学生可以使用团队创建研究组或特殊兴趣组。 这将帮助在课堂内部和外部接受团队。

在我们的经验中，用户教育有助于确保负责人的使用。 一旦用户知道创建团队不是匿名的，他们就会理解 carelessly 创建它们的含义，并倾向于 shy 退出该工具。

如果您确定要控制哪些人可以创建团队，请参阅[管理可创建 Office 365 组的人员](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何在学期或季度的开始期间自动为每个课程创建团队？

在每个学期或季度开始时，您将需要许多新团队。 使用自动化方法自动创建这些团队、使用适当的用户填充它们以及设置正确的权限，这可能会有意义：

-   学校数据同步可为 Exchange Online 和 SharePoint Online 创建 Office 365 组、Microsoft 团队的课堂团队和 OneNote 课堂笔记本、用于 Intune 教育的学校组以及 rostering 和单一登录（SSO）集成第三方应用程序。 了解有关[学校数据同步的概览的](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)详细信息。
-   通过 PowerShell，你可以创建团队和频道，并自动配置设置。 有关详细信息，请参阅[Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。
-   你可以使用 Microsoft Graph API （当前在 beta 中）来创建、配置、克隆和存档团队。 有关详细信息，请参阅[使用 Microsoft GRAPH API 处理 Microsoft 团队](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。

> [!TIP]
> 学校数据同步为每个已同步的类创建 Office 365 组，并[启用隐藏的组成员身份](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)，以便只有课堂中的教师和学生才能看到该类的成员。 如果使用不同的进程创建类组，请使用 UnifiedGroup cmdlet 的 HiddenGroupMembershipEnabled 参数来满足相同的隐私要求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>在学期或季度结束时如何处理团队？

我们建议您首先考虑在学校半学期或季度结束时如何处理团队数据：是删除它还是让学生在完成课程后仍可供学生使用。 您需要记住学校日历，以便您设置的任何策略不会与假日冲突。 你可以使用以下工具实现你的策略：

-   **保留策略：** 使用此功能可删除早于指定时期的所有数据，以确保从聊天中删除旧数据（适用于所有或部分用户）和频道。 您还可以将团队配置为保留内容，使其无法删除。 有关详细信息，请参阅[Microsoft 团队的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **过期策略：** 将团队配置为在特定天数后过期。 过期之前的三十天，将通知团队的所有所有者需要续订其团队，否则将被删除（尽管管理员可以恢复已删除的团队还需30天）。 此设置对于确保未使用的团队 sunsetted 非常有用。 有关详细信息，请参阅[Office 365 组过期策略](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **存档团队：** 此设置将团队置于只读模式。 它们仍然可以被浏览和搜索，但没有人可以添加任何新帖子。 [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)介绍团队所有者如何存档团队。团队所有者还可以使用[GRAPH API （beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)来存档或还原团队。
 
> [!IMPORTANT]
> 使用 Office 365 组过期策略要求属于一个或多个 Office 365 组成员的每个唯一用户的 Azure Active Directory Premium P1 许可证。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>我的教职员是否有团队模板可供我创建团队时使用？

是。 创建新团队时，用户可以**从现有模板中选择 "创建团队**"，团队所有者还可以使用[图形 API （beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)从可用模板创建新团队。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>我可以通过 PowerShell 或图形自动执行哪些任务？

[Microsoft GRAPH API （beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以执行下列操作：

-   创建团队。
-   添加成员和所有者。
-   添加频道。
-   添加应用程序。
-   通过克隆现有团队和获取其选项卡来为这些步骤提供快捷方式。
-   向用户提供您刚创建的团队的链接。
-   当不再需要成员、所有者、频道和应用时，可将其删除。
-   如果团队不再处于活动状态，则将其存档。 
-   删除团队。
-   创建通道线程

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以执行以下操作：

-   创建团队。
-   添加成员和所有者。
-   添加频道。
-   当不再需要成员、所有者和频道时，可将其删除。
-   删除团队。

> [!TIP]
> Graph API 和 PowerShell cmdlet 不断添加功能。 请确保经常查看[Microsoft GRAPH API （beta）](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章以获取功能增强。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>我是否可以控制我的教职员和学生可以访问的团队功能？

是。 你可以使用策略控制你的用户有权访问的特定消息、会议、调用和实时事件功能。 你可以使用租户范围的设置将相同设置应用于所有设置，或者根据需要应用用户级别策略。 

有关团队策略的更多详细信息，请参阅[管理你的组织的 Microsoft 团队设置](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>是否可以控制教职员工和学生协作的外部团体？

可以使用来宾访问邀请来自租户外部的用户，这对于研究协作或来宾讲座非常有用：

-   使用域 whitelisting 根据其域允许或阻止来宾。
-   为特定的 Office 365 组和团队打开和关闭来宾访问权限，以控制哪些团队可以（且无法）邀请来宾。
-   使用审核日志查看向受邀请的来宾发送了哪些警报。

有关详细信息，请参阅[Office 365 组中的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>我可以查看有关现有团队的哪些信息？

你可以查看审核日志以查看：

-   被邀请成为哪个团队的来宾。
-   创建了哪个团队。

有关详细信息，请参阅[在 Microsoft 团队中搜索事件的审核日志](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>团队快速演变。 如何保持最新状态？

我们建议使用以下资源来获取团队的最新更新：

-   [Microsoft 团队中的新增功能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft 团队博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
