---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 了解如何管理会议团队中的策略设置。
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036626"
---
# <a name="manage-meeting-policies-in-teams"></a>管理团队中的会议策略

::: zone target="docs"
会议策略用于控制对会议的组织中的用户安排的会议的参与者可用的功能。 在创建策略，并进行更改后，您可以然后用户分配策略。 管理会议策略中的 Microsoft 团队管理中心或使用[PowerShell](teams-powershell-overview.md)。

您可以按以下方式，这会影响会议开始之前用户的会议体验实施策略开始，在会议期间或之后会议。 

|实现类型  |说明  |
|---------|---------|
|每个组织者    |实现的每个组织者策略时，所有会议参与者都继承的组织者的策略。 例如，**自动允许人员加入**是每个组织者策略和控制用户加入会议直接还是在分配策略的用户安排的会议会议厅中等待的选择。          |
|每个用户    |实现的每用户策略时，仅将每用户策略应用于限制为组织者和/或会议参与者的某些功能。 例如，**允许立即开会**为每用户策略。     |
|每个组织者和每个用户     |当实现的每个组织者和每用户策略的组合时，则某些功能将限制会议参与者基于其策略和组织者的策略。 例如，**允许云录制**是每个组织者和每用户策略。 启用此设置，以允许会议组织者和参与者启动和停止录制。 

默认情况下，创建名为全局 （组织范围内默认值） 的策略。 默认情况下，您的组织中的所有用户将都分配此会议策略。 可以更改此策略，或创建一个或多个自定义策略并向其分配用户。 创建自定义策略时，可以允许或防止某些功能提供给用户，然后将其分配给一个或多个用户拥有应用于它们的设置。 

## <a name="change-or-create-a-meeting-policy"></a>更改或创建的会议策略

若要更改或创建的会议策略，请转到 Microsoft 团队管理中心 >**会议** > **会议策略**。 从列表中选择一个策略，或选择**新策略**。 如果您正在创建新策略，将添加的名称和说明。 名称不能包含特殊字符也能超过 64 个字符。 选择您的设置，然后选择**保存**。

例如，假设您有大量的用户，并且想要限制其会议将需要的带宽量。 您可以创建名为"带宽有限"的新自定义策略，并禁用以下设置：

在**音频 & 视频**: 下
- 关闭云录制
- 关闭允许 IP 视频

在**内容共享**: 下
- 禁用屏幕共享模式
- 关闭白板
- 关闭共享便笺

然后将策略分配给用户。

> [!NOTE] 
> 用户可以一次只能有一个会议策略分配。 

## <a name="assign-a-meeting-policy-to-users"></a>向用户分配的会议策略

如果要将策略应用于一个用户，在左侧的导航窗格中，选择**用户**，然后单击用户的显示名称。 选择用户的页上，单击**分配策略**，旁边的**编辑**。 然后，在**编辑用户策略**窗格中的**会议策略**，下，从下拉列表中，选择会议策略，然后选择**保存**。 您可以从用户的列表来分配策略。 若要执行此操作，请通过单击左侧的用户的显示名称选择用户。 选择**编辑设置**。 然后，**编辑设置**窗格中的**会议策略**，下，从下拉列表中，选择的策略，然后选择**保存**。 
 
如果要将策略应用于多个用户，在左侧的导航窗格中，选择**用户**，然后通过单击左侧的用户名称，选择每个用户，然后单击**编辑设置**。 在**编辑设置**窗格中，**会议策略**，下从下拉列表中，选择策略，然后选择**保存**。
 
按如下方式向一个或多个用户还可以分配的会议策略：

1. 转到**Microsoft 团队管理中心** > **会议** > **会议策略**。
2. 通过单击左侧的策略名称选择的策略。
3. 选择**管理用户**。
4. 在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。 要添加的每个用户重复此步骤。
5. 完成添加用户时，选择**保存**。
 
> [!NOTE] 
> 不能删除策略，如果用户已分配给它。 您必须首先将不同的策略分配给所有受影响的用户，然后可以删除原始的策略。
 
## <a name="meeting-policy-settings"></a>会议策略设置

当您选择**会议策略**页上的现有策略，或选择要添加新的策略的**新策略**时，您可以配置以下设置。

- [常规](#meeting-policy-settings---general)
- [音频 & 视频](#meeting-policy-settings---audio--video)
- [内容共享](#meeting-policy-settings---content-sharing)
- [参与者 & 来宾](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>会议策略设置-常规

- [在通道允许立即开会](#allow-meet-now-in-channels)
- [允许专用立即开会 （即将推出）](#allow-private-meet-now-coming-soon)
- [允许 Outlook 外接程序](#allow-the-outlook-add-in)
- [允许通道会议日程安排](#allow-channel-meeting-scheduling)
- [允许安排专用会议](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>在通道允许立即开会

这是一个每用户策略，并将应用会议之前启动。 此设置控制用户是否可以在工作组通道中启动临时会议。 如果您关闭此上，当用户在工作组频道发布一条消息，用户可以单击**立即开会**下方撰写框以在该频道中启动临时会议。

![会议策略开会会议 now.png](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>允许专用立即开会 （即将推出）

这是一个每用户策略，并将应用会议之前启动。 此设置控制用户是否可以开始临时专用会议。  

### <a name="allow-the-outlook-add-in"></a>允许 Outlook 外接程序

这是一个每用户策略，并将应用会议之前启动。 此设置控制是否可以在 Outlook （Windows、 Mac、 web 和移动） 从计划团队会议。

![会议的策略-outlook-添加-in.png](media/meeting-policies-outlook-add-in.png)

如果您关闭此操作，用户将无法在 Outlook 中创建新的会议时安排团队会议。 例如，在 Windows 上的 Outlook 中，**新团队会议**选项不会显示在功能区中。

### <a name="allow-channel-meeting-scheduling"></a>允许通道会议日程安排

这是一个每用户策略，并将应用会议之前启动。 此设置控制用户是否可以安排会议中的团队通道。  如果您关闭此操作，**计划会议**选项将不可用向用户，当他们团队通道中启动会议并他们安排会议在工作组中从会议时，**选择要满足通道**选项不会对用户可用。

![会议的策略-计划-a-meeting.png](media/meeting-policies-schedule-a-meeting.png)

![meeting-policies-select-a-channel-to-meet-in.png](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>允许安排专用会议

这是一个每用户策略，并将应用会议之前启动。 此设置控制用户是否可以安排团队中的专用会议。 不将其发布到团队中的通道时，会议是专用。

请注意，如果您关闭**允许安排专用会议**和**允许通道会议日程安排****计划会议**选项将不可用，用户将无法在工作组中安排会议。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>会议策略设置-音频 & 视频

- [允许转录](#allow-transcription)
- [允许云录制](#allow-cloud-recording)
- [允许 IP 视频](#allow-ip-video)
- [媒体比特率 (Kb)](#media-bit-rate-kbs)
- [启用 live 标题 （即将推出）](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>允许转录

这是每个组织者和每用户策略的组合。 此设置控制标题和转录功能是否可用播放会议录制过程。 如果您关闭此操作，**搜索**和**抄送**选项将不可用播放会议录制过程。 启动录制的人员需要该设置，以便录制还包括转录开启。 

请注意，录制的会议的转录目前仅支持用户拥有语言中设置为英语的团队和时将英语朗读会议中。

![会议的策略-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>允许云录制

这是每个组织者和每用户策略的组合。 此设置控制是否可以记录此用户的会议。 录制可以启动由会议组织者或另一个会议参与者如果参与者为打开的策略设置，并且它们从同一组织身份验证的用户。

联盟和匿名用户，如组织外部的人员无法开始录制。 来宾用户无法启动或停止录制。 

![会议的策略-recording.png](media/meeting-policies-recording.png)

让我们看一下下面的示例。

|用户 |会议策略  |允许云录制 |
|---------|---------|---------|
|Daniela | 全局   | False |
|Amanda | Location1MeetingPolicy | True|
|John （外部用户） | 不适用 | 不适用|

无法录制 Daniela 由组织的会议并 Amanda，拥有启用此策略设置，无法记录由 Daniela 组织的会议。 可以记录由 Amanda 组织的会议，但是，Daniela，拥有禁用此策略设置和 John 属于外部用户，无法记录由 Amanda 组织的会议。

若要详细了解云会议录制，请参阅[团队云会议录制](cloud-recording.md)。

### <a name="allow-ip-video"></a>允许 IP 视频

这是每个组织者和每用户策略的组合。 视频会议的关键组件。 在某些组织中，管理员可能需要更多控制哪些用户的会议有视频。 此设置控制是否视频可以打开和 1:1 中由用户托管的会议呼叫和由用户启动的组呼叫。 已启用，此策略的用户组织的会议允许会议参与者，在会议中的视频共享如果会议参与者还可以启用的策略。 会议参与者未分配的任何策略 （例如，匿名和联盟参与者） 继承的会议组织者的策略。

![会议的策略-音频-视频-settings.png](media/meeting-policies-audio-video-settings.png)

让我们看一下下面的示例。

|用户 |会议策略  |允许 IP 视频 |
|---------|---------|---------|
|Daniela   | 全局   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

允许视频以打开由 Daniela 承载的会议。 Daniela 可以加入会议，然后打开视频。 Amanda 无法打开在 Daniela 的会议，因为 Amanda 的策略设置为不允许视频会议的视频。 Amanda 可以看到视频会议中的其他参与者共享。

由 Amanda 承载的会议，没有人可以打开视频，无论视频的策略分配给它们。 这意味着 Daniela 无法打开在 Amanda 的会议中的视频。  

如果 Daniela 上使用视频呼叫 Amanda，Amanda 可以应答呼叫以纯音频形式。  当连接呼叫时，Amanda 可以看到 Daniela 的视频，但无法打开视频。 如果 Amanda 调用 Daniela，Daniela 可以应答的呼叫的视频和音频。 当连接呼叫时，Daniela 可以打开或关闭其视频中，根据需要。

### <a name="media-bit-rate-kbs"></a>媒体比特率 (Kb)

这是每个管理器策略。 此设置确定音频、 视频和视频基于应用程序共享呼叫和用户的会议中传输媒体比特率。 其应用于的上行和下行媒体可以遍历呼叫或会议中的用户。 此设置为您提供了管理组织中的带宽精细的控制。 根据所需的用户的会议方案，建议您拥有足够带宽就地良好质量体验。 最小值是 30 Kbps，最大值取决于会议方案。 若要了解有关推荐带宽良好质量会议、 通话和团队中的实时事件的最小的详细信息，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。

如果没有足够带宽，会议，参与者将看到一条消息，指示网络质量不佳。

对于需要最高质量视频体验的会议，如 CEO 板会议和团队 live 事件，我们建议您将带宽设置为 10 Mbps。 设置的最大的体验，即使团队媒体堆栈会适应低带宽的条件时检测到某些网络条件，具体取决于该方案。 

### <a name="enable-live-captions-coming-soon"></a>启用 live 标题 （即将推出）

这是一个每用户策略，并在会议期间适用。 如果在此设置，用户会看到一个选项，在会议期间显示标题。

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>会议策略设置的内容共享

- [屏幕共享模式](#screen-sharing-mode)
- [允许参与者授予或请求控制权](#allow-a-participant-to-give-or-request-control)
- [允许外部参与者授予或请求控制权](#allow-an-external-participant-to-give-or-request-control)
- [允许 PowerPoint 共享](#allow-powerpoint-sharing)
- [允许白板](#allow-whiteboard)
- [允许共享的便笺](#allow-shared-notes)
- [（即将推出） 的会议中允许聊天](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>屏幕共享模式

这是每个组织者和每用户策略的组合。 此设置控制是否桌面和/或窗口共享用户的会议中允许。 会议参与者未分配的任何策略 （的示例中，匿名、 来宾、 B2B 和联盟的参与者） 继承的会议组织者的策略。

|设置值 |行为  |
|---------|---------|
|**整个屏幕**    | 在会议中允许的完整桌面共享和应用程序共享 |
|**单个应用程序**   | 在会议中允许，应用程序共享        |
|**已禁用**     |屏幕共享和应用程序共享关闭会议中。       |

让我们看一下下面的示例。

|用户 |会议策略 |屏幕共享模式 |
|---------|---------|---------|
|Daniela  | 全局   | 整个屏幕 |
|Amanda   | Location1MeetingPolicy  | 已禁用 |

由 Daniela 承载的会议允许会议参与者共享其整个屏幕或特定应用程序。 如果 Amanda 加入 Daniela 的会议，Amanda 也不能共享其屏幕或特定应用程序，这是因为其策略设置已禁用。 由 Amanda 承载的会议中, 不允许任何人共享其屏幕或单个应用程序，无论屏幕共享模式策略分配给它们。 这意味着 Daniela 不能共享其屏幕或 Amanda 的会议中的单个应用程序。  

目前，用户无法播放视频或共享其屏幕团队会议中的，如果他们正在使用 Google Chrome。

### <a name="allow-a-participant-to-give-or-request-control"></a>允许参与者授予或请求控制权

这是一个每用户策略。 此设置控制用户是否可以共享的桌面或窗口的控制权移交给其他与会者。 要授予控制权，悬停在屏幕顶部。 

如果启用此设置是用户，**授予控制权**选项顶栏中显示在共享会话中。 

![会议策略授予 control.png](media/meeting-policies-give-control.png)

如果设置为用户已关闭，**授予控制权**选项不可用。

![meeting-policies-give-control-not-available.png](media/meeting-policies-give-control-not-available.png)

让我们看一下下面的示例。

|用户 |会议策略  |允许参与者授予或请求控制权 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela 可以共享的桌面或窗口的控制权移交给其他中按 Babek 而 Babek 无法向其他参与者授予控制权的参与者。

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允许外部参与者授予或请求控制权

这是一个每用户策略。 此设置控制是否在会议中的外部参与者可以与其共享的桌面或窗口的控制权移交给其他参与者在会议中。 团队会议中的外部参与者可进行分类，如下所示：  

   - 匿名用户
   - 来宾用户  
   - B2B 用户
   - 联盟的用户  

由组织中的**允许外部参与者授予或请求控制**设置控制是否联盟的用户可以控制权移交给外部用户共享时。

### <a name="allow-powerpoint-sharing"></a>允许 PowerPoint 共享

这是一个每用户策略。 此设置控制用户是否可以共享在会议中的 PowerPoint 幻灯片背面图案。 外部用户，其中包括匿名、 来宾，和联盟用户继承的会议组织者的策略。

让我们看一下下面的示例。

|用户 |会议策略  |允许 PowerPoint 共享 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda 无法共享在会议中的 PowerPoint 幻灯片背面图案，即使她是会议组织者。 即使会议按 Amanda，Daniela 可以共享 PowerPoint 幻灯片背面图案。 Amanda 可以查看在会议中，由其他人共享 PowerPoint 幻灯片背面图案，即使她不能共享 PowerPoint 幻灯片背面图案。

### <a name="allow-whiteboard"></a>允许白板

这是一个每用户策略。 此设置控制用户是否可以共享在会议中的白板。 外部用户，其中包括匿名、 B2B 和联盟的用户，继承的会议组织者的策略。 

让我们看一下下面的示例。

|用户 |会议策略  |允许白板|
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

即使她是会议组织者，Amanda 无法共享在会议中的白板。 即使 Amanda 由组织会议时，Daniela 可以共享在白板。  

### <a name="allow-shared-notes"></a>允许共享的便笺

这是一个每用户策略。 此设置控制用户是否可以创建和共享在会议中的注释。 外部用户，其中包括匿名、 B2B 和联盟的用户，继承的会议组织者的策略。 **会议笔记**选项卡目前少于 20 个参与者仅中支持的会议。 

让我们看一下下面的示例。

|用户 |会议策略  |允许共享的便笺 |
|---------|---------|---------|
|Daniela   | 全局   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela 可以 Amanda 的会议中添加注释和 Amanda 不能在任何会议中添加注释。

### <a name="allow-chat-in-meetings-coming-soon"></a>（即将推出） 的会议中允许聊天

这是每个管理器策略。 此设置控制是否在用户的会议中允许 meeting 聊天。 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>会议策略设置-参与者 & 来宾

他们允许会议中的会议参与者等待之前加入会议并参与的级别对会议厅中这些设置控制。

- [自动允许人员加入](#automatically-admit-people)
- [允许匿名用户开始会议](#allow-anonymous-people-to-start-a-meeting)
- [允许电话拨入式用户绕过大厅](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [允许组织者覆盖会议厅设置](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a>自动允许人员加入

这是每个管理器策略。 此设置控制是否人员加入会议直接或通过身份验证的用户获准加入会议之前，在会议厅等待。

![会议的策略-lobby.png](media/meeting-policies-lobby.png)

 会议组织者可以单击更改此设置为他们安排每个会议的会议邀请中**会议选项**。 **（即将推出）**
  
|设置值  |加入行为 |
|---------|---------|
|**所有人**   |所有会议参与者都加入会议直接而不需要在会议厅等待。 这包括经过身份验证的用户、 联盟的用户、 来宾、 匿名用户和通过电话拨入的人员。       |
|**您的组织和联盟的组织中的所有人**     |组织，包括来宾用户和联盟组织内的经过身份验证的用户加入会议直接而不需要在会议厅等待。  匿名用户和通过电话拨入用户在会议厅等待。   |
|**您的组织中的所有人**    |从内组织，包括来宾用户的经过身份验证的用户加入会议直接而不需要在会议厅等待。  联盟的用户和匿名用户通过电话拨入的用户在会议厅等待。           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>允许匿名用户开始会议

这是每个管理器策略。 此设置控制匿名的人员，包括 B2B 和联盟的用户是否可以参加加入经过身份验证的用户从组织的情况下的用户的会议。 

![会议的策略-匿名-用户-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

在会议中存在经过身份验证的用户时，下面是人员的匿名加入行为。

|允许匿名用户开始会议  |自动允许人员加入 |加入匿名用户的行为 |
|---------|---------|---------|
|True    | 所有人      | 直接加入         |
|   | 您的组织中的所有人       | 在会议厅中等待        |
|   | 您的组织和联盟的组织中的所有人       | 在会议厅中等待         |
|False    | 所有人        | 直接加入        |
|   | 您的组织中的所有人     | 在会议厅中等待        |
|   | 您的组织和联盟的组织中的所有人      | 在会议厅中等待         |

存在于会议中没有经过身份验证的用户时，下面是人员的匿名加入行为。

|允许匿名用户开始会议 |自动允许人员加入  |加入匿名用户的行为 |
|---------|---------|---------|
|True    | 所有人      | 直接加入         |
|   | 您的组织中的所有人       | 在会议厅中等待        |
|   | 您的组织和联盟的组织中的所有人       | 在会议厅中等待         |
|False    | 所有人        | 在会议厅中等待。 第一个经过身份验证的用户加入会议时，用户自动获准加入会议。        |
|   | 您的组织中的所有人     |在会议厅中等待         |
|   | 您的组织和联盟的组织中的所有人      | 在会议厅中等待         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>允许电话拨入式用户绕过大厅 （即将推出）

这是每个管理器策略。 此设置控制是否通过电话拨入的人员加入会议直接或**自动允许人员加入**设置无论会议厅中等待。

下面是人员的通过电话拨入加入行为。

|允许电话拨入式用户绕过大厅  |自动允许的用户  |加入的拨入的人员的行为 |
|---------|---------|---------|
|True    | 所有人      | 直接加入         |
|   | 您的组织中的所有人       | 直接加入        |
|   | 您的组织和联盟的组织中的所有人       | 直接加入         |
|False    | 所有人        | 直接加入        |
|   | 您的组织中的所有人     |在会议厅中等待         |
|   | 您的组织和联盟的组织中的所有人      | 在会议厅中等待         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>允许组织者覆盖会议厅设置 （即将推出）

这是每个管理器策略。 此设置控制会议组织者可以重写他们安排新的会议时，**自动允许人员加入**和**允许电话拨入式用户绕过大厅**中设置管理会议厅设置。 

会议组织者可以单击更改会议厅设置为他们安排每个会议的会议邀请中**会议选项**。 

下面是此设置如何影响是否会议组织者可以更改**自动允许人员加入**设置每个会议组织者计划。

|允许组织者覆盖会议厅设置  |自动允许人员加入  |行为 |
|---------|---------|---------|
|True    | 所有人      | 组织者可以将设置更改任何其他值。 |
|   | 您的组织中的所有人       | 组织者可以将设置更改任何其他值。|
|   | 您的组织和联盟的组织中的所有人       | 组织者可以更改此为其他任何值。         |
|False    | 所有人        | 组织者可以将设置更改任何其他值。|
|   | 您的组织中的所有人     |组织者可以设置更改为**您的组织中的每个人**。 |
|   | 您的组织和联盟的组织中的所有人      | 组织者无法覆盖会议厅设置。 |

下面是此设置如何影响是否会议组织者可以更改的每个会议组织者计划**允许将绕过大厅电话拨入式用户**设置。
    
|允许组织者覆盖会议厅设置  |允许电话拨入式用户绕过大厅  |行为 |
|---------|---------|---------|
|True    |  True        | 组织者可以更改该设置为 False。       |
|True      | False         | 组织者可以更改该设置为 True。        |
|False     | True        |组织者可以更改该设置为 False。         |
|False      |False          |组织者不能覆盖会议厅设置，并不能允许电话拨入式用户绕过大厅会议中。        |

[完整的文章](meeting-policies-in-teams.md)

## <a name="related-topics"></a>相关主题
[团队中的邮件策略](messaging-policies-in-teams.md)
