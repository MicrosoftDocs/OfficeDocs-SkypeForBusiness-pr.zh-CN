---
title: Microsoft Teams 中的团队和频道概述
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解可用于各种需求（例如财务、活动计划、销售等）的不同团队、频道和应用。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f6b3cbb80fb209c519593c28077b03e4a13ed9
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865166"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams 中的团队和频道概述

> [!NOTE]
> 查看以下信息以了解聊天、团队、频道&应用中Teams。 然后，转到聊天、[团队](deploy-chat-teams-channels-microsoft-teams-landing-page.md)、频道&应用，Teams浏览对推出计划Teams决策列表。

我们首先来了解 Microsoft Teams 如何允许单个团队进行自我组织并跨业务场景进行协作：

- **Teams** 是围绕组织中不同项目和结果的一组人员、内容和工具。

    - 可以创建只允许受邀用户加入的专用团队。
    - Teams可公开开放，组织内部的任何人都可以加入 (最多 10，000) 。
    
    团队用于将一群人集中在一起，以便这些人密切合作来完成事情。 对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的，也可以是持续存在的，以反映组织的内部结构（例如，部门和办公室位置）。 跨团队频道的对话、文件和笔记仅对团队成员可见。

- **频道** 是团队中的专用区域，用于保留按特定主题、项目、专业（适用于你的团队的任何内容！）组织的对话。 在频道中共享的文件 ("文件"选项卡) 存储在SharePoint。 若要了解有关详细信息，请阅读[如何SharePoint Online OneDrive for Business如何与 Teams 交互](SharePoint-OneDrive-interact.md)。

    - 频道是对话发生的位置以及实际完成工作的位置。 频道可以开放给所有团队成员，或者如果您需要更多精选受众，则他们可以是私人的。 标准频道用于团队中每个人都可以参与的对话，专用频道限制与团队[](private-channels.md)中一小组人员的通信。
    - 当使用包含选项卡、连接器和机器人的应用扩展频道时，通道最有价值，这些选项卡、连接器和机器人增加了对团队成员的价值。 有关详细信息，请参阅应用中的应用、[机器人&连接器Teams。](deploy-apps-microsoft-teams-landing-page.md)
    
有关使用团队和频道的帮助，请查看[Teams和频道](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499)。

观看此简短视频，详细了解创建团队和频道的最佳实践。

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>成员身份、角色和设置
------------------------------

**团队成员身份**

为Microsoft Teams激活团队时，指定的团队所有者可以邀请他们合作的任何员工加入其团队。 Microsoft Teams 使团队所有者能够根据用户姓名在组织中轻松添加。 根据你的组织的设置，属于团队成员但不属于你的组织的来宾也可以添加到你的团队。 有关更多信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。 

团队所有者还可以基于现有团队组创建Microsoft 365团队。 对组进行的任何更改将自动与Microsoft Teams同步。 基于现有组创建Microsoft 365组不仅简化了邀请和管理成员的过程，而且还可以同步组Microsoft Teams。

**团队角色**

有两个主要角色在Microsoft Teams： 

- **团队所有者** - 创建团队的人。 团队所有者可以在邀请联系人加入团队时或者在他们加入团队后将团队的任意成员设为共同所有者。 拥有多个团队所有者可以分担管理设置和成员身份（包括邀请）的责任。
- **团队成员** - 所有者邀请加入其团队的人。

此外，如果设置了审核，团队所有者和成员可以具有频道的审阅人功能。 审阅人可以在频道中启动新帖子，并控制团队成员是否可以回复现有频道消息。 团队所有者可以在频道内分配审阅人。  (团队所有者默认具有审阅人功能。) 频道内的审阅人可以添加或删除该频道内的其他审阅人。 有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

**团队设置** 

团队所有者可以直接在团队中管理团队范围的Microsoft Teams。 设置包括添加团队图片、跨团队成员设置权限以创建标准和专用频道、添加选项卡和连接器、@mentioning整个[](private-channels.md)团队或频道以及 GIF、贴纸和 Meme 的使用。

请花三分钟时间观看此适用于团队所有者的指南视频：

   > [!VIDEO https://www.youtube.com/embed/kalV4dG-oFo]

如果你是 Microsoft Teams 或 Microsoft 365 管理员Office 365，则有权访问 Microsoft Teams 管理中心中的系统范围设置。 这些设置可能会影响团队所有者在团队设置下看到的选项和默认设置。 例如，你可以为团队范围的公告、讨论和资源启用默认频道"常规"，这将在所有团队中显示。

默认情况下，所有用户都有权在 Microsoft Teams 中创建团队（要对此进行修改，请参阅[在 Teams 中指定角色和权限](assign-roles-permissions.md)）。 现有组Microsoft 365用户还可以增强其权限，Teams功能。

让用户参与协作的一个关键早期Microsoft Teams活动是帮助用户思考并了解Teams如何增强日常协作。 与人员交谈，帮助他们选择他们当前以分片方式协作的业务方案。 通过相关选项卡将它们汇集到频道中，以帮助他们完成工作。 Teams 最强大的用例之一就是跨组织流程。 

<a name="example-teams"></a>示例Teams
--------------

下面是不同类型的用户如何设置其团队、频道和应用 (选项卡/连接器/机器人) 。 这有助于启动与用户社区Microsoft Teams对话。 在思考如何在组织中实施Microsoft Teams时，请记住，可以提供有关如何构建团队的指导;但是，用户可以控制如何自行组织。 这些示例正是促使团队开始仔细思考各种可能性。

Microsoft Teams是打破组织孤岛和提升跨职能团队的不错选择，因此请鼓励用户考虑职能团队而不是组织边界。

|团队类型  |可能的频道  |应用（选项卡 ![使用选项卡描述文件夹的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/连接器 ![一个描述连接块的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/聊天机器人 ![一个描绘小机器人的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|销售     |年度销售会议<br></br> 季度业务回顾<br></br> 月度销售渠道回顾<br></br> 销售战术 |Power BI<br></br>Trello<br></br>CRM<br></br>汇总聊天机器人         |
|公共关系     |新闻发布<br></br>新闻和更新<br></br>核实         |RSS 源<br></br>Twitter         |
|活动计划     |市场营销<br></br>后勤工作和计划<br></br>场地<br></br>预算         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|市场营销/投放市场   |市场调研<br></br>消息传递支柱系统<br></br>沟通计划<br></br>市场营销材料清单        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|技术运营    |事故管理<br></br>冲刺计划<br></br>工作项<br></br>基础结构和操作         |团队服务<br></br>Jira<br></br>AzureBot         |
|产品团队      |战略<br></br>市场营销<br></br>销售<br></br>运营<br></br>见解<br></br>服务和支持         |Power BI<br></br>团队服务         |
|财务    |当前财政<br></br>财年计划<br></br>预测<br></br>应收账款<br></br>应付账款         |Power BI<br></br>Google Analytics         |
|后勤工作     |仓储运营<br></br>车辆维护<br></br>司机值勤名单         |气象服务<br></br>行程/道路中断<br></br>Planner<br></br>Tubot<br></br>UPS 聊天机器人         |
|人力资源     |人才管理<br></br>招聘<br></br>绩效考核计划<br></br>信念         |人力资源工具<br></br>外部公开招聘网站<br></br>Growbot         |
|跨组织 <br></br>虚拟团队 |战略<br></br>员工团队发展<br></br>完成和调研         |Power BI<br></br>Microsoft Stream         |

可以创建与组织结构Teams一致的组织。 这最适合希望提高员工激励、进行团队特定审核、阐明员工入职流程、讨论员工计划以及提高不同员工可见性的领导。  

![按团队和频道组织的层次结构图Microsoft Teams。](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>组织范围的团队

如果组织的用户数不超过 5，000，可以创建组织范围的团队。 组织范围的团队为组织中的每个人提供自动方式，以便成为单个团队的一部分进行协作。 有关详细信息，包括创建和管理组织范围内团队的最佳实践，请参阅在 Microsoft Teams 中创建组织[范围的Microsoft Teams。](create-an-org-wide-team.md)
