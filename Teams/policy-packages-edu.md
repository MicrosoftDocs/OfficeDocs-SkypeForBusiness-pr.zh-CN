---
title: 适用于教育机构管理员的 Microsoft 团队策略包
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的策略程序包。
ms.openlocfilehash: a49ab725ff0042b75afca9b1f9b4d7d9655c34b7
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676250"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>适用于教育机构管理员的 Microsoft 团队策略包

Microsoft 团队中的策略程序包会收集预定义策略和策略设置，你可以分配给你的机构中具有类似角色的用户。 策略程序包简化、优化和帮助在管理策略时提供一致性。 在正常做法中，你将为每个用户分配一个策略程序包，并根据需要重新定义每个程序包中的策略以满足该用户组的需求。 更新程序包中的设置时，分配到该程序包的所有用户都将更改为批量更新。

通常，教育机构有许多具有独特需求的用户类型，具体取决于学生的年龄和成熟度。 例如，你可能希望授予教师和教职员工对 Microsoft 团队的完全访问权限，但想要限制 Microsoft 团队功能，以便学生能够鼓励安全且专注于学习环境。 你可以使用策略程序包根据你的学校社区中不同 cohorts 的需求来调整设置。

## <a name="what-is-a-policy-package"></a>什么是策略包？

策略程序包允许你控制 Microsoft 团队的功能，这些功能允许或限制 Microsoft 团队针对你的组织中的特定人员集使用。 每个策略程序包均围绕用户角色进行设计，其中包含支持该角色的典型活动的预定义策略和策略设置。

策略程序包的预定义策略：
- 消息传递
- 会议
- 应用设置
- 通话
- 实时事件

Microsoft 团队当前包含以下策略包：

|Microsoft 团队管理中心中列出的程序包名称 |最适合用于  |说明 |
|:--- |:--- |:--- |
|Education_Teacher| 教育版和员工| 使用此组策略和策略设置向组织内的教师和员工授予通过 Microsoft 团队的聊天、通话和会议的完全访问权限。 |
|Education_PrimaryStudent | 主要学校过时的学生  | 较旧的，您的机构内的主要学校过期学生可能需要 Microsoft 团队中的更多限制。 使用此组策略和策略设置来限制会议创建和管理、聊天管理和私人通话等功能。 |
|Education_SecondaryStudent| 次要学校过期的学生 | 在你的机构内的次要学校过时学生可能需要 Microsoft 团队中的更多限制。 使用此组策略和策略设置来限制会议创建和管理、聊天管理和私人通话等功能。 |
|Education_HigherEducationStudent | 高等教育学生 | 更高的教育 intuition 在您的内学生可能比较小的学生需要的限制更少，但建议您采取一些限制。 你可以使用这组策略和策略设置授予你的组织内的聊天、通话和会议的访问权限，但限制学生如何将 Microsoft 团队与外部参与者配合使用。 |
|||

每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。 例如，当你将 Education_Teacher 策略包分配给学校中的教师时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。

![Education_Teacher 策略程序包的屏幕截图](media/policy-packages-education_teacher.png)

> [!NOTE]
> 如果你决定教师和管理支持人员需要不同的策略，则可以重新使用现有程序包的用途：标识你当前未使用的程序包，并将设置更改为适用于该组的设置。 您可能需要向自己做笔记，其中有哪些组拥有哪个程序包，但这是唯一重新安排程序包的障碍。

## <a name="why-use-policy-packages"></a>为什么使用策略程序包

如果您的机构拥有成百上千的用户，您可能会问自己： "为什么要花时间为所有用户分配一个程序包？"

将程序包分配给成百上千用户是管理时间方面的投资，无需任何疑问。 投资的一个重要之处是，他们在一段时间内而不是立即支付。

在教育环境中，有许多具有相同或类似角色的用户。 当您以同样的方式管理用户体验时，您可以花费更少的时间进行工作。 软件包组特定于机构中各种角色的一组策略。 具有相同许可证但角色不同的用户可以根据其角色分配相关策略，这比调整单个用户的策略更有效。

一旦机构中的所有用户都已分类到组中，并且应用了程序包，从随后的用户管理程序包设置就是为分配到该程序包的所有用户更改程序包设置。 你可以选择在将用户分配给程序包之前或之后对包内的策略进行微调。

请参阅在[Microsoft 团队中管理策略程序包](manage-policy-packages.md)，了解有关为单个用户分配程序包、向多达20个用户批量分配程序包以及管理和更新与每个程序包关联的策略的分步指导。
