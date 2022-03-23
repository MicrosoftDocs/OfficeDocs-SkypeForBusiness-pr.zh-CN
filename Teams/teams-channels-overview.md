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
ms.localizationpriority: high
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
ms.openlocfilehash: 97af2abe8542a885f8a0056ed90f2a61330ba8a0
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711926"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Microsoft Teams 中的团队和频道概述

我们首先来了解 Microsoft Teams 如何允许单个团队进行自我组织并跨业务场景进行协作：

- **团队** 是与组织内不同项目和成果相关的人员、内容和工具的集合。

    - 可以创建私人团队，仅供受邀用户加入。
    - 也可以创建公共开放团队，组织中的任何人都可以加入（最多 10,000 个成员）。
    
    团队旨在将一组紧密协作的人员聚集在一起以完成工作。 对于基于项目的工作（例如，推出产品或创建数字化船室），团队可以是动态的，也可以是持续存在的，以反映组织的内部结构（例如部门和办公室位置）。 跨团队频道的对话、文件和笔记仅对团队成员可见。

- **频道** 是团队中的专用部分，用于保持按特定主题、项目、学科（适用于团队的一切类别）组织的对话。 你在频道（“文件”选项卡上）共享的文件将存储在 SharePoint 中。 若要了解详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)。

    - 频道是进行对话和实际完成工作的地方。 频道可以向所有团队成员（标准频道）、所选团队成员（[专用](private-channels.md)）或团队内外的选定人员（[共享频道](shared-channels.md)）开放。
    - 频道的重要价值体现在使用包括选项卡、连接器和机器人等应用扩展频道时，因为这些应用可以提高其对团队成员的价值。要了解详细信息，请参阅 [Teams 中的应用、机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。
    
有关使用团队和频道的帮助，请查看 [Teams 和频道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)。

有关与使用 Teams 相关的限制的信息，请参阅 [Microsoft Teams 的限制和规范](/microsoftteams/limits-specifications-teams)。

## <a name="membership-roles-and-settings"></a>成员资格、角色和设置

**团队成员资格**

在为整个组织激活 Teams 后，团队所有者可以邀请贵组织内与他们合作的任何人加入其团队。 Teams 使团队所有者能够根据用户姓名轻松添加组织成员。 根据组织的设置，可将组织外部的人员作为来宾或共享频道中的外部参与者添加到你的团队。 有关详细信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。 

团队所有者还可以基于现有 Microsoft 365 组创建团队。 对组成员资格所做的任何更改都将自动与 Teams 同步。

**团队角色**

Teams 中有两个主要角色： 

- **团队所有者** - 创建团队的人员。 团队所有者可以在邀请人员加入团队时或者在他们加入团队后将团队的任意成员设为共同所有者。 设置多个所有者可以分担管理设置和成员资格（包括邀请）的责任。
- **团队成员** - 由所有者邀请加入团队的人员。

此外，如果设置了审核，则团队所有者和成员可以拥有频道的审核员功能。 审核员可以在频道中发布新帖子，并控制团队成员能否回复现有频道消息。 团队所有者可以在频道内指派审核员。 （默认情况下，团队所有者具有审核员功能。）频道内的审核员可在该频道中添加或删除其他审核员。 有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

> [!NOTE]
> 当添加团队所有者时，他们也会被添加为成员，除非团队是在 Teams 管理中心创建的或者团队已添加到新的或现有 Microsoft 365 组。

**团队设置** 

团队所有者可以在 Teams 中直接管理团队范围的设置。设置包括以下功能：添加团队图片、设置团队成员创建标准、专用和共享频道、添加选项卡和连接器、@提及整个团队或频道，以及使用 GIF、贴纸和 Meme。

如果是 Microsoft 365 中的 Teams 管理员，则可以在 Teams 管理中心访问系统范围的设置。 这些设置可能会影响团队所有者在团队设置下看到的选项和默认设置。 例如，可以为团队范围的公告、讨论和资源启用默认频道“常规”，它将在所有团队中显示。

默认情况下，所有用户都有权创建团队。若要对此进行修改，请参阅[在 Teams 中分配角色和权限](assign-roles-permissions.md)。

吸引用户使用 Teams 的一项关键早期计划活动是帮助人们考虑和了解 Teams 如何在其日常生活中增强协作。 与其他用户交谈，帮助他们选择当前以分散方式协作的业务场景。 将他们带入具有可帮助他们完成工作的相关选项卡的频道。 Teams 最强大的用例之一是任何跨组织流程。

> [!NOTE]
> 在 Teams 中创建新团队或专用或共享频道时，将自动在 SharePoint 中创建团队网站。 要编辑此团队网站的网站说明或分类，请转到相应频道的“[在 Microsoft Teams 中设置](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d)”。
>
> 了解有关管理 [Microsoft Teams 连接的团队网站](/SharePoint/teams-connected-sites)的详细信息。

## <a name="channel-feature-comparison"></a>频道功能比较

下表显示了每个频道类型的 Teams 功能的比较。

|功能|标准频道|专用频道|共享频道|
|:-------|:---------------|:--------------|:-------------|
|无需将人员添加到团队，即可将人员添加到频道。|否|否|是|
|频道成员身份可以限制为团队的子集。|否|是|是|
|可以直接将频道与其他团队共享。|否|否|是|
|频道可以直接与其父团队共享。|不适用|否|是|
|来宾可以参与频道。|是|是|否|
|外部参与者（B2B 直接连接）可以参与频道。|否|否|是|
|每个频道都有一个专用的 SharePoint 网站。|否|是|是|
|计划内会议|是|否|是|
|Planner|是|否|否|
|机器人、连接器和消息传递扩展|是|否|否|
|在课堂团队中受支持|是|是|否|
|标记|是|否|否|
|分析|是|是|否|

## <a name="org-wide-teams"></a>组织范围的团队

如果组织的用户数不超过 10,000 个，则可以创建组织范围的团队。 组织范围的团队为组织中的每个人提供了自动加入单个协作团队的方法。 有关详细信息（包括创建和管理组织范围团队的最佳做法），请参阅[在 Microsoft Teams 中创建组织范围的团队](create-an-org-wide-team.md)。

## <a name="next-steps"></a>后续步骤

阅读 [Teams 中的聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)，查看对 Teams 推广至关重要的决策列表。
