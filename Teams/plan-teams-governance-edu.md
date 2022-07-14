---
title: 面向管理员的 Microsoft 教育版管理常见问题解答
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft 教育组管理员使用 Teams 的常见问题解答。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fe9c0b19e5ba586ac8bfe430295de459c3d836d2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790177"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>面向管理员的 Microsoft 教育版管理常见问题解答

> [!Tip]
> 观看以下会话，详细了解 Microsoft Teams 中的管理： [Microsoft Teams 中的治理、管理和生命周期](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>如何实现控制团队创建？ 我担心学生会创建不合适的团队。

为了避免名称不当或误导性，或者只是为了为团队的命名方式提供更多结构，可以使用当前预览版 (Microsoft 365 组命名策略) ：

-   **前缀-后缀命名策略** 可以使用前缀或后缀来定义团队 (组) 的命名约定，例如 **GRP_US_My Group_Engineering**。 前缀和后缀可以是固定字符串或用户属性 (，例如 **[部门]**) ，这些属性根据创建团队的用户添加到名称中。
-   **自定义阻止字词** 可以上传一组阻止特定组织中的用户以他们创建的团队名称使用的字词。 例如，可以阻止在不适用的组的团队名称中使用 **CEO**、 **工资单** 和 **人力资源** 术语。
-   **分类** 你可以创建组织中的用户在创建 Microsoft 365 组时可以设置的分类。 

> [!IMPORTANT]
> 使用Microsoft 365 组命名策略需要为一个或多个 Microsoft 365 组成员的每个唯一用户Azure Active Directory Premium P1许可证或 Azure AD 基本 EDU 许可证。

有关详细说明，请参阅 [Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。

> [!Note]
> 如果团队是通过使用来自其他系统 (（例如学校数据同步）的输入自动创建的，) 请验证输入数据是否符合已配置的命名策略;否则，团队创建将失败。

## <a name="can-i-see-who-created-a-team"></a>我能看出谁创建了一个团队吗？

若要了解创建特定团队的人员，请参阅 [Microsoft Teams 中事件的审核日志](audit-log-events.md)。

## <a name="can-i-control-who-can-create-teams"></a>是否可以控制谁可以创建团队？

一般情况下，我们建议不要阻止任何人创建团队。 如果每个人都可以创建团队，则 Teams 更有可能被广泛采用。 教职员工、教师或学生可以使用 Teams 创建学习组或特殊兴趣组。 这将有助于在教室内外接受 Teams。

在我们的体验中，用户教育有助于确保负责任的 Teams 使用情况。 一旦用户了解创建团队不是匿名的，他们就会理解粗心创建团队的含义，并倾向于回避滥用该工具。

如果确定要控制谁可以创建团队，请参阅[“管理谁可以创建Microsoft 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>如何实现在学期或季度初自动为每个课程创建一个团队？

在每个学期或四分之一开始，你将需要一些新团队。 采取自动方法自动创建这些团队、使用正确的用户填充这些团队并设置正确的权限可能是有意义的：

-   学校数据同步可以为 Exchange Online 和 SharePoint Online 创建Microsoft 365 组、Microsoft Teams 和 OneNote 课堂笔记本的课堂团队、教育Intune的学校组，以及适用于许多其他第三方应用程序的名册和单一登录 (SSO) 集成。 详细了解 [学校数据同步概述](/schooldatasync/overview-of-school-data-sync)。
-   借助 PowerShell，可以创建团队和频道，并自动配置设置。 有关详细信息，请参阅 [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 。
-   可以使用 beta) 中当前的 Microsoft 图形 API (创建、配置、克隆和存档团队。 有关详细信息，请参阅[使用 Microsoft 图形 API与 Microsoft Teams 协作](/graph/api/resources/teams-api-overview)。

> [!TIP]
> 学校数据同步为每个已同步的班级创建一个 Microsoft 365 组，并 [启用隐藏的组成员身份](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) ，以便只有班内的教师和学生才能看到该类的成员。 如果使用其他进程创建类组，请使用 New-UnifiedGroup cmdlet 的 HiddenGroupMembershipEnabled 参数来满足相同的隐私要求。

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>如何实现在学期或季度结束时与球队打交道？

我们建议你首先考虑在学校学期或季度结束后如何处理 Teams 数据：是删除它，还是在学生完成课程后将其保留为可用。 你需要记住学校日历，这样你设置的任何策略就不会与假期冲突。 可以使用以下工具来实现策略：

-   **保留策略：** 使用此项可删除指定的年龄超过该年龄的所有数据，以确保从聊天中删除旧数据， (所有或某些用户) 和频道。 还可以将 Teams 配置为保留内容，以便无法将其删除。 有关详细信息，请参阅 [Microsoft Teams 的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。
-   **到期策略：** 将团队配置为在一定天数后过期。 在过期前 30 天，团队的所有所有者都会收到需要续订其团队的通知，否则会 (删除该团队，尽管管理员可以在) 再恢复已删除的团队 30 天。 此设置对于确保未使用的团队处于日落中非常有用。 详细了解 [Microsoft 365 组过期策略](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。

-   **存档团队：** 此设置将团队置于只读模式。 仍然可以浏览和搜索它们，但没有人可以添加任何新帖子。 [存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)说明团队所有者如何存档团队;团队所有者还可以使用[图形 API (beta) ](/graph/api/resources/teams-api-overview)存档或还原团队。
 
> [!IMPORTANT]
> 使用Microsoft 365 组过期策略需要为作为一个或多个 Microsoft 365 组成员的每个唯一用户Azure Active Directory Premium P1许可证。

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>是否有团队模板供教职员工在创建团队时使用？

是。 用户可以在创建新团队时 **从现有模板中选择“创建团队**”，Teams 所有者还可以使用 [图形 API (beta)](/graph/api/resources/teams-api-overview)从可用模板创建新团队。

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>可以通过 PowerShell 或 Graph 自动执行哪些任务？

[Microsoft 图形 API (beta) ](/graph/api/resources/teams-api-overview)可以执行以下操作：

-   创建团队。
-   添加成员和所有者。
-   添加通道。
-   添加应用。
-   通过克隆现有团队并获取其选项卡来缩短这些步骤。
-   为用户提供指向刚刚创建的团队的链接。
-   不再需要成员、所有者、频道和应用时，请将其删除。
-   当团队不再处于活动状态时，请存档该团队。 
-   删除团队。
-   创建通道线程

[PowerShell](/powershell/module/teams/?view=teams-ps) 可以执行以下操作：

-   创建团队。
-   添加成员和所有者。
-   添加通道。
-   不再需要成员、所有者和频道时，请将其删除。
-   删除团队。

> [!TIP]
> 图形 API和 PowerShell cmdlet 不断添加功能。 请确保经常检查 [Microsoft 图形 API (beta) ](/graph/api/resources/teams-api-overview)和 [PowerShell](/powershell/module/teams/?view=teams-ps) 文章以获取功能增强功能。  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>能否控制我的教职员工和学生有权访问的 Teams 功能？

是。 可以使用策略来控制用户有权访问的特定消息传送、会议、呼叫和实时事件功能。 可以使用租户范围的设置向所有人应用相同的设置，或根据需要应用用户级策略。 

有关 Teams 策略的更多详细信息，请参阅 [管理组织的 Microsoft Teams 设置](enable-features-office-365.md)。
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>能否控制教职员工和学生合作的外部方？

可以使用来宾访问从租户外部邀请用户，这对于研究协作或来宾讲座非常有用：

-   使用域允许列表根据来宾的域允许或阻止来宾。
-   为特定Microsoft 365 组和团队打开和关闭来宾访问权限，以控制哪些团队可以 (和不能) 邀请来宾。
-   使用审核日志查看发送给受邀来宾的警报。

有关详细信息，请参阅[Microsoft 365 组中的来宾访问权限](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。

## <a name="what-information-can-i-review-about-existing-teams"></a>可以查看有关现有团队的信息？

可以检查审核日志以查看：

-   谁被邀请作为客人加入哪个团队。
-   谁创建了哪个团队。

有关详细信息，请参阅 [在 Microsoft Teams 中搜索事件的审核日志](audit-log-events.md)。

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>团队发展得如此之快。 如何保持最新状态？

建议使用以下资源获取 Teams 上的最新更新：

-   [Microsoft Teams 中的新增功能](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)