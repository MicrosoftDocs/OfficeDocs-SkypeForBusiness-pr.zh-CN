---
title: Microsoft Teams 中的团队和频道概述
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解可用于各种需求（例如财务、活动计划、销售等）的不同团队、频道和应用。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12dca0160b4434472e2afa60971fb80ddebf925d
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483399"
---
> [!NOTE]
> 查看以下信息，了解 Teams 中的聊天、团队、频道和应用。 然后，转到 [Teams 中的聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)，查看对你的 Teams 推广至关重要的决策列表。

<a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams 中的团队和频道概述
=================================================

我们首先来了解 Microsoft Teams 如何允许单个团队进行自我组织并跨业务场景进行协作：

- **团队**是与组织内不同项目和成果相关的人员、内容和工具的集合。

    - 可以创建只对受邀用户私有的团队。

    - 也可以创建公用的开放团队，组织中的任何人都可以加入（最多 5000 个成员）。
    
    团队旨在将一组紧密协作的人员召集在一起完成工作。 对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的，也可以是持续存在的，以反映组织的内部结构（例如，部门和办公室位置）。 跨团队频道的对话、文件和笔记仅对团队成员可见。

- **频道**是团队中的专门部分，用于保持按照特定主题、项目、学科（适用于团队的一切学科）组织的对话。 你在频道（“文件”选项卡上）共享的文件将存储在 SharePoint 中。 若要了解详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)。

    - 团队频道是团队中每个人都可以公开对话的地方。 私人聊天仅对参与聊天的人员可见（你在聊天中共享的文件将存储在 OneDrive for Business 中）。 

    - 可以使用包括选项卡、连接器和聊天机器人的应用扩展频道，从而提高其对团队成员的价值。 若要了解详细信息，请参阅 [Teams 中的应用、机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。

观看此简短视频，了解有关创建团队和频道的最佳做法的详细信息。

   > [!VIDEO https://www.youtube.com/embed/hjJWtoaRJeE]

<a name="membership-roles-and-settings"></a>成员资格、角色和设置
------------------------------

**团队成员资格**

为你的整个组织激活 Microsoft Teams 后，指定团队所有者将能够邀请一起合作的任何员工加入他们的团队。 Microsoft Teams 使团队所有者能够根据用户姓名在组织中轻松添加。 根据你的组织的设置，属于团队成员但不属于你的组织的来宾也可以添加到你的团队。 有关更多信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。 

团队所有者也可以根据现有 Office 365 组创建团队。 对组所做的任何更改都将自动与 Microsoft Teams 同步。 根据现有 Office 365 组创建团队不仅可以简化邀请和管理成员的流程，还可以同步 Microsoft Teams 内的组文件。

**团队角色**

Microsoft Teams 中有两个主要角色： 

- **团队所有者** - 创建团队的人员。 团队所有者可以在邀请联系人加入团队时或者在他们加入团队后将团队的任意成员设为共同所有者。 设置多个所有者可以分担管理设置和成员资格（包括邀请）的责任。
- **团队成员** - 由所有者邀请加入团队的人员。

此外，如果设置了审核，则团队所有者和成员可以拥有频道的审核员功能。 审核员可以在频道中发布新帖子，并控制团队成员能否回复现有频道消息。 团队所有者可以在频道内指派审核员。 （默认情况下，团队所有者具有审核员功能。）频道内的审核员可在该频道中添加或删除其他审核员。 有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

**团队设置** 

团队所有者可以直接在 Microsoft Teams 中管理团队范围设置。 设置包括添加团队图片、跨团队成员设置创建频道、添加选项卡和连接器和 @提及整个团队或频道的功能，以及 GIF、贴纸和 Meme 的使用情况。 

请花三分钟时间观看面向团队所有者的指导视频： 

   > [!VIDEO https://www.youtube.com/embed/7XcDSuw6NR4]

如果你是 Office 365 中的 Microsoft Teams 管理员，你可以在 Microsoft Teams 管理中心访问系统范围设置。 这些设置可能会影响团队所有者在团队设置下看到的选项和默认设置。 例如，你可以为团队范围的公告、讨论和资源启用默认频道“常规”，它将在所有团队中显示。

默认情况下，所有用户都具有在 Microsoft Teams 中创建团队的权限（若要修改此设置，请参阅[在 Teams 中分配角色和权限](assign-roles-permissions.md)）。 现有 Office 365 组的用户也可以使用 Teams 功能增强其权限。

吸引用户使用 Teams 的一项关键的早期计划活动是帮助人们考虑和了解 Microsoft Teams 如何在其日常生活中增强协作。 与其他用户交谈，帮助他们选择当前以分散方式协作的业务场景。 将他们带入具有可帮助他们完成工作的相关选项卡的频道。 Teams 最强大的用例之一是任何跨组织流程。 

<a name="example-teams"></a>示例团队
--------------

以下是一些功能示例，说明不同类型的用户如何设置他们的团队、频道和应用（选项卡/连接器/机器人）。 这有助于与用户社区开展有关 Microsoft Teams 的对话。 当你考虑如何在贵组织中实施 Microsoft Teams 时，请注意，你可以指导如何建立团队，但用户可以控制如何自我组织。 这些只是帮助团队开始思考各种可能性的示例。

Microsoft Teams 的特点在于打破组织界限及推动跨职能团队，因此，鼓励你的用户从职能团队而不是组织界限角度考虑这一点。

|团队类型  |可能的频道  |应用（选项卡 ![描述包含选项卡的文件夹的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/连接器 ![描述连接块的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/机器人 ![描述小机器人的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|销售额     |年度销售会议<br></br> 季度业务回顾<br></br> 月度销售渠道回顾<br></br> 销售战术 |Power BI<br></br>Trello<br></br>CRM<br></br>汇总聊天机器人         |
|公共关系     |新闻稿<br></br>新闻和更新<br></br>核实         |RSS 源<br></br>Twitter         |
|活动规划     |市场营销<br></br>后勤工作和计划<br></br>场地<br></br>预算         |Twitter<br></br>Facebook<br></br>Planner<br></br>PDF         |
|市场营销/投放市场   |市场调查<br></br>消息传递支柱系统<br></br>沟通计划<br></br>市场营销材料清单        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|技术运营    |事故管理<br></br>冲刺计划<br></br>工作项<br></br>基础结构和操作         |Team Services<br></br>Jira<br></br>AzureBot         |
|产品团队      |策略<br></br>市场营销<br></br>销售额<br></br>操作<br></br>见解<br></br>服务和支持         |Power BI<br></br>团队服务         |
|财务    |当前财政<br></br>财年计划<br></br>预测<br></br>应收账款<br></br>应付账款         |Power BI<br></br>Google Analytics         |
|后勤     |仓储运营<br></br>车辆维护<br></br>司机值勤名单         |气象服务<br></br>行程/道路中断<br></br>Planner<br></br>Tubot<br></br>UPS 聊天机器人         |
|人力资源     |人才管理<br></br>招聘<br></br>绩效考核计划<br></br>信念         |人力资源工具<br></br>外部公开招聘网站<br></br>Growbot         |
|跨组织 <br></br>虚拟团队 |策略<br></br>员工团队发展<br></br>完成和调研         |Power BI<br></br>Microsoft Stream         |

可以根据组织结构创建团队。 对于想要推动士气、举行团队特定评审、澄清员工入职流程、讨论人力计划并提高跨分散人力的可见性的领导来说，这最为适用。  

![在 Microsoft Teams 中组织的团队和频道的层次结构图。](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>组织范围的团队

如果贵组织的用户数不超过 5,000 个，则可以创建组织范围的团队。 组织范围的团队为组织中的每个人提供了自动加入单个协作团队的方法。 有关详细信息（包括创建和管理组织范围团队的最佳做法），请参阅[在 Microsoft Teams 中创建组织范围的团队](create-an-org-wide-team.md)。
