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
f1.keywords:
- CSH
ms.custom: okr_smb
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cf14616d4cfa2abc2caa99aee052b30e902172d
ms.sourcegitcommit: 769241842058cfb4618460fad2dde1494a3609a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42574019"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams 中的团队和频道概述

> [!NOTE]
> 查看以下信息以了解团队中的聊天、团队、频道 & 应用。 然后，转到 "[聊天"、"团队"、"频道"、"& 团队中的应用"，](deploy-chat-teams-channels-microsoft-teams-landing-page.md)浏览针对团队推出的重要决策列表。

我们首先来了解 Microsoft Teams 如何允许单个团队进行自我组织并跨业务场景进行协作：

- **团队**是组织内不同项目和结果周围的人员、内容和工具的集合。

    - 可以创建只允许受邀用户加入的专用团队。
    - 也可以将团队创建为公共和开放，并且组织内的任何人都可以加入（最多可达5000个成员）。
    
    团队用于将一群人集中在一起，以便这些人密切合作来完成事情。 对于基于项目的工作（例如，使某个产品上市或创建数字化作战室），团队可以是动态的，也可以是持续存在的，以反映组织的内部结构（例如，部门和办公室位置）。 跨团队频道的对话、文件和笔记仅对团队成员可见。

- **频道**是团队中的专用区域，用于保留按特定主题、项目、专业（适用于你的团队的任何内容！）组织的对话。 在频道中共享的文件（在 "文件" 选项卡上）存储在 SharePoint 中。 若要了解详细信息，请参阅[SharePoint Online 和 OneDrive For Business 如何与团队进行交互](SharePoint-OneDrive-interact.md)。

    - 频道是指出现对话的地方以及工作实际完成的位置。 可以向所有团队成员开放频道，或者，如果你需要更多的选择受众，则可以使用专用。 标准频道用于与团队中的每个人都可以参与和[专用频道](private-channels.md)限制与团队中人员的子集进行通信的对话。
    - 通过包含选项卡、连接器和机器人的应用进行扩展时，通道最有价值，这些应用会将其值增加到团队成员。 若要了解详细信息，请参阅[团队中的应用、bot、& 连接器](deploy-apps-microsoft-teams-landing-page.md)。
    
有关使用团队和频道的帮助，请查看[团队和频道](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499)。

观看此简短视频，了解有关创建团队和频道的最佳做法的详细信息。

   > [!VIDEO https://www.youtube.com/embed/WkAVgNKn0hs]

<a name="membership-roles-and-settings"></a>成员身份、角色和设置
------------------------------

**团队成员身份**

为您的整个组织激活 Microsoft 团队后，指定的团队所有者可以邀请他们使用的任何员工加入其团队。 Microsoft Teams 使团队所有者能够根据用户姓名在组织中轻松添加。 根据你的组织的设置，属于团队成员但不属于你的组织的来宾也可以添加到你的团队。 有关更多信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。 

团队所有者也可以根据现有 Office 365 组创建团队。 对组所做的任何更改都将自动与 Microsoft 团队同步。 根据现有 Office 365 组创建团队不仅可以简化邀请和管理成员的流程，还可以同步 Microsoft Teams 内的组文件。

**团队角色**

Microsoft 团队中有两个主要角色： 

- **团队所有者**-创建团队的人员。 团队所有者可以在邀请联系人加入团队时或者在他们加入团队后将团队的任意成员设为共同所有者。 有了多个团队所有者，您可以分享管理设置和成员身份的责任，包括邀请。
- **工作组成员**-所有者邀请加入其团队的人员。

此外，如果设置了 "裁决"，团队所有者和成员可以拥有频道的版主功能。 审阅人可以在频道中启动新的文章，并控制团队成员是否可以答复现有频道消息。 团队所有者可在频道内分配监督人。 （默认情况下，团队所有者具有审阅者功能。）频道内的审阅人可以在该频道中添加或删除其他监督人。 有关详细信息，请参阅[在 Microsoft 团队中设置和管理通道裁决](manage-channel-moderation-in-teams.md)。

**团队设置** 

团队所有者可以直接在 Microsoft 团队中管理团队范围的设置。 设置包括添加团队图片的功能、在团队成员之间设置创建标准和[专用通道](private-channels.md)的权限、添加选项卡和连接器、@mentioning 整个团队或频道以及 gif、贴纸和 meme 的用法。

请花三分钟时间查看有关团队所有者的此转到指南的视频：

   > [!VIDEO https://www.youtube.com/embed/kalV4dG-oFo]

如果你是 Office 365 中的 Microsoft 团队管理员，则可以访问 Microsoft 团队管理中心中的系统范围设置。 这些设置可能会影响团队所有者在团队设置下看到的选项和默认设置。 例如，你可以为团队范围内的通知、讨论和资源启用默认频道 "常规"，这些通知将显示在所有团队中。

默认情况下，所有用户都有权在 Microsoft Teams 中创建团队（要对此进行修改，请参阅[在 Teams 中指定角色和权限](assign-roles-permissions.md)）。 现有 Office 365 组的用户还可以使用团队功能增强其权限。

与 Microsoft 团队接洽用户的一个重要计划活动是帮助人们思考和理解团队如何在日常生活中增强协作。 与其他人交谈，帮助他们选择当前以零碎方式进行协作的业务方案。 将它们放在一个频道中，并显示相关选项卡，帮助他们完成工作。 Teams 最强大的用例之一就是跨组织流程。 

<a name="example-teams"></a>示例团队
--------------

下面是一些功能示例，介绍不同类型的用户如何设置其团队、频道和应用（选项卡/连接器/bot）。 这可能有助于开始与你的用户社区进行有关 Microsoft 团队的对话。 当你考虑如何在你的组织中实现 Microsoft 团队时，请记住，你可以提供有关如何组织其团队的指导。但是，用户可以控制如何进行自我整理。 这些示例正是促使团队开始仔细思考各种可能性。

Microsoft 团队非常适用于细分组织小仓库和提升跨职能团队，因此鼓励用户考虑职能团队，而不是组织边界。

|团队类型  |可能的频道  |应用（选项卡 ![描述带有选项卡的文件夹的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/连接器 ![描述连接块的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/聊天机器人 ![描述小机器人机器人的图标](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
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

可以创建与组织结构一致的团队。 这最适用于希望推动士气的领导者、具有特定于团队的评论、澄清员工加入流程、讨论劳动力计划以及提高各种劳动力的知名度。  

![Microsoft 团队中组织的团队和频道的层次结构图表。](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>组织范围的团队

如果您的组织不超过5000个用户，则可以创建组织范围的团队。 组织范围的团队为组织中的每个人提供了一种自动方法，作为单个团队协作的一部分。 有关详细信息（包括创建和管理组织范围的团队的最佳做法），请参阅[在 Microsoft 团队中创建组织范围的团队](create-an-org-wide-team.md)。
