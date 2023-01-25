---
title: " (IT 管理员) 管理对 Teams 会议的匿名参与者访问权限"
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 对于 IT 专业人员 - 了解匿名会议参与在 Microsoft Teams 中的工作原理。
ms.openlocfilehash: a4f1833059febf2f8481cba9f1b3716519613e89
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983730"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a> (IT 管理员) 管理对 Teams 会议的匿名参与者访问权限

组织托管的会议中的匿名参与者是身份无法验证的参与者。 这可能包括：

- 未使用工作或学校帐户登录 Teams 的人员 
-  ([外部访问](manage-external-access.md)) 中配置的不受信任的组织以及信任但不信任组织的组织人员。

匿名会议加入由组织级别设置和用户级别策略控制。 若要使匿名会议加入正常工作：
- **匿名用户可以加入会议** Teams 会议设置 (组织级别) 必须启用。
- 必须为会议组织者分配一个 Teams 会议策略，其中“ **允许匿名人员加入会议** ”控件已打开。

默认情况下，组织和默认全局会议策略中将启用匿名会议加入。 我们建议保持组织级别设置，并使用会议策略为不同的用户打开或关闭匿名会议加入， (会议组织者) 。

请注意，如果启用了匿名会议加入，大厅策略会影响匿名参与者加入会议的方式。 有关详细信息，请参阅 [控制谁可以绕过 Microsoft Teams 中的会议大厅](who-can-bypass-meeting-lobby.md)。

#### <a name="meetings-with-trusted-organizations"></a>与受信任组织的会议

为外部会议和聊天设置受信任的组织时，如果两个组织未正确配置外部访问设置，则来自这些组织的与会者可能会被视为匿名。 有关详细信息，请参阅 [外部会议和聊天的受信任组织](manage-external-access.md)。

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>管理组织的匿名会议加入

必须启用组织级别的匿名会议加入设置，组织中的任何人才能创建允许匿名参与者的会议。

> [!Important]
> **匿名参与者可以加入会议** 组织范围的设置将在将来删除。 建议将此设置保留为 **“打开** ”，并使用 **“允许匿名人员加入会议** ”用户级会议策略控制来允许或阻止匿名会议加入。

为组织配置匿名会议加入
1. 转到 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)。

1. 在左侧导航中，转到“**会议**” > “**会议设置**”。

1. 在 **“参与者”** 下，将 **“匿名参与者可以加入会议** ”设置为 **“开** (推荐) ”或 **“关闭**”。

    ![管理中心内会议的参与者设置的屏幕截图。](media/meeting-settings-participants.png "Microsoft Teams 管理中心 Teams 会议的参与者设置的屏幕截图")

1. 选择“**保存**”。

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>管理哪些会议组织者可以允许匿名加入会议

可以控制哪些用户或组可以主持包含匿名参与者的会议。 为此，请将启用匿名会议加入的会议策略分配给需要与匿名参与者主持会议的每个会议组织者。

为特定会议组织者配置匿名会议加入
1. 转到 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)。

1. 在左侧导航中，转到 **“会议**”“ > **会议策略**”。

1. 选择要修改的策略。

1. 将 **“允许匿名人员加入会议”** 设置为 **“打开**”。

1. 选择“**保存**”。

对会议策略的更改最多可能需要 24 小时才能生效。

## <a name="configure-anonymous-meeting-join-using-powershell"></a>使用 PowerShell 配置匿名会议加入

可以使用以下方法控制匿名参与者是否可以加入会议：

- `-DisableAnonymousJoin` [Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration) 中用于配置组织级别设置的参数。  (建议将此设置保留为 False，并使用 Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting 在用户或组级别控制匿名会议加入。) 
- `-AllowAnonymousUsersToJoinMeeting` [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 中的参数，用于配置用户级别会议策略

若要允许匿名参与者加入会议，必须通过设置以下值将这两者都配置为允许匿名加入会议：

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin` 设置为 **$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting`设置为相关会议组织者的 **$true**

## <a name="block-anonymous-meeting-join-for-specific-client-types"></a>阻止特定客户端类型的匿名会议加入

允许匿名参与者加入会议时，他们可以使用 Teams 客户端或使用[Azure 通信服务](/azure/communication-services/)生成的自定义客户端。 

管理员可以使用 `-BlockedAnonymousJoinClientTypes` [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes) 中的 参数来阻止这些客户端类型之一。

## <a name="anonymous-participants-meeting-experience"></a>匿名参与者的会议体验

匿名参与者的功能与其他会议参与者不同。 例如，匿名参与者：

- 在会议前后无法访问会议聊天
- 无法访问 Microsoft 365 中的个人资料卡 (个人资料卡 - Microsoft 支持部门) 

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>匿名参与者如何与会议中的应用交互

默认情况下，启用允许匿名参与者在会议中与应用交互的设置。

配置匿名会议参与者的应用访问权限

1. 转到 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)。

1. 在左侧导航中，转到“**会议**” > “**会议设置**”。

1. 在 **“参与者”** 下，将  **“匿名参与者可以与会议中的应用交互”** 设置为 **“打开** ”或 **“关闭**”。

还可以使用 PowerShell 对此进行 `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`控制。

匿名参与者继承全局 (组织范围的默认) Teams 应用权限策略。 只要该策略中启用了应用，匿名参与者可以在 Teams 会议中与 **应用交互，并且匿名参与者可以在会议中的应用处于****打开状态**。

请注意，匿名参与者只能与会议中已有的应用交互，不能获取和/或管理这些应用。

## <a name="related-topics"></a>相关主题

[在没有 Teams 帐户的情况下加入会议](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[使用 Microsoft Teams 管理中心配置组织范围的策略](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部参与者会收到“登录到 Teams 以加入或联系会议组织者”](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[在 Teams 中分配策略 - 入门](policy-assignment-overview.md)