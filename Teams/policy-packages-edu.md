---
title: 面向 EDU 管理员的 Microsoft Teams 策略和策略包
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 了解教育或 EDU 设置中的策略，以及如何在 Microsoft Teams 中使用和管理策略包。
ms.openlocfilehash: fcc6a5d22d5e499cf698e424148ff37cd3ee054e
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021880"
---
# <a name="teams-policies-and-policy-packages-for-education"></a>面向教育的 Teams 策略和策略包

> [!NOTE]
> 有关 Microsoft Teams 中策略的更多信息，请查看[向 Microsoft Teams 中的用户分配策略](assign-policies.md)。

请务必注意，本文将介绍多种向 Teams 中的用户分配策略的方法。

- 手动分配给单个用户。
- 通过 PowerShell 批量分配给多个用户。
- 将策略包分配给单个或多个用户。

这些方法的优缺点取决于机构的个人需求。

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a>管理员：Microsoft Teams 策略管理入门

Microsoft Teams 的核心是使用户能够执行诸如参加会议或实时事件、聊天、拨打电话和使用应用之类的事情。 设置恰当的 Microsoft Teams 管理员策略是为 Teams 中的学生营造安全的学习环境的关键一步。 作为管理员，你可以使用策略来控制你的教育机构中的用户可以使用的 Teams 功能。

下面是你将在 Microsoft Teams 中找到的策略区域列表：

- 会议
- 实时事件
- 通话
- 消息传递
- Teams
- 应用权限

:::image type="content" source="media/edu-admin-center-users.png" alt-text="应用了策略的用户的屏幕截图。":::

使用管理员凭据登录后，可轻松地在 [ Microsoft Teams 管理中心](https://admin.teams.microsoft.com)中管理所有 Teams 策略。

### <a name="where-to-find-microsoft-teams-policies"></a>在哪里可以找到 Microsoft Teams 策略

登录 Teams 管理中心后，可单击 Teams 管理中心左侧导航中的策略选项，转到需要管理的任何 Teams 区域的策略设置。 我们提供了消息传递策略位置的屏幕截图。

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 管理中心中的消息策略位置。":::

### <a name="how-to-create-and-update-a-policy-definition"></a>如何创建和更新策略定义

在向用户分配策略之前，你需要首先通过 Teams 为每个功能区域添加和创建策略定义。

> [!NOTE]
> 建议为学生和教师设置不同的策略定义。

默认情况下，将为每个新用户（学生或教师）分配每个功能区域的全局（组织范围默认）策略定义。 建议按照下列步骤操作：

1. 为每个 Teams 功能区域创建一个自定义策略定义，然后可以将其分配给教师（如果不这样做，则你对全局策略所做的任何更改都会限制教师，直到他们拥有自己的策略为止）。
1. 将教师分配给新的策略定义。
1. 更新全局（组织范围默认）策略定义，然后将其分配给学生。

若要创建或编辑策略定义，请转到要使用的策略功能区域（例如，消息传递策略）。 如果想要创建新的自定义策略定义（将为针对教师创建的自定义策略定义执行此操作），请选择“**添加**”。 或者，若要更改现有策略定义，请选择“**编辑**”（如果选择为学生更新全局策略，则会执行此操作）。

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="消息传递策略部分的特写，可看到“添加”按钮。":::

无论选择添加还是编辑策略定义，你都将进入一个视图，其中列出了与此策略区域相关的所有策略选项。 使用此列表可选择要在策略定义中设置的值。

![包含与所选策略区域相关的策略选项的页面。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> 离开页面前，请不要忘记选择“**保存**”。

### <a name="how-to-assign-a-policy-definition-to-a-user"></a>如何向用户分配策略定义

> [!NOTE]
> 分配策略定义时，可能需要一段时间才能传播给所有用户和客户端。 首次在 Azure/M365 中创建用户帐户时，以及每当有新学生加入教育机构时，你都可能需要执行此操作。

创建或更新策略定义后，可通过在策略页面中选择“**管理用户**”，搜索所需的用户，然后应用策略，将其分配给用户。

![消息传递策略页面顶部右侧的“管理用户”面板。](media/edu-manage-users-pane.png)

你还可以通过导航到“用户”，选择要为其更新策略的用户，选择“策略”，然后选择“编辑”，将策略分配给用户。 在此处，可以选择对于每个功能区域要分配给用户的策略定义。

> [!IMPORTANT]
> 如果你是大型教育机构的一员，则可能很难利用 Microsoft Teams 管理门户体验为每个用户设置策略。 最好通过 PowerShell 批量分配策略。 我们提供了一些特定于 EDU 的信息，说明如何[将策略分配给教育机构中的大量用户](batch-policy-assignment-edu.md)（如果需要），你还可以查看下面有关策略包的部分，这是另一种管理大量用户的策略和设置的好方法。

![“编辑用户策略”窗格，位于“已分配的策略”页面右上方。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a>Microsoft Teams 中的策略包

Teams 中的策略包将收集预定义策略和上述策略设置，并将其分配给机构中具有相似角色的用户。 策略包可简化并有助于提供一致的策略管理。 通常，为每个用户分配一个策略包，然后根据需要重新定义每个包中的策略，以满足该用户组的需要。 更新包中的设置时，分配给该包的所有用户都将作为批量更新进行更改。

一般情况下，教育机构的许多用户有其独特的需求，部分取决于学生的年龄和成熟度。 例如，你可能想要授予教师和教职员工对 Microsoft Teams 的完全访问权限，但想要对学生限制 Microsoft Teams 功能，以便鼓励营造安全且专注的学习环境。 可使用策略包根据教育机构社区中不同群体的需求来定制设置。

> [!NOTE]
> 有关详细信息，可查看[管理 Microsoft Teams 中的策略包](manage-policy-packages.md)，了解有关向单个用户分配包、向多达 5000 个用户批量分配包以及管理和更新链接到每个包的策略的分步指导。

就像本文前面的策略列表一样，策略包预定义以下各项的策略：

- 会议
- 实时事件
- 通话
- 消息传递
- Teams
- 应用权限

Microsoft Teams 当前包含以下策略包：

|Microsoft Teams 管理中心中列出的包名称 |最适合用于  |说明 |
|:--- |:--- |:--- |
|**Education_Teacher**| 教师和教职员工| 使用这组策略和策略设置可以为组织中的教师和教职员工授予通过 Microsoft Teams 进行聊天、通话和会议的完全访问权限。 |
|**Education_PrimaryStudent**| 小学适龄学生  | 你所在机构内年幼的小学适龄学生可能需要 Microsoft Teams 中的更多限制。 使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。 |
|**Education_SecondaryStudent**| 中学学龄学生 | 你所在机构内的中学适龄学生可能需要 Microsoft Teams 中的更多限制。 使用这组策略和策略设置可限制会议创建和管理、聊天管理和私人通话等功能。 |
|**Education_HigherEducationStudent**| 高等教育学生 | 你所在机构内的高等教育学生所需的限制可能比年幼学生要少，但是可能建议采用某些限制。 可以使用这组策略和策略设置来授予对组织内的聊天、通话和会议的访问权限，但限制学生与外部参与者一起使用 Microsoft Teams 的方式。 |
|**Education_PrimaryTeacher_RemoteLearning**| 教师和教职员工 | 创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。 |
|**Education_PrimaryStudent_RemoteLearning**| 小学适龄学生| 创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="策略包页面，其中包含可供选择的策略包列表。":::

将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。 例如，当你将 Education_Teacher 策略包分配给教育机构中的教师时，将为包中的每个策略创建一个名为 Education_Teacher 的策略。

![Education_Teacher 策略包的屏幕截图](media/policy-packages-education_teacher.png)

> [!NOTE]
> 如果确定教师和管理支持人员需要不同的策略，则可以重新调整现有包：识别当前不使用的包，并更改设置以适合该组。 你可能需要自己记录哪个小组拥有哪个包，但这是重新调整包的唯一障碍。

## <a name="policies-that-should-be-assigned-for-student-safety"></a>应为学生安全分配的策略

### <a name="meeting-policies"></a>会议策略

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a>关闭创建和启动会议的功能

> [!NOTE]
> 你现在可能还没有在租户中发现此功能。 这是因为此功能当前还在推出过程中，将在完成在所有租户上的部署后向所有用户推出。 有关详细信息，请参阅 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355)。

若要确保学生无法安排会议来进行无人参与的通信，可通过以下常规设置将会议策略设置为**关闭**会议创建功能：

- **允许在频道中立即开会**：关闭
- **允许 Outlook 加载项**：关闭
- **允许安排频道会议**：关闭
- **允许安排私人会议**：关闭

![远程学习页面上的教育学生，显示“常规”部分，此处的所有选项均已关闭。](media/edu-policy-list-a.png)

- 在同一页面上，在会议部分中的“参与者和来宾”中：
  - **允许在私人会议中立即开会**：关闭
  - **允许在会议中聊天**：已禁用

![“参与者和来宾”部分，“允许在私人会议中立即开会”设置为“关闭”。](media/edu-participants-and-guests.png)

为学生关闭“**允许在频道中立即开会**”、“**允许安排频道会议**”、“**允许安排私人会议**”和“**在私人会议中立即开会**”，不仅可阻止学生以组织者身份安排会议，还可为教育客户提供以下安全措施：

- 如果学生尝试在教师之前加入会议，则他们将无法在最新版本的 Teams 应用中加入会议。
- 尽管会议创建适用于任何用户和任何许可证，但是上述有关会议加入阻止的安全措施仅基于用户的许可证类型应用于 Teams 中的教育客户。

如果你将“**允许在会议中聊天**”策略更改为禁用，并阻止学生从上方安排会议，但是继续对教育工作者启用此策略时（对于不是从某个频道或频道中的“立即开会”安排的会议），则学生将无法在教师加入会议之前进行聊天，也不能在会议结束后进行聊天。 他们仍然可以在会议之前、期间和之后查看历史聊天记录。 例如，他们将能够查看来自老师的消息或会议录制链接（如果录制了会议）。

如果学生和教师都禁用了“**允许在会议中聊天**”策略，则任何人都无法在会议聊天窗口中聊天。 上述关于会议聊天限制的安全措施仅基于用户的许可类型应用于 Teams 中的教育客户。

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a>控制学生是否可以在通话和会议期间分享他们的视频

在会议策略部分，确保为学生设置的音频和视频值与教育机构的指导原则以及学生、教师、家长和监护人的期望相符（“**允许云录制**”除外，建议将其设置为“**关闭**”）。

选项如下：

- **允许听录**：关闭/打开
- **允许云录制**：**关闭**
- **允许 IP 视频**：关闭/打开

:::image type="content" source="media/edu-policy-list-b.png" alt-text="远程学习页面中的教育学生，其中显示视频选项。":::

### <a name="live-events-policies"></a>实时事件策略

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a>关闭创建和启动实时事件的功能

若要确保学生无法计划实时事件来进行无人参与的通信，请为学生禁用“**允许安排**”策略，方法是将其设置为“**关闭**”。

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="远程学习页面中的教育学生，其中“允许安排”选项已关闭。":::

### <a name="calling-policies"></a>通话策略

#### <a name="turn-off-the-ability-to-make-private-calls"></a>关闭进行私人通话的功能

若要确保学生无法与其他学生或教师进行私人通话，可为学生禁用“**拨打私人电话**”策略，方法是将其设置为“**关闭**”。

:::image type="content" source="media/edu-private-calls-off.png" alt-text="远程学习页面中的教育学生，其中“拨打私人电话”设置为“关闭”。":::

### <a name="messaging-policies"></a>消息传递策略

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a>关闭删除或编辑已发送消息的功能

- 对于学生：若要确保学生发送的消息未被删除或更改，学生应将以下设置设为“**关闭**”：
  - **删除已发送的消息**
  - **编辑已发送的消息**
- 对于教师：若要确保教师能够审查或删除学生发送的不适当消息，教师应将以下设置设为“**打开**”：
  - **所有者可以删除已发送的消息**（此设置允许教师删除不适当的学生消息）
  - **删除已发送的消息**
  - **编辑已发送的消息**

![远程学习页面中的教育学生，学生和教师的已发送消息设置。](media/edu-delete-edit-sent.png)

> [!NOTE]
> 有关此主题的详细信息，请查看[将课堂团队中的学生设为静音](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)。

#### <a name="control-whether-students-can-chat-privately"></a>控制学生是否可以私下聊天

确保为学生设置的“**聊天打开/关闭**”值与教育机构的指导原则以及学生和教师的期望相符。 此控件可打开或关闭用户在 Teams 中一对一私聊或群聊的功能。

![远程学习页面中的教育学生，其中聊天选项已关闭。](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a>控制学生是否可以对其消息进行个性化设置

确保为学生设置的值与教育机构的指导原则以及学生、教师、家长和监护人的期望相符。 建议将“**适用于学生的 Giphy**”设置为“**关闭**”，并**打开**“**Meme 和贴纸**”。

![远程学习页面上的教育学生，包含 Giphy 选项以及 Meme 和贴纸选项。](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a>控制学生是否可以发送语音消息

确保为学生设置的“**创建语音消息**”值与教育机构的指导原则以及学生和教师的期望相符。

![远程学习页面中的教育学生，包含“创建语音消息”选项。](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a>关闭从聊天中删除用户的功能

学生不应能够从其参与的任何聊天中删除其他用户。 “**从组聊天中删除用户**”的设置应设为“**关闭**”。

![远程学习页面中的教育学生，其中“从组聊天中删除用户”设置为“关闭”。](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a>Teams 策略

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a>关闭发现和创建专用频道的功能

若要确保学生无法创建专用频道作为个人空间来在没有监督的情况下进行交流，请为学生将“**创建专用频道**”策略设置为“**关闭**”。

![Teams 策略页面，“新建团队策略”面板重叠在页面右侧，该面板上的“创建专用频道”设置为“关闭”。](media/edu-private-channels.png)

> [!IMPORTANT]
> 你可能还希望确保学生无法在 Microsoft Teams 中创建新团队。 这实际上是一个 M365 组设置，可在[此处](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)了解更多信息。

### <a name="app-permission-policies"></a>应用权限策略

#### <a name="control-whether-students-can-add-apps-within-teams"></a>控制学生是否可以在 Teams 中添加应用

确保为学生设置的值与教育机构的指导原则相符。 例如，如果希望让学生使用你批准的应用程序，则可以选择：

- **Microsoft 应用**：**允许所有应用**
- **对于第三方应用**：**允许特定的应用并阻止其他所有应用**
- **对于租户应用**：**允许特定的应用并阻止其他所有应用**

:::image type="content" source="media/edu-policies-apps.png" alt-text="远程学习页面中的教育学生以及设置的应用策略选项。":::

> [!NOTE]
> 这是一个示例，如上所述，应按照教育机构的指导原则设置这些策略。

## <a name="policies-that-should-be-assigned-for-educators"></a>应为教师分配的策略

这些是建议管理员应用于教师的策略设置，以便他们可以为其学生提供安全的课堂体验。

> [!NOTE]
> 与将在下面看到的教师部分相比，针对学生的策略建议包含更多信息。 尽管你可以根据自己的教育机构的政策和程序来设置策略设置，但此处提供的建议与学生的安全密切相关。

### <a name="meeting-policies"></a>会议策略

这些设置将允许教师控制对其会议的访问。

- **允许匿名人员发起会议**：**关闭**
- **自动允许人员**：**你所在组织中的所有人**
- **允许拨号加入的用户绕过大厅**：**关闭**
- <sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**

<sup>1</sup> 该设置不在 Microsoft Teams 管理中心中，因此你将需要使用 PowerShell 通过 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 或 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 设置 **DesignatedPresenterRoleMode** 参数。 这将把 Teams“**会议选项**”中的“**谁可以参加?** 设置的默认值设置为“**只有我**”。 通过此设置，只有会议组织者可以成为演示者，所有其他会议参与者都将被指定为与会者。 若要了解详细信息，请参阅“[会议策略设置 - 指定的演示者角色模式](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode)”。

> [!NOTE]
> 对于不是教师的教职员工，你可能希望将参数设置为 **EveryoneUserOverride**（对应于 Teams 中的“**每个人**”设置）或 **EveryoneInCompanyUserOverride**（对应于 Teams 中的“**我的组织中的人员**”设置。）

### <a name="messaging-policies"></a>消息传递策略

将“**所有者可以删除已发送的消息**”设置为“**打开**”时，教师能够监视聊天会话并删除频道会议中不适当的消息。

> [!NOTE]
> 这样，当在频道内创建会议时，教师可以删除班级聊天中不适当的消息，或者删除频道本身内的消息。

## <a name="what-educators-can-do-to-protect-students"></a>教师可执行哪些操作来保护学生

当然，虽然设置策略是管理员在 Teams 设置中主动保护学生的一种好方法，但教师是定期与学生互动的人，他们在确保学生安全方面也起着至关重要的作用。 管理员可能需要与同自己协作的讲师讨论以下信息。

### <a name="set-meeting-roles-through-your-meeting-options"></a>通过会议选项设置会议角色

通过会议选项，你可以控制会议参与者以与会者还是演示者身份加入你的会议。 选项如下：

- 转到“**日历**”并导航到要更新的会议。 单击或点击会议加入链接附近的“**会议选项**”以打开“**会议选项**”。

![加入 Microsoft Teams 会议邀请，“会议选项”位于邀请链接下方的最右边。](media/edu-join-meeting-options.png)

- 通过“**谁可以绕过大厅**”部分来控制谁可以直接进入会议。 将其设置为“**我组织中的人员**”以防止外部用户有选项进入，然后将“**始终允许呼叫者绕过大厅**”设置为“**关闭**”，以使参与者等待准许加入会议，而不是立即加入会议。 你还可以选择“**在呼叫方加入或退出会议时通知**”，并且应将其设置为“**打开**”，以便你始终了解哪些人出席会议。
- 控制作为演示者或与会者加入会议的人员。 可以选择“**仅我**”来指定所有其他参与者为与会者。 对于在课堂环境中举行的会议，这是最安全的设置。
  - 如果希望会议中有多个演示者，请选择“**特定用户**”，然后选择应作为演示者加入的其他参与者。 如果希望所有参与者都作为演示者加入会议，请选择“**所有人**”。

:::image type="content" source="media/edu-meeting-options.png" alt-text="“谁可以绕过大厅”下拉列表并选中“我组织中的人员”，“谁可进行演示”下拉列表并选中“仅我”。":::

### <a name="roles-in-an-online-meeting"></a>联机会议中的角色

会议的每位参与者都会被分配演示者或与会者角色。 参与者的角色控制他们在会议中可以执行的操作。 请参阅下表。

|功能  |组织者/演示者  |与会者  |
|---------|---------|---------|
|说话和共享视频     |     Y     |     Y     |
|参加会议聊天     |     Y     |     Y     |
|私下查看其他人共享的 PowerPoint 文件     |     Y     |     Y     |
|共享内容     |     Y     |     N     |
|使其他参与者静音|     Y     |     N     |
|删除参与者      |     Y     |     N     |
|允许大厅中的参与者进入|     Y     |     N     |
|更改其他参与者的角色     |     Y     |     N     |
|开始或停止录制     |     Y     |     N     |

### <a name="change-roles-during-a-meeting"></a>在会议期间更改角色

会议的每位参与者都会被分配演示者或与会者角色。 参与者的角色控制他们在会议中可以执行的操作。

- 要更改参与者的角色，请在通话控件中单击或点击“**显示参与者**”。 右键单击需要更改其角色的参与者，然后选择“**设为与会者**”或“**设为演示者**”。

![“人脉”栏，显示一个菜单选项，“设为与会者”是菜单上的第四个选项。](media/edu-make-attendee-menu.png)

- 要快速访问你的会议选项并更改当前参与者和将来加入会议的任何人的会议角色设置，请在通话控件中单击或点击“**更多操作**”，然后单击“**显示会议详细信息**”。 可在会议的加入链接附近找到指向“**会议选项**”的链接。

:::image type="content" source="media/edu-meeting-details.png" alt-text="会议窗口，右侧为会议详细信息窗格。":::

### <a name="mute-student-comments"></a>将学生评论静音

会议结束后，如果安排了频道会议，则可以阻止学生进一步发表评论。

#### <a name="for-a-specific-meeting"></a>对于特定会议

当你在频道中安排会议时，会议本身是一个频道帖子，并且会议聊天是帖子的副本。 作为团队所有者，你可对该帖子单击或点击“**更多操作**”，然后单击“**编辑**”。

:::image type="content" source="media/edu-meeting-edit.png" alt-text="在频道帖子上选择更多选项，可看到“编辑”菜单选项显示为弹出菜单上的第二个选项。":::

编辑窗格上有一个下拉选项，可将该选项设置为“**你和审查方可以回复**”。

![在“编辑”菜单上，显示“每个人都可以回复”选项以及“你和审查方可以回复”选项旁边的复选标记。](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a>对于团队的所有会议和发布

你可以控制学生何时可以在课堂团队和会议聊天中发布和回复。 单击或点击团队的“**更多操作**”，单击“**管理团队**”，转到“**成员**”，然后选择要静音的个人或“**将所有学生设为静音**”。

![与会者会议列表，列表顶部显示了将单个学生设为静音或将所有学生设为静音的选项。](media/edu-student-mute.png)

## <a name="further-reading"></a>延伸阅读

请查看[使用 Teams 会议进行远程学习时保证学生安全](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)，了解有关保护学生的详细信息。
