---
title: 开始使用 Microsoft Teams 进行远程学习
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Microsoft Teams 教育版远程学习入门指南。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466020"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>开始使用 Microsoft Teams 进行远程学习

本文介绍使用 Microsoft Teams 为远程学习设置教育机构的 IT 管理步骤。

在 Teams 中， **教师** 可以：

- 快速与学生交谈。
- 共享文件和网站。
- 创建 OneNote 课堂笔记本。
  - 组织交互式课程。
  - 提供有效且及时的反馈。
- 分配和评分分配。
- 在专业学习社区中共享教学材料。

**教育管理员和工作人员** 可以：

- 随时了解事件。
- 使用 Staff Teams 进行公告和主题对话进行协作。

# <a name="accounts--licenses"></a>[帐户&许可证](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>用户帐户、许可证和标识安全性

Teams 使用 Microsoft 365 对用户进行身份验证并提供服务。 所有用户都应建立 Microsoft 365 标识，以促进协作。

如果用户标识尚不存在，请按照此过程建立它们：

1. [使用学校数据同步创建用户](/microsoft-365/education/deploy/school-data-sync)。
2. [向用户分配许可证](teams-edu-licensing.md)。
3. [创建 Microsoft 365 组](Office-365-groups.md)。
4. [设置 Exchange](Exchange-Teams-interact.md)。
5. [设置 SharePoint 和 OneDrive](SharePoint-OneDrive-interact.md)。
6. [设置具有 Google 电子邮件的用户](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)。

Microsoft Teams 包含在所有 Microsoft 365 计划中，包括免费 A1 教育计划。

有关部署 Microsoft 365 和设置 Teams 的指南，请查看 [“创建 Microsoft 365 租户](/microsoft-365/education/deploy/create-your-office-365-tenant)”。

# <a name="set-up-teams"></a>[设置 Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>轻松设置团队

下面是使用 Teams 启动和运行需要执行的两项操作：

### <a name="1-allow-users-to-create-teams"></a>1. 允许用户创建团队

**默认情况下，每个人都可以创建 Microsoft 365 组和 Teams**，但此功能可能并不总是合适的。

例如，一些学校可能希望在没有监督的情况下限制学生创建 Teams。 Microsoft 365 组和团队创建可能 [仅限于某些安全组](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

对于高等教育机构，我们建议允许每个人（包括学生）为课程、研究、组项目和学习组创建团队。

有关如何创建 Teams 的演练，请参阅 [Microsoft Teams 中的“创建类团队](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)”。

### <a name="2-configure-user-experiences-using-policies"></a>2. 使用策略配置用户体验

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 查看 [在 Teams 中确保学生安全进行远程学习](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8)。
>
> 若要查看我们的 EDU 策略建议，请参阅 [适用于教育的 Teams 策略和策略包](policy-packages-edu.md)。

Teams 策略控制特定用户或组可用的功能。 策略可以定义应允许谁使用私人聊天、私人通话、会议日程安排、可共享的内容类型等。

**高等教育工作人员、教师和学生** 可以使用默认 (全球) 政策。 可以调整策略以向 Teams 添加更多功能，包括 [翻译功能](messaging-policies-in-teams.md#messaging-policy-settings) 和 [自动会议听录](meetings-policies-recording-and-transcription.md#transcription)。

**中小学生** 可能需要受限的功能。 建议对“全局 (组织范围的默认) ”策略进行学生策略更改。

应为 **小学教职员工和教育工作者** 分配授予关键功能的政策，例如允许私人聊天和会议安排。 [向员工和教师批量分配这些策略](batch-group-policy-assignment-edu.md)。

> [!IMPORTANT]
> 对于分配给任何用户的会议策略，建议将 **“自动允许人员** ”设置为 **组织中的“每个人**”。 这将确保必须先从大厅中接纳未经身份验证的用户，然后才能加入 Teams 会议。
>
> 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-participants-and-guests.md#automatically-admit-people)。

# <a name="class-teams"></a>[课堂团队](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>创建课堂团队，以便安全地使用课堂

Microsoft Teams 教育版提供了针对教育用途的[特定团队类型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)。 [课堂团队类型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)是为课堂使用而设计的，并带有支持课堂需要的特定功能，包括：

- 作业。
- 成绩。
- OneNote 课堂笔记本。
- 用于保护学生只读内容的[课堂材料文件夹](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)。
- [见解](./class-insights.md)，可提供有关每课堂的学生参与度、作业和幸福感的实时数据。
- [早期教师有权在](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) 添加学生之前设置课程。
- 使中断性学生和其他特殊权限静音的能力。

可以通过以下方式创建类团队：

- [学校数据同步 (SDS) ](#automatic-team-creation-using-sds)。
- [使用 Microsoft 365 类组以教师为主导的创建](#educator-led-team-creation-from-microsoft-365-class-groups)。
- [使用 Graph API 的 PowerShell 脚本](#powershell-script-using-graph-apis)。
- [手动创建团队](#manual-team-creation)。

我们将逐步介绍各种选项，以帮助你选择最适合你需求的正确部署路径。

### <a name="automatic-team-creation-using-sds"></a>使用 SDS 自动创建团队

[学校数据同步 (SDS) ](/SchoolDataSync) 从机构的记录系统中读取数据，例如学生信息系统 (SIS) 或学习管理系统 (LMS) 。

SDS 可以从任何记录系统导入数据，并将内置连接器导入到许多 [SIS 供应商](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support)。  

#### <a name="benefits-of-sds"></a>SDS 的优势

- 自动创建用户并应用许可证。
- 自动创建和维护类团队。
- 与 SIS/LMS 同步以维护学生成员身份更改。
- [允许教师在添加学生之前准备课程](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。
- 可以自动创建安全组。
- 为范围管理委派创建管理单元。
- [允许教师密码重置](/schooldatasync/how-to-enable-teacher-password-reset)。
- 具有用于重命名和存档组和团队的内置清理功能。
- [将成绩从 Teams 同步到 SIS](/schooldatasync/grade-sync)。
- [保护学生的个人数据](/schooldatasync/protecting-student-personal-data)。
- 跟踪和管理监护人的同意。
- 提供更好的教育版 Insights数据。

#### <a name="considerations-for-sds"></a>SDS 的注意事项

SDS 通过两个步骤创建团队：

1. SDS 在 Azure Active Directory (Azure AD) 中创建 Microsoft 365 组。
2. SDS 会自动将该组转换为团队。

创建团队的第二步在SDS中是可选的。 管理员可能不希望根据部署时间和可能产生的未使用团队的数量自动创建团队。 相反，请参阅 [教师领导的团队创建方法](#educator-led-team-creation-from-microsoft-365-class-groups)。  

#### <a name="get-started-with-sds"></a>SDS 入门

若要开始，请转到 [学校数据同步 (SDS) ](/SchoolDataSync) 并联系 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 以获得免费部署帮助。  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>从 Microsoft 365 类组创建教师领导的团队

教师领导的团队创建使教师可以轻松创建所需的课程。  

此方法允许使用 SDS 为每个类创建组 (建议) 或使用[图形 API](/graph/api/educationroot-post-classes)自行创建它们。

准备课堂组后，教师可以将其组转换为团队：

1. 在 Teams 中选择“Teams”选项卡。
2. 在客户端顶部，选择 **“建议的类** ”图标。

#### <a name="benefits-of-educator-led-team-creation"></a>教师领导的团队创建的优点

- 除非教师打算使用这些课程，否则会准备和建议，但不会创建这些课程。
- 对于拥有超过 500，000 个团队的机构，此方法可减少不必要的团队数。
- [SDS 权益](#benefits-of-sds)。
- 图形 API好处。
  - 让教师控制要创建哪些类。
  - 不需要与 SDS 集成。

#### <a name="considerations-for-educator-led-team-creation"></a>教师领导的团队创建注意事项

- 非完全自动化，需要某些教师操作。
- 无权创建团队的教师仍然可以 [从现有组创建团队](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)。
- 图形 API需要高度的技术专长、创建和运行脚本的时间以及解决任何问题的时间。

#### <a name="get-started-with-educator-led-team-creation"></a>以教师为主导的团队创建入门

若要开始使用 SDS 方法，请转到 [学校数据同步 (SDS) ](/SchoolDataSync) 并联系 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 以获得免费部署帮助。

- 需要关闭 SDS 配置文件中的自动团队创建开关。
- 可以使用两个 SDS 配置文件为班级团队使用自动创建和教师主导的团队创建组合。

若要使用 Graph API 方法，请参阅 [Graph API](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) 并 [创建课堂团队](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)。  

### <a name="powershell-script-using-graph-apis"></a>PowerShell 脚本（使用 Graph API）

借助 PowerShell，可以编写脚本来创建团队和频道，并自动配置设置。

此方法要求管理员 [先创建组，添加教师和学生，然后创建团队](/graph/teams-create-group-and-team)。

还可以使用 [Microsoft 图形 API创建、配置、克隆和存档团队](/graph/api/resources/teams-api-overview)。

#### <a name="benefits-of-powershell-scripts"></a>PowerShell 脚本的优点

- 让 IT 管理员控制类创建。
- 可用于创建教师提前访问团队或学生即时访问团队的选项。
- [将学生成员身份更改同步到 Azure AD 组](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)。

#### <a name="considerations-for-powershell-scripts"></a>PowerShell 脚本的注意事项

- 需要高级别的技术知识和时间来创建和运行脚本，并修复创建班级组时出现的任何问题。
- 无内置错误处理或重试逻辑。
- 成员身份更改不会与 SIS 同步。

> [!NOTE]
> 课堂团队需要隐藏的组成员身份，以便只有课堂中的教师和学生可以查看班级的成员。 若要创建 Microsoft 365 类组，请 [参阅“创建类团队](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) ”以满足隐私要求。

### <a name="manual-team-creation"></a>初始团队创建

用户可以通过能够创建自己的团队来定制其 Teams 体验。

根据用户的权限，他们可以：

- [设置自己的团队并邀请用户，包括学生](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)。
- [手动将用户添加到团队](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)。
- [共享联接代码](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。
- [共享指向团队的链接](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。

最好让教师将学生添加到团队，以确保学生获得访问权限，并收到已添加他们的通知。

#### <a name="benefits-of-manual-team-creation"></a>手动创建团队的好处

- 让教师完全控制课堂创建。
- 立即创建类团队。

#### <a name="considerations-for-manual-team-creation"></a>手动创建团队的注意事项

- 需要教师的行动和时间。
- 学生成员身份不会与 SIS 同步，需要手动管理。
- 学生将立即获得课堂团队的访问权限。

### <a name="recommended-best-practices"></a>建议的最佳做法

- 尽早部署，以确保所有东西都能有效地工作，并为开学第一天做好准备。

- 对于 SDS 自动创建团队的问题，教师可以使用 [教师领导的团队创建方法](#educator-led-team-creation-from-microsoft-365-class-groups) 重试。 [手动创建团队](#manual-team-creation) 是另一种解决方案，但类不会与 SIS 同步。

- 租户团队限制为50万个团队。 因此，管理员应减少未使用的团队数，以避免达到这些限制。 有关详细信息，请参阅 [Microsoft Teams 的限制和规范](limits-specifications-teams.md)。  

# <a name="educator-early-access"></a>[教师提前访问](#tab/early-access)

## <a name="early-access-to-class-teams"></a>提早访问课堂团队

早期访问课堂 Teams 允许教师在学生查看之前访问其课堂团队。 教师在授予学生访问权限之前，将有时间设置、添加文件和进行组织。

当他们准备好让学生访问团队时，他们可以 [激活他们的班级](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>如何创建课堂团队，使教师可以在录取学生之前提前访问以设置团队？

默认情况下，从组（通过 SDS、由教师领导或 Graph API）创建的团队会自动创建抢先体验团队。

若要使用 Graph API 创建自己的提前访问团队，需要[创建一个班级](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)并[从组创建团队](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)。

### <a name="how-do-i-check-if-a-class-is-activated"></a>如何检查是否已激活班级？

在 [团队资源类型](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true)中，查看属性 [isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true)，以查看是否激活了类。

使用[“获取团队”API](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) 查询特定类的 ```isMembershipLimitedToOwners``` 属性。 如果团队已激活，将返回值 false。 如果团队尚未激活，它将返回 true 值。

### <a name="how-do-i-activate-a-class-for-an-educator"></a>如何为教师激活班级？

使用 [更新团队 API](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true)，并将属性设置 ```isMembershipLimitedToOwners``` 为 false，以代表教师激活团队。 激活团队后，无法反转。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>创建职员团队，促进其沟通和协作

[教职员工类型团队](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) 供教育管理员和工作人员共享信息，并共同开展全院的举措。

教育管理员可以通过团队创建向导、 [在创建团队后添加成员](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)或 [共享加入代码或链接来向团队](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)添加员工。

# <a name="meeting-scenarios"></a>[会议方案](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>团队会议应用场景

### <a name="collaborative-meetings-for-virtual-classes"></a>虚拟课堂协作会议

[Microsoft Teams 会议](./tutorial-meetings-in-teams.yml)支持多达 250 个并发与会者，包括音频、视频、[内容共享](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、白板和共享笔记功能。

会议可以是：

- [在 Teams 客户端中计划](./tutorial-meetings-in-teams.yml)。
- 记录并保存供与会者稍后查看。
- [转录以轻松查找内容](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)。
- 使用笔记本电脑或手机摄像头、麦克风和扬声器进行访问。
- [针对特定设备进行了优化](https://products.office.com/microsoft-teams/across-devices/devices)。
- 为所有参与者结束，以确保学生不在无人监督的会议中。

### <a name="districtuniversity-events-or-updates"></a>地区/大学事件或更新

某些会议具有大量受众和额外的生产需求。 这些会议通常具有定义的演示者、制作人和接受审核的问答。

Teams 使用 [Microsoft Teams 实时事件](teams-live-events/what-are-teams-live-events.md)来支持这些会话。

实时事件可用于方案，例如：

- 区域或大学范围的更新。
- 领导力地址。
- 有关大型课程或学生组的说明。
- 扩展到社区。

了解如何在以下处进行实时会话：

- [计划和计划实时活动](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)。
- [生成实时事件](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)。
- [参加直播活动](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)。
- [调试 Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)。

# <a name="resources"></a>[资源](#tab/resources)

## <a name="support-resources"></a>支持资源

有关过渡到远程学习的一般概述， [请从此处开始](https://www.microsoft.com/education/remote-learning)

如果你是 IT 管理员、教师、学生或监护人，这些资源可以帮助你使用 Teams：

- **IT 管理员**
  - [按平台分组的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  - [下载并分发 Teams 客户端](get-clients.md)。
  - [Teams 故障排除](/MicrosoftTeams/troubleshoot/teams)。
  - [用于虚拟化桌面基础结构的 Teams](./teams-for-vdi.md)。
  - [监视和管理呼叫质量](monitor-call-quality-qos.md)。
  - [验证 Teams 的服务运行状况](service-health.md)。
  - [优化远程员工的 Microsoft 365 流量](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)。
  - [Teams 的支持联系人](/microsoft-365/admin/contact-support-for-business-products)。
  - [Teams 教育版网络研讨会](https://aka.ms/TeamsEDUWebinars)。

- **教师**
  - [教师帮助中心](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)。
  - [远程学习帮助](https://aka.ms/RemoteLearningHelp)。
  - [下载 Teams](get-clients.md)。
  - [Teams 教育版网络研讨会](https://aka.ms/TeamsEDUWebinars)。
  - [面向使用 Teams 的教师的在线课程](https://education.microsoft.com/course/9c9f5c11/overview)。
  - [使用 Teams 创建协作学习环境的联机课程](https://education.microsoft.com/course/b1e15cfc/overview)。
  - [提交支持票证](https://www.microsoft.com/microsoft-teams/download-app)。

- **学生**
  - [学生帮助中心](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694)。
  - [远程学习帮助](https://aka.ms/RemoteLearningHelp)。
  - [下载 Teams](https://www.microsoft.com/microsoft-teams/download-app)。

- **监护人**
  - [远程学习帮助](https://aka.ms/RemoteLearningHelp)。
  - [下载 Teams](https://www.microsoft.com/microsoft-teams/download-app)。

---
