---
title: 面向教育版管理员的 Microsoft Teams 资源
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Microsoft 团队 for 教育机构的远程学习启动指南。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403832"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Microsoft 团队开始使用 "远程学习"

Microsoft 团队是一种将对话、内容、工作分配和应用集中到同一位置的平台。 构建协作式教室，在专业学习社区中连接，并与同事保持联系-所有这些都是通过单个体验实现的。

使用本文中的最佳做法，开始使用 Microsoft 团队满足你的教育需求，以便启用远程学习功能。 Microsoft 团队可用于实现课堂协作，让学生参与对话、提供虚拟会议平台和分配作业。 学校管理员和员工可以使用团队进行通知和 topical 对话，保持最新状态并协作。 教师可以使用专业学习社区分享说明性材料。

Microsoft 团队拥有适用于桌面（Windows、Mac 和 Linux）、web 和移动设备（Android 和 iOS）的[客户端](get-clients.md)，确保你的所有教职员工和学生可以保持连接。

有关详细信息，请参阅[适用于教育网络研讨会系列的团队](https://aka.ms/TeamsEDUWebinars)使用方案。

## <a name="user-accounts-licenses-and-identity-security"></a>用户帐户、许可证和标识安全

Microsoft 团队利用 Microsoft 365 功能对用户进行身份验证和提供服务。 教职员工、教师和学生应建立标识，以便促进协作。 如果尚不存在标识，请按照此过程进行设置。

[需要为用户启用团队许可证](user-access.md)后才能开始使用团队功能。 团队依靠其他 Microsoft 365 功能（如[Office 365 组](Office-365-groups.md)、 [Exchange](Exchange-Teams-interact.md)、 [SharePoint 和 OneDrive](SharePoint-OneDrive-interact.md) ）来实现协作方案。 如果同时启用了所有这些服务，用户将获得最佳团队体验。 [对于拥有由 Google 托管的电子邮件的用户，团队是受支持的](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)。

## <a name="easily-set-up-microsoft-teams"></a>轻松设置 Microsoft 团队

以下是开始和与团队协作时需要执行的两个操作：

### <a name="1-allow-users-to-create-teams"></a>1. 允许用户创建团队

学生和教育人员可以在最少的障碍中使用团队，并能够灵活地根据自己的需要对其进行调整。 用户可定制其团队体验的一种方法是能够创建满足其需求的团队。 **默认情况下，每个人都可以创建 Office 365 组和团队**。 有时，此功能可能不合适;例如，某些客户可能希望限制主要学生的创建团队。 如果需要，可以将 Office 365 组和团队创建[限制为环境内的某些安全组](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。

更高版本的客户可在让每个人（包括学生）创建团队、研究、组项目和研究组时受益。 主要的学校可能希望限制学生创建团队，以确保所有学生到学生的通信都在包含成人的论坛中发生。 在这种情况下，可以将 Office 365 组和团队创建限制为所有教育版和员工。

### <a name="2-configure-user-experiences-using-policies"></a>2. 使用策略配置用户体验

[团队策略](teams-policies.md)提供控制特定用户或用户组的可用选项的功能。 可应用策略来定义应允许哪些用户使用私人聊天、私人通话、会议安排、可共享的内容类型等。

**更高的教育员工、教育和学生也**受益于默认（全局）策略附带的功能。 可启用一些其他策略设置以向 Microsoft 团队添加更多功能，包括[在邮件策略中启用翻译功能](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)，以及允许自动在会议策略中进行会议。

**主要-次要学校学生**可能需要提供给学生的受限功能。 策略设置学生可以执行的操作的边界。 由于学生填充通常是最大的一组用户，并且通常会收到最严格的设置，建议将学生策略更改为 "全局（组织范围的默认）" 策略。

以下是一组常用的非默认策略配置，这些配置将分配给主要辅助学生以限制学生之间的 unmoderated 通信：

#### <a name="messaging-policy"></a>邮件策略

- 更改设置为 "关闭"
- Giphy 内容分级设置为 "strict"
- 将已设置的邮件翻译为 "开"
- 使用设置为 "关闭" 的优先级通知发送紧急邮件
- 将用户从组聊天室中删除设置为 "关闭"

#### <a name="meeting-policy"></a>会议策略

- 允许频道中的 "立即开会" 设置为 "关闭"
- 允许将 Outlook 加载项设置为 "关闭"
- 允许将频道会议计划设置设置为 "关闭"
- 允许将专用会议安排设置为 "关闭"
- "允许在私人会议中立即开会" 设置为 "关闭"

#### <a name="live-events-policy"></a>实时事件策略

- 允许计划设置为 "关闭"

#### <a name="calling-policy"></a>呼叫策略

- 将私人通话设置为 "关"

#### <a name="teams-policy"></a>团队策略

- 创建专用频道设置为 "关闭"

应为**主要教职员工人员和教育**部门分配策略，以授予可能受学生限制的核心功能。 创建允许私人聊天和会议计划（新策略的默认设置）的新策略。 [通过安全组成员身份将这些策略分配给您的员工并进行教育](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)。

## <a name="start-using-teams"></a>开始使用团队

### <a name="create-class-teams-for-secure-classroom-use"></a>创建课堂团队以确保课堂使用

Microsoft 教育版团队提供[特定的团队类型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)供教育使用。 [课堂团队类型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)适用于具有特定功能的教室，其中包括：工作分配、OneNote 课堂笔记本、[课堂材料文件夹](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)（用于保护学生的只读内容），以及将中断的学生设为静音的功能。 可通过多种方式部署类团队：

1. [学校数据同步](https://sds.microsoft.com/)（SDS）可**由其设置**，从而允许基于学校信息系统中的信息为所有课程创建类团队。 此过程将为每个分区设置团队，并使教师和学生海报同步。在 admitting 学生之前，[教师将能够准备好其团队](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。 或者，如果教师不使用团队，学生不会被获准加入团队，因为教师从不单击 "激活"。 SDS 支持用于数据导入的80多个不同的学校信息系统（SIS 系统），并且[SDS 支持团队](https://aka.ms/SDSSupport)准备好帮助你规划和配置。
1. **教师设置**自己的课堂类型团队并邀请学生。 教师可以通过[向团队添加学生](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)、[共享加入代码](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)或[共享团队链接来](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)执行此操作。 如果可能，建议教师将学生添加到团队以确保学生获得访问权限，并通知他们已添加到团队。

在团队设置后，团队所有者可以[自定义其团队的设置](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158)，包括添加[团队图片](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0)、为课堂主题或组协作区域[创建通道](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US)、将 Quizlet/Flipgrid/Kahoot 等[应用添加](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77)到表面现有的教学内容，并[提及其团队以供他们第一次发布](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2)通知所有人并开始对话。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>为员工沟通和协作创建教职员工团队

[教职员工类型团队](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf)专为学校管理员和员工设计，可轻松共享信息并协作处理学校范围内的计划，包括发布通知、设置会议、共享内容和引入外部应用，如[任务跟踪的 Planner](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2)。 学校管理员可以通过团队创建向导将学校职员添加到团队，在[创建团队后添加成员](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)，或者通过[共享加入代码或链接到团队](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。 [创建频道](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525)是按工作流或主题组织对话和文件的绝佳方式。 [团队所有者的转指南](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US)是了解团队所有者责任和功能的绝佳位置。

## <a name="teams-meeting-scenarios"></a>团队会议方案

### <a name="collaborative-meetings-for-virtual-classes"></a>虚拟课堂协作会议

[Microsoft 团队会议](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)最多支持250个并发与会者，包括音频、视频、[内容共享](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、白板和共享笔记的功能。 会议可以在 Microsoft 团队客户中安排在[专用空间内或团队频道内会议](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams)，以便所有团队成员都知道。 可以录制和保存会议，以便与会者以后查看。 这些唱片还可以[transcribed，以便轻松找到](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)讨论过的内容。 便携式电脑或移动电话网络摄像头、麦克风和扬声器可用于会议，您可以从[Microsoft 团队优化的设备](https://products.office.com/microsoft-teams/across-devices/devices)获取高级音频/视频质量。

### <a name="districtuniversity-events-or-updates"></a>地区/大学活动或更新

某些指令需要更大的受众和其他生产功能。 这些会议通常已定义演示者、制造商和&A 的 "审核问答"。 Microsoft 团队使用[Microsoft 团队实时事件](teams-live-events/what-are-teams-live-events.md)支持这些会话。 实时事件可用于方案，例如地区或大学范围的更新、领导地址以及对大型课堂或学生组的说明，或者扩展到您的社区。 详细了解如何在以下位置执行实时会话：[计划和安排实时事件](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)、[制作实时](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)事件、[参与实时事件](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)以及[主持问答&a](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)。

## <a name="recommended-tips--tricks"></a>& 诀窍的推荐技巧

你可以在以下位置了解有关 Microsoft 团队如何在教育中使用的详细信息： [Microsoft 团队教育](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)版。

> [!NOTE]
> 某些关键的 Microsoft 团队功能并非特定于教育版。 核心团队功能的提示和技巧可在以下位置找到： [Microsoft 团队帮助和学习](https://support.office.com/teams)。

## <a name="adoption-content"></a>采纳内容

Microsoft 已制定了部署 Microsoft 团队的[采纳内容](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)和策略指南。 [Microsoft 团队采纳指南](https://teamworktools.azurewebsites.net/tft/index.html)提供了更好的可用内容概述，[团队客户成功工具包](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)提供了许多可用于团队意识的模板。 Microsoft 教师版中心提供教育特定培训，了解如何在课堂上使用[Microsoft 团队](https://education.microsoft.com/learningPath/18793af1)和[OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) 。

其他采纳资源包括：

- ["您可以在以下情况中执行： 90" 快速提示视频](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Microsoft 团队教育视频播放列表](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [博客：了解此学校如何使用团队进行距离学习](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>支持准备情况

IT 专业人员和支持人员可以使用 Microsoft 团队 IT 体系结构海报和管理员技术培训，快速掌握团队体系结构和 Microsoft 365 功能的基础使用。

其他支持资源包括：

- [Microsoft 团队安装和更新问题疑难解答](troubleshoot-installation.md)
- [监视和管理通话质量](monitor-call-quality-qos.md)
- [验证 Teams 的服务运行状况](service-health.md)
- [Teams 的支持资源](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [监视和管理通话质量](monitor-call-quality-qos.md)
- [验证 Teams 的服务运行状况](service-health.md)
- [Teams 的支持资源](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Microsoft 团队帮助中心](https://support.office.com/en-us/teams)
