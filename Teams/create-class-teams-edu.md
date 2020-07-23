---
title: 创建课堂团队的推荐方法和最佳做法
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: 了解如何为学校创建课堂团队的推荐方法和最佳做法。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3e8b8e8605b5e4f916389109cb611996aa90a895
ms.sourcegitcommit: 34a30c2c9a8e32bfcb382c3e6e7237f277ec361d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45206760"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>创建课堂团队的推荐方法和最佳做法

Microsoft Teams 教育版提供了针对教育用途的  [特定团队类型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) 。 [课堂团队类型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)是为课堂使用而设计的，并带有支持课堂需要的特定功能，包括：  

- 分配
- 分数
- OneNote 课堂笔记本  
- [课堂材料文件夹](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) 确保学生只读内容
- [教师尽早的访问权](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)在设置班级之前就开始添加学生 
- 可以静音处理捣乱的学生及其他特殊权限  

有几种创建课堂团队的方法，而 Teams 教育版有一组独特的部署工具，可以使创建课堂团队尽可变得能简单。 我们将逐步介绍各种选项，以帮助你选择最适合你需求的正确部署路径。  

## <a name="automatic-team-creation-using-sds"></a>使用 SDS 自动创建团队

**2020 年 7 月底即将推出此功能。**

自动化团队创建节省了IT管理员和老师的时间。 它确保了教师已经创建了所有的课堂团队，并已准备好在登录时设置。 [学校数据同步 (SDS)](https://docs.microsoft.com/SchoolDataSync)是一款免费的 Office 365 教育工具，可以从教育机构的记录系统中读取数据，例如学生信息系统（SIS）或学习管理系统（LMS）。 SDS 使用这些数据以多种方式丰富 Office 365 的设置，包括批量创建课堂团队，以及与信息系统保持同步，以便在注册情况发生变化时随时更新教师和学生成员。 SDS 可以导入任何记录系统中的数据，并将内置连接器用于许多世界现有[ SIS 供应商](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support)。 我们强烈推荐使用SDS，因为它有以下优点。  

### <a name="benefits"></a>优点

- 自动创建和维护课堂团队 - 教师将能够登录到 Teams，并立即开始教学。
- 成员身份与 SIS/LMS 同步来维护学生成员身份更改。
- EDU 客户成功团队可提供免费部署协助。
- [教师尽早的访问权](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)：教育工作者在录取学生之前有时间准备他们的团队。  
- 可选地创建用户并应用 Office 365 许可证。
- 创建跨 Office 365 使用的安全组，包括团队策略。
- 为限定范围的管理委托和[教师密码重置](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)创建管理单元。 
- 为了减少管理员的工作，会有用于大规模处理的内置错误、重试处理、节流回退和会话稳定性。  
- 内置的清理功能，可在组和团队过时后重命名和存档。
- [分数同步](https://docs.microsoft.com/schooldatasync/grade-sync)：老师们可以以小组为单位进行评分，并让系统自动将各小组的成绩写回 SIS 的成绩单上。 
- [学生数据保护](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data)：防止学生使用非 Microsoft 的应用程序，并跟踪和管理家长许可。 
- 为了丰富有关的教育见解，导入的数据将用于用户角色、组织（学校）和其他重要数据。  

### <a name="considerations"></a>注意事项

SDS 以两个步骤创建团队。 第一步在 Azure Active Directory (Azure AD) 中创建一个 Microsoft 365 组，第二步将该组自动转换为一个团队。 创建团队的第二步在SDS中是可选的。 管理员可能不希望根据部署时间和可能产生的未使用团队的数量自动创建团队。 我们建议拥有50万或以上团队的院校关闭 SDS 中的自动团队创建切换，并使用[教师领导的团队创建方法](#teacher-led-team-creation-from-office-365-class-groups)。  

### <a name="get-started"></a>开始使用

首先，请访问[学校数据同步（SDS）](https://docs.microsoft.com/SchoolDataSync)并联系[https://aka.ms/sdssupport](https://aka.ms/sdssupport)部署协助。  

## <a name="teacher-led-team-creation-from-office-365-class-groups"></a>由 Office 365 课堂教师领导的团队创建

**此功能将于 2020 年 8 月中旬推出。**

如果你想让教师轻松快速地创建他们需要的课堂，那么由教师领导的团队创建是一个很好的部署选项。 我们还建议拥有50万个团队的机构使用这种方法来最小化外部创建的团队的数量。  

这种混合方法允许你使用 SDS 为每个课程创建组（推荐），或者使用[Graph API](https://docs.microsoft.com/graph/api/educationroot-post-classes)自己创建组。 在课堂组准备好之后，教育者可以使用建议的**班级图标**将他们的群组转换成小组。

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="显示建议课堂图标的屏幕截图":::

### <a name="benefits"></a>优点

- [教师尽早的访问权](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)：教育工作者在录取学生之前有时间准备他们的团队。  
- 减少未使用和不必要的团队数量。 这些课堂已经准备好并已接受建议，但除非教师打算使用它们，否则不会创建它们。 我们建议有超过50万个团的大型机构使用此选项来减少混乱。
- SDS
    - 成员身份与 SIS/LMS 同步来维护学生成员身份更改。
    - EDU 客户成功团队可提供免费部署协助。
    - 可选地创建用户并应用 Office 365 许可证。
    - 创建跨 Office 365 使用的安全组，包括团队策略。
    - 为限定范围的管理委托和[教师密码重置](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)创建管理单元。
    - 为了减少管理员的工作，会有用于大规模处理的内置错误、重试处理、节流回退和会话稳定性。 
    - 内置的清理功能，可在组和团队过时后重命名和存档。 
    - [分数同步](https://docs.microsoft.com/schooldatasync/grade-sync)：老师们可以以小组为单位进行评分，并让系统自动将各小组的成绩写回 SIS 的成绩单上。 
    - [学生数据保护](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data)：防止学生使用非 Microsoft 的应用程序，并跟踪和管理家长许可。 
    - 为了丰富有关的教育见解，导入的数据将用于用户角色、组织（学校）和其他重要数据。
- Graph API
    - 额外的灵活性和控制。
    - 不需要与 SDS 集成。

### <a name="considerations"></a>注意事项

- 非完全自动化，需要某些教师操作。
- 没有权限创建团队的教师仍可从现有组中创建团队，如[下](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)所示 。
- Graph API 需要高级别的技术知识和时间来创建和运行脚本，并修复创建班级组时出现的任何问题。

### <a name="get-started"></a>开始使用

开始使用 SDS 方法，请访问[学校数据同步（SDS）](https://docs.microsoft.com/SchoolDataSync)并联系[https://aka.ms/sdssupport](https://aka.ms/sdssupport)部署协助。 

若要使用 Graph API 方法，请参阅 [Graph API](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) 并 [创建课堂团队](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)。  

> [!NOTE]
> 若要将此方法用于 SDS，需要在 SDS 配置文件中关闭自动团队创建切换。 你还可以通过使用两个 SDS 配置文件，将自动和教师端团队创建的组合用于所需的和可选的课堂团队。

## <a name="powershell-script-using-graph-apis"></a>PowerShell 脚本（使用 Graph API）

借助 PowerShell，你可编写脚本来自动创建团队、频道和配置设置。 它要求管理员先创建组，再添加教师和学生，然后按[此处](https://docs.microsoft.com/graph/teams-create-group-and-team)所示创建团队。 此外，还可使用 Microsoft Graph API 创建、配置、克隆和存档团队。 有关详细信息，请参阅[将 Microsoft Graph API 与 Microsoft Teams 结合使用](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)协同工作，[Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams)和[创建课堂团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type)。 使用 Graph API 是获得更多控制和灵活性的好方法，它需要高级别的技术知识，并会在初始时间内花更多时间。  

### <a name="benefits"></a>优点

- 额外的灵活性和控制。
- 可用于创建教师尽早的访问权团队或即时学生访问团队的选项。  
- 如果[从组创建团队](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group)，则教师将拥有尽早访问权限，并且将同步对 Azure AD 组的学生成员身份更改。

### <a name="considerations"></a>注意事项

- 需要高级别的技术知识和时间来创建和运行脚本，并修复创建班级组时出现的任何问题。
- 无内置错误处理或重试逻辑。
- 成员身份更改不会与 SIS 同步。 

> [!NOTE]
> 课堂团队需要隐藏的组成员身份，以便只有课堂中的教师和学生可以查看班级的成员。 若要创建 Office 365 课堂组，请参阅[创建课堂团队](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)以达到相同的隐私要求。

## <a name="manual-team-creation"></a>初始团队创建

当学生和教师能够以最小的障碍使用 Teams 并灵活地根据自己的需求对其进行调整时，他们将能够充分利用 Teams。 支持用户调整其 Teams 体验的方法之一是允许其创建满足自己需求的团队。 按[此处](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)查看教师设置自己的班级类型团队并邀请学生。 教师可以通过[将学生添加到团队](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)、[共享加入代码](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)或[共享指向团队的链接](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)来邀请学生。 如果可能，最好让教师将学生添加到团队，以确保学生获得访问权限并收到其已添加到团队的通知。

### <a name="benefits"></a>优点

- 为教师提供额外的灵活性。
- 即时团队创建和访问。  

### <a name="considerations"></a>注意事项

- 需要教师的行动和时间。
- 学生成员关系未与 SIS 同步，需要手动管理。
- 不会让教师尽早访问其团队。 学生将立即获得访问权限。

## <a name="recommended-best-practices"></a>建议的最佳做法

- 及早部署！ 尽早部署，以确保所有东西都能有效地工作，并为开学第一天做好准备。 如果你使用的是 SDS，则无需获得完整的学生成员身份即可开始 SDS 部署。 它将在你的 SIS 中提供该信息时同步学生。
- 如果你有超过50万的团队，我们建议使用[教师指导团队创建方法](#teacher-led-team-creation-from-office-365-class-groups)。 它仅创建相关和所需的课堂团队，减少未使用的团队和垃圾邮件。  
- 如果存在任何问题（例如找不到课堂），而 SDS 自动创建团队和教师立即需要它们，则可以使用[教师指导团队创建方法](#teacher-led-team-creation-from-office-365-class-groups)重试。 [手动创建团队](#manual-team-creation)是另一种解决方案，但是，它不会更新您的团队成员。  
- 租户团队限制为50万个团队。 因此，管理员应该主动尝试减少未使用团队的数量，以避免达到这些限制以至延长设置时间。 有关限制的详细信息，请参阅[ Microsoft Teams 的限制和规范](limits-specifications-teams.md)。  
