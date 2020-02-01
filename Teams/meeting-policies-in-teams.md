---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 了解如何在团队中管理会议策略设置。
ms.openlocfilehash: 9199be5eced7faee3e72f7b94c1f9e3be3c9573c
ms.sourcegitcommit: a47bd5194672820380d30722b60779ce2d8a8f78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "41649094"
---
# <a name="manage-meeting-policies-in-teams"></a>管理团队中的会议策略

::: zone target="docs"
会议策略用于控制会议参与者对由您的组织中的用户安排的会议参与者可用的功能。 创建策略并进行更改后，您可以将用户分配到该策略。 可在 Microsoft 团队管理中心或通过使用[PowerShell](teams-powershell-overview.md)管理会议策略。

你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。

|实现类型  |说明  |
|---------|---------|
|每个组织者    |实施按组织者策略时，所有会议参与者都将继承组织者的策略。 例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。          |
|每用户    |当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。 例如，"**允许在频道中立即开会**" 是每用户策略。     |
|每个组织者和每用户     |当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。 例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。 启用此设置可允许会议组织者和参与者开始和停止录制。

默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。 默认情况下，组织中的所有用户都分配有 "全局会议策略"。 你可以对其进行更改或创建一个或多个自定义策略，并向其分配用户。 除非你创建和分配自定义策略，否则用户将获取全局策略。 创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给将对其应用设置的一个或多个用户。

## <a name="change-or-create-a-meeting-policy"></a>更改或创建会议策略

若要更改或创建会议策略，请转到 Microsoft 团队**管理中心 >** > "会议**策略**"。 从列表中选择一个策略，或选择 "**添加**"。 如果要创建新策略，请添加名称和说明。 名称不能包含特殊字符，也不能超过64个字符。 选择您的设置，然后选择 "**保存**"。

例如，假设你有一组用户，并且想要限制其会议所需的带宽量。 您将创建一个名为 "有限带宽" 的新自定义策略，并禁用以下设置：

在 "**音频 & 视频**：
- 关闭 "允许云录制"。
- 关闭 "允许 IP 视频"。

在 "**内容共享**" 下：
- 禁用屏幕共享模式。
- 关闭 "允许白板"。
- 关闭 "允许共享笔记"。

然后向用户分配策略。

> [!NOTE]
> 一次只能向一个用户分配一个会议策略。

## <a name="assign-a-meeting-policy-to-users"></a>向用户分配会议策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。
2. 通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。
3. 在 "**会议策略**" 下，选择要分配的策略，然后单击 "**应用**"。

若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**会议** > **会议策略**"。
2. 通过单击策略名称的左侧，选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
5. 添加完用户后，选择 "**保存**"。

> [!NOTE]
> 如果向用户分配了该策略，则不能删除该策略。 必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。

## <a name="meeting-policy-settings"></a>会议策略设置

在 "**会议策略**" 页面上选择现有策略或选择 "**添加**" 以添加新策略时，可以为以下项配置设置。

- [常规](#meeting-policy-settings---general)
- [音频 & 视频](#meeting-policy-settings---audio--video)
- [内容共享](#meeting-policy-settings---content-sharing)
- [参与者 & 来宾](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>会议策略设置-常规

- [允许在频道中立即开会](#allow-meet-now-in-channels)
- [允许 Outlook 加载项](#allow-the-outlook-add-in)
- [允许频道会议安排](#allow-channel-meeting-scheduling)
- [允许安排私人会议](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>允许在频道中立即开会

这是每用户策略，在会议开始之前应用。 此设置控制用户是否可以在团队频道中启动临时会议。 如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下的 "**立即开会**" 以在频道中启动临时会议。

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>允许 Outlook 加载项

这是每用户策略，在会议开始之前应用。 此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。 例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。

### <a name="allow-channel-meeting-scheduling"></a>允许频道会议安排

这是每用户策略，在会议开始之前应用。 此设置控制用户是否可以在团队频道中安排会议。  如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>允许安排私人会议

这是每用户策略，在会议开始之前应用。 此设置控制用户是否可以在团队中安排私人会议。 当会议未发布到团队中的频道时，它是私有的。

请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>会议策略设置-音频 & 视频

- [允许脚本](#allow-transcription)
- [允许云录制](#allow-cloud-recording)
- [允许 IP 视频](#allow-ip-video)
- [媒体比特率（KBs）](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>允许脚本

这是每个组织单位和每用户策略的组合。 此设置控制播放会议录制期间是否提供字幕和脚本功能。 如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。 启动录制的人员需要启用此设置，以便录制还包括脚本。 

请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>允许云录制

这是每个组织单位和每用户策略的组合。 此设置控制是否可以录制此用户的会议。 录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。

组织外部的人员（如联盟用户和匿名用户）无法启动录制。 来宾用户无法启动或停止录制。 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

我们来看看下面的示例。

|用户 |会议策略  |允许云录制 |
|---------|---------|---------|
|Daniela | 全局   | False |
|Amanda | Location1MeetingPolicy | True|
|John （外部用户） | 不适用 | 不适用|

按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。 可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。

若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。

### <a name="allow-ip-video"></a>允许 IP 视频

这是每个组织单位和每用户策略的组合。 视频是会议的关键组件。 在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。 此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。 已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。 未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

我们来看看下面的示例。

|用户 |会议策略  |允许 IP 视频 |
|---------|---------|---------|
|Daniela   | 全局   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

通过 Daniela 托管的会议允许打开视频。 Daniela 可以加入会议并打开视频。 Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。 Amanda 可以查看会议中其他参与者共享的视频。

在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。 这意味着 Daniela 无法在 Amanda 的会议中打开视频。  

如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。  当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。 如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。 通话接通后，Daniela 可以根据需要打开或关闭她的视频。

### <a name="media-bit-rate-kbs"></a>媒体比特率（KBs）

这是每个用户的策略。 此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。 它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。 此设置使你能够更细致地控制组织中的带宽管理。 根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。 最小值为 30 Kbps，最大值取决于会议方案。 若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。

如果会议带宽不足，参与者会看到指示网络质量不佳的消息。

对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。 即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。 

## <a name="meeting-policy-settings---content-sharing"></a>会议策略设置-内容共享

- [屏幕共享模式](#screen-sharing-mode)
- [允许参与者授予或请求控制](#allow-a-participant-to-give-or-request-control)
- [允许外部参与者授予或请求控制](#allow-an-external-participant-to-give-or-request-control)
- [允许 PowerPoint 共享](#allow-powerpoint-sharing)
- [允许白板](#allow-whiteboard)
- [允许共享笔记](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>屏幕共享模式

这是每个组织单位和每用户策略的组合。 此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。 未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。

|设置值 |行为  |
|---------|---------|
|**整个屏幕**    | 会议中允许进行完整的桌面共享和应用程序共享 |
|**单应用程序**   | 允许在会议中共享应用程序        |
|**已禁用**     |会议中已关闭屏幕共享和应用程序共享。       |

我们来看看下面的示例。

|用户 |会议策略 |屏幕共享模式 |
|---------|---------|---------|
|Daniela  | 全局   | 整个屏幕 |
|Amanda   | Location1MeetingPolicy  | 已禁用 |

由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。 如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。 在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。 这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。  

当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。

### <a name="allow-a-participant-to-give-or-request-control"></a>允许参与者授予或请求控制

这是每个用户的策略。 此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。 若要赋予控制权，请将鼠标悬停在屏幕顶部。 

如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

我们来看看下面的示例。

|用户 |会议策略  |允许参与者授予或请求控制 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。

若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。

> [!NOTE]
> 若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。 如果任何一方在浏览器中运行 Teams，则不支持控制。 这是由我们计划修复的一个技术限制造成。 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允许外部参与者授予或请求控制

这是每个用户的策略。 此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。 团队会议中的外部参与者可以按如下方式进行分类：  

- 匿名用户
- 来宾用户  
- B2B 用户
- 联合用户  

联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。

若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。

### <a name="allow-powerpoint-sharing"></a>允许 PowerPoint 共享

这是每个用户的策略。 此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。 外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。

我们来看看下面的示例。

|用户 |会议策略  |允许 PowerPoint 共享 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。 Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。 Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。

### <a name="allow-whiteboard"></a>允许白板

这是每个用户的策略。 此设置控制用户是否可以在会议中共享白板。 外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。 

我们来看看下面的示例。

|用户 |会议策略  |允许白板|
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。 即使会议是按 Amanda 组织的，Daniela 也可以共享白板。  

### <a name="allow-shared-notes"></a>允许共享笔记

这是每个用户的策略。 此设置控制用户是否可以在会议中创建和共享笔记。 外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。 "**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。

我们来看看下面的示例。

|用户 |会议策略  |允许共享笔记 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。

## <a name="meeting-policy-settings---participants--guests"></a>会议策略设置-参与者 & 来宾

这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。

- [让匿名人员开始会议](#let-anonymous-people-start-a-meeting)
- [自动允许人员](#automatically-admit-people)
- [允许拨入用户绕过大厅](#allow-dial-in-users-to-bypass-the-lobby)
- [允许在私人会议中立即开会](#allow-meet-now-in-private-meetings)
- [启用实时字幕](#enable-live-captions)
- [允许在会议中聊天](#allow-chat-in-meetings)

> [!NOTE]
>用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。 如果你的组具有音频会议，并使用它进行连接，请参阅[Office 365 中的音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

### <a name="let-anonymous-people-start-a-meeting"></a>让匿名人员开始会议

这是每个组织者的策略。 此设置控制匿名人员（包括 B2B）和联盟用户是否可以在没有经过身份验证的组织中加入用户的会议。 

![显示一条消息给正在等待的用户的屏幕截图](media/meeting-policies-anonymous-user-lobby.png)

下面是在会议中提供了身份验证用户时匿名用户的加入行为。

|让匿名人员开始会议  |自动允许人员 |匿名人员的加入行为 |
|---------|---------|---------|
|True    | 人均      | 直接加入         |
|   | 您的组织中的每个人       | 在大厅中等待        |
|   | 组织和联盟组织中的每个人       | 在大厅中等待         |
|False    | 人均        | 直接加入        |
|   | 您的组织中的每个人     | 在大厅中等待        |
|   | 组织和联盟组织中的每个人      | 在大厅中等待         |

下面是当会议中没有经过身份验证的用户时匿名用户的加入行为。

|让匿名人员开始会议 |自动允许人员  |匿名人员的加入行为 |
|---------|---------|---------|
|True    | 人均      | 直接加入         |
|   | 您的组织中的每个人       | 在大厅中等待        |
|   | 组织和联盟组织中的每个人       | 在大厅中等待         |
|False    | 人均        | 在大厅中等待。 当第一个经过身份验证的用户加入会议时，将自动向用户提供许可。        |
|   | 您的组织中的每个人     |在大厅中等待         |
|   | 组织和联盟组织中的每个人      | 在大厅中等待         |

### <a name="automatically-admit-people"></a>自动允许人员

这是每个组织者的策略。 此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。 **（即将推出）**
  
|设置值  |联接行为 |
|---------|---------|
|**人均**   |所有会议参与者都直接加入会议，而无需在大厅中等待。 这包括经过身份验证的用户、联盟用户、来宾、匿名用户和通过电话拨入的用户。       |
|**组织和联盟组织中的每个人**     |组织内的经过身份验证的用户，包括来宾用户和联盟组织中的用户，直接加入会议，而无需在大厅中等待。  通过电话拨入的匿名用户和用户在大厅中等待。   |
|**您的组织中的每个人**    |来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。  联合用户、匿名用户和通过电话拨入的用户在大厅中等待。           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允许拨入用户绕过大厅

这是每个组织者的策略。 此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。

下面是通过电话拨入的用户的加入行为。

|允许拨入用户绕过大厅  |自动允许人员  |拨入的用户的加入行为 |
|---------|---------|---------|
|True    | 人均      | 直接加入         |
|   | 您的组织中的每个人       | 直接加入        |
|   | 组织和联盟组织中的每个人       | 直接加入         |
|False    | 人均        | 直接加入        |
|   | 您的组织中的每个人     |在大厅中等待         |
|   | 组织和联盟组织中的每个人      | 在大厅中等待         |

### <a name="allow-meet-now-in-private-meetings"></a>允许在私人会议中立即开会

这是每用户策略，在会议开始之前应用。 此设置控制用户是否可以启动 ad hoc 私人会议。 

### <a name="enable-live-captions"></a>启用实时字幕

这是每用户策略，在会议期间应用。 此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|设置值 |行为  |
|---------|---------|
|**已禁用，但组织者可以替代**     | 会议期间不会为用户自动打开实时字幕。 用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。 这是默认设置。 |
|**已禁用**     | 会议期间，用户已禁用实时字幕。 用户不能选择将其打开。          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>允许在会议中聊天

这是每个组织者的策略。 此设置控制是否允许在用户的会议中使用会议聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="related-topics"></a>相关主题

[团队中的消息传递策略](messaging-policies-in-teams.md)
