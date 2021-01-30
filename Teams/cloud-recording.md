---
title: Teams 云会议录制
author: tonysmit
ms.author: tonysmit
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
f1.keywords:
- NOCSH
description: 有关在 Teams 中部署云语音功能以录制 Teams 会议和群组通话以捕获音频、视频和屏幕共享活动的实用指南。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fb43635d8155d6fe98f02e561ea843ca8c74a4e
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055634"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

在 Microsoft Teams 中，用户可录制其 Teams 会议和组内通话，以便捕获音频、视频和屏幕共享活动。 还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制在云中进行，并保存在 [Microsoft Stream](https://docs.microsoft.com/stream/) 中，因此用户可以安全地在组织中共享录像。

相关：[Teams 会议录制最终用户文档](https://aka.ms/recordmeeting)

>[!Note]
> 将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](tmr-meeting-recording-change.md) 将是一种分阶段的方法。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月你必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行会议录制。

> [!NOTE]
> 有关在 Teams 会议中使用角色以及如何更改用户角色的信息，请参阅 Teams [会议中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Teams 云会议录制的先决条件

若要录制 Teams 用户的会议，必须为租户启用 Microsoft Stream。 此外，会议组织者和将发起录制的人员需要满足下列先决条件：

- 用户拥有 Office 365 E1、E3、E5、A1、A3、A5、Microsoft 365 商业高级版、商业标准版或 Business Basic<sup>1</sup>
- 用户已同意公司指南（如果由管理员设置）
- 用户在 Microsoft Stream 中有足够的存储空间来保存录像
- 用户将 CsTeamsMeetingPolicy -AllowCloudRecording 设置设置为 true，以便录制会议和群组通话
- 用户将 CsTeamsCallingPolicy -AllowCloudRecordingForCalls 设置设置为 true，以便记录 1：1 调用
- 用户不是会议中的匿名、来宾或联合用户
- 若要为用户的会议启用听录，他们分配到的 Teams 会议策略必须将 -AllowTranscription 设置设置为 true。

<sup>1</sup> 自 2020 年 8 月 20 日起，使用 A1 的用户对会议录制文件的访问权限将在 21 天后过期。 有关详细信息，请参阅"[将 Microsoft Teams 会议录制文件上传到流式传输"。](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)

> [!IMPORTANT] 
> 如果希望用户只录制和下载录制文件，则无需为用户分配 Microsoft Stream 许可证。 这意味着录制内容不会存储在 Microsoft Stream 中，而是存储在 Async 媒体服务 (AMS) 在删除前有 21 天的限制。 目前管理员无法控制或管理它，包括无法删除它。

> [!IMPORTANT]
> 另请注意，对于 AMS 上的录制，录制保留期受聊天消息本身的影响。 因此，删除原始 AMS 录制聊天消息将阻止用户访问录制内容。 有两种方案可能会影响这一点。 1) 用户手动删除聊天消息 - 在这种情况下，由于原始消息已不存在，用户将无法再访问录制内容，并且无法再进行下载。 但是，录制内容本身可能仍在 Microsoft 的内部系统中保留一 (不超过原始的 21 天) 。 2) 聊天消息由聊天保留策略删除 - AMS 录制直接绑定到聊天保留策略。 因此，虽然默认情况下 AMS 上的录制内容将在删除前保留 21 天，但如果在 21 天期限之前删除了聊天消息，由于聊天消息保留策略，也将删除录制内容。 此后无法恢复录制内容。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>为组织中的用户设置 Teams 云会议录制

本部分介绍如何设置和规划 Teams 会议录制。

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>为组织中用户启用 Microsoft Stream

Microsoft Stream 作为符合条件的 Microsoft 365 和 Office 365 订阅的一部分提供，或作为独立服务的一部分提供。  有关详细信息，请参阅 [Stream 许可概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 现已包含在 Microsoft 365 商业版、Microsoft 365 商业标准版和 Microsoft 365 商业版基本版中。

详细了解如何在 [Microsoft 365 或 Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) 中向用户分配许可证，以便用户可以访问 Microsoft Stream。 确保未针对用户阻止 Microsoft Stream，如"阻止 Microsoft Stream 注册" [中的定义](https://docs.microsoft.com/stream/disable-user-organization)。

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>确保用户在 Microsoft Stream 中具有上传视频权限

默认情况下，只要 Stream 处于启用状态并获得许可证，公司中的每个人都可在 Stream 中创建内容。 Microsoft Stream 管理员可以[限制员工在 Stream 中创建内容](https://docs.microsoft.com/stream/restrict-uploaders)。 此受限列表中的用户将不能录制会议。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知员工让其同意 Microsoft Stream 中的公司指南

如果 Microsoft Stream 管理员已[设置公司指南策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工在保存内容前接受此策略，则用户必须先执行此操作，然后才能在 Microsoft Teams 中进行录制。 在组织中推出录制功能前，请确保用户已同意该策略。

### <a name="turn-on-or-turn-off-cloud-recording"></a>打开或关闭云录制

你可以使用 Microsoft Teams 管理中心或 PowerShell 来设置 Teams 会议策略，以控制是否可以录制用户的会议。

在 Microsoft Teams 管理中心中，打开或关闭会议策略中的“**允许云录制**”设置。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-in-teams.md#allow-cloud-recording)。

借助 PowerShell，你可以配置 TeamsMeetingPolicy 中的 AllowCloudRecording 设置。 若要了解详细信息，请参阅[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 和 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

请注意，会议组织者和录制发起人均需具有录制会议所需的录制权限。 除非向用户分配了自定义策略，否则用户会获取全局策略，该策略默认已启用 AllowCloudRecording。

> [!NOTE]
> 有关使用 Teams 角色配置谁有权录制会议的信息，请参阅 [Teams 会议的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

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
|      我希望为大多数用户关闭录制，但选择性地启用允许录制的特定用户       | <ol><li>确认全局 CsTeamsMeetingPolicy 中 AllowCloudRecording = False<li>为大多数用户授予了全局 CsTeamsMeetingPolicy 或授予了 AllowCloudRecording = False 的 CsTeamsMeetingPolicy 策略之一<li>为所有其他用户授予了 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会议录像的存储位置

会议录制存储在 Microsoft Stream 云存储空间内。 目前，对于 Teams 数据存储在国内的客户而言，如果 Microsoft Stream 在其存放数据的国内数据驻留区域中不可用，则会为其关闭 Teams 会议录制功能。 即使 Microsoft Stream 在地区内数据驻留区域不可用，也可以为应存储在国内的客户启用会议录制功能。 为此，可以允许录制内容存储在 Microsoft Stream 的最近地理区域中。 

如果你的 Teams 数据存储在国内，并且你希望在国内存储会议录像，我们建议你关闭该功能，然后在我们将 Microsoft Stream 部署到你所用的国内数据驻留区域后再将其打开。 若要为组织中所有用户关闭该功能，请关闭 Microsoft Teams 管理中心内全局 Teams 会议策略中的"允许云录制"设置。 但是，如果仍希望允许将录制内容存储在 Microsoft Stream 的最近地理区域中，则必须在更改发生之前同时启用"允许云录制"和"允许区域外录制存储"。

若要在全局策略中启用区域内录制，请使用以下 cmdlet：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

下面总结了当你在此更改生效后打开会议录制时会发生的情况：

|如果打开会议录制...|会议录像的存储位置 |
|---|---|
|在 Microsoft Stream 在你的国内数据驻留区域可用之前 |位于最近的 Microsoft Stream 区域|
|Microsoft Stream 在你的国内数据驻留区域可用后 |在你的国内数据驻留区域|

对于尚未开启会议录制的新增和现有租户，当 Microsoft Stream 在国内数据驻留区域中可用后，新录制的内容将存储在国内。 但是，在 Microsoft Stream 可用于国内数据驻留区域之前启用会议录制的任何租户将继续将 Microsoft Stream 存储用于现有和新录制，即使 Microsoft Stream 在地区内数据驻留区域可用。

若要查找你的 Microsoft Stream 数据的存储区域，请在 Microsoft Stream 中单击右上角的 **?**， 单击“**关于 Microsoft Stream**”，然后单击“**您的数据存储于**”。  若要深入了解 Microsoft Stream 存储数据的区域，请参阅 [Microsoft Stream 常见问题解答](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要详细了解 Microsoft 365 或 Office 365 中跨服务存储数据的位置，请参阅数据所在的 [位置？](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>打开或关闭录制转录

此设置控制在播放会议录制期间字幕和听录功能是否可用。 如果关闭此功能，在播放会议录制期间，"搜索"和"抄送"选项将不可用。 开始录制的人需要启用此设置，以便录制还包括听录。

> [!NOTE]
> 目前，仅 Teams 中语言设置为英语以及会议中会说出英语的用户支持录制的会议的听录。 它们与会议录制一起存储在 Microsoft Stream 云存储中。

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

1 小时录像的大小为 400 MB。 请务必了解所录文件所需要的容量，并确保在 Microsoft Stream 中有足够的可用存储空间。  阅读 [Microsoft 流许可概述](https://docs.microsoft.com/stream/license-overview) ，了解订阅中包含的基本存储以及如何购买其他存储。

## <a name="manage-meeting-recordings"></a>管理会议录像

我们将会议录像视为租户所有的内容。 如果录像的所有者离开了公司，管理员可以在管理员模式下打开 Microsoft Stream 中的录制视频 URL。 管理员可以删除相应录像、更新任何录制元数据或更改所录制视频的权限。 深入了解 [Stream 中的管理员功能](https://docs.microsoft.com/stream/manage-content-permissions)。

> [!NOTE]
> 有关管理录像和用户访问的其他信息，请参阅[管理 Microsoft Stream 中的用户数据](https://docs.microsoft.com/stream/managing-user-data)和 [Microsoft Stream 中的权限和隐私](https://docs.microsoft.com/stream/portal-permissions)。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>会议录像的合规性和电子数据展示

会议录制存储在 Microsoft Stream 中，符合 Microsoft 365 和 Office 365 层 C 规范。 为了在 Microsoft Stream 中支持对会议或通话录像感兴趣的合规性管理员的电子数据展示请求，我们会在 Microsoft Teams 的合规性内容搜索功能中提供录制已完成的消息。 合规性管理员可在合规性内容搜索预览中的项目主题行中查找关键字“录像”，找到组织中的会议和通话录像。 查看所有录像的前提条件是，他们需要在 Microsoft Stream 中具有管理员访问权限。 深入了解如何[分配 Stream 中的管理员权限](https://docs.microsoft.com/stream/assign-administrator-user-role)。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
