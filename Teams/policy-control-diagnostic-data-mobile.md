---
title: Microsoft Teams 所需的移动设备诊断数据
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 策略控制的移动设备属性和事件列表。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91203a9e35954e695bea5482c41674137320b487
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674234"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 所需的移动设备诊断数据

以下文章包含 Microsoft Teams 移动设备事件的列表，以及各个事件收集的属性列表。

要详细了解诊断数据，包括如何控制发送到 Microsoft 的诊断数据，请参阅 [从 Teams 应用发送到 Microsoft 的诊断数据](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft)。 要查看要发送到 Microsoft 的诊断数据，可使用 [诊断数据查看器](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)。

## <a name="events"></a>事件

> [!NOTE]
> 下面列出了所有事件的通用属性，若要评论它们，请参阅[与所有事件一起发送的属性](#properties-sent-with-all-events)。

### <a name="panelaction"></a>面板视图

> [!NOTE]
> 关于PanelAction 事件属性的详细信息，请参阅[与面板操作事件一起发送的属性](#properties-sent-with-panelaction-events)。

- **acceptUser** - 用户已接受 1：1 聊天。
- **accessibilityUserConfiguration** - 当用户切换辅助功能时。
- **acknowledgeSettingChange** - 在“我们已更新通知设置”对话框中确认更新。 这是一个用于确认更新通知和确定整体通知可靠性的功能成功指标。
- **actionComposeMenu**
  - 创建邮件扩展使用情况。
  - 行动消息扩展使用情况。
- **active_session_banner_dismissed** - 已取消位置共享可用提醒横幅。
- **activityChatClicked** - 在“**活动**”选项卡中选择非实时聊天或显示拆分视图时触发。
- **activityContextMenu** - 活动源中的溢出操作。
- **activityFeedClick** - 点击了活动源项，并导航到了机器人聊天。
- **activityFeedLongPress** - 捕获订阅源项目上的长按手势。
- **activityFeedSwipe** - 捕获订阅源项目上的轻扫手势。
- **activityFilterClick** - 捕获活动筛选器使用情况。
- **activityFilterOptionsClick** - 捕获活动筛选器使用情况。
- **activityFilterOptionsClicked** - 捕获活动筛选器使用情况。
- **activityLiveChatClicked** - 从“**活动**”选项卡上的实时会议中选择聊天时触发。
- **activityLiveDetailsClicked** - 当从“**活动**”选项卡上的实时会议中选择“**详细信息**”时触发。
- **activityTabClicked** - 有助于确定：
  - 显示“**活动**”选项卡。
  - Teams 捕获“**活动**”选项卡事件。
- **activityTypeDropdown** - 捕获活动筛选器使用情况，以在“**我的活动**”和“**源**”之间切换。
- **addChannel** - 添加频道。此项目提供有关成功创建频道的数据。
- **addMember**- 已在“**更多**”菜单中选中并触发了“**邀请他人**”按钮。
- **addMembers** - 将成员添加到团队或专用频道。
- **addToCalendar** - 为“专用日历”中缺少的日历事件选择“**添加到日历**”按钮。
- **addToList** - 已将联系人添加到联系人列表。
- **addToMeeting** - 在会议的参与者列表中，选择“**添加到会议**”按钮（适用于聊天的参与者）。
- **addUserAsContact** - 可通过从联系人的个人资料卡片中选择“**添加联系人**”图标来添加联系人。
- **admitAll** - 从“大厅”一节选择“**全部允许**”按钮的次数。
- **admitParticipant** - 从会议名单中允许某人参加会议的次数。
- **alertsNavAlert** - 点击源项目。
- **aliasDiscoverabilitySettingOpened** - discoverabaility 设置的入口点。
- **android: null** - 聊天机器人静音或取消静音。 这正增强只添加应用程序信息聊天的现有遥测。
- **anonymousMeetingJoin** - 在匿名加入提供名称页上选择“**加入会议**”或在“名称”对话框中单击“**确定**”。
- **anonymousMeetingJoinWelcome** - 在匿名加入会议登陆页面上选择“**作为来宾加入**”。
- **anonymousMeetingPostMeetingChat** - “呼叫结束屏幕”上用户查看聊天的数量。
- **anonymousMeetingPostMeetingRejoin** - 匿名用户尝试重新加入会议的次数。
- **anonymousMeetingSignIn** - 用户从名称输入屏幕导航到登录的次数。
- **anonymousMeetingSignInWelcome** - 在匿名加入会议登录页上选择 **登录和加入**。
- **anonymousMeetingToggleMuted** - 选择“静音”切换按钮的次数。
- **anonymousMeetingToggleVideo** - 选择“视频”切换按钮的次数。
- **appKilled** - 已终止应用程序。
- **approveTimeOffRequest** - 当一线员工 (FLW) 经理批准一线员工休假请求时。
- **assigneeChange** - 在将新的代理人添加到任务项目时触发。
- **assignmentPickerClicked** - 已选中“**分配给**”按钮，打开“代理人选取器”页面。
- **assignmentRemoved** - 当通过选择 “**x**” 从任务项中移除代理人（这是删除代理人的唯一方法）时触发。
- **attachmentAdded** - 确认已成功添加任务中的附件。
- **attachmentDeleted** - 确认已成功删除任务中的附件。
- **attachmentUpdated** - 确认已成功更新任务中的附件。
- **audioOnlyLowBatteryBanner** - 由于电池电量不足，选择了“**仅音频**”选项。
- **audioOnlyPoorNetworkBanner** - 由于连接横幅不良，选择了“**关闭视频**”选项。
- **audioUserDoubleTap** - 双击音频参与者。
- **autoReconnectCallmebackCallDrop** - 在呼叫结束屏幕上选择 **Callmeback** 按钮的次数。
- **autoReconnectDialIn**
  - 在重新连接 UFD 上选择“**拨入**”按钮。
  - 重新连接时选择“**拨入**”按钮的次数。
- **autoReconnectDialInonCallDrop** - “**拨入**”按钮在已断开连接的 UFD 上被选中。
- **autoReconnectDialOut** - 在重新连接的 UFD 上选择 **给我回电** 按钮。
- **autoReconnectRejoinonCallDrop** - 在呼叫结束屏幕上选择“**重新加入**”或“**重拨**”按钮的次数。
- **backFromCallMePSTN** - 给我回电 PSTN 号码流程未完成。
- **backToPhotoShare** - 返回到相机。
- **backToStageFromWhiteboard** - 从白板中返回到通话屏幕。
- **backToWhiteboardFromStage** -从通话屏幕进入白板。
- **blockAnonymous** - 时间：
  - 启用通话设置以从设置中阻止没有来电显示的呼叫。
  - 禁用通话设置以从设置中阻止没有来电显示的呼叫。
  - 启用通话设置以从操作表中阻止没有来电显示的呼叫。
  - 禁用通话设置以从操作工作表中阻止没有来电显示的呼叫。
- **blockCaller** - 阻止：
  - 新 iOS 呼叫操作表中的号码和联系人。
  - 联系人卡片中的联系人和号码。
  - 设置中的数字。
- **blockChat** - 阻止机器人聊天。 这增强了现有聊天的遥测功能，并且只添加了应用程序信息。
- **botClickCardAction** - 连接器卡用法。
- **brbFormOpened** - 用户已请求发送反馈。
- **brbFormSubmit** - 用户已提交反馈。
- **breakStartEndClicked** - 在上班打卡屏幕上，选择“**开始**”或“**结束休息时间**”按钮。
- **breakStartEndTriggered** - 注册用户选择使用休息时间开始或结束。
- **bucketSelected** - 确认已成功选择存储桶。
- **bucketUnselected** - 确认已成功取消选择存储桶。
- **bucketPickerClicked** - 确认成功启动了存储桶选取器。
- **BYOELiveEventJoin** - BYOE（广播自己的活动）直播活动由用户加入。
- **calendarLiveChatClicked** - 在“**日程安排**”选项卡上的实时会议中聊天。
- **calendarMeetingJoin** - 从日历中选择“**加入会议**”按钮。
- **calendarTab** -在底部栏中选择“**会议**”选项卡。在了解日历使用情况和与底部底部其他应用进行比较，或确定从底部栏选择后，呈现日历文章是否失败非常有用。
- **calendarTabClicked** - 在下面列出的情况下，这将显示日历的使用情况，并允许你与底部栏上的其他导航栏应用程序进行比较。 这可用于确定在以下情况下是否存在故障：
  - 此时将显示“**日程安排**”选项卡。
  - 在底部栏中选择“**会议**”选项卡。
- **calendarUpcomingChatClicked** - 在“**日程安排**”选项卡上即将到来的会议中聊天。
- **callAccepted** - 已接受通话。
- **callAcceptedSFB** - 已接受通话。
- **callAppPreference** - 已选择首选通话应用程序。
- **callControlsManualDismiss** - 手动解除通话控件。
- **callControlsManualInvoke** - 通话控件是手动调用的。
- **callHistoryItemExpand** - 已展开通话历史记录项。
- **callHistoryTab** - 在通话中选择 **CallHistory** 选项卡。
- **callInProgressShown** - 将显示**_呼叫进行中_* 的横幅。
- **callMePSTNConnected** - 已成功 **呼叫我**。
- **callOrMeetUpAddParticipants** - 触发时间：
  - 在 1:1 呼叫屏幕上点击“添加参与者”按钮。
  - 在“添加参与者”中选择“人员” (VoIP)。
  - 在“添加参与者”中选择 PSTN。
  - 在实时私人会议中添加人员。
  - 在实时私人会议中选择 PSTN。
  - 在实时私人会议中选择公司联系人。
  - 在实时私人会议中选择设备联系人。
  - 在实时私人会议中添加已完成参与者。
  - 在实时频道会议中添加人员。
  - 在实时频道会议中选择 PSTN。
  - 在实时频道会议中选择团队成员。
  - 在实时频道会议中选择设备联系人。
  - 在实时频道会议中添加已完成参与者。
- **callOrMeetUpAddParticipantsDone** - 用户完成其参与者的添加。
- **callOrMeetUpAddRoom** - 触发时间：
  - 在名单中选择了“**添加会议室**”。
  - 在“添加会议室”中选择了搜索结果。
  - 为“附近”选择“**关闭**”。
  - 为“附近”选择了“**启用 BT**”或“**位置**”。
  - 在“添加会议室”中选择了附近会议室结果。
  - 在“添加会议室”中选择了推荐会议室结果。
  - 在“添加会议室”中选择了“**完成**”。
- **callOrMeetUpAudioOffSwitch** - 在同伴加入模式下的实时通话或会议中，翻转 **音频关闭** 按钮。
- **callOrMeetUpAutoReconnect** - 网络性能差会导致用户的设备进入“自动重新连接”模式。
- **callOrMeetUpCallAccepted** - 触发时间：
  - 接受通话。
  - 接受 PSTN 通话。
- **callOrMeetUpCallEnded** - 触发时间：
  - 点击了“**终止呼叫**”按钮。
  - 在 callOrMeetupLive 中时点击了 “**终止呼叫**”按钮。
  - 在锁屏界面中时点击了“**终止呼叫**”按钮。
  - 在通知中时点击了“**终止呼叫**”按钮。
  - 在应用内时点击了“**终止呼叫**”按钮。
  - 在 callKit 中时点击了“**终止呼叫**”按钮。
  - 点击了 PSTN 的“**终止呼叫**”按钮。
- **callOrMeetUpChatWithParticipants** - 在实时会议或呼叫中切换聊天。
- **callOrMeetUpDeviceAudioSwitch** - 触发时间：
  - 将音频源切换到扬声器。
  - 将音频源切换到设备。
  - 将音频源切换到蓝牙。
  - 将音频源切换到音频关闭。
  - 在实时会议或通话中切换扬声器。
  - 在实时会议或通话中将扬声器切换到音频关闭。
  - 在同伴加入模式下的实时通话或会面中，翻转“**音频关闭**”按钮。
  - 在 PSTN 中时的设备音频切换。
- **callOrMeetUpEnterDriveMode** - 从“**...**”菜单手动切换到行车模式。
- **callOrMeetupExitDriveMode** - 点击了“**退出行车模式**”。
- **callOrMeetUpHold** - 触发时间：
  - 在实时会议或呼叫过程中，点击了“**保持**”按钮。
  - PSTN 中的呼叫保持。
- **callOrMeetUpIncomingVideoSwitch** - 在实时会议或电话中关闭 IncomingVideo。
- **callOrMeetUpInvitedParticipants** - 触发时间：
  - 在私人实时会议期间，单击 **其他已邀请人员** 参与者组底部的“**查看全部**”。
  - 在实时频道会议期间，单击 **其他已邀请人员** 参与者组底部的“**查看全部**”。
- **callOrMeetUpJoinedParticipants** - 触发时间：
  - 在私人实时会议期间，单击 **正在开会** 参与者组底部的“**查看全部**”。
  - 在实时频道会议期间，单击 **正在开会** 参与者组底部的“**查看全部**”。
- **callOrMeetUpLobbyParticipants** - 触发时间：
  - 在私人实时会议期间，单击 **大厅** 参与者组底部的“**查看全部**”。
  - 在实时频道会议期间，单击 **大厅** 参与者组底部的“**查看全部**”。
- **callOrMeetUpMicrophoneSwitch** - 触发时间：
  - 打开麦克风。
  - 关闭麦克风。
  - 在实时会议或通话中选择 **麦克风** 按钮。
  - 在 PSTN 期间的麦克风切换。
- **callOrMeetUpMuteParticipant** - 远程参与者已静音。
- **callOrMeetUpMuteParticipants** -在实时会议或呼叫中将所有参与者静音。
- **callOrMeetUpParticipants** - 参与者在实时会议或通话中切换。
- **callOrMeetUpRemoteMuteUFD** - 你已被静音 UFD。
- **callOrMeetUpResume** 触发时间：
  - 在实时会议或通话中选择 **恢复** 按钮。
  - PSTN 中的通话恢复。
- **callOrMeetUpSearchParticipants** - 触发时间：
  - 在参加私人实时会议的过程中，单击了“**搜索**”。
  - 在私人会议期间查看 **大厅** 参与者组后单击 **搜索**。
  - 在私人会议期间查看 **正在开会** 参与者组后单击 **搜索**。
  - 在私人会议期间查看 **其他已邀请人员** 参与者组后单击 **搜索**。
  - 在参加实时频道会议的过程中，单击了“**搜索**”。
  - 在实时频道会议期间查看 **大厅** 参与者组后单击 **搜索**。
  - 在实时频道会议期间查看 **正在会议** 参与者组后单击 **搜索**。
  - 在实时频道会议期间查看 **其他已邀请人员** 参与者组后单击 **搜索**。
- **callOrMeetUpVideoSwitch** - 触发时间：
  - 打开视频。
  - 关闭视频。
  - 实时会议或呼叫过程中选中了视频按钮。
- **callPark** - 触发时间：
  - ...**菜单中** 选择了 **“寄存呼叫**”。
  - “**检索**”按钮处于选中状态。
  - 在检索对话框中选中了 **拾取**。
  - 在检索对话框中选中了 **取消**。
- **callPreferenceSetting** - 呼叫首选项应用程序设置。
- **callsTabNewCall** - 在“**通话**”选项卡中选择“**新通话**”。
- **callTransfer** - 呼叫转移开始。
- **callVoicemailTab** - 在“通话”中选择了“**语音邮件**”选项卡。
- **cameraPermissionCancel** - 在相机权限对话框中选择“**取消**”。
- **cameraPermissionGoToSettings** - 从相机权限对话框导航到 **设置**。
- **cancelEditMeeting** - 选择“**编辑会议**”后，在会议计划程序页上选择“**关闭**”按钮。 当用户放弃 "编辑会议" 选择时，会将此载入记录。
- **cancelFileShare** - 在确认对话框中选择了“**取消**”。
- **cancelFileUpload** - 在上载对话框中选择了 **x**。
- **cancelMeeting** - 从“会议详细信息”页面中选择“**取消事件**”。 用于获取已取消会议数的聚合数据。
- **cancelNavigationToLink** - 已选择“取消导航”。
- **cancelRequestToJoinTeam** - 取消加入团队的请求。
- **cancelRequestToJoinTeamError** - 取消加入请求出错。
- **cancelNewMeeting** - 要记录放弃的会议选择，请在以下情况下验证导致这些选择的原因：
  - "会议计划程序" 页面上的 " **关闭"** 按钮处于选中状态。
  - 选择“**编辑会议**”后，将在会议计划程序页上选择“**关闭**”按钮。
- **cardView - No AS assigned** - 卡片视图和卡片渲染。 卡片是关键的平台结构，测量它们的使用和模式对于理解平台的使用和保持对客户端潜在问题的警惕是必要的。 此项用于测量任何加入团队时的错误。
- **castPpt** - 事件触发时间：
  - 已选中 PowerPoint 选项。
  - 已选中特定的 PowerPoint。
  - 在文件选取器页面中选中了 Teams 和频道文件夹。
  - 选择 "文件选取器" 页面中的 OneDrive 文件夹。
  - 停止强制转换会话。
  - 点击多任务 PiP。
  - 从“文件视图”中选择显示选项。
- **castScreen** - 请参阅：
  - 点击 "共享屏幕" 选项。
  - 停止屏幕共享会话。
  - 从文件视图中选择显示选项。
- **center_on_team_clicked** - 用户成功地在组上将地图居中。
- **channelFollow** -打开频道的通知。
- **channelUnfollow** -关闭频道的通知。
- **channelsActiveSetting** - **当我在桌面上处于活动状态时通知我** 通知设置已更改。
- **chatCreation** -成功创建聊天。
- **changeIsActiveSetting** - 基于桌面活动更改通知。
- **频道** - 聊天中的“新邮件”按钮或文本框。
- **channelDetails** - 频道导航信息，适用于以下情况：
  - 已选中频道标题。
  - 将导航到“频道详细信息”页。
- **channelFollow/channelUnfollow** -关注或取消关注频道。
- **channelNav** - 从任意位置导航到频道。
- **channelNavTab** - 在以下情况下，为 Teams 中的文件提供成功和可发现性数据：
  - 在频道中已选中“**文件**”选项卡。
  - 有连接器卡回复。
- **channelNotificationSettings** - 触发时间：
  - 已选择“**新通知设置**”对话框。
  - 已在“频道视图”中选中“频道通知设置”按钮。
  - 选中了“频道通知设置”。
- **channelSelected** - 确认已为新计划成功选择频道。
- **channelSendMessage** - 触发时间：
  - 已发送频道消息。
  - 聊天机器人在撰写框中被 @提及。
- **channelTabOverflow** - 选择频道中的“**更多**”选项卡。
- **聊天** - 参考：
  - 聊天中的“新邮件”按钮或文本框。
  - callHistory 项上所选的 1:1 聊天。
  - 呼叫列表上的 1:1 聊天选择。
- **chat - No AS Assigned** - 查看未读聊天或编辑聊天名单，特别是：
  - 当用户添加到聊天时，选择“**完成**”按钮。
  - 已选择聊天列表筛选器，按未读进行筛选。
- **chatAddChat** - 已点击“添加成员到聊天”按钮（这对 1:1 聊天和群组聊天是相同的）。
- **chatAllowJoinViaLink** - 打开或关闭“聊天详细信息”页面中的“加入链接”功能。
- **chatAvatarEdit** - 从“聊天详细信息”页面跟踪有多少组更改了其头像。
- **chatAvatarEditCamera** - 当用户从实时摄像头源编辑头像时触发。
- **chatAvatarEditGallery** - 当用户从手机图片库编辑头像时触发。
- **chatAvatarEditView** - 当用户查看现有头像时触发。
- **chatListNavConversations** - 用户点击聊天列表项时。
- **chatCancelAudioCall** - 取消群组音频呼叫 - 确认对话框。
- **chatCancelVideoCall** - 取消组视频呼叫 - 确认对话框。
- **chatCM_CopyText** - 点击聊天上下文菜单上的“**复制文本**”。
- **chatCM_DeleteMessage** - 点击聊天上下文菜单上的“**删除消息**”。
- **chatCM_edit** - 点击聊天上下文菜单上的“**编辑**”。
- **chatCM_Forward** - 点击聊天上下文菜单上的“**转发**”。
- **chatCM_markUnread** - 点击聊天上下文菜单中“**标记为未读**”。
- **chatCM_save** - 点击聊天上下文菜单上的“**保存**”。
- **chatCM_SeenBy** - 点击上下文菜单选项上的“**已看**”。 已读回执，例如已读用户 (readby)。
- **chatContactsEnter** - 已进入“**聊天联系人**”选项卡。
- **chatDetails** - 在以下情况下，提供聊天详细信息页的成功和可发现性数据：
  - 已选中聊天标题。
  - 导航到“聊天详细信息”页面。
- **chatRecentEnter** - 已进入“**聊天最近**”选项卡。
- **chatSendMessage** - 发送聊天消息。
- **chatShareLink** 跟踪发送组邀请链接的用户数。
- **chatStartAudioCall** - 触发时间：
  - 已点击 1:1 音频呼叫按钮。
  - 在搜索结果上点击“**音频**”按钮。
  - 点击右侧的“**开始呼叫**”按钮。
  - 通过 callHistory 项目点击的 1:1 音频呼叫。
  - 通过语音邮件项点击的 1:1 音频呼叫。
  - 发出组音频呼叫 - 确认对话框。
- **chatStartAudioCallOnBehalfOf** - 代理以上司的身份从操作表开始通话。
- **chatStartAudioCallOnBehalfOfMyself** - 代理以我的身份从操作表开始呼叫。
- **chatStartAudioCallSFB** - 已点击 1:1 音频呼叫按钮。
- **chatStartVideoCall** - 触发时间：
  - 已点击 1:1 视频呼叫按钮。
  - 在搜索结果上点击“视频”按钮。
  - 从 callHistory 项点击的 1:1 视频呼叫。
  - 发出组视频呼叫 - 确认对话框。
- **chatStartVideoCallSFB** - 点击的 1:1 视频通话按钮。
- **chatWithMeetingParticipants** - 从“会议详细信息”页中选择“**聊天**”选项卡。
- **checkListAddClicked** - 在清单的任务详细信息视图部分中选中了“**添加项目**”。
- **checkListItemAdded** - 已为任务创建清单项。
- **checkListItemDeleted** - 已从任务中删除清单项。 
- **checkListItemUpdated** - 已为任务更新清单项。
- **channelPickerClicked** - 确认已成功启动频道选取器。
- **checklistSeeAllClicked** 在“任务详细信息”中选择“**查看全部**”按钮以查看所有清单项时。
- **chicletExpand** -了解如何在移动设备上预览卡片和预览关闭行为。
- **clearFilter** - 当查看任务列表清除所有筛选器时。
- **clickPhotoOfficeLens** - 选择”**拍照**” - “启动摄像头”（仅适用于 Android）。
- **clockInEntryTeamSelectionShown** - 用户在未打卡的情况下，选择了打卡时钟的团队。
- **clockInOutClicked** - 在上班打卡屏幕上，已选择“**上班打卡**”或“**下班打卡**”按钮。
- **clockInOutTriggered** - 注册一个用户的上下班打卡。除非已选中了位置（假定位置是必需的），否则不会触发此操作。
- **closedBannerMessage** - 通知的横幅消息关闭时触发。
- **closeLobbyBanner** - 使用“**关闭**”按钮关闭大堂 toast 的次数。
- **commentAdded** - 确认已将注释添加到任务中。
- **commentsClicked** - 确认已成功启动注释 视图。
- **commentUpdated** - 确认已成功更新某个任务的注释。
- **companionBannerJoin** - 选择顶层横幅上的“**加入**”。
- **companionDismiss** - 关闭伴侣横幅。
- **companionDismissProximity** - 关闭伴侣横幅。
- **companionJoin** - 在工作表上选择“作为伴侣加入”选项。
- **companionJoinProximity** - 已通过伴侣横幅加入。
- **completeVaultFRE** - 用户完成生成用于加密其安全数据的主密钥过程。
- **completionStateChange** - 在任务列表的筛选器视图中选择已完成或未完成的筛选器切换时触发。
- **composeExpandComposer** - 已点击“**格式**”按钮。
- **composeFilePick** - 已启动原生文件选取器。
- **composeImagePicker** - 已点击 **图像** 按钮。
- **composeLocation** - 已点击撰写中的“**位置**”按钮。
- **composeMention** - @提及。
- **composeOpenEmoticonPicker** - 已点击笑脸选取器。
- **composeOpenFunPicker** - 已点击娱乐选取器。
- **composeParticipantAdded** - 当参与者被添加到“排班”应用程序时。
- **composeSearchResult** - 消息扩展结果选择，有助于理解应用程序搜索结果的相关性。 还增强了应用程序数据的消息发送遥测。
- **composeSelectExtension** - 点击 ME 应用程序。
- **composeSendSendreply** - 单击一个智能答复项。
- **composeSendMessage** - 使用应用程序数据增强消息发送遥测。
- **confirmAudioOn** - 用户确认他们希望打开音频。
- **confirmFileShare** - 在确认对话框中选择“**共享**”。
- **consultTransfer** - 触发时间：
  - 选择“**转移**” > “**首先咨询**”
  - 将转接目标设置为人员
  - 将转接目标设置为电话号码。
- **consultTransferCall** - 触发时间：
  - 启动咨询呼叫。
  - 已在确认转移对话框中选择“确认”。
  - 已在确认转移对话框中选择“取消”。
  - 已选中“**横幅转移**”按钮。
  - 已选中“**横幅恢复**”按钮。
- **consultTransferChat** 触发时间：
  - 启动咨询聊天。
  - 已在确认转移对话框中选择“确认”。
  - 在确认转移对话框中选择“确认”。
  - 选择“**横幅转移**”按钮或“**横幅恢复**”按钮。
- **consumeVoiceMessage** - 已播放语音消息。
- **ContactCard_SeeMoreOOF** - 查看更多的长 OOF 消息。
- **contactOrganizer** - 已选择“**联系组织者**”。
- **conversation, tabs** - 已选中选项卡。
- **copyLink** - 将链接复制到频道发布。
- **contactActivity** - 选择了从联系人卡片查看用户活动的按钮时。
- **conversation** - 当用户导航到“**聊天**”或“**发布**”选项卡时。
- **cortanaClose** - 当用户手动关闭 Cortana 画布时。
- **cortanaEduCategorySelect** - 当用户单击教育提示类别项时。
- **cortanaEduOpen** - 当教育页面在 Cortana 画布上显示时。
- **cortanaInvoke** - 当 Cortana 开始收听时。
- **cortanaKWSSwitchToggle** - 当用户点击 Cortana 设置页面中的 KWS 开关时。
- **cortanaMicPermissionDialogButtonClick** - 当用户在 Cortana 画布上授予或拒绝麦克风权限时。
- **cortanaOpen** - 当用户打开 Cortana 画布时。
- **cortanaOptionsOpen** - 当用户点击 Cortana 画布上的选项按钮时。
- **cortanaSafetyFirstActions** - 当用户接受安全优先声明时。
- **cortanaSafetyFirstLaunch** - 当 FRE 完成后用户首次打开 Cortana 时。 
- **cortanaSettingsOpen** - 当用户通过单击 Cortana 画布上的 Cortana 设置按钮打开 Cortana 设置页面时。 
- **cortanaStopResponding** - 当用户单击 Cortana 画布上的取消按钮时。
- **cortanaUserSettingsLaunch** - 当用户在 Teams 设置中打开 Cortana 设置时。
- **cortanaVoiceSelect** - 当用户在 Cortana 设置页面中选择 Cortana 语音字体时。
- **createChannel** - 在以下情况下，提供有关成功创建或放弃新频道创建操作的成功数据：
  - 在“**创建频道**”页面上选择了“**完成**”按钮。
  - 在“**创建频道**”页面上选择了“**取消**”按钮。
- **createComposeExtension** - 创建消息扩展用法，或操作 ME 用法。
- **createConversationClicked** - 与其他工作人员创建对话时。
- **createDefaultPlannerPlan** - 当任务应用程序首次由该组中的任何人打开时，会自动创建一个共享列表，选中使用 Planner 服务创建的自动列表。 确认用户第一次尝试创建共享任务列表时已在 Planner 中成功创建默认共享任务列表。
- **createOrJoinTeam** - 选择 **+** 按钮可创建或加入团队。
- **createPersonalPlan** - 已创建个人列表，检查使用 ToDo 服务创建的列表。 确认在 ToDo 中创建了新个人任务列表。
- **createPersonalSubtask** - 确认已成功创建个人子任务。
- **createPersonalTask** - 确认已成功创建个人任务。
- **createPlan** - 确认已成功创建共享任务列表。 确认已通过中间层成功创建共享计划。
- **createPlannerPlan** - 创建了共享列表，检查使用 Planner 服务创建的列表。 确认已在 Planner 中创建新共享任务列表。
- **createPlannerTask** - 检查对 Planner 服务的呼叫。 确认已在共享任务列表中成功创建任务。
- **createShiftClicked** - 当经理选择“**创建排班**”时。
- **createShiftOrTimeOffClicked** - 如果选择“**创建排班**”或“**休假**”，则触发。
- **createTask** - 用于创建操作失败时，检查 Planner 服务的调用。确认任务创建操作失败。
- **createTaskList** - 当用户从主页视图导航到“创建计划”视图时。
- **createTeam** - 在以下情况下，提供有关创建新团队的成功创建或放弃操作的成功数据：
  - 在“**创建团队**”页面上选择了“**完成**”按钮。
  - 在“**创建团队**”页面上选择了“**取消**”按钮。
- **createTeam, createChannel** - 在以下情况下，这将提供有关在团队中成功添加成员和成功创建新团队的成功数据：
  - 在“**添加成员**”页面中选中“**跳过**”按钮（首先选中现有）。
  - 在“**添加成员**”页面中选中“**完成**”按钮（首先选中现有）。
  - 显示团队或频道创建确认。
- **crossCloudDialogCancel** - 为跨云对话框选择了“**取消**”。
- **crossCloudDialogJoin** - 为跨云对话框选择“**作为来宾加入**”。
- **dashboardNav** - 用户导航到聊天仪表板上的平铺。
- **dateChanged** - 用户修改了排班日期。
- **datePickerLaunch** - 确认日期选取器已成功启动。
- **dayClicked** - 选择用户查看其班次时的日视图。
- **daySaved** - 用户保留该日的可用性和一天的排班。
- **declineTimeOffRequest** - 当用户拒绝休假请求时。 这是休假的一项关键功能，经理可以拒绝请假请求。
- **deleteClicked** - 在“任务详细信息”中选择“**删除**”时，将显示确认对话框。
- **deleteContact** - 用户删除现有私有联系人。
- **deleteMeeting** - 从“会议详细信息”页面中选择“**删除**”按钮。
- **deletePersonalTask** - 确认已成功删除个人任务。
- **deletePersonalSubtask** - 确认已成功删除个人子任务。
- **deletePersonalVaultItem** - 用户请求删除其个人保险箱。
- **deletePlannerTask** - 确认共享任务删除操作已成功完成。
- **deleteShift** - 排班删除。
- **duration_picker_dismissed** - 当解除持续时间选取器时。
- **deleteTask** - 使用 Planner 服务验证删除操作是否成功。 确认任务删除失败，即删除任务失败。
- **deleteVoicemail** - 已点击删除语音邮件项目。
- **demotedToAttendee** - 用户降级对话框中的演示者 - “**更改**”按钮。
- **denyParticipant** - 用户拒绝某人从名单中输入的次数。
- **descriptionChanged** - 确认已成功更改共享任务描述。
- **descriptionClicked** - 当用户从任务详细信息中选择“**查看描述**”时。
- **detailsTabClicked** - 在会议上选择了“**详细信息**”选项卡。
- **deviceAddressBookSync** - 从设置页打开通讯簿同步时触发。
- **deviceAddressBookUnsync** - 从设置页关闭通讯簿同步时触发。
- **deviceSyncEnabled** - 已启用设备同步。
- **deviceSyncDisabled** - 设备同步已禁用。
- **dialIn** - 用户选择“拨入”会议（不同位置）。
- **dialInBadNetworkBanner** - 已为不良连接横幅选择了“**拨号**”。
- **dialInBadNetworkBannerCancel** - 在本机对话中取消“**拨入**”。
- **dialInBadNetworkBannerConfirm** - 在本机对话框中确认“**拨入**”。
- **dialInCall** - 在“**拨入**”弹出窗口中选择 **呼叫**。
- **dialInCancel** - 在“**拨入**”弹出窗口中选择“**取消**”。
- **dialOutCall** - 当用户执行以下操作时触发：
  - 加入行车模式。
  - 在“**给我回电**”弹出窗口上选择“**呼叫**”。
- **dialOutCallAAD** - 当从操作表中的“**我的号码**”中选择任何号码时
- **dialOutCallRecent** - 当从操作表中上一个最近号码中选择任何号码时。
- **dialOutCancel** - 在“**给我回电**”弹出窗口中选择了“**取消**”。
- **dialOutDialog** - 在操作表中选择了“**新编号**”。
- **dialOutFailRetry** - 从故障标志中选择“**重试**”。
- **DialPad** - 从通话列表中选择“**拨号盘**”。
- **directShare** - 共享指向 Sms/电子邮件本机应用的邀请链接。
- **disableCategory** - 禁用通知类型或禁用来电通知。
- **disabled** - 在首次运行体验 (FRE) 中选择 **跳过通知**。 这为跳过 FRE 流中的通知提供了关键的成功数据。
- **disableQuietDays** - 已禁用“免打扰日”。 免打扰日功能成功遥测。
- **disableQuietHours** - 已禁用“免打扰时间”。
- **discoverTeams** - 导航到 "浏览和加入团队" 页面。
- **Dismiss_earlycancelledCQF** - 已解除 CQF 早期取消的呼叫表。
- **Dismiss_ratemycallCQF** - 已解除 CQF 的通话评分表。
- **Dismiss_ratemyliveeventCQF** - 已解除 CQF 的实时事件评分表单。
- **dismissBadNetworkBanner** - 已为不良连接横幅选择了“**关闭**”。
- **dismissFlyout** - 已选择 **关闭** 按钮。
- **dismissModality** - 模态选取器在未共享的情况下退出。
- **dismissModalityPicker** - 已选中“**模态选取器**”按钮。
- **dismissReadReceiptsNotice** - 已从功能通知中选择“**明白了**”。
- **dismissStartRecording** - 开始录制时关闭错误。
- **dismissStopRecording** - 停止录制时关闭错误。
- **dismissUseWifiForVideoBanner** - 用户关闭横幅时触发：
  - 这告知用户远程参与者视频被阻止，用户必须切换到 WiFi 才能看到。
  - 这告诉用户，用户必须切换到 WiF i才能共享视频。
- **DLPDelete** - 用户删除了被阻止的邮件。
- **DLPEdit** - 用户编辑了被阻止的邮件。
- **DLPOverride** - 用户重写了阻止的消息。
- **DLPOverrideReport** - 用户报告了误报，并重写了该消息。
- **DLPReport** - 用户报告了误报。
- **DLPResolve** - 用户尝试解析 DLP 消息。
- **DLPSeeOriginal** - 用户点击查看原始消息。
- **downloadFile** - 有助于：
  - 确定是否启动了下载操作。
  - 确定是否已成功下载文件。
- **dragDatePickerHandle**
- **dtmfPSTNCall** - 已点击“拨号盘”上的 DTMF 按钮。
- **dueDateChanged** - 当用户为任务分配到期日期时触发。
- **dueDatePickerClicked** - 在任务详细信息中选择“**到期日期**”按钮时触发，打开截止日期选取器页面。
- **dueDateSelected** - 当用户在查看任务列表时按到期日期应用筛选器时触发。
- **dueDateUnselected** - 当用户在查看任务列表时取消按到期日期筛选时触发。
- **edit** - 聊天消息中的“**编辑**”按钮。
- **editChannel** - 用户选择按钮来编辑他们拥有或管理的频道。
- **editContact** - 用户编辑现有的私有联系人，这可以通过导航到联系人卡片来完成。
- **editMeetingResponse** - 从“会议详细信息”页编辑会议答复。
- **editNavigation** - 在“**更多**”菜单中选择“**重新排序**”以编辑底部栏应用程序的顺序。
- **editRsvpMeetingOptions** - 选择“**请回复**”以更改先前的选择。
- **editShiftClicked** - 编辑排班。
- **editSmartReply** - 已编辑智能答复项。
- **editTeam** - 用户点击按钮编辑他们拥有或管理的团队。
- **editTeam, editChannel** - 在以下情况下，与成功增加团队成员和成功创建现有团队有关：
  - 在“**添加成员**”页面（现有团队或频道）中选择“**取消**”按钮。
  - 在“**添加成员**”页面（现有团队或频道）中选择“**完成**”按钮。
- **emergencyCall** - 发出紧急呼叫的通话套餐。
- **emergencyCallDirectRouting** - 发出紧急呼叫直接路由。
- **emergencyCallLocationPolicyBased** - 使用“拨号盘” DialEmergency。
- **emergencycallSecurityDeskNotify** - 发出紧急呼叫，通知安全服务台。
- **enableCategory** - 启用时与通知设置相关：
  - 一种通知类型。
  - 来电通知。
- **enabled** - 关于在首次运行体验 (FRE) 流中启用通知：
  - 在首次运行体验 (FRE) 中选择了 **启用通知**。
  - 在提醒中选择了启用。
- **enabled/disabled** - 调用权限或联系人权限（仅适用于 Android）。
- **enabled, notNow** - 通知权限提示“**接受**”按钮，首次运行体验 (FRE) 通知权限 (iOS)。 这将捕获启用通知功能的人数并提供信息。
- **enablediOSPrompt** - 用户实际上在 iOS 通知权限提示中启用通知。 这将提供有关在 iOS 中实际从通知权限提示符启用通知的用户的信息。
- **enabledQuietDays** - 已启用“免打扰日”。
- **enableLocationPermission** - 当用户为共享位置功能启用位置权限时。
- **enableQuietDays** - 用户启用“免打扰日”。
- **enableQuietHours** - 启用了“免打扰时间”。
- **endEditing** - 已按下“**保存**”按钮。
- **endFileShare** - 在文件共享对话框中选择了“**返回**”。
- **endMyShift** - 处于共享模式的设备数或注销次数。
- **endPhotoShare** - **x** 从照片共享中退出。
- **entryPointClicked** - 在“**日程安排**”选项卡中选择“**请求**”。请求用于一线员工 (FLW) 请求排班时间等...
- **endPSTNCallSelected** - 用户结束 PSTN 和内容呼叫。
- **endPSTNCallShown** - 系统会提示用户结束 PSTN 或内容呼叫。
- **endVideoShare** - **x** 从视频共享中退出。
- **errorShown** - 显示错误。
- **expand/collapse** - 设备联系人或公司联系人部分。
- **expandCollapseSection** - 点击一个分区标题以展开或折叠分区。
- **Expected: atMention - Android: chatSendMessage - iOS: sendMsg** - 在编辑框中 @提及 机器人。
- **Expected: botClickCardAction - Android: showCard - iOS: missing** - 点击卡片按钮。卡片是一种关键平台构造，并衡量其使用情况和模式是了解平台使用情况并随时查看客户端上的潜在问题所必需的。
- **Expected: chatSendMessage - iOS: composeSendMessage** - 点击“**回复**”并回复频道中的机器人聊天。
- **Expected: composeSendMessage - Android: replyChannel - iOS: missing** - 点击“**回复**”并回复频道中的机器人聊天。
- **Expected: messageLike - Android: reactLike_CM** - 为聊天机器人消息点赞。
- **Expected: messageUnread - Android: markAsLastUnread** - 机器人程序消息的消息上下文菜单选项。
- **federatedUpgradeNewChat** - 旧聊天将升级到本机。
- **files** - 跟踪聊天室和频道文件选项卡中的文件列表是否成功完成。
- **fileSelected** - 已选择 PowerPoint 演示文稿。
- **fileThumbnailPreviewDownloaded** - 帮助识别文件的缩略图是否已成功呈现。
- **fileThumbnailPreviewFromCache** - 捕获是否成功从缓存中显示缩略图，并帮助确定是否为文件成功呈现缩略图。
- **fileThumbnailPreviewNotAvailable** - 帮助确定是否成功呈现文件的缩略图。
- **fillFrameVideo** - 从操作表填充构图。
- **firstTimeSignedIn** 登录或注册触发事件：
  - 登录成功。
  - 首次登录成功。
  - 用户看到登录错误。
  - 记录首次登录时实施的 MAM/MDM 策略的遥测。
  - 首次成功登录后记录应用安装引用的参数。
- **fitToFrameVideo** - 从操作表适应框架。
- **flipCamera** - 翻转相机。
- **forcedUpdateAccept** - 用户接受在“强制更新”对话框中更新应用程序版本。
- **forcedUpdateExit** - 用户关闭应用程序，而不是在“强制更新”对话框中更新应用程序版本。
- **forcedUpdatePrompt** - 在需要联系旧版本的用户（可能没有最新安全和隐私修复程序）的情况下使用。
- **formattingBold** - 用户选择加粗格式。
- **formattingHighlight** - 用户选择突出显示格式。
- **formattingImportant** - 用户选择重要性。
- **formattingItatlics** - 用户选择斜体。
- **formattingTextColor** - 用户选择文本颜色格式。
- **formattingUnderline** - 用户选择下划线。
- **FRE - No AS Assigned** - 在应用程序启动时记录有关 MAM/MDM 策略的遥测。 用于 MAM 和 MDM 的 Intune 集成遥测。 提供有关首次运行体验 (FRE) 期间失败的成功数据。
- **freActionClicked** - 在首次运行体验 (FRE) 中选择了“**入门**”、“**稍后尝试**”或“**关闭**” (GPS)。
- **freDone** - 首次运行体验 (FRE) 已经完成。
- **freTriggered** - 用户可以查看首次运行体验 (FRE) 上的打卡时钟。
- **funSearchQueryEntered** - 已进入 Giphy 查询。 Teams 中 giphy 附件功能的成功数据。
- **funSelectItem** - 已选择 Giphy 图像。 Teams 中 giphy 附件功能的成功数据。
- **galleryImage** - 已上传图像 - 库。
- **get_directions_clicked** - 选择了“**获取方向**”按钮。
- **giphyUserDisabled** - 用户选择拒绝 Giphy 条款/条件。
- **giphyUserEnabled** - 用户选择接受 Giphy 条款/条件。
- **goToNotificationSettings** - 从“**更新通知设置**”对话框转到“通知设置”页。
- **GPSPromptClicked** - 在操作系统提示中选择“**允许**”或“**不允许**”。
- **group_map_closed** - 用户从聊天打开地图视图。
- **group_map_open** - 用户关闭地图视图。
- **groupCallJoin** - 用户加入群呼。
- **groupClicked** - 跟踪用户选择排班组的时间。
- **guideMe** - 用户选择通知他们 3P 应用程序阻止通知的横幅，并提供故障排除指导。
- **hamburgerMenu** - 导航到汉堡菜单。汉堡菜单包含重要操作，例如帐户切换、通知设置、数据设置和配置文件设置。
- **handoffComplete** - 此设备上的会议或电话已关闭。
- **handoffJoin** 在操作表上选择了会议移交选项。
- **hardwareAudioOff** - 通过硬件按钮关闭音频。
- **hardwareAudioOn** - 通过硬件按钮启用音频。
- **hide** - 隐藏聊天。
- **hideChannel** -从团队和频道列表中隐藏频道。
- **image** - 图像。
- **inAppNotification**- 当用户在应用中处于活动状态时点击通知时触发。
- **immediateCallForward** - 已设置即时呼叫转接目标，或启用即时呼叫转接（禁用来电时振铃）。
- **importanceToggleClicked** - **!** 时触发的情况 已在任务项详细信息中切换字段。
- **importantMessage_select** - 用户从优先级上下文菜单中选择重要消息。
- **importantMessageSend** - 用户发送重要邮件。
- **inCallDialOut** - 用户从呼叫更多选项中选择“**给我回电**”按钮。
- **initiatePhotoShare** - 启动照片共享。
- **initiateVideoShare** - 启动视频共享。
- **install** - 安装或安装事件。
- **installReferrer** - 在首次安装后记录应用安装引用参数。
- **invisionWhiteboardClicked** - 已选择 Invision 白板：
  - “**频道文件**”选项卡。
  - 会议“**聊天文件**”选项卡。
- **inviteFreemium** - 在邀请屏幕中点击 **+** 按钮。
- **inviteGuest** - 在邀请屏幕中点击 **+** 按钮。
- **joinFromDeeplinkInTeams** - 用户通过深层链接从 Teams 应用程序中加入。
- **joinFromDeeplinkOutsideTeams** - 用户从 Teams 应用程序外部通过深层链接加入。
- **joinFromJoinLauncher** - 从联接启动器加入的用户。
- **joinFromNudge** -从提醒加入的用户。
- **joinFromStore** - 从 App Store 下载应用后加入的用户。
- **joinMeeting** - 在以下情况下检测从日历加入会议成功或失败：
  - 通过“拨入”加入会议。
  - 通过“给我回电”加入会议。
  - 仅加入会议内容。
  - 从“日程”视图中选择“**会议加入**”按钮。
- **joinOptionsEdu** - EDU 用户选择加入预定会议的选项，并显示正确的选项。
- **joinTeam** - 已按下 **加入** 按钮。
- **joinViaCode** - 用户通过代码加入会议。
- **labelPickerClicked** - 确认标签选取器已成功启动。
- **labelSelected** - 确认已成功选择标签。
- **labelUnselected** - 确认已成功取消选择标签。
- **launchLinksGallery** - 当用户从仪表板进入链接库时。
- **launchSlideshow** - 用户从三个可能应用功能位置之一启动幻灯片全屏图像查看器。 
- **Launch source such as direct, link, appShortcut** - 直接或通过链接启动（在应用程序启动时记录移动应用程序管理 (MAM) 或移动设备管理 (MDM) 遥测，为活动用户收集数据）。
- **lastSearchableAliasTurnedOff** - 用户已禁用帐户的所有可搜索别名。
- **leaveChat** - 确认离开聊天。
- **legacyChatLink** - 已选中旧聊天的链接。
- **链接** - 用户通过输入 Teams 应用程序启动兑换邀请链接。
- **likeAppDismiss** - 当询问用户是否喜欢该应用程序的提示被取消而没有响应时。
- **likeAppNo** - 当询问用户是否喜欢该应用程序的提示收到“否”的响应时。
- **likeAppYes** - 当询问用户是否喜欢该应用程序的提示收到“是”的响应时。
- **likeMsg** - 选择“**赞**”。
- **linkPreviewCancel** - 了解预览关闭行为。
- **listUserClicked** - 当用户在“正在工作”中选择用户时。
- **liveCaptions** - 打开或关闭辅助字幕。
- **liveEventAdditonalLink** - 已选中额外的链接。
- **liveEventInfo** - 已选择“**信息**”按钮。
- **liveEventJoin** - 用户加入实时事件。
- **liveEventLeave** - 已按下“**离开**”按钮。
- **liveEventPresenterJoin** - 演示者加入实时事件。
- **liveEventPresenterJoinAsAttendee** - 作为与会者加入的实时事件演示者。
- **liveEventQnA** - 已选中“**问答**”图标。
- **liveEventYammer** - 已选择 **Yammer** 图标。
- **liveMeetingPushNotificationClicked** - 已选择推送通知。
- **liveMeetingToastClicked** - 已选择应用内 toast。
- **live_location_in_chats_from_profile_clicked** - 在用户配置视图中选择“**实时位置**”。
- **lobbyPickAudio** - 用户从大厅切换音频输出的次数。
- **lobbyToggleMuted** - 用户从大厅打开或关闭麦克风的次数。
- **lobbyToggleVideo** - 用户从大厅打开或关闭视频的次数。
- **logOutClicked** - 用户注销时。
- **location_active_tracking** - 用户的设备切换为有效跟踪。
- **locationCard** - 选择位置卡片。
- **location_family_sync** - 显示在 MSA 系列应用程序中创建的家庭组成员。 确认显示所有可授予同意的家庭成员。
- **location_data_use_privacy_denied** - 用户已拒绝接收隐私条款。
- **location_group_map_sync** - 已打开地图视图。
- **location_map_load** - 加载地图视图。
- **location_map_markers_load** - 地图视图加载。确认地图视图中正确显示所有主动共享用户的位置标记。
- **location_message_send** - 用户启动位置共享会话。
- **location_data_use_privacy_denied** - 用户在解释 TFL使用位置数据的弹出窗口上关闭或选择“**暂不**”。
- **location_data_use_privacy_granted** - 用户在解释 TFL 使用位置数据的弹出窗口上选择了“**允许**”。
- **location_settings_open** - 用户打开位置设置。
- **location_sharing_start** - 用户在聊天中共享其实时位置。
- **location_sharing_stop** - 用户在聊天中停止共享其实时位置。
- **loginFailed** - 用户无法登录。
- **loginSuccess** - 用户能够登录。
- **logoutVault** - 用户从应用中注销，然后从保险箱中注销。 
- **manageBlockedNumbers** - 通过设置访问阻止的号码。
- **manageVaultKey** - 用户更改其安全密钥管理选择 (MSA 与自跟踪)。
- **manualSendMessage** - 手动发送一封邮件。
- **mapAppPicker** - 当用户点击位置卡时选择要使用的映射应用程序时。
- **markAsRead** - 标记为“已读”。
- **markAsUnread** - 标记为“未读”。
- **markChannelRead** - 用户将频道标记为已读。
- **messageBookmarkMessage** - 连接器卡保存。 将现有遥测与应用特定数据配合使用。 或保存聊天机器人消息。
- **markAsLastUnread** 连接器卡上下文菜单。
- **maskCallerId** - 用户启用或禁用呼叫设置来屏蔽呼叫号码。
- **meetingAttachmentFileClick** - 会议附件项已单击。
- **meetingAttachmentFileOptions** - 会议附件项选项已单击。
- **meetingAttachmentSeeMoreClick** - 会议附件“查看更多”按钮已单击。
- **meetingDetailCalendarList** - 从日历列表中选择“会议详细信息”页，或选择“会议详细信息”页上的“**详细信息**”选项卡。
- **meetingDetailChatWithParticipants** - 从“会议详细信息”页与参与者聊天。
- **meetingDetailDeleteMeetingforSelf** - 从“会议详细信息”页中为自己删除会议。
- **meetingDetailJoin** - 从“会议详细信息”页中选择“**会议加入**”按钮。
- **meetingDetailParticipants** - 请参见“会议详细信息”页面中的所有参与者。
- **meetingDetailScheduledMeeting** - 从计划会议对象中选择的会议详细信息页 (**...**) ，或选择计划会议的 **“详细信息** ”选项卡。
- **meetingDetailSearchParticipants** - 在会议日程中的会议参与者中选择“**搜索**”。
- **meetingInsightFileClick** - 会议相关文件项已单击。
- **meetingInsightFileLocatorClick** - 会议相关内容定位符提示按钮已单击。
- **meetingInsightFileOptions** - 会议相关文件项选项已单击。
- **meetingInsightSeeMoreClick** - 会议相关内容“查看更多”按钮已单击。
- **meetingJoinLeave** - 点击了“离开” -> 点击“**加入**”按钮后点击了 **x**。
- **meetingJoinNow** - 选中了“**现在加入 VOIP**”。
- **meetingJoinNowWithCallMe** - 用户使用“**呼叫我**”加入会议。
- **meetingJoinNowWithPSTN** - 用户使用“拨入”加入会议。
- **meetingLeaveChat** - 离开聊天。
- **meetingMuteChat** - 将聊天设为静音。
- **meetingNotesCreatedInChatLink** - 在私人会议聊天或频道会议聊天中选择 **创建会议笔记** chicklet。
- **meetingNotesMentionCharLink** - 私人会议聊天中已选中 @提及 链接。
- **meetingNotesMentionChatLink** - 频道会议聊天中已选中 @提及 链接。
- **meetingNotesTabEntryPoint** - 在私人会议或频道中选择“**会议笔记**”选项卡。
- **meetingNotificationSettingsAccepted** - 通知设置选项已更改为“仅接受”。
- **meetingNotificationSettingsAll** - 通知设置选项已更改为“全部”。
- **meetingNotificationSettingsNone** - 通知设置选项已更改为“无”。
- **messagePriority_select** - 已选择消息优先级入口点。
- **messageSeeOriginal** - 用户将翻译后的消息还原为原始消息。
- **meetingSeeParticipantsChatDetails** - 查看所有参与者。
- **memberListLoadMore** - 向下滚动以加载更多。
- **messagedEditMessage** - 用户编辑邮件。
- **messageShareMessage** - 共享邮件。
- **messageTranslate** - 用户翻译邮件。
- **messageUnabletoEdit** - 用户无法编辑邮件。
- **meetingUserAnonB2B** - 匿名 B2B 加入了会议。
- **meetingUserAnonB2C** - 匿名 B2C 加入了会议。
- **meetingUserDialIn** - PSTN (拨入) 用户加入了会议。
- **meetingUserDialOut** - PSTN 回拨用户加入了会议。
- **meetingUserFederated** - 联合用户加入了会议。
- **meetingUserFreemium** - 免费增值用户加入了会议。
- **meetingUserGuest** - 来宾用户加入了会议。
- **meetingUserTenant** - 租户内用户加入了会议。
- **memeGenerated** - 当用户输入图像和文本数据生成 Meme 时。 
- **meProfileFetch** - 指示成功提取和创建配置文件。
- **messageCopyMessage** - 复制邮件。
- **messageDelete** - 删除邮件。
- **messageEditMessage** - 编辑邮件。
- **messageForwardMessage** - 用户从“邮件上下文”菜单中选择转发入口点。
- **messageLike/messageUnlike** - 给消息点赞或取消赞。
- **messageMuteSender** - 将发件人静音或取消静音。
- **messageLike** - 为连接器卡点赞。 将现有遥测与应用特定数据配合使用。
- **messageScheduledMeeting** - 已选择频道中的会议对象（不仅是已计划对象）。
- **messageTriggered** - 这是邮件触发通知的情况。
- **micPermissionCancel** - 在“麦克风权限”对话框中选择了“**取消**”。
- **micPermissionGoToSettings** - 用户从“麦克风权限”对话框导航到“设置”。
- **MicrosoftWhiteboardClicked** - 在“**频道文件**”选项卡或“**会议聊天文件**”选项卡上选择了 Microsoft Whiteboard。
- **moreOptionsClicked** - 当 **...** 右上角的菜单在任务项编辑器屏幕上被选中时触发。
- **moveTaskClicked** - 任务项更多选项列表中的选项。
- **msaAddDeleteAliasLinkClicked** - 链接以在 MSA 配置文件页上设置别名。
- **multiCallEndFromUFD** - 在多个呼叫情况下，用户结束通话保持的次数。
- **multiCallResumeFromUFD** - 用户选择从通话保持恢复呼叫的次数。
- **multiCallSwitch** - 用户选择选项来切换呼叫并显示通话保持列表的次数。
- **multipleAccounts** - 用户的帐户数。
- **multipleTenants** - 每个帐户的租户数。
- **mute** - 将聊天设为静音。
- **muteOnWhiteboard** - 用户在白板屏幕上静音或取消静音。
- **muteParticipant** - 将参与者静音（移到操作表）。
- **my_location_button_clicked** - 用户通过选择“**我的位置**”按钮将地图在其位置上居中。
- **my_location_clicked** - 用户通过选择地图上的 **蓝点** 将地图在其位置上居中。
- **myShiftPilickClick** - 只有当正在发送的请求是调换或优惠时才能记录。 **选择了"我的班次** 选取器"。
- **nameGroupChat** - 命名群聊。
- **nativeTimeClockBreak** - 打卡时钟上的休息时间。
- **nativeChatLink** - 已选中指向本机聊天的链接。
- **navActivity**- 导航到“活动源”页面。

- **navBookmark** - 用户导航到底部栏或应用程序托盘上的“**已保存**”选项卡或应用程序。
- **navCalendar** - 测量用户是否导航到日历。
- **navCallingSettings** - 用户导航到通话设置。
- **navCalls** - 点击了“**通话**”选项卡。
- **navCamera** - 用户导航到底部栏或应用程序托盘上的 **摄像头** 选项卡或应用程序。
- **navChat** - 用户导航到底部栏或应用程序托盘上的 **聊天** 选项卡或应用程序。
- **navContacts** - 用户导航到底部栏或应用程序托盘上的 **联系人** 或 **人员** 选项卡或应用程序。
- **navDashboardTab** - 用户导航到对话中的“**仪表板**”选项卡。
- **navDynamics365** - Dynamics365 应用打开时触发。
- **navFiles** - 选择了文件应用程序，跟踪用户是否可以在应用程序托盘 (iOS) 中启动文件应用程序。
- **navFilesTab** - 选择了文件应用程序，跟踪用户是否可以在底部导航栏 (iOS) 中启动文件应用程序。
- **navMeetings** - 点击了 **日历** 选项卡。
- **navNotes** - 在“笔记”应用打开时触发。
- **navOrganization** - 在“组织”应用打开时触发。
- **navOrgChart** - Orgchart 应用打开时触发。
- **navPeople** - 在“人脉”应用打开时触发事件。
- **navPeopleSettings** - 当导航到“设置”菜单中的“**人员**”类别时触发。
- **navPersonalFiles** - 已选中文件应用程序，跟踪用户是否可以在底部导航栏 (Android) 启动文件应用程序。
- **navPhotoTab** - **照片** 选项卡。
- **navSaved** - 用户导航到底部栏或应用程序托盘上的“**已保存**”选项卡或应用程序。
- **navSelectPlan** - 当用户选择从主页视图导航到的共享计划时。
- **navSelectPersonalList** - 当用户选择从主页视图导航到的个人计划时。
- **navSelectSmartList** - 当用户选择从主页视图导航到的智能计划时。
- **navTasks** - 在“任务”应用打开时触发。
- **navTeams** - 点击“**查看全部**”。
- **navVideocamera** - 用户导航到底部栏或应用程序托盘上的 **摄像头** 选项卡或应用程序。
- **navVideoTab** - **视频** 选项卡。
- **navVoicemail** - 用户导航到语音邮件页面。
- **navWalkieTalkie** 用户已打开对讲机应用程序。
- **navWiki** - 在 Wiki 应用打开时触发。
- **newChat** - 用户创建聊天。
- **newCall** - 点击“**新通话**”按钮。
- **newCallDialPad** - 点击选项卡上的 **拨号盘**。
- **newCallPeople** - 点击选项卡上的“**人员**”按钮。
- **noBGActivityDetected** - 超过后台活动失败的阈值。
- **notBlockedDevice** - 用户在 30 天内未达到后台活动失败的阈值。
- **notNow** - 在提醒中选中“**暂不**”。
- **notNowUpdate** - UpdateDefer.
- **notification/notification_clicked** – 在点击通知时触发。
- **notificationNavChannelConversation** - 使用频道对话通知启动应用程序。
- **notificationNavChannelThreadConversation** - 使用频道对话中特定消息的通知启动应用程序。
- **notificationSettingTurnedOff** - 关闭 Android 版 Teams 应用程序的推送通知。
- **notificationNavPreCall** - 用户会收到会议开始的通知，该通知会将用户导航到所选内容的预拨屏幕。
- **ocvFeedback** - 与 OCV 反馈表的性能有关。
- **ocvFormCancelled** - 当 OCV 反馈表单被取消并且用户返回应用程序时发送的事件。
- **ocvFormOpened** - 打开 OCV 表单时发送的事件。
- **ocvFormSubmit** - 当用户单击 OCV 反馈表上的提交时发送的事件。
- **offerRecipientClicked** - 仅当发送的请求是代班时才记录。 用户进入团队成员选取器以提供代班。 代班意味着提供排班休假。
- **offerSwapShiftFromL1** - 用户试图从排班列表中代班或交换的排班类型。 iOS 操作是 **SwipedRight** 和 Android 操作是 **LongPressed**。
- **offerSwapShiftFromL1Triggered** - 用户提供与另一用户交换排班。
- **officeLens** - 应用程序启动 OfficeLens 相机功能时，在以下任一情况下激发：
  - 用户尝试将照片附加到其消息中
  - 用户尝试拍摄照片并直接上传到库。
- **officeLens or cameraImage** - 已选择相机图片 - 标准相机或 Office Lens。
- **onBackClicked** - 每当选择“上一步”箭头向后导航页面时。
- **oneNote** - 用户打开 OneNote 应用时。
- **open** - 点击“通知设置”。
- **open edit** - Wiki 使用情况遥测 - 用户选择编辑 Wiki。
- **openApp** - 正在打开个人应用。
- **openAppDrawer** - 在底部栏选择“**更多**”以打开应用抽屉。
- **openEditMeetingForm** - 从会议详细信息页面中选择了“**编辑**”按钮。
- **openFile** - 有助于：
  - 确定文件能够在聊天中成功打开。
  - 确定文件能够从文件列表中打开。
  - 检查是否可以从 OneDrive 列表打开文件。
  - 确认打开的文件可从频道列表中打开。
  - 确定是否可以从群聊中打开文件。
  - 确定是否可以从“文件”应用程序成功打开文件。
  - 确定是否可从 chicklet 成功打开消息文件。
  - 确定是否可以成功打开最近列表中的文件。
  - 确定是否可以成功打开文件列表中的文件。
  - 确定是否可以从消息文件 chicklet 打开文件。
  - 确定是否可以从文件列表中成功打开文件。
- **openInAppClicked** 在任务项目中的更多选项列表中的选项仅适用于个人任务。
- **opensCalendarView** - 在“**日程安排**”选项卡中点击“**未完成班次**”。
- **openContactCard** - 用户点击人员应用程序中的 **联系人** 图标或联系人，即可启动该联系人的个人资料卡片。
- **openContactCard_ReactionSummary** - 从回应摘要页面导航到“联系人卡片”。
- **openFileInApp** - 帮助确定用户是选择在 Teams 外部还是 Teams 内部打开文件。
- **openHamburgerMenu** - 选择 **汉堡** 图标（左上角）可打开侧菜单以访问设置、状态和租户切换。
- **openInStream** - 打开 Stream 中的视频。
- **openMeetingDetails** - 打开特定会议的会议详细信息或“打开会议详细信息”页面。
- **openModalityPicker** - X = ChatsAndChannels 适用于聊天和频道。
- **openNewMeetingForm** - 确认已成功更新个人子任务。
- **openNewMeetingForm** - 在设置新会议时打开日程安排程序。
- **openPhotoLibrary** - 选择照片库。
- **openQuietDays** - 导航到“免打扰日”页面。
- **openQuietHours** - 导航到“免打扰时间”页面。
- **openReactionHoverBubble** - 按“回应摘要”页面上的“**添加回应**”按钮。
- **openReactionSummary** - 调用回应摘要抽屉。
- **openSettingsSetUpInstructions** - 从说明中打开 **设置**。
- **openSharedLink** - 当用户从仪表板链接磁贴或链接库打开链接时。
- **openShiftsClicked** - 有多少人点击 **日历** 图标。
- **orgChart - No AS assigned** - 组织结构图的基本用法遥测。
- **pageEntered** - 用户进入了页面。
- **parental_consent_grant** - 用户向其 MSFamily 中的未成年人授予使用 TFL 中实时位置功能的权限。
- **parental_consent_remove** - 用户撤销其 MSFamily 中未成年人使用 TFL 中实时位置功能的权限。
- **pauseVoicemail** - 在语音邮件项目上点击了“**暂停**”。
- **peoplePickerDismissed** - 指示人员选取器已解除。
- **peoplePickerInvoked** - 人员选取器可在 Teams 移动版的七个位置使用，包括（但不限于）：
  - 新聊天选取器。
  - 转发邮件。
  - 添加参与者到会议。
- **personalAppNavBotChat** - 导航到个人应用程序中的机器人程序。
- **personalAppNavTab** - 导航到个人应用程序中的选项卡。
- **photoLibraryPicker** - 点击了图像选取器中的“**打开照片库**”。
- **pickGalleryPhoto** - 从库中选择照片。
- **pickParticipantChatDetails** - 从列表中选择用户。
- **pickRecentPhoto** - 选择要共享的最近添加的图像。
- **pinChannel** - 固定一个频道以在团队和频道列表上方显示。
- **pinSelf** - 从操作表固定我自己。
- **pinUser** - 从操作表固定用户。
- **place_created** - 用户已创建一个共享地点。
- **place_deleted** - 用户已删除共享地点。
- **place_edited** - 用户已编辑共享地点。
- **播放** - 播放录制内容。
- **playVoicemail** - 已点击 **播放** 语音邮件项。
- **plusButtonClicked** - 选择 **加号按钮** (**+**).
- **pptNextSlide** - 作为演示者或私下观看下一张幻灯片。
- **pptPreviousSlide** - 作为演示者或私下观看的上一张幻灯片。
- **pptReturnToPresenter** - 转到 **实时** 幻灯片（演示者和其他人都在其中）。
- **pptStopPresenting** - 停止演示。
- **pptTakeControl** - 取得控制权。
- **preJoinAddRoom** - 在预加入下拉列表中选择“**添加会议室**”按钮，在“**添加会议室**”情景中选择“**加入**”。
- **preJoinAudioOff** - 在预加入下拉列表中选择“**音频关闭**”按钮。
- **preJoinAutoAddRoom** - 当附近有会议室时，选择“**立即加入**”。
- **preJoinBack** - 选中了 **后退** 或 **关闭** 按钮。
- **preJoinDenied** - 用户无法加入会议。
- **preJoinDeviceAudio** - 从下拉列表中选择 **使用设备音频加入**。
- **preJoinDialIn** - 在预加入下拉列表中选择“**拨入**”按钮。
- **preJoinDialInCall** - 用户确认预加入“**拨入**”请求。
- **preJoinDialInCancel** - 用户取消预加入“**拨入**”请求。
- **preJoinDialOut** - 在预加入下拉列表中选择“**给我回电**”按钮。
- **preJoinDialOutCall** - 用户确认预加入“**给我回电**”请求。
- **preJoinDialOutCancel** - 用户取消预加入“**给我回电**”请求。
- **preJoinPSTNOptions** - 用户为其他加入选项选择下拉列表。
- **priorityChange** - 在查看任务列表时应用优先级筛选器时触发。
- **priorityPickerClicked** - 当用户从任务列表筛选器屏幕导航到优先级筛选器选取器时触发。
- **privateMeetingJoin** - 从私人会议聊天中点击了“**会议加入**”按钮。
- **processInBG** - 在后台处理传入通知 (Android)。
- **processInFG** - 在前台处理传入通知 (Android)。
- **profileNameSaved** - 配置文件名称已更新。
- **progressItemClicked** - 确认用户已成功打开任务的进度选取器。
- **promotedToPresenter** - 用户在对话框中提升与会者 - **更改** 按钮。
- **provideFeedbackDismiss** - 关闭询问用户是否希望发送关于他们不喜欢该应用程序的反馈的提示。
- **provideFeedbackNo** - 对提示询问用户是否希望发送关于他们不喜欢该应用程序的反馈，回答“否”。
- **provideFeedbackYes** - 对提示询问用户是否希望发送关于他们不喜欢该应用程序的反馈，回答“是”。
- **provideRatingDismiss** - 在用户说他们喜欢这个应用后，关闭询问用户是否愿意在 App Store 上对我们进行评分的提示。
- **provideRatingNo** - 当用户在说他们喜欢此应用后是否愿意在 App Store上给我们评分时，回答“否”。
- **provideRatingYes** - 当用户在说他们喜欢此应用后是否愿意在 App Store上给我们评分时，回答“是”。
- **proximityPermissionDismissed** - 已解除权限横幅。
- **proximityPermissionGranted** - 允许弹出窗口。
- **proximityPermissionViewed** - 点击了权限横幅。
- **pushNotification** - 触发时间：
  - 通过通知启动。
  - 已选中推送通知。
  - 点击了“重新连接推送通知”。
  - **Reconnect failed** 点击了推送通知。
- **quickNotificationAction** - 当用户与通知上的某个快速操作响应交互时（例如可以直接从推送通知中给消息点赞）。
- **quickSelectImagePicker** - 快速选择。
- **quickStartLiveEventJoin** - 用户加入了快速入门直播活动。
- **quietHoursValues** - 在后退按钮导航中捕获“免打扰时间”状态。
- **quotedReplySent** - 用户使用上下文类型发送了答复消息。
- **reactAngry_CM** - 从上下文菜单作出“生气”的回应。
- **reactAngry_HB** - 从悬浮气泡作出“生气”的回应。
- **reactHeart_CM** - 从上下文菜单作出“爱心”回应。
- **reactHeart_HB** - 从悬浮气泡作出“爱心”回应。
- **reactLaugh_CM** - 从上下文菜单作出“大笑”回应。
- **reactLaugh_HB** - 从悬浮气泡作出“大笑”回应。
- **reactLike_CM** - 从上下文菜单点赞或给机器人消息点赞。
- **reactLike_doubleTap** - 双击点赞。
- **reactLaugh_HB** - 从悬浮气泡点赞。
- **reactSad_CM** - 从上下文菜单作出“悲伤”的回应。
- **reactSad_HB** - 从悬浮气泡作出“悲伤”的回应。
- **reactSurprised_CM** - 从上下文菜单作出“惊奇”的回应。
- **reactSurprised_HB** - 从悬浮气泡作出“惊奇”的回应。
- **reactRemoved_HB** - 当用户通过“回应摘要”页面删除回应时。
- **readReceipts** - 用户已启用功能。
- **redeemInvite** - 应用内兑换。
- **redeemLinkInAppStart** - 用户从 Teams 应用程序中发起兑换邀请链接。
- **refreshCalendarList** - 下拉以刷新日程视图。
- **refreshLinksGallery** - 当用户向下滑动以刷新链接库时。
- **removeAssignee** - 确认从“作业选取器”视图中删除了代理人（与在“作业选择器”视图之外选择 **x** 时触发的 *assignmentRemoved* 相反）。
- **removeMeeting** - 从已取消会议的“会议详细信息”页中选择“**从日历中删除**”。
- **removeParticipantFromEditMeeting** - 从“会议详细信息”页中选择“**编辑会议**”后删除参与者。
- **removeParticipantFromNewMeeting** - 设置新会议时从“计划程序”页中删除参与者。
- **removeReplyObject** - 用户从撰写中删除了回复对象。
- **removeUser** - 确认从“作业选取器”视图中删除了代理人（与在“作业选择器”视图之外选择 **x** 时触发的 *assignmentRemoved* 相反）。
- **removeUser_CM** - 当用户通过聊天参与者列表删除某人时。
- **removeUserConfirm** - 用户已确认“删除用户”对话框。
- **removeUserContextMenu** - 用户通过上下文菜单删除了参与者。
- **removeUserSwipe** - 用户通过轻扫删除了参与者。
- **reorderChannelItem** - 用户重新排序已固定频道。
- **reportAbuseConfirmation** - 当用户在确认屏幕上选择“**完成**”按钮时。
- **reportAbuseOpen** 在上下文菜单中选择“**报告问题**”按钮的次数。
- **reportAbuseSend** - 当用户选择“**报告**”按钮时，遥测应存储所选报告的类型。
- **replyChain** - 在回复链（会话）中选择“**新消息**”按钮或文本框。
- **replyChannel** - 频道中选择的“**回复**”按钮。
- **replyNavigation** - 已选择回复对象以导航到引用的文章。
- **replySendMessage** - 发送频道回复。
- **replyViaMsgOptions** - 用户已通过上下文菜单启动回复。
- **replyViaSwipe** - 用户通过轻扫启动回复。
- **requestActedOn** - 经理操作未完成班次请求时触发。
- **requestActionClicked** - 当用户请求操作时，例如选择了排班请求（一线员工 (FLW) 经理查看或一线员工。
- **requestDetailsClicked** - 选择排班请求时（一线员工 (FLW) 经理查看或一线员工）。
- **requestJoinTeam** - 已按下“**请求**”按钮。
- **requestSent** - 如有已发送请求，则会记录。
- **requestToJoinTeam** - 请求加入团队（公共或私人）。
- **requestToJoinTeamError** - 加入请求出错。
- **requestTypeClicked** - 确定人员从请求选取器中选择的请求类型。
- **resetLocalVault** - 用户重置并清除设备中的所有安全数据。
- **resolveIssue** - 在通知疑难解答浮出控件中选择了“**解析**”以导航到阻止程序应用。
- **responseClicked** - 用户选择回复页面。
- **retryButtonClicked** - 已选中“**重试**”按钮。
- **returnToMessage** - 选择了“**返回**”按钮以导航回邮件。
- **runningLate** - 用户迟到。
- **safeLink** - 链接已验证为安全。
- **saveEditMeeting** - 更新会议后，在“会议计划程序”页上选择“**保存**”按钮。
- **saveNewMeeting** - 在“会议计划程序”页上选择“**保存**”按钮。 记录成功保存的会议以及由于客户端或服务错误而无法创建的会议的百分比。
- **savePlanClicked** - 从应用程序默认打开的新计划创建者中选择了“**创建**”时触发。
- **scenarioChannelDashboard** - 用户导航到聊天仪表板上的磁贴。
- **scenarioDashboardNav** - 用户导航到对话中的仪表板选项卡（聊天选项卡的同级）。
- **scheduledMeetingJoin** - 从计划会议对象中选择“**会议加入**”按钮。
- **scrollCalendarList** - 测量日历中的滚动。
- **scrollDatePicker** - 滚动日历日期选取器控件。
- **searchAbandoned** - 确定是否已放弃搜索。
- **searchCancelled** - 确定是否：
  - 搜索成功或用户放弃搜索。
  - 搜索查询成功。
- **searchContacts** - 从通话清单中搜索。
- **searchInitiated** - 确定是否可以触发搜索，以及搜索触发器的源。
- **searchMeetingParticipants** - 搜索要添加到计划程序表单中的参与者。 区分创建的约会数与创建的会议数。
- **searchResultsClicked** - 确定：
  - 如果能成功找到相关结果。
  - 如果搜索结果来自“所有”选项卡而不是单个域。
- **searchTabClicked** - 确定：
  - 搜索结果的域信息 - 用于人员、聊天、消息和文件。
  - 如果成功找到相关结果。
- **seeAllMeetingParticipants** - 从“会议详细信息”页面中选择“**全部查看**”，或查看所有参与者。 记录日历漏斗的各项用户数据，其中日历会议详细信息起着重要作用，它有助于验证“拨入”、Teams 会议、RSVP 等的选择..
- **seeMeetingDescription** - 打开“会议详细信息”页，或从“会议详细信息”页中选择“**查看更多**”有关会议的说明。 记录日历漏斗的各项数据，其中日历会议详细信息起着重要作用，它有助于验证“拨入”、Teams 会议、RSVP 等的选择..
- **seeRsvpMeetingOptions** - 从 **RSVP** 弹出窗口中选择“**通知组织者**”，或从“会议详细信息”页中选择 RSVP 选项。
- **selectActivityType** - 捕获订阅源项上的选定手势。
- **selectCalendarDate** - 在日历日期选取器控件上选择特定日期。
- **selectDevice** - 在显示应用程序中选择特定设备。
- **selectGeneralSetting** - 转到“常规设置”。
- **selection** - 选择了设备联系人或公司联系人。
- **selectMeetingChicklet** | 会议。
- **selectMeetingRsvpOption** - 选择 **RSVP** 按钮以选择选项。
- **selectMeetingRsvpOptions** - 选择 **RSVP** 按钮以选择选项。
- **selectPersonalList** - 确认用户通过点击个人任务列表成功导航到该列表。
- **selectPlannerList** - 确认用户通过点击共享任务列表成功导航到该列表。
- **selectSettingOption** - 转到汉堡菜单中的“**设置**”选项卡。
- **selectTheme** - 启用深色主题。
- **selectUser** - 确认已成功为任务选择了代理人。
- **selfLongPress** - 长按我自己。
- **Send_earlycancelledCQF** - 用户在 CQF 早前取消的通话表单上提交反馈。
- **send_map_pin_clicked** - 用户发送静态位置。
- **Send_ratemycallCQF** - 用户在 CQF 评价我的通话表单上提交反馈。
- **Send_ratemyliveeventCQF** - 用户在 CQF 评价我的实时事件表单上提交反馈。
- **sendForward** - 用户确认从转发选取器发送转发消息。
- **sendImage** - 发送图像。
- **sendLocation** - 发送位置。
- **sendMsg** - 在答复中选择“**发送**”。
- **sendRequestBulkClicked** - 每次发送批量请求时都会记录一次。
- **sendRequestClicked** - 已选择“**发送的排班请求**”。
- **sendVoiceMessage** - 释放“**录制**”按钮。
- **Setting/Dismiss** - 设备联系人设置。
- **settingsNavReadReceiptNotice** - 用户从功能通知转到设置。
- **settingsOpened** - 当用户的设备时区与团队时区不匹配，且用户转到“设置”时，会触发此事件。
- **setupPinVault** - 用户为其帐户保存安全 PIN。 
- **shareCharmCompleted** - 用户已通过应用程序共享超级按钮完成邀请链接的共享。
- **shareCharmOpened** - 用户已通过应用程序共享超级按钮启动邀请链接的共享。 
- **shareFile** - 选择“**共享文件**“时触发。 也有助于检查：
  - 用户能够启动共享文件操作。
  - 用户可以成功共享文件。
- **shareHistory** - 已选择共享历史选取器。
- **shareInto** -- 用户将其他应用程序中的内容共享到 Teams 中。
- **sharePlanToChat** - 共享列表作为 chicklet 手动从任务应用程序共享到群聊，检查通过后端消息服务发送的 chicklet。
- **sharePPTFromChannels** - 已选择 **Teams 和频道**。
- **sharePPTFromOneDrive** - 已选择 **OneDrive**。
- **shareRecording** - 共享录制内容。
- **shareScreen** - 启动或停止屏幕共享。
- **shareShift** - 共享排班时提供的信息。
- **shareShiftsClicked** - 未完成班次的详细信息。
- **shareTray** - **共享。。。** 在操作表中选择。
- **shiftAssigneeClicked** - 显示特定排班详细信息的“排班日历视图”。
- **shiftDetails** - 通过它可查看排班的详细信息。
- **shiftDetailsCalendar** - 用户转到排班详细信息。
- **shiftDetailsMyShifts** - 在“**日程安排**”选项卡中单击“**日历**”。
- **shiftDetailsTodaysCoworkers** - 在上班打卡屏幕上，选择了“**开始**”或“**结束休息时间**”按钮。
- **shortCircuitContactCount** - 从联系人获取中接收到的与通讯簿匹配的短路联系人数。
- **showBanner** - **WiFi 连接的次数，未显示 Internet** 横幅。
- **showCard** - 点击卡片按钮。卡片是一种关键平台构造，并衡量其使用情况和模式是了解平台使用情况并随时查看客户端上的潜在问题所必需的。
- **shownReadReceiptNotice** - 带设置选项的用户显示功能提示。
- **signIn** - 在欢迎页上选择了 **登录**，或者点击了 **登录** 按钮。
- **SignInWithOTP** - 用户选择该选项以来宾身份使用一次性密码 (OTP) 登录。 
- **signUp** - 已选择“**创建免费帐户**”或“**免费注册**”。
- **SignUpFromSignIn**- 用户点击 **从登录创建新帐户** 选项。
- **simultaneousCallForward** - 触发时间：
  - 设置了同时呼叫转发目标。
  - 已启用同步呼叫转移（启用来电时振铃并设置振铃）。
- **skipVerificationForLink** - 用户已选择跳过验证。
- **smartReply** - 单击智能答复切换按钮。
- **SMSSendMessage** - 用户发送短信。
- **sortChanged** - 用户在查看任务列表时更改排序顺序时触发。
- **SSOAccountListItem**：当用户点击 SSO 帐户登录时触发。
- **startEditing** - 选中了“**编辑**”按钮。
- **startPresentPhoto** - 开始演示照片。
- **startPresentVideo** - 开始展示视频。
- **startPSTNCall** - 因以下原因触发：
  - 全局搜索（人员）中的 PSTN 结果。
  - 设备 contactCard 发出的 PSTN 呼叫。
  - callList 发出的 PSTN 呼叫。
  - 使用拨号盘的 DialPSTN 号码。
- **startRecording** 开始录制。
- **startVoicemailCall** - 已选择“**改变语音邮件问候语**”。
- **static_place_selected** - 用户拖动地图以选择静态位置。
- **statusCheckBoxClicked** - 任务项已完成或未完成时触发。
- **statusMsgCancel** - 用户取消对状态邮件的更改。
- **statusMsgExpiry** - 用户设置到期时间。
- **statusMsgSet** - 用户设置新状态邮件。
- **statusPageViaContactCard** - 用户通过联系人卡片输入状态撰写体验。
- **statusPageViaHamburger** - 用户通过汉堡进入状态撰写体验。
- **stop_location_sharing_logout** - 用户注销应用。
- **stopMeetingButton** - 用户离开大厅而未被允许进入会议室的次数。
- **stopPresentPhoto** - 停止演示照片。
- **stopPresentVideo** - 停止演示视频。
- **stopRecording** - 停止录制。
- **structuredMeetingsBannerDismiss** - 用户取消通知其会议角色的横幅。
- **stuckOnConnectingDialInSelected** - 在抽屉上选择“**拨入**”。
- **stuckOnConnectingRetrySelected** - 在抽屉上选择“**重试**”。
- **stuckOnConnectingShownDismissed** - 用户已关闭抽屉。
- **suggested_place_selected** - 用户通过选择建议位置来共享静态位置。
- **切换**- 从应用切换租户或帐户。 这是主动度量帐户/租户切换问题并提供平滑的帐户/租户切换体验所必需的。
- **switchTeamAction** -用户在打卡时钟内切换团队。 这将在用户选择要切换到哪个团队后触发。
- **switchTeamsDialogTriggered** - 用户查看“**排班**”选项卡。
- **tabActionCopyLink** - 用户在移动设备上如何发现和使用选项卡复制链接。
- **tabActionMoreOptions** - 从选项卡中了解省略号 (**…**) 用法。
- **TabActionOpenInBroopenser** - 使用浏览器使用情况打开。如果用户更喜欢在 Teams 外部打开选项卡，有必要了解这一点。
- **tabActionOpenInBrowserFromTab** - 了解从选项卡中在浏览器使用情况中打开，以获得更多选项-可发现性和使用情况。
- **TabActionOpenInTeams** - 使用中打开。在了解选项卡是否默认设置为在 Teams 中打开时，这一点是关键。
- **tabActionRemove** - 了解删除选项的可发现性以及该功能的用法。
- **tabActionRename** - 了解可发现的重命名以及功能的用法。
- **tabActionSetting, Android - fix** - 用户如何在移动设备上发现和使用标签配置。
- **table** - 选择表格。
- **tabListMoreOptions** - 了解选项卡更多选项的用法。
- **tabOpen** - 在打开的选项卡中记录成功，或者是否在打开选项卡的方式中存在问题。
- **tabViewed** - 仅当发送的请求是交换请求时，才记录到 **Teams 排班** 选取器中。
- **takePhoto** - 拍照。
- **takePhotoPicker** - 在图像选取器中选择 **拍照**。
- **tapChicletExpand** - 用户如何在移动设备上预览卡片。
- **tapDatePickerHandle** - 展开日历日期选取器控件。
- **tapSettings** - 在移动设备上重新配置应用程序的用户数。
- **tasksAppLaunchAdaptiveCard** - 任务应用程序在群聊中从自适应卡打开，通过 IC3 服务的 URL 检查应用程序启动情况。
- **tasksAppLaunchComposeExtension** - 任务应用程序在群聊中从撰写扩展打开，通过 MT 服务检查应用程序启动情况。
- **tasksAppLaunchDashboard** - 任务应用程序从仪表板磁贴或特定计划打开，通过 MT 服务检查应用程序启动。
- **tasksAppLaunchDashboardSeeAll** - 任务应用程序从仪表板上的“**查看全部**”按钮打开，通过 MT 服务检查应用程序启动。
- **tasksAppLaunchDefault** - 任务应用程序从底部抽屉打开，通过 MT 服务检查应用程序启动情况。
- **tabCalendarClicked** - 用户从团队选取器中选择了团队。
- **teamChannelChanged** - 当用户从计划列表中选择并导航到计划时触发。仅发送到 appInsights，不能发送到 Aria。
- **teamCreate** - 用户选择创建新团队的选项。
- **teamEdit** - 用户编辑他们拥有或管理的团队的某些方面。
- **teamNav** - 查看 Teams 的菜单选项。
- **teamsDeviceCallResumed** - 用户使用蓝牙连接外设（移动电话接口）重新激活保持的通话。
- **teamSelectedClicked** - 当用户选择为时间表 **选定团队** 时。
- **teamShiftPickerClicked** - 当用户添加新的中断项时。 用户保存改变后立即记录事件。
- **租户切换** - 在切换租户上。MTMA（多个租户和多个帐户）的功能成功指标，这有助于主动识别并解决问题，提供流畅的切换体验。
- **tenantSwitchUnsupportedError** - 租户不支持错误（当用户看到错误时）。MTMA（多个租户和多个帐户）的功能成功指标，提供有关帐户或租户切换错误的遥测，以便我们可以主动识别并修复问题，并提供流畅的切换体验。
- **timeClockClicked** -用户在“我的排班”选项卡上选择“**打卡时钟**”。
- **timeOffReasonClicked** - 确定是否引用了休假原因。
- **timesheetAddClicked** - 当用户添加其休息时间注释时。 用户保存改变后立即记录事件。
 **timesheetBreakAdded** - 添加新时钟项。 保存更改后将记录事件。
- **timesheetBreakEdited** - 当用户确认其时间表时。 当用户在模式中点击确认时将记录该事件。
- **timesheetBreakNoteAdded** - 当用户删除其时间表时。 当用户在模式中确认删除时将记录该事件。
- **timesheetClockAdded** - 用户为时间表选择“编辑”时。
- **timesheetClockEdited**  当用户在已编辑的时间表上选择“保存”时。
- **timesheetConfirmed** - 当用户向其时间表编辑添加注释时。 用户保存改变后立即记录事件。
- **timesheetDeleted** - 用户是否设置或没有设置排班提醒，以及用户希望在排班前收到警报的分钟数。
- **timesheetEditClicked** - 用户配置遥测。
- **timesheetEditSaved** - 用户点击用户配置文件中的时间表以打开该用户的时间表。
- **timesheetNoteAdded** - 查看已批准的休假。
- **titleChanged** - 任务项标题更改时触发，每个字符更改时触发。
- **toast** - 已选中应用内 toast。
- **toggleChannelsInChat** - 打开或关闭功能。 统一聊天和频道体验的功能成功指标。
- **toggleClicked** - 选择了切换。
- **transferNow** - 触发时间：
  - 用户选择“**转接**” > “**立即转接**”。
  - 转接目标设置为“人员”。
  - 转接目标设置为“电话号码”。
- **translateFailed** - 翻译失败（脱机除外）。 邮件翻译功能的功能成功指标。
- **trigger_created** - 用户已创建地理围栏。
- **trigger_deleted** - 用户已删除地理围栏。
- **unansweredCallForward** - 设置了未接听的呼叫转移目标。 还启用未接听呼叫转移（启用了电话振铃和未如果无人应答）。
- **unblockCaller** - 取消阻止：
  - 操作表中的联系人或号码。
  - 联系人卡片中的联系人或号码。
  - 设置中的号码。
- **unblockChat** - 取消阻止机器人聊天。
- **unpinChannel** - 取消固定频道。
- **unpinSelf** - 从操作表取消固定你自己。
- **unpinUser** - 从操作表取消固定用户。
- **unsafeLink** - 已确定链接是不安全的。
- **updatePersonalTask** - 确认已成功更新个人任务。
- **updatePlaybackSpeedVoicemail** - 已更改语音邮件播放速度值。
- **updateTask** - 确认更新任务操作失败。
- **updateTaskState** - 确认任务状态已更新。行动。
- **升级** - 在“**更多**”菜单中选择“**升级**”按钮。
- **上载文件** - 用户选择 **从设备上载**。
- **uploadSelectedFile** - 在这些情况下触发：
  - 在频道中成功上传文件。
  - 在聊天中成功上传文件。
  - 在回复窗口上载文件。
  - 在群聊中成功上传文件。
  - 核心方案的用法。
  - 频道中上载方案的开始。
  - 聊天中上载方案的开始。
  - 频道中上载方案结束的开始。
  - 已成功将文件上传到“**文件**”选项卡。
  - 如果在文件上载期间对提示进行了操作。
  - 如果所选文件上载成功。
- **uploadSelectFile** - 成功选择文件；成功选择“**上载文件**”按钮。
- **urgentMessageSelect** - 从优先级上下文菜单中选择紧急消息。
- **urgentMessageSend** - 发送紧急消息。
- **url** - URL。
- **urlPreview** - URL 预览。
- **urlPreviewAdd** - 添加 URL 预览。
- **urlPreviewOpen** - URL 预览打开。
- **urlPreviewRemove** - 已删除 URL 预览。
- **userConfiguration** - 查看待处理的休假请求。
- **userJoinedViaShareLink** - 用户从链接加入了会议。
- **userLongPress** - 长按参与者。
- **userProfileOpened** - 用户选择“**用户**”图标以打开用户配置文件。
- userTimesheetOpened** - 用户从用户配置文件中选择时间表以打开此人的时间表。
- **useWifiForAudioDialog** - 当系统提示时，用户选择“**没问题**”，而管理员已经阻止了使用移动数据的音频和视频呼叫。
- **useWifiForVideoDialog** - 触发时间：
  - 当管理员阻止使用移动数据的视频呼叫时，在系统提示时选择“**没问题**”。
  - 正在尝试在会议中启用视频，而管理员已在手机网络上阻止它。
  - 当管理员阻止使用移动数据的会议视频呼叫时，在系统提示时选择“**没问题**”。
- **videoUserDoubleTap** - 双击视频参与者。
- **viewChannelMembers** - 查看频道成员列表。
- **viewContactCard** - ContactCard 选择自：
  - CallHistory 项。
  - 语音邮件项目。
  - 通话清单。
- **viewed** - 用户已查看页面。
- **viewFullAllDayMeetingList** - 移动设备上的“日程”视图。
- **viewLobbyFromBanner** - 用户从通知横幅中选择“**查看大厅**”的次数。
- **viewMeetingDetails** - 在“会议详细信息”页上选择“**...**”菜单。 关于移动日历上“**更多**”菜单的用法。
- **viewMeetingOccurrence** - 打开定期会议实例的会议详细信息。 遥测记录整个日历漏斗中的用户数据，其中日历会议详细信息起着重要作用，有助于验证“选择拨入”、Teams 会议、RSVP等。
- **viewMeetingSeries** - 在以下情况下记录会议系列的成功呈现：
  - 从实例切换到系列会议详细信息页时。
  - 从“会议详细信息”页面选择“**查看系列**”时。
- **viewOrgChart** - 组织结构图的基本用法遥测。
- **viewRequests** - 已按下“**查看请求**”按钮。
- **voiceDataCollectionOptOut** - 用户通过单击横幅从移动设备中选择退出录制。
- **voicemail - No AS Assigned** - 演讲者点击语音邮件项目。
- **whiteboardUsed** - 用户在白板上注释（Web 视图上的任何操作）。
- **wiki - No AS assigned** - Wiki 用法遥测。
- **poorNetworkBanner** - 显示较差网络横幅。
- **badNetworkBanner** - 显示错误网络横幅。

### <a name="panelview"></a>视图面板

> [!NOTE]
> 关于视图面板事件属性的详细信息，请参阅[与视图面板事件一起发送的属性](#properties-sent-with-panelview-events)。

- **appInstall**：在安装后用户首次打开应用时触发。
- **fileDeleteFailed** - 文件删除操作失败时触发。
- **fileDeleteSuccess** - 文件删除操作成功时触发。
- **filePreview** - 在以下情况下触发：
  - 在文件预览屏幕中点击“共享”选项时。
  - 在文件预览屏幕中点击“复制”选项时。
  - 在文件预览屏幕中点击“下载”选项时。
  - 成功加载文件预览时。
- **files** - 在以下情况下触发：
  - 在 Teams 应用中预览文件时。
  - 在 OneDrive 文件屏幕点击“文件上载”选项时。
  - 在文件预览屏幕中点击“复制链接”选项时。
  - 文件共享屏幕关闭时。
  - 打开“文件选项”菜单或单击该菜单中的某个选项时。
  - “通话中”文件屏幕打开时。
  - 点击打开文件时。
- **filesChannel** - 打开频道文件屏幕时触发。
- **fileSources** - 打开“文件选项”菜单或单击该菜单中的某个选项时触发。
- **filesPersonal** - 在 OneDrive 或“最近使用的文件”屏幕中加载一批文件时触发。
- **fileUploadDeleteTriggered** - 从消息区域删除或拆离文件附件时触发。
- **fileUploadFailed** - 文件上传操作失败时触发。
- **fileUploadIndividualNotification** - 当文件上载通知的内容更改或与通知交互时触发。 这些交互可能包括如轻扫以消除通知或点击通知等手势。
- **fileUploadSuccess** - 文件上传操作成功时触发。
- **fileUploadSummaryNotification** - 当文件上载摘要通知的内容更改或与通知交互时触发。 这些交互可能包括如轻扫以消除通知或点击通知等手势。
- **meetingFiles** - 打开会议文件屏幕时触发。
- **meetNowActionSheet** - 在用户创建“立即开会”的会议时触发。
- **navPersonalFiles** - 执行文件屏幕导航时触发。
- **signInSSOPage**：用户在登录时查看单一登录页时触发。
-- **signInError**：用户在登录时遇到任何错误时触发。 这是主动识别和修复用户在登录期间遇到的问题所必需的。 
-- **TfLSignInSuccessful**：当用户成功登录到个人 Microsoft 帐户时触发。 这是了解登录和注册可靠性以及主动识别和修复问题所必需的。
-- **TfWFreemiumSignInSuccessful**：当用户成功登录到 freemium 帐户时触发。 这是了解登录和注册可靠性以及主动识别和修复问题所必需的。
-- **TfWSignInSuccessful**：当用户成功登录到工作或学校帐户时触发。 这是了解登录和注册可靠性以及主动识别和修复问题所必需的。
- **appDrawer** - 成功打开应用抽屉时触发。
- **appPolicyChange** - 当用户在本地重置并保存新选项卡顺序时触发。
- **app_stageview** - 成功呈现阶段视图时触发。

### <a name="scenario"></a>使用场景

> [!NOTE]
> 有关场景事件属性的详细信息，请参阅 [与方案事件一起发送的属性](#properties-sent-with-scenario-events)。
> 
- **acquire_resource_token_interactive**- 通过交互式登录获取身份验证令牌时触发的必需服务调用。 
- **acquire_resource_token_silent**- 通过无提示登录获取身份验证令牌时触发的必需服务调用。
- **add_buddy** - 捕获添加联系人的状态。
- **app_crash2** - 在应用意外崩溃时触发。 提供有关 Teams 应用崩溃频率的信息。 
- **app_incremental_sync_launch** - 确认药丸计数已为冷启动成功更新。
- **app_incremental_sync_resume** - 确认药丸计数已为暖/热启动成功更新。
- **app_start_cold** - 监视应用冷启动（仅限 Android）。
- **app_start_hot** - 监视应用热启动（仅限 Android）。
- **app_start_warm** - 监视应用暖启动（仅限 Android）。
- **auth_adal_tokens**- 执行无提示身份验证所需的服务调用。 当用户启动应用或令牌在到期时刷新时触发。
- **chat_add_giphy** - 确认 Giphy GIF 渲染操作已成功或失败。
- **chat_send_message_sfc**- 在 SfC 互操作聊天中发送聊天消息时触发。
- **cortanaError** - 监视 Cortana 错误发生。
- **cortanaView** - 监视 Cortana 画布出现。
- **cortanaRestart** - 监视 Cortana 重启。
- **cortanaSetNewConversation** 监控 Cortana 设置新对话。
- **cortanaSpeechRecognization** 监控 Cortana 语音识别延迟。
- **cortanaStart** 监控 Cortana 后端启动。
- **cortanaStartListening** 监控 Cortana 开始收听。
- **cortanaStopListening** 监控 Cortana 停止收听。
- **cortanaThinking** 监控 Cortana 状态更改为思考（等待服务的响应）。
- **cortanaTokenRefresh** 监控 Cortana 令牌在前台刷新。 
- **cortanaWarmingUp** 监控 Cortana 预热开始（Cortana 已打开，但令牌仍在获取）。
- **cortana_admin_policy_refresh** - 监控 Cortana 管理员策略刷新。
- **cortana_background_token_refresh** - 监控 Cortana 令牌刷新。
- **cortana_initialization** - 监控 Cortana 初始化 步骤。
- **cortana_sdk_events** - 监控 Cortana 启动相关事件。
- **cortana_skill_action_execution** - 监控 Cortana 操作执行。
- **cortana_skill_action_delay** - 确认延迟操作开始。
- **cortana_watchdog** - 监控 Cortana 监视器恢复过程。
- **create_default_plan_and_nav_to_view** - 确认已成功创建默认共享任务列表，以及用户在操作后登录到结果视图所用的时间。
- **create_new_chat_thread_sfc**- 为 SfC 互操作聊天创建新的聊天线程时触发。
- **create_personal_plan_and_nav_to_view** - 确认成功创建个人任务列表，以及用户在操作后登录到结果视图所用的时间。
- **create_personal_task** - 确认成功创建个人任务项。
- **create_planner_plan_and_nav_to_view** - 确认成功创建共享任务列表，以及用户在操作后登录结果视图所用的时间。
- **create_planner_task** - 确认成功创建共享任务项目。
- **forwardExistingAmsObject** 确认媒体转发操作成功或失败。
- **delete_personal_plan** - 确认成功删除个人任务列表。
- **delete_personal_task** - 确认成功删除个人任务项。
- **delete_planner_plan** - 确认成功删除共享任务列表。
- **delete_planner_task** - 确认成功删除共享任务项。
- **json_parse_failure**- 提供有关 JSON 分析问题的频率的信息。
- **fetch_me_profile** - 用户配置文件创建状态。
- **getProfilePicture**- 获取用户配置图片必需的服务调用。 
- **get_resource_token_async**：异步获取 Azure Active Directory 资源令牌所需的服务调用。
- **get_resource_token_sync**：同步获取 Azure Active Directory 资源令牌所需的服务调用。
- **get_sender_sub_scenario** - 在活动中获取发送方子方案。
- **interactiveAuthNopa2** – 在无密码用户中断以进行交互式身份验证时触发。
- **load_chat_plans_list** - 确认成功获取聊天计划视图的计划。
- **load_home_page** - 确认成功获取主要主页视图的个人和共享任务列表。
- **load_personal_task_list** - 确认成功获取任务列表视图的个人任务列表的任务。
- **load_shared_task_list** - 确认成功获取任务列表视图的共享任务列表的任务。
- **load_smart_task_list** - 确认成功获取任务列表视图的智能任务列表任务。
- **meetingAttachmentRender** - 确认呈现会议附件。
- **meetingInsightFetch** - 确认获取会议相关内容。
- **meetingInsightLocatorRender** - 确认呈现会议相关内容定位符提示。
- **meetingInsightRender** - 确认呈现会议相关内容。
- **meetingInsightVisible** - 确认会议相关内容可见。
- **open_image** 确认全屏图像渲染成功或失败。
- **rename_personal_plan** - 确认成功重命名个人任务列表。
- **rename_planner_plan** - 确认成功重命名共享任务列表。
- **save_image** 确认图像保存操作成功或失败。
- **saveMeProfile**- 用户保存配置文件时触发的所需服务调用
- **share_image** 确认图像共享操作已成功或失败。
- **smart_reply_enabled** - 确认当前用户已启用智能答复。
- **smart_reply_received** - 确认已收到智能答复建议。
- **smart_reply_banned** - 确认当前用户无法显示智能答复。
- **park_call_for_hold_v2** - 使用呼叫暂停确认呼叫保留成功或失败。
- **unpark_call_for_hold_v2** - 使用未暂停呼叫确认恢复呼叫成功或失败。 
- **update_planner_task_and_nav_to_view** - 确认成功更新共享任务项，以及用户在操作后登陆结果视图所用的时间。
- **update_personal_task_and_nav_to_view** - 确认已成功更新个人任务项，以及用户登陆结果视图所用时间。 
- **updatePlannerTask** - 确认用户已成功更新共享任务列表中的任务。
- **upload_images** 确认图像上传操作成功或失败。
- **upload_voice_messages** 确认语音消息上传操作成功或失败。
- **voiceMessageUpload** 确认语音消息上传操作成功或失败。
- **cancel_channel_meeting** 确认取消频道会议已成功或失败。
- **cancel_meeting** 确认取消会议已成功或失败。
- **cancel_private_meeting** 确认取消私人会议已成功或失败。
- **edit_channel_meeting** 确认频道会议编辑操作已成功或失败。
- **edit_meeting** 确认会议的编辑操作已成功或失败。
- **server_fetch_agenda_view** 确认使用中间层 API 进行的日历事件同步已成功或失败。
- **server_fetch_date_picker_view** 确认使用 Outlook REST API 进行的日历事件同步已成功或失败。
- **server_fetch_agenda_view_group** 确认使用中间层 API 为 TFL 组进行的日历事件同步已成功或失败。
- **server_fetch_date_picker_view_incremental** 确认使用 Outlook REST API 进行的日历事件增量同步已成功或失败。
- **meeting_details** - 确认会议详细信息同步已成功或失败。
- **show_meeting_participants** - 确认显示会议参与者名单已成功或失败。
- **搜索** - 确认整个搜索会话已成功或失败。
- **time_based_retention_shared_channel** - 捕获用于修剪数据库的性能数据。
- **toggle_searchability** - 捕获用于标记/取消标记别名的网络调用状态。
- **sync_user_entitlements_and_app_definitions** - 提取 aggregatedEntitlements 所需的服务调用。
- **bots_load_mediacards** - 在聊天和频道中配置连接器卡片时实例化捕获。
- **bots_load_one_card** - 在与机器人聊天时，捕获是否存在并加载了至少一张卡片。
- **load_assignments** - 捕获用于加载分配应用的异常处理。
- **load_channel_tab** - 捕获频道选项卡的加载。（仅限 Android）
- **load_messaging_extension_results** - 捕获消息传递扩展搜索/查询结果的加载。 （仅限 Android）
- **load_static_tab** - 捕获静态选项卡的加载。（仅限 Android）
- **app_authenticated** - 确认身份验证成功且已提取令牌。 （仅限 Android）
- **blocked_by_conditional_access** - 在身份验证中接收条件访问阻止的错误代码时。 （在这种情况下，系统尝试强制刷新主令牌）。 （仅限 Android）
- **get_resource_token_sync** - 在系统尝试同步提取应用资源的令牌时触发。 （仅限 Android）
- **get_resource_token_async** - 在系统尝试异步提取应用资源的令牌时触发。 （仅限 Android）

## <a name="oneplayer-events"></a>OnePlayer 事件
> [!NOTE]
> 对于 OnePlayer 事件，仅应用 [OnePlayer 事件属性列表](#property-lists-for-oneplayer-events) 中列出的属性。
### <a name="oneplayer-user-action-events"></a>OnePlayer 用户操作事件
- **PlayerPlay** - 确认用户是否点击 OnePlayer 视图中的“播放”按钮。
- **PlayerPause** - 确认用户是否点击 OnePlayer 视图中的“暂停”按钮。
- **PlayerSeek** - 确认用户是使用 OnePlayer 视图中的查找栏还是“”向前/向后”按钮查找视频（仅限 iOS）。
- **VideoPlayerSeekForward** - 确认用户是使用 OnePlayer 视图中的查找栏还是“向前”按钮查找视频（仅限 Android）。
- **VideoPlayerSeekBackward** - 确认用户是使用 OnePlayer 视图中的查找栏还是“向后”按钮查找视频（仅限 Android）。
- **ChangePlaybackSpeed** - 确认用户是否选择了新的播放速度。
- **changePlaybackQuality** - 确认用户是否选择了新的视频质量进行播放。
- **ShareVideo** - 确认用户是否已点击“共享”图标。
- **PlayerClose** - 确认用户是否已点击“关闭”图标。
- **VideoCaptionsOn** - 确认用户是否已打开字幕。
- **VideoCaptionsOff** - 确认用户是否已关闭字幕。
- **ChangePlayerOrientation** - 确认用户是否更改了设备的方向。
- **OpenPlayerSettingsMenu** - 确认用户是否已打开“设置”菜单。
- **OpenPlaybackSpeedMenu** - 确认用户是否已打开“播放速度”菜单。
- **PlayerAction** - 主机应用提供的自定义操作。

### <a name="oneplayer-playback-events"></a>OnePlayer 播放事件
- **PlayerHeartbeat** - 这是一个定期事件，可将玩家的当前状态和播放发送到日志。

## <a name="property-lists"></a>属性列表

### <a name="properties-sent-with-all-events"></a>与所有事件一起发送的属性

| 属性名称                    | 说明                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | 事件生成时间                                                |
| EventInfo_Name                   | 事件名称-用于区分事件类型               |
| EventInfo_BaseType/name          | 事件名称 - 用于区分一个事件中的事件类型   |
| EventInfo_Source                 | 事件生成源                                       |
| AppInfo_Language                 | 应用语言                                                         |
| AppInfo_ETag                     | 分配给用户的 试验 ID                                     |
| DeviceInfo_OsBuild               | 操作系统的内部版本                                              |
| UserInfo_Mri                     | 键入用户 ID。                                                       |
| Session_RunId                    | 会话 ID 的类型                                                 |
| DeviceInfo_DetailModel           | 设备的型号                                                  |
| UserInfo_TimeZone                | 用户的时区                                                |
| DeviceInfo_OsName                | 设备 OS 名称                                                       |
| DeviceInfo_NetworkProvider       | 设备网络提供商                                              |
| DeviceInfo_Model                 | 设备型号                                                         |
| DeviceInfo_NetworkType           | 设备网络类型                                                  |
| UserInfo_Language                | 用户语言 - 类似于应用语言                              |
| client_ring/UserInfo_Ring        | 帮助向早期采用者发布功能的用户环           |
| UserInfo_Id                      | 用户 ID                                                              |
| UserInfo_TenantId                | 租户 ID                                                            |
| EventInfo_SdkVersion             | 用于生成事件的 SDK 版本                               |
| DeviceInfo_Id                    | 设备 OS 提供的设备 ID                                      |
| eventpriority                    | 事件的优先级                                                 |
| DeviceInfo_Make                  | 设备制造商                                                  |
| AppInfo_Version                  | 应用的版本                                                   |
| DeviceInfo_OsVersion             | 设备 OS 版本                                                    |
| Session_Id/SessionId             | 请求的会话 ID                                            |
| Session_Environment              | 会话环境                                                  |
| isNetworkIssue                   | 如果在服务请求时出现网络问题，则捕获信息 |
| UserRole                         | 租户中的用户角色                                                |
| Tenant_Model                     | 捕获帐户是免费增值帐户还是企业帐户          |
| licenseType/UserInfo_LicenseType | 分配给用户的许可类型。                                    |
| UserLocale                       | 正在访问应用程序的区域设置                                |
| Intune_sdkVersion                | Intune SDK 版本                                            |
| Intune_sdkBundleVersion          | Intune SDK 详细版本                                   |
| AppInfo_Environment              | 正在访问应用的环境                         |

### <a name="properties-sent-with-panelaction-events"></a>与动作面板事件一起发送的属性

| 属性名称         | 说明                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | 被用户操作访问的资源的 Uri                  |
| Panel_Uri             | 提供给用户的面板Uri                             |
| Action_Gesture        | 用户在应用程序上执行的手势类型                       |
| Action_ScenarioType   | 与功能商业指标相关的功能分组       |
| Panel_Type            | 用户访问的面板类型                                    |
| Action_Outcome        | 用户所执行的操作的结果                            |
| Team_Id               | 用户进行操作的团队的ID           |
| Module_Type           | 承载用户操作所在模块的类型                        |
| Module_Name           | 承载用户操作所在模块的名称                        |
| Module_Summary        | 承载用户操作的模块摘要                      |
| Thread_Id             | 用户访问的线程的 ID                         |
| Panel_PreviousUri     | 之前的面板的 URI                                          |
| Panel_Region          | 应用程序中托管了面板的区域                       |
| Panel_LaunchMethod    | 启动面板的方法                        |
| Panel_PreviousType    | 之前的面板的类型                                         |
| Thread_Type           | 用户访问的线程类型                                    |
| Module_State          | 用户访问的模块的状态                               |
| Action_Scenario       | 与商业指标相关的一组功能中的功能 |
| Panel_LaunchSource    | 已启动的面板的数据源信息                  |
| Tab_Type              | 用户访问的选项卡类型                                   |
| Team_Type             | 用户访问的团队类型                                      |

### <a name="properties-sent-with-panelview-events"></a>与视图面板事件一起发送的属性

| Panel_Uri          | 提供给用户的面板Uri                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | 用户访问的面板类型                          |
| Team_Id            | 用户进行操作的团队的ID |
| Thread_Id          | 用户访问的线程的 ID               |
| Panel_PreviousUri  | 之前的面板的 URI                                |
| Panel_Region       | 应用程序中托管了面板的区域             |
| Panel_LaunchMethod | 启动面板的方法              |
| Panel_PreviousType | 之前的面板的类型                               |
| Thread_Type        | 用户访问的线程类型                          |
| Panel_LaunchSource | 已启动的面板的数据源信息        |
| Tab_Type           | 用户访问的选项卡类型                         |
| Team_Type          | 用户访问的团队类型                            |

### <a name="properties-sent-with-scenario-events"></a>与场景事件一起发送的属性

| 属性名称        | 说明 |
|----------------------|-------------|
| Scenario_Status      | 方案的状态 - 放弃/确定/错误 |
| Scenario_Step        | 当方案包含具有不同故障点的多个步骤时，此属性捕获有关该步骤的详细信息 |
| Scenario_StatusCode  | 属性根据方案成功或失败记录方案的状态代码 |

### <a name="properties-sent-with-trace-events"></a>与跟踪事件一起发送的属性

| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | 包含错误字符串和有关可能发生故障的原因的详细信息 |

## <a name="property-lists-for-oneplayer-events"></a>OnePlayer 事件的属性列表

### <a name="1-properties-sent-with-all-oneplayer-events"></a>1. 与所有 OnePlayer 事件一起发送的属性
##### <a name="11-standard-properties"></a>1.1 标准属性
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| eventType | 事件类型（Applogic、ErrorAlert、Performance、UserAction） |
| accountType   | 用户账户类型（例如，业务） |
| 组件     | OnePlayer |
| 语言      | 应用的区域设置/语言 |
| 平台      | OnePlayer 的平台 (iOS/Android) |
| tenantId      | 租户 ID|
| 版本       | 正在使用的 OnePlayer 版本 |
| aadUserId     | 用户 ID |                                

##### <a name="12-player-properties"></a>1.2 播放器属性
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| engineName    | 基础播放器名称（适用于 iOS 的 AVFoundation/适用于 Android 的 ExoPlayer） |
| engineVersion | 操作系统版本 |
| loadMode      | 播放器的加载模式 |
| playbackSessionId | 播放的会话 ID |

##### <a name="13-host-properties"></a>1.3 主机属性 
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| hostIntegrationType | 主机集成类型（例如，包、OneUP） |
| hostPlatform  | 主机应用的平台 |
| hostProperties| 主机属性（如果有）（仅限 iOS） |
| hostApp       | 主机应用名称 |
| hostVersion   | 主机应用的版本 |

##### <a name="14-experimentation-properties"></a>1.4 实验属性
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| 振铃          | 用户所属的振铃 |
| hostSettings  | 主机应用设置的属性 (moreOptionsEnabled、shareFeatureEnabled、playbackQualityFeatureEnabled、playbackSpeedFeatureEnabled) |
| flightFilters | 说明 |
| flightsOverridden | 已覆盖或未覆盖外部测试版布尔值 |

##### <a name="15-service-properties"></a>1.5 服务属性
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| contentType   | 正在接受服务的内容的类型 |
| 环境   | 环境名称  |
| mediaService  | 正在使用哪些媒体（SOP、ODB、ODC、IC3-AMS、未知） |
| mediaType     | 正在播放的媒体类型  |
| playbackTech  | 媒体的播放技术  |
| correlationId | 媒体的相关 ID（如果有） |

### <a name="2-properties-sent-with-all-oneplayer-user-action-events"></a>2. 与所有 OnePlayer 用户操作事件一起发送的属性 
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| actionType    | 正在执行的操作类型，如单击、拖动和轻拂（仅限 iOS）|
| isIntentional | 操作为有意或无意时的布尔值（仅限 iOS） |

#### <a name="21-properties-sent-with-changeplaybackquality-event"></a>2.1 与 changePlaybackQuality 事件一起发送的属性
| 属性名称 | 说明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| currentPlaybackQuality | 当前播放的质量 |

#### <a name="22-properties-sent-with-changeplaybackspeed-event"></a>2.2 与 ChangePlaybackSpeed 事件一起发送的属性
| 属性名称 | 说明 |
|---------------|------------------------------------------------------------------------------------------------|
| previousPlaybackRate  | 视频的上一个播放速率（仅限 iOS） |
| currentPlaybackRate   | 视频的当前播放速率 |

#### <a name="23-properties-sent-with-playerseek-event-ios-only"></a>2.3 与 PlayerSeek 事件一起发送的属性（仅限 iOS）
| 属性名称 | 说明 |
|---------------|------------------------------------------------------------------------------------------------|
| seekSource    | 查找的源（搜索条、forwardButton、backwardButton） |
| seekValue     | 查找位置 |

### <a name="3-properties-sent-with-oneplayer-heartbeat-event"></a>3. 与 OnePlayer 心跳事件一起发送的属性
| 属性名称 | 说明 |
|---------------|------------------------------------------------------------------------------------------------|
| mediaCurrentTime | 媒体的当前播放时间（仅限 iOS）|
| isLoaded | 已加载媒体 |
| loadTimeMs | 所花费的加载时间（以毫秒为单位） |
| numberOfStalls | 播放期间停滞次数（仅限 iOS） |
| bufferingCount | 播放期间停滞次数（仅限 Android） |
| observedBitrate | 播放期间观察到的比特率（仅限 iOS） |
| avgBitrateBitsPerSecond | 播放期间观察到的比特率（仅限 Android） |
| playedSeconds | 事件发生前已播放秒数 |
| rebufferingSeconds | 播放期间重新缓冲秒数 |
| timeSinceSourceSetMs | 自设定源起的时间（毫秒） |
| triggerType | 触发类型（缓冲、错误、errorLog、canPlayThrough、intervalHeartbeat、sourceset、卸载） |
| errorId | 错误（如果有）的错误 ID |
| errorCorrelationId | 错误（如果有）的错误相关 ID |
| errorLog | 错误（如果有）的错误日志 |
| errorType | 错误（如果有）的错误类型 |
| errorMessage | 错误（如果有）的错误消息 |
| errorStack | 错误（如果有）的扩展错误信息 |
| metaUrl | 媒体的 Meta URL |
| odspDocId | 媒体的 ODSP 文档 ID |
| siteId | 媒体的网站 ID |
| teamsCallId | 媒体的 Teams 呼叫 ID（如果有） |
