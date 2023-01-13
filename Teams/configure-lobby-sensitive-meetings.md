---
title: 为敏感会议配置 Microsoft Teams 会议大厅
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 了解如何使用管理策略、敏感度标签和会议模板配置 Teams 会议大厅，以增强敏感会议的安全性。
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800149"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>为敏感会议配置 Microsoft Teams 会议大厅

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

会议大厅是一种工具，可用于确保不让不适当的人员参加会议。 通过在大厅中举行不同类型的参与者，会议组织者可以对他们进行审核，并确保他们适合参加会议。

默认情况下，组织中的人员和 [来宾](guest-access.md) 直接被允许参加会议，来自受信任域的参与者和匿名参与者必须在大厅中等待会议组织者允许。 会议组织者可以为他们创建的每个会议更改此默认设置。

Teams 管理员可以使用会议策略、会议模板和敏感度标签为不同用户和不同类型的会议自定义体验，从而控制大厅和其他相关设置。

下表列出了可用于帮助管理组织的大厅体验的功能以及配置位置。

|设置|管理员策略|敏感度标签|模板|会议组织者|
|:------|:----------:|:---------------:|:------:|:---------------:|
|拨入呼叫者加入或离开时报出|否|否|是|是|
|匿名用户和拨入呼叫者可以开始会议|是|否|否|否|
|匿名用户可以加入会议|是|否|否|否|
|人员拨入可以绕过大厅|是|是|是|是|
|谁可以绕过大厅|是|是|是|是|

有关如何使用模板和敏感度标签配置会议设置的信息，请参阅 [Microsoft Teams 中的自定义会议模板概述](custom-meeting-templates-overview.md) 和使用 [敏感度标签保护日历项目、Teams 会议和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)。

> [!Note]
> 敏感度标签和自定义会议模板中的会议设置需要Teams 高级版。

## <a name="lobby-settings-for-different-types-of-meetings"></a>不同类型的会议的大厅设置

以下设置适用于可以绕过大厅的人员：

- 所有人
- 我的组织中人员、受信任的组织和来宾
- 组织中用户和来宾
- 我的组织中的人员
- 受邀人员
- 组织者和共同组织者

虽然会议组织者通常选择要用于每个会议的设置，但你可以使用会议模板或敏感度标签强制实施特定设置。

如果组织要求组织外部人员不参加某些类型的会议，请考虑仅允许组织中的人员绕过大厅的会议模板。 这可确保被意外邀请或发送会议链接的组织外部人员无法直接加入会议。

如果你的组织有共享高度敏感信息的会议，并且你需要确保只有某些人参加，请考虑使用仅允许会议组织者绕过大厅的会议模板或敏感度标签。 这可确保组织者可以审查每个传入的参与者，以确保他们应参加会议。 这还会阻止会议开始，直到组织者加入。

对于一般敏感会议，请考虑使用“**已邀请人员**”选项。 这可确保没有会议邀请的人员 (包括转发邀请) 大厅。  (会议组织者还可以在创建会议时阻止转发。) 

有关同时使用会议模板和敏感度标签的信息，请参阅 [将 Teams 会议模板、敏感度标签和管理策略用于敏感会议](meeting-templates-sensitivity-labels-policies.md)。

### <a name="attendees-calling-in-by-phone"></a>与会者通过电话呼叫

默认情况下，通过电话拨入的与会者会通过大厅。 管理员可以更改此默认值，而 **拨入用户可以绕过大厅** 管理员会议策略。 如果要强制启用或关闭此设置，必须使用会议模板或敏感度标签。

如果希望允许呼叫者绕过大厅，会议组织者可以控制此设置，也可以通过会议模板或敏感度标签强制实施此设置。

#### <a name="join-and-leave-notifications"></a>加入和离开通知

会议组织者可以选择让与会者在加入或离开会议时通过电话通知他们。 如果要确保为某些类型的会议宣布电话与会者，可以使用会议模板强制实施此设置。

## <a name="meeting-with-anonymous-participants"></a>与匿名参与者的会议

除非允许所有人绕过大厅，否则匿名参与者必须通过大厅才能参加会议。 然后，会议组织者可以决定是否允许这些参与者参加。

如果你的组织根本不允许匿名参与者加入会议，则可以关闭 Teams 管理中心中的 **“匿名用户可以加入会议** ”设置。 有关详细信息，请参阅 [在 Microsoft Teams 中管理会议设置](/microsoftteams/meeting-settings-in-teams)。

如果你的组织中有某些组（例如市场营销组）需要组织与匿名参与者的会议，而其他人（如研究）则不需要，则可以使用 Teams 会议策略为不同的组配置匿名会议加入。  (需要启用“ **匿名用户可以加入会议** ”设置，才能正常工作。) 有关详细信息，请参阅 [会议策略设置 - 参与者&来宾](/microsoftteams/meeting-policies-participants-and-guests)。

## <a name="related-topics"></a>相关主题

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)

[在 Microsoft Teams 中管理外部会议和聊天](/microsoftteams/manage-external-access)
