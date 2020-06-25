---
title: Teams 云会议录制
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在团队中部署云语音功能以录制团队会议和群组通话以捕获音频、视频和屏幕共享活动的实用指南。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97fa736a1f2277dbd9da2305b75bf16b26d34e73
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874409"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

在 Microsoft Teams 中，用户可录制其 Teams 会议和组内通话，以便捕获音频、视频和屏幕共享活动。 还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制在云中进行，并保存在 [Microsoft Stream](https://docs.microsoft.com/stream/) 中，因此用户可以安全地在组织中共享录像。

相关：[Teams 会议录制最终用户文档](https://aka.ms/recordmeeting)

> [!NOTE]
> 有关在团队会议中使用角色以及如何更改用户角色的信息，请参阅[团队会议中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 云会议录制的先决条件

对于要录制的团队用户的会议，必须为租户启用 Microsoft Stream。 此外，会议组织者和将发起录制的人员需要满足下列先决条件：

- 用户拥有 Office 365 E1、E3、E5、A1、A3、A5、M365 商业版、商业高级版或商业协作版
- 用户需要获得针对 Microsoft Stream 的许可<sup>1</sup> 
- 用户拥有 Microsoft Stream 上传视频权限
- 用户已同意公司指南（如果由管理员设置）
- 用户在 Microsoft Stream 中有足够的存储空间来保存录像
- 用户的 TeamsMeetingPolicy-AllowCloudRecording 设置已设置为 true
- 用户不是会议中的匿名、来宾或联合用户
- 若要为用户的会议启用脚本，则分配给他们的团队会议策略必须具有-AllowTranscription 设置才能设置为 true。

需要授予<sup>1</sup>个用户将会议上载/下载到 Microsoft Stream 的许可证，但不需要许可证即可录制会议。 如果你希望阻止用户录制 Microsoft Teams 会议，则必须为其授予将 AllowCloudRecording 设置为 $False 的 TeamsMeetingPolicy。

> [!IMPORTANT] 
> 如果希望用户只录制和下载录制文件，则无需为用户分配 Microsoft Stream 许可证。 这将意味着，录制不会存储在 Microsoft Stream 中，而是存储在 Azure 媒体服务（AMS）中，在删除之前将有21天的限制。 目前管理员无法控制或管理它，包括无法删除它。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>为组织中的用户设置 Teams 云会议录制

本部分介绍如何设置和规划 Teams 会议录制。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>为组织中的用户打开 Microsoft Stream

Microsoft Stream 作为符合条件的 Microsoft 365 和 Office 365 订阅的一部分，或作为独立服务提供。  有关详细信息，请参阅 [Stream 许可概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 现已包含在 Microsoft 365 商业版、Microsoft 365 商业标准版和 Microsoft 365 商业版中。

了解有关如何为[microsoft 365 或 Office 365 中的用户分配许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)的详细信息，以便用户可以访问 microsoft Stream。 确保未阻止用户的 Microsoft Stream，如[Microsoft stream 的 "阻止登录](https://docs.microsoft.com/stream/disable-user-organization)" 中所定义。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>确保用户在 Microsoft Stream 中上载视频权限

默认情况下，只要 Stream 处于启用状态并获得许可证，公司中的每个人都可在 Stream 中创建内容。 Microsoft Stream 管理员可以[限制员工在 Stream 中创建内容](https://docs.microsoft.com/stream/restrict-uploaders)。 此受限列表中的用户将不能录制会议。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知员工让其同意 Microsoft Stream 中的公司指南

如果 Microsoft Stream 管理员已[设置公司指南策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工在保存内容前接受此策略，则用户必须先执行此操作，然后才能在 Microsoft Teams 中进行录制。 在组织中推出录制功能前，请确保用户已同意该策略。

### <a name="turn-on-or-turn-off-cloud-recording"></a>打开或关闭云录制

你可以使用 Microsoft Teams 管理中心或 PowerShell 来设置 Teams 会议策略，以控制是否可以录制用户的会议。

在 Microsoft Teams 管理中心中，打开或关闭会议策略中的“**允许云录制**”设置。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-in-teams.md#allow-cloud-recording)。

借助 PowerShell，你可以配置 TeamsMeetingPolicy 中的 AllowCloudRecording 设置。 若要了解详细信息，请参阅[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

请注意，会议组织者和录制发起人均需具有录制会议所需的录制权限。 除非已向用户分配了自定义策略，否则用户将获取全局策略，默认情况下，该策略启用 AllowCloudRecording。

> [!NOTE]
> 有关使用团队角色配置谁有权录制会议的详细信息，请参阅[团队会议中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要在全局策略中更改 AllowCloudRecording 的值，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 使用场景                                                                 |                                                                                                                                                                         步骤                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我希望公司中的所有用户都能录制自己的会议                                    |                                                                     <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = True<li>所有用户都拥有全局 CsTeamsMeetingPolicy 或拥有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 </ol>                                                                     |
| 我希望大多数用户能够录制会议，但有选择地禁用不允许其进行录制的特定用户 |        <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = True<li>大多数用户都拥有全局 CsTeamsMeetingPolicy 或拥有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一<li>为所有其他用户授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一</ol>         |
|                                                   我希望 100% 禁止录制                                                   |                                                                <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False<li>为所有用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一                                                                 |
|      我希望为大多数用户关闭录制，但有选择地启用允许录制的特定用户       | <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False<li>为大多数用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一<li>为所有其他用户授予了 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会议录像的存储位置

会议录制存储在 Microsoft Stream 云存储空间内。 录制会议后，Microsoft Stream 将永久保留（或直到录制所有者将其删除）。 如果录制未上载到流，则会将其存储在团队云存储中，在这里，可以下载20天。 目前，对于 Teams 数据存储在国内的客户而言，如果 Microsoft Stream 在其存放数据的国内数据驻留区域中不可用，则会为其关闭 Teams 会议录制功能。

若要查找你的 Microsoft Stream 数据的存储区域，请在 Microsoft Stream 中单击右上角的 **?**， 单击“**关于 Microsoft Stream**”，然后单击“**您的数据存储于**”。  若要深入了解 Microsoft Stream 存储数据的区域，请参阅 [Microsoft Stream 常见问题解答](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要了解有关在 Microsoft 365 或 Office 365 中跨服务存储数据的位置的详细信息，请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>打开或关闭录制转录

此设置控制播放会议录制期间是否提供字幕和脚本功能。 如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。 启动录制的人员需要启用此设置，以便录制还包括脚本。

请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。

你可以使用 Microsoft Teams 管理中心或 PowerShell 来设置 Teams 会议策略，以控制录制发起人是否可以选择转录会议录制。

在 Microsoft Teams 管理中心中，打开或关闭会议策略中的“**允许转录**”设置。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-in-teams.md#allow-transcription)。

借助 PowerShell，你可以配置 TeamsMeetingPolicy 中的 AllowTranscription 设置。 若要了解详细信息，请参阅[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

除非你已为用户分配了自定义策略，否则用户将获得全局策略，该策略默认禁用 AllowTranscription。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

若要在全局策略中更改 AllowTranscription 的值，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
</br>
</br>

|使用场景|步骤 |
|---|---|
|我希望公司的所有用户都能够在发起会议录制时进行转录 |<ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowTranscription = True <li>所有用户都拥有全局 CsTeamsMeetingPolicy 或拥有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|我希望大多数用户能够转录会议录制，但有选择地禁用不允许其进行转录的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowTranscription = True <li>大多数用户都拥有全局 CsTeamsMeetingPolicy 或拥有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一 <li>为所有其他用户授予了 AllowTranscription = False 的 CsTeamsMeetingPolicy 策略之一 </ol>|
|我希望 100% 禁止录制转录 |<ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowTranscription = False <li>为所有用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowTranscription = False 的 CsTeamsMeetingPolicy 策略之一 </ol>|
|希望对大多数用户禁用转录，但有选择地启用允许其进行转录的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False <li>为大多数用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一 <li>为所有其他用户授予了 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 </ol>|
|||

### <a name="planning-for-storage"></a>存储规划

1 小时录像的大小为 400 MB。 请务必了解所录文件所需要的容量，并确保在 Microsoft Stream 中有足够的可用存储空间。  阅读[Microsoft Stream 许可概述](https://docs.microsoft.com/stream/license-overview)以了解订阅中包含的基本存储以及如何购买其他存储空间。

## <a name="manage-meeting-recordings"></a>管理会议录像

我们将会议录像视为租户所有的内容。 如果录像的所有者离开了公司，管理员可以在管理员模式下打开 Microsoft Stream 中的录制视频 URL。 管理员可以删除相应录像、更新任何录制元数据或更改所录制视频的权限。 深入了解 [Stream 中的管理员功能](https://docs.microsoft.com/stream/manage-content-permissions)。

> [!NOTE]
> 有关管理录像和用户访问的其他信息，请参阅[管理 Microsoft Stream 中的用户数据](https://docs.microsoft.com/stream/managing-user-data)和 [Microsoft Stream 中的权限和隐私](https://docs.microsoft.com/stream/portal-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会议录像的合规性和电子数据展示

会议录制存储在 Microsoft Stream 中，即 Microsoft 365 和 Office 365 第 C 版兼容。 为了在 Microsoft Stream 中支持对会议或通话录像感兴趣的合规性管理员的电子数据展示请求，我们会在 Microsoft Teams 的合规性内容搜索功能中提供录制已完成的消息。 合规性管理员可在合规性内容搜索预览中的项目主题行中查找关键字“录像”，找到组织中的会议和通话录像。 查看所有录像的前提条件是，他们需要在 Microsoft Stream 中具有管理员访问权限。 深入了解如何[分配 Stream 中的管理员权限](https://docs.microsoft.com/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
