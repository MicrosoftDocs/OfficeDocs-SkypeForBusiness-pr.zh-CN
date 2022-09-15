---
title: Teams 云会议录制
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: 在 Teams 中部署云语音功能的实用指南，用于记录 Teams 会议和组内通话，以捕获音频、视频和屏幕共享活动。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1360847f187d98118d0b5468638cf1d6eb215fb8
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706859"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

在 Microsoft Teams 中，用户可录制其 Teams 会议和组内通话，以便捕获音频、视频和屏幕共享活动。 还有一个用于为录制内容添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制在云中进行，并保存在 OneDrive 和 SharePoint 中，因此用户可以安全地在组织中共享录制内容。

录制会议时，自动执行以下操作：

- 上传到 OneDrive 或 SharePoint
- 向受邀加入会议的人员授予权限
- 在会议聊天中链接
- 在 Teams 日历中会议的“录制和脚本”选项卡中显示
- 添加到 Microsoft 365 的各种文件列表：与我共享、office.com、推荐、最近使用等。
- 为 Microsoft 365 搜索编制索引

相关：[Teams 会议录制最终用户文档](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> 从使用 Microsoft Stream（经典）到 OneDrive 和 SharePoint 进行会议录制的更改将于 2021 年 8 月自动发生。 有关详细信息，请参阅 [使用 OneDrive 和 SharePoint 或 Stream 进行会议录制](tmr-meeting-recording-change.md)。

> [!NOTE]
> 有关在 Teams 会议中使用角色以及如何更改用户角色的信息，请参阅 [Teams 会议中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。 有关实时事件录制选项，请参阅 [Teams 中的实时事件录制策略](teams-live-events/live-events-recording-policies.md)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 云会议录制的先决条件

要录制 Teams 用户的会议，必须为租户启用 OneDrive 和 SharePoint。 此外，会议组织者和将启动录制的人员都需要满足下列先决条件：

- 用户在 OneDrive 中具有足够的存储空间，可用于保存非频道会议录制内容。

- Teams 的频道在 SharePoint 中具有足够的存储空间，可用于保存频道会议录制内容。

- 用户已将 `CsTeamsMeetingPolicy -AllowCloudRecording` 设置设置为 true，以便录制会议和群组通话。

- 用户已将 `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` 设置设置为 true 以便录制 1 对 1 通话。

- 用户不是会议中的匿名、来宾或联合用户。

- 要为用户会议启用转录功能，所分配到的 Teams 会议策略必须将 `-AllowTranscription` 设置设为 true。

- 要使频道会议录制内容能够保存，以使频道成员无法编辑或下载录制内容，必须将 `CSTeamsMeetingPolicy -ChannelRecordingDownload` 设置设为阻止。

> [!IMPORTANT]
>
> 如果希望用户仅录制和下载录制内容，则用户将无需启用 OneDrive for 或 SharePoint。 这意味着录制内容不会存储在 OneDrive 或 SharePoint 中，而是改为存储在临时 Teams 存储中 21 天，之后才会删除。 目前，管理员无法对其进行控制、管理或删除。
>
> 有关 [临时会议录制内容存储工作原理的详细信息](#temp-storage)，请参阅下文。  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>为组织中的用户设置 Teams 云会议录制

本部分介绍如何通过 [Teams 会议策略](policy-assignment-overview.md) 设置和计划录制 Teams 会议。

### <a name="turn-on-or-turn-off-cloud-recording"></a>打开或关闭云录制

你可以使用 Microsoft Teams 管理中心或 PowerShell 来设置 Teams 会议策略，以控制是否可以录制用户的会议。

在 Microsoft Teams 管理中心，打开或关闭会议策略中的 **云录制** 设置。 要了解详细信息，请参阅 [音频和视频的会议策略设置](meetings-policies-recording-and-transcription.md#cloud-recording)。

借助 PowerShell，你可以配置 TeamsMeetingPolicy 中的 AllowCloudRecording 设置。 若要了解详细信息，请参阅[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

请注意，会议组织者和录制发起人均需具有录制会议所需的录制权限。 除非已向用户分配了自定义策略，否则用户将获得默认已启用 AllowCloudRecording 的全局策略。

> [!NOTE]
> 有关使用 Teams 角色配置具有录制会议权限的用户的详细信息，请参阅 [Teams 会议中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要在全局策略中更改 AllowCloudRecording 的值，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|使用场景|步骤|
|--|--|
| 我希望公司中的所有用户都能够录制自己的会议。 | <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = True。<li>所有用户都具有全局 CsTeamsMeetingPolicy，或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一。</ol> |
| 希望大多数用户能够录制会议，但有选择地禁用不允许录制的特定用户。 | <ol><li>确认 GlobalCsTeamsMeetingPolicy 具有 AllowCloudRecording = True。<li>大多数用户都具有全局 CsTeamsMeetingPolicy，或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一。<li>为所有其他用户授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一。</ol> |
| 我希望 100% 禁止录制。 | <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False。<li>为所有用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一。 |
| 我希望关闭大多数用户的录制功能，但有选择地启用允许录制的特定用户。 | <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False。<li>为大多数用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一。<li>为所有其他用户授予了 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一。 <ol> |

<a name="bd-channel"></a>

### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>阻止或允许下载频道会议录制内容

此设置控制频道会议是否保存到频道中的“录制内容”文件夹或“录制内容\仅供查看”文件夹。 此设置适用于选择频道会议记录用户的策略。

此设置的两个值为：

- **允许**（默认）- 将频道会议录制内容保存到频道中的“录制内容”文件夹。 录制文件的权限将基于频道 SharePoint 权限。 这与为频道上传的任何其他文件相同。

- **阻止** - 将频道会议录制内容保存到频道中的“录制内容\仅供查看”文件夹。 频道所有者将具有对此文件夹中录制内容的完全权限，但频道成员将仅拥有读取权限，而无法下载。

使用 PowerShell 在 TeamsMeetingPolicy 中配置 ChannelRecordingDownload 设置。 要了解详细信息，请参阅 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

除非已向用户分配自定义策略，否则用户将获取全局策略，默认情况下，该策略将 ChannelRecordingDownload 设置为“允许”。

要让用户回退到全局策略，请使用以下 cmdlet 删除向用户进行的特定策略分配：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

要更改全局策略中 ChannelRecordingDownload 的值，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> ChannelRecordingDownload 设置仅在 Teams PowerShell 模块版本 2.4.1 预览版或更高版本中可用。 要下载模块的最新预览版本，请使用此命令：
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>打开或关闭录制转录

此设置控制播放会议录制内容期间是否提供字幕和转录功能。 启动录制的人员需要打开此设置，才能使用这些功能进行录制。
  
启用此设置将创建与会议记录一起存储的脚本，它在会议录制内容中启用“**搜索**”、“**CC**”和“**脚本**”。

> [!NOTE]
> 该录制会议听录目前仅支持英语（美国）、英语（加拿大）、英语（印度）、英语（英国）、英语（澳大利亚）、英语（新西兰）、阿拉伯语（阿拉伯联合酋长国）、阿拉伯语（阿拉伯联合酋长国）、阿拉伯语（沙特阿拉伯）、中文（简体，中国）、中文（繁体，香港特别行政区）、中文（繁体，中国台湾）、捷克语（捷克语）、丹麦语（丹麦）、荷兰语（比利时）、荷兰语（荷兰）、荷兰语（荷兰）、法语（加拿大）、法语（法国）、芬兰语（芬兰）、德语（德国）、希腊语（希腊）、希伯来语（以色列）、印地语（印度）、匈牙利语（匈牙利）、意大利语（意大利）、日语（日本）、韩语（韩国）、挪威语（挪威）、波兰语（波兰）、葡萄牙语（巴西）、葡萄牙语（葡萄牙）、罗马尼亚语（罗马尼亚）、俄语（俄罗斯）、斯洛伐克语（斯洛伐克）、西班牙语（墨西哥）、西班牙语（西班牙）、瑞典语（瑞典）、泰语（泰国）、土耳其语（土耳其）、乌克兰语（乌克兰）、越南语（越南）。 它们与会议录制内容一起存储在 OneDrive 和 SharePoint 云存储中。

你可以使用 Microsoft Teams 管理中心或 PowerShell 来设置 Teams 会议策略，以控制录制发起人是否可以选择转录会议录制。

在 Microsoft Teams 管理中心中，打开或关闭会议策略中的“**允许转录**”设置。 要了解详细信息，请参阅 [音频和视频的会议策略设置](meetings-policies-recording-and-transcription.md#transcription)。

借助 PowerShell，你可以配置 TeamsMeetingPolicy 中的 AllowTranscription 设置。 若要了解详细信息，请参阅[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

除非你已为用户分配了自定义策略，否则用户将获得全局策略，该策略默认禁用 AllowTranscription。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要在全局策略中更改 AllowTranscription 的值，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

|使用场景|步骤 |
|---|---|
|我希望公司的所有用户都能够在发起会议录制时进行转录。 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True。 <li>所有用户都具有全局 CsTeamsMeetingPolicy ，或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|希望大多数用户能够转录会议录制内容，但有选择地禁用未获允许转录的特定用户。 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True。 <li>大多数用户都具有全局 CsTeamsMeetingPolicy，或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一。 <li>为所有其他用户授予了 AllowTranscription = False 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|我希望 100% 禁止录制内容转录。 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = False。 <li>向所有用户授予了全局 CsTeamsMeetingPolicy，或授予了 AllowTranscription = False 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|我希望对大多数用户禁用转录，但有选择地启用允许其进行转录的特定用户。 |<ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False。 <li>为大多数用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一。 <li>为所有其他用户授予了 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一。 </ol>|

### <a name="terms-of-use-acceptance"></a>使用条款接受

如果你的组织具有你希望用户在录制会议之前接受的会议录制策略，请使用 [Azure Active Directory使用条款](/azure/active-directory/conditional-access/terms-of-use)功能。 此功能允许用户在访问 Microsoft Teams 之前接受组织的用户策略条款。 此功能并不特定于单击录制按钮，但与整体使用 Teams 或其他 Microsoft 365 应用相关。 我们的建议是将会议录制信息添加到使用 Teams 或 Microsoft 365 的总体使用条款中。

### <a name="set-a-custom-privacy-policy-url"></a>设置自定义隐私策略 URL

作为管理员，你可以使用组织的自定义链接更新 Teams 录制和听录隐私策略 URL。 可以使用以下步骤在 [Azure AD 管理中心](https://aad.portal.azure.com)执行此操作：

1. 登录到 Azure AD 管理中心。
1. 转到“**Azure Active Directory**” > “**属性**”。
1. 使用指向隐私策略的链接更新 **隐私语句 URL** 字段。

> [!NOTE]
> 如果已为组织更新此字段，则无需进行任何更改。

添加隐私策略 URL 后，默认 Teams 会议录制和听录隐私声明将被替换为组织提供的新 URL。

> [!NOTE]
> 加入组织托管的 Teams 会议的匿名、来宾、联合用户仍将具有默认的 Teams 会议录制和听录隐私策略。

## <a name="permissions-and-storage"></a>权限和存储

会议录制内容存储在 OneDrive 和 SharePoint 云存储中。 位置和权限取决于会议类型和用户在会议中的角色。 下面列出了应用于录制内容的默认权限，对视频录制文件具有完全编辑权限的用户可以更改权限，并稍后根据需要与其他人共享。

### <a name="non-channel-meetings"></a>非频道会议

- 录制内容存储在单击“录制”的用户的 OneDrive 中名为“**录制内容**”的文件夹中。 

  示例： *录制器的 OneDrive*/**录制**

- 受邀加入会议的人员（外部参与者除外）将自动获得对录制文件的查看权限，但无法下载。

- 会议所有者和单击“录制”的人员将获得完全的编辑权限，能够更改权限并与其他人共享。

### <a name="channel-meetings"></a>频道会议

如果将 `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` 设置为允许（默认值），则：

- 录制内容存储在 Teams 网站文档库中名为 **录制内容** 的文件夹中。

  示例： *Teams 名称 - 频道名称*/**文档**/**录制**

- 单击“录制”的成员对录制内容具有编辑权限。

- 其他每个成员的权限都基于频道 SharePoint 权限。

如果将 `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` 设置为阻止，则：

- 录制内容存储在 Teams 网站文档库中名为 **录制内容/仅供查看** 的文件夹中。 

  示例： *Teams 名称 - 频道名称*/**文档/录制/仅查看**

- 频道所有者将对此文件夹中录制内容具有完全的编辑和下载权限。

- 频道成员则将仅具有查看权限，而无法下载。

有关特定会议类型的详细信息，请参阅下表：

| 会议类型  | 谁单击了“录制”？| 录制内容位于何处？ | 谁具有访问权限？ R/W、R 或共享  |
|-------------|-----------------------|------------------------|------------------------|
|与内部参与方进行 1 对 1 通话             |呼叫方                 |呼叫方的 OneDrive 帐户                        |呼叫方是所有者，且具有完全权限。 <br /><br />被呼叫方（如果在同一租户中）具有只读访问权限。没有共享访问权限。 <br /><br /> 被呼叫方（如果位于不同租户中）没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|与内部参与方的 1 对 1 通话             |被呼叫方                 |被呼叫方的 OneDrive 帐户                        |被呼叫方是所有者，且具有完全权限。 <br /><br />呼叫方（如果在同一租户中）具有只读访问权限。 <br /><br />呼叫方（如果位于不同的租户中）无访问权限。 被呼叫方必须将其共享给呼叫方。|
|使用外部呼叫进行 1：1 通话             |呼叫方                 |呼叫方的 OneDrive 帐户                        |呼叫方是所有者，且具有完全权限。<br /> <br />被呼叫方没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|使用外部呼叫进行 1：1 通话             |被呼叫方                 |被呼叫方的 OneDrive 帐户                        |被呼叫方是所有者，且具有完全权限。<br /><br />呼叫方没有访问权限。 被呼叫方必须将其共享给呼叫方。|
|群组通话                                 |通话的任何成员 |单击“录制”的 OneDrive 帐户的组成员  |单击“录制”的成员具有完全权限。 <br /><br /> 来自同一租户的其他成员具有读取权限。 <br /><br /> 来自不同租户的其他组成员则没有权限。|
|临时/计划的会议                    |组织者              |组织者的 OneDrive 帐户                     |组织者对录制内容具有完全权限。 <br /><br /> 会议的所有其他成员都具有读取权限，但无法下载。|
|临时/计划的会议                    |其他会议成员   |单击“录制”的会议成员                                  |单击“录制”的成员对录制内容具有完全权限。 <br /><br />组织者具有编辑权限，且可以共享。<br /><br /> 所有其他会议成员都具有读取权限，但无法下载。|
|与外部参与者的临时/计划会议|组织者              |组织者的 OneDrive 帐户                     |组织者对录制内容具有完全权限。<br /> <br /> 来自组织者所在同一租户的会议的所有其他成员都具有读取权限，但无法下载。 <br /><br /> 所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|与外部参与者的临时/计划会议|其他会议成员   |单击“录制”的成员                                  |单击“录制”的成员对录制内容具有完全权限。 组织者具有编辑权限，且可以共享。 <br /><br /> 来自组织者所在同一租户的会议的所有其他成员都具有读取权限，但无法下载。 <br /><br />所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|频道会议                            |频道成员         |该频道 Teams 的 SharePoint 位置                   |如果将 Set-CsTeamsMeetingPolicy -ChannelRecordingDownload 设置为允许（默认），则单击“录制”的成员具有对录制内容的编辑权限。 其他每个成员的权限都基于频道 SharePoint 权限。<Br><Br>如果将 Set-CsTeamsMeetingPolicy -ChannelRecordingDownload 设置为阻止，则频道所有者将对录制内容具有完全权限，但频道成员将仅具有读取权限，而无法下载。|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>无法上传到 OneDrive 和 SharePoint 时的临时存储

如果会议录制内容无法上传到 OneDrive 和 SharePoint，则将在删除之前的 21 天内暂时可从 Teams 下载。 目前管理员无法对其进行控制和管理，也无法将其删除。

会议录制内容可能由于以下原因存储在此临时存储中：

- 对于非频道会议，如果正在录制的用户没有 OneDrive 或其 OneDrive 已达到其存储配额
- 对于频道会议，如果 SharePoint 网站已达到其存储配额，或网站尚未预配
- 如果启用了特定的 OneDrive 和 SharePoint 策略，则限制用户在未处于特定 IP 范围内时上传文件等。

因此而进行的录制内容保留是临时存储，受到聊天消息本身的影响。 因此，如果删除录制内容的原始聊天消息，用户将无法访问该录制内容。 有两种方案可能会影响到此情况：

- **用户手动删除聊天消息** - 在这种情况下，由于原始消息不再可用，用户将不再能够访问录制内容，并将无法再进一步下载。 但是，录制内容本身仍可在 Microsoft 内部系统中保留一段时间（不超过原始的 21 天）。

- **按聊天保留策略删除录制聊天消息** - 临时存储录制内容与聊天保留策略直接相关。 因此，虽然默认情况下 Teams 临时存储上的录制内容将在删除前保留 21 天，但如果由于聊天消息保留策略的原因在该 21 天时段之前删除了聊天消息，则录制内容也将删除。 此后将无法恢复录制内容。

### <a name="planning-for-storage"></a>存储规划

1 小时录像的大小为 400 MB。 请确保已了解录制文件所需的容量，并在 OneDrive 和 SharePoint 中有足够的可用存储空间。  阅读 [设置 OneDrive 的默认存储空间](/onedrive/set-default-storage-space) 和 [管理 SharePoint 网站存储限制](/sharepoint/manage-site-collection-storage-limits)，以了解订阅中包含的基本存储空间以及如何购买额外存储空间。
  
## <a name="manage-meeting-recordings"></a>管理会议录制内容

会议录制内容作为视频文件存储在 OneDrive 和 SharePoint 中，并遵循这些平台中提供的管理和治理选项。 有关详细信息，请参阅 [SharePoint 治理概述](/sharepoint/governance-overview)。

对于非频道会议，录制内容存储在录制者的 OneDrive 中，因此员工离职后所有权和保留的处理将遵循常规的 [OneDrive 和 SharePoint 流程](/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

会议录制的默认过期时间为 120 天。 可以关闭会议自动过期设置或更改默认过期时间。 有关[会议录制自动过期的](meetings-policies-recording-and-transcription.md#meetings-automatically-expire)Mer informasjon。

## <a name="closed-captions-for-recordings"></a>录制内容的隐藏式字幕

仅当用户在录制时打开了听录功能时，才会在播放期间提供 Teams 会议录制内容的隐藏式字幕。 管理员必须 [通过策略启用录制听录](#turn-on-or-turn-off-recording-transcription)，以确保其用户可以选择使用听录来记录会议。

作为所有者，你可以隐藏会议录制内容中的字幕，尽管会议脚本仍可在 Teams 上使用，除非你将其从 Teams 删除。

今天,录制内容视频文件的隐藏式字幕已链接到 Teams 会议脚本。 在大多数情况下，此链接将在文件的生命周期内一直保存，但如果在同一 OneDrive 或 SharePoint 网站中复制该视频文件，则链接可能会损坏，这将导致字幕在复制的视频文件上不可用。

将来对 Teams 中脚本和录制内容之间的链接所做的任何更改都将在此处和消息中心通知中进行阐明。 如果将来有任何更改，我们将确保录制时间不到 60 天的录制文件将会议的脚本显示为字幕。

> [!NOTE]
> 会议转录在 GCC 中尚不可用。

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>会议录制的电子数据展示和合规性

### <a name="ediscovery"></a>电子数据展示

会议录制内容存储在 OneDrive 和 SharePoint 中，符合 Microsoft 365 和 Office 365 D 层的要求。 为了支持对会议或通话录制感兴趣的合规性管理员的电子数据展示请求，我们在 Microsoft Teams 的合规性内容搜索功能中提供了录制已完成消息。 合规性管理员可在合规性内容搜索预览中的项目主题行中查找关键字“录像”，找到组织中的会议和通话录像。

此外，还可以通过电子数据展示搜索 SharePoint 和 OneDrive 上的文件来查找会议录制内容视频文件。

要了解有关电子数据展示的详细信息，请参阅 [Microsoft 365 的电子数据展示解决方案](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>保留策略

你可以通过 ProgID 属性以仅将 Teams 会议录制视频文件为目标来应用自动保留标签。 有关详细信息，请参阅 [如何为 Teams 会议录制内容自动应用保留标签](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings)。

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Microsoft Purview 数据丢失防护 (DLP) 策略

也可以通过 ProgID 属性将 DLP 策略应用于会议录制文件。 在 SharePoint 和 OneDrive 中文件的 DLP 规则中，将条件设置为：

- Document 属性 = *ProgID*
- 值 = *Media.Meeting*

要了解有关 DLP 的详细信息，请参阅文章 [了解数据丢失防护](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>会议录制诊断工具

### <a name="user-cannot-record-meetings"></a>用户无法录制会议

如果你是管理员，则可以使用以下诊断工具来验证用户是否已正确配置为在 Teams 中录制会议:

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。

   > [!div class="nextstepaction"]
   > [运行测试: 会议录制](https://aka.ms/MeetingRecordingDiag)

2. 在“运行”诊断窗格中，输入无法在 **用户名或 Email** 字段中录制会议的用户电子邮件，然后选择 **运行测试**。

3. 测试将返回解决任何租户或策略配置的最佳后续步骤，以验证用户是否已正确配置为在 Teams 中录制会议。
  
### <a name="meeting-record-is-missing"></a>缺少会议记录

如果你是管理员，则可以使用以下诊断工具来验证会议录制是否已成功完成，并根据会议 ID 和录制开始时间将其上传到 Stream 或 OneDrive:

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。

   > [!div class="nextstepaction"]
   > [运行测试: 缺少会议录制](https://aka.ms/MissingRecordingDiag)

2. 在“运行诊断”窗格中，在会议 URL 中输入会议 **的 URL，该 URL 记录** 字段 (通常在会议邀请) 以及会议记录时间？字段中的 **会议** 日期，然后选择 **“运行测试**”。

3. 测试将验证会议录制是否已成功完成，并且已上传到 Stream 或 OneDrive。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
