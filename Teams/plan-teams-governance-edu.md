---
title: 面向 IT 专业人员的 Microsoft 团队的 Microsoft 教育调控常见问题
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用团队的 Microsoft 教育组管理员从常见问题的答案。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf271132e9de19d5952e05e12b91b3a9e87ea529
ms.sourcegitcommit: c85211a22921d02ffa9f300a4f8350ffbb90b38c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2018
ms.locfileid: "22331267"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>对于管理员 Microsoft 教育调控常见问题

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何控制团队创建？ 我担心学生打算创建不正确的团队。

若要避免不正确或令人误解的名称，或只是为了提供更多结构如何命名团队，您可以使用 Office 365 组命名策略 （当前中预览）：

-   **前缀后缀命名策略**您可以使用前缀或后缀定义命名约定的团队 （组），例如， **GRP_US_My Group_Engineering**。 可以固定前缀和后缀，字符串或用户属性 （如 **[部门]**） 添加到基于该团队创建用户的名称。
-   **自定义阻止单词**您可以上载一套字词，阻止特定的组织中的用户使用他们创建的工作组的名称中。 例如，可以阻止条款**CEO**、**工资**和**HR**在它们不应用于的组的工作组名称中使用。
-   **分类**您可以创建您的组织中的用户创建 Office 365 组时可以设置的分类。 

> [!IMPORTANT]
> 组命名策略的 Office 365 组的成员的唯一用户需要使用 Azure Active Directory Premium P1 许可证。

有关详细说明，请参阅[Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果团队通过使用从其他系统 （例如，学校数据同步） 输入自动创建，请验证输入的数据符合命名策略已配置;如果它不，团队创建将失败。

## <a name="can-i-see-who-created-a-team"></a>可以查看工作组的创建者？

若要了解特定的团队的创建者，请参阅[Search 中的 Microsoft 团队的事件的审核日志](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>可以控制谁可以创建团队？

一般情况下，我们建议不要使任何人创建团队。 所有人都可以创建团队，团队更容易被广泛采用。 教师、 教师或学生可以使用团队创建研究组或感兴趣的组。 这将帮助团队内部和外部课堂接受。

我们的经验，用户教育有助于确保负责团队使用率。 只要用户了解创建团队不匿名，他们了解不小心创建它们的含义，并倾向于不愿意滥用工具。

如果您确实要控制可以创建团队，请参阅[的 Manage 可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何自动创建每个课程的团队期末或一个季度的开头？

在每个期末或一个季度开始时，您将需要大量新团队。 可能有意义才能自动化的方法，以自动创建这些团队，其中填充正确的用户，并设置正确的权限：

-   学校数据同步可以为 Exchange Online 和 SharePoint Online 的 Microsoft 团队和 OneNote 类笔记本的类团队、 用于教育和 rostering Intune 和单一登录 (SSO) 集成的许多其他学校组创建 Office 365 组第三方应用程序。 有关详细信息[学校数据同步的概述](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)。
-   使用 PowerShell，您可以创建工作组和通道，并配置设置自动。 有关详细信息，请参阅[Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。
-   可以使用 Microsoft Graph API （当前 beta) 中创建、 配置、 复制，并存档团队。 有关详细信息，请参阅[使用 Microsoft Graph API 以使用 Microsoft 团队](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>我该如何处理与团队期末或一个季度结束时？

我们建议您首先考虑有关您希望如何处理团队数据时学校期末或一个季度通过： 是否将其删除或使其可以学生的即使它们完成本课程。 您需要学校日历请记住，因此您设置的任何策略与假日不会发生冲突。 您可以使用以下工具来实现您的策略：

-   **保留策略：** 用于删除早于指定以确保旧数据已从 （对于所有或某些用户） 的聊天和频道期限的所有数据。 您还可以配置团队保留内容，因此不能删除它。 有关详细信息，请参阅[Microsoft 团队的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **到期策略：** 配置团队某些天后过期。 到期日期之前的 30 天，其团队需要更新，否则它将被删除 （虽然其他 30 天，管理员可以恢复已删除的工作组） 通知的工作组的所有所有者。 此设置是以确保未使用的团队 sunsetted 非常有用。 了解更多信息，请访问[Office 365 组过期策略](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **存档团队：** 此设置将团队置于只读模式。 它们可以仍浏览和搜索，但没有人可以添加任何新文章。 [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)介绍如何团队所有者可以存档团队;团队所有者还可以使用[图形 API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)存档或还原团队。
 
## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>是否有我教职员工创建团队时要使用的工作组模板？

是。 创建一个新的团队时，用户可以选择**从现有模板创建团队**和团队所有者还可以使用[图形 API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)从可用的模板创建新的团队。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>通过 PowerShell 或图形可以自动哪些任务？

[Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以执行以下操作：

-   创建工作组。
-   添加成员和所有者。
-   添加通道。
-   添加应用程序。
-   快捷方式通过克隆现有这些步骤团队，并太获取其选项卡。
-   向您刚创建的团队为用户提供一个链接。
-   当不再需要删除成员、 所有者、 通道和应用程序。
-   不再处于活动状态时存档团队。 
-   删除团队。
-   创建通道线程

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以执行以下操作：

-   创建工作组。
-   添加成员和所有者。
-   添加通道。
-   当不再需要删除成员、 所有者和通道。
-   删除团队。

> [!TIP]
> 图形 API 和 PowerShell cmdlet 不断地将添加功能。 请确保要检查功能增强通常[Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>可以控制我教职员工和学生有权访问哪些团队功能？

是。 您可以使用策略来控制特定消息、 会议、 通话，并 live 用户有权访问事件功能。 可以使用租户范围的设置相同的设置应用于所有，或如果需要应用用户级别策略。 

有关团队策略的详细信息，请参阅[Office 365 组织中的管理 Microsoft 团队功能](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>可以控制哪些外部方我教职员工和学生协作？

您可以使用来宾访问您的租户，可用于研究协作或来宾讲座之外邀请中的用户：

-   使用域添加到白名单允许或阻止来宾根据其域。
-   关闭来宾访问打开和关闭特定的 Office 365 组和团队以控制该团队可以 （并且不能） 邀请来宾。
-   使用审核日志来查看哪些通知发送到被邀请的来宾。

有关详细信息，请参阅[Office 365 组中的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>可以查看有关现有团队哪些信息？

您可以检查审核日志，请参阅：

-   被邀请以来宾身份到哪个工作组。
-   哪个团队的创建者。

有关详细信息，请参阅[Search 中的 Microsoft 团队的事件的审核日志](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>团队，以便快速发展。 如何保持最新状态？

我们建议团队获取最新的更新的以下资源：

-   [What's new in Microsoft 团队](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft 团队博客 （英文)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
