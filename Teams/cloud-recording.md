---
title: Teams 云会议录制
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sonua
search.appverid: MET150
description: 在 Microsoft Teams 中部署云语音功能实践指导
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1819aa33dd951483754f4c00377865460a3765ff
ms.sourcegitcommit: d4113b46e9afbc4ae6bd3e870851cfb822031ff0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "26620080"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

在 Microsoft 团队中，用户可以记录其团队会议和捕获音频、 视频和共享活动的屏幕的组呼叫。 还有一个选项以录制内容已自动转录，以便用户可以播放会议录制与字幕和搜索重要讨论项在脚本中。 录制云中发生的情况，并保存到[Microsoft 流](https://docs.microsoft.com/stream/)，以便用户可以跨组织安全地共享它。

相关：[团队会议录制最终用户文档](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>团队云会议录制的先决条件

要记录的团队用户的会议，必须为租户启用 Microsoft 流。 此外，则会议组织者和正在启动录制的人员所必需的以下先决条件：

- 用户具有 Office 365 E1、 E3、 E5、 A1，A3、 A5、 M365 业务、 企业高级版或业务 Essentials
- 用户需要 Microsoft 流的许可
- 用户具有 Microsoft 流上载视频的权限
- 用户已同意的公司准则，如果管理员设置
- 用户要保存录制的 Microsoft 流中具有足够的存储空间
- 用户具有 TeamsMeetingPolicy AllowCloudRecording 设置设置为 true
- 用户具有 TeamsMeetingPolicy AllowTranscription 设置设置为 true，以便用户可以选择是否自动，理赔录制
- 用户不是匿名，来宾或会议中的联合的用户

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>设置团队云会议录制您的组织中的用户

本节介绍如何设置和规划团队会议录制。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>为组织中的用户启用 Microsoft 流

Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。  请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)的详细信息。  Microsoft 365 企业版和 Office 365 企业高级版，Office 365 业务 Essentials 现在包含 Microsoft 流。

了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。 确保 Microsoft 流将不阻止用户，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中定义。

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>确保用户具有上载 Microsoft 流中的视频权限

默认情况下，公司中的所有人都可以在流中，创建内容后启用流和许可证分配给用户。 Microsoft 流管理员可以[限制用于创建内容的员工](https://docs.microsoft.com/stream/restrict-uploaders)对流中。 此限制的列表中的用户将无法录制会议。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知员工同意 Microsoft 流中的公司准则

如果 Microsoft 流管理员[设置公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，用户必须完成之前的 Microsoft 团队中的记录。 推出组织中的录制功能之前，请确保用户同意策略。

### <a name="enabledisable-cloud-recording-for-users"></a>启用/禁用将云用户录制

使用中的设置 AllowCloudRecording 团队 powershell TeamsMeetingPolicy 控制是否允许用户的会议录制。 您可以了解有关管理 Office 365 PowerShell 中使用的 TeamsMeetingPolicy[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

请注意，会议组织者和录制发起者需要有权录制会议录制。 除非您的自定义策略分配给用户，用户将获得全局策略，其中包含默认情况下禁用 AllowTranscription。

对于用户回退到全局策略，使用以下 cmdlet 删除特定的策略分配的用户：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改的 AllowCloudRecording 全局策略中的值，请使用以下 cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 应用场景                                                                 |                                                                                                                                                                         步骤                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我希望公司能够记录其会议中的所有用户                                    |                                                                     <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>所有用户都有全局 CsTeamsMeetingPolicy 或与 AllowCloudRecording CsTeamsMeetingPolicy 策略之一 = True </ol>                                                                     |
| 我希望大多数我用户能够以记录其会议，但有选择地禁用特定用户不允许进行录音 |        <ol><li>确认 GlobalCsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>大多数用户具有全局 CsTeamsMeetingPolicy 或一个 CsTeamsMeetingPolicy 策略的与 AllowCloudRecording = True<li>所有其他用户已被授予与 AllowCloudRecording CsTeamsMeetingPolicy 策略之一 = False</ol>         |
|                                                   我希望录制为 100%已禁用                                                   |                                                                <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>所有用户已被都授予全局 CsTeamsMeetingPolicy OR CsTeamsMeetingPolicy 策略之一与 AllowCloudRecording = False                                                                 |
|      我希望录制的大部分用户禁用，但有选择性地启用特定用户允许进行录音       | <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或一个 CsTeamsMeetingPolicy 策略的与 AllowCloudRecording = False<li>所有其他用户已被授予与 AllowCloudRecording CsTeamsMeetingPolicy 策略之一 = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="enabledisable-recording-transcription-for-users"></a>启用/禁用的用户的录制转录

在用户记录其团队会议时，他们可以确认是否脚本应自动生成后录制会议。 如果管理员已禁用会议组织者和录制启动器转录功能，录制发起者不会选择，理赔会议录制。

使用中的设置 AllowTranscription 团队 powershell TeamsMeetingPolicy 控制是否录制启动器获取理赔会议录制可选择。 您可以了解有关管理 Office 365 PowerShell 中使用的 TeamsMeetingPolicy[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

已分配给用户的自定义策略，除非他们获取全局策略，其中已禁用默认情况下启用。

对于用户回退到全局策略，使用以下 cmdlet 删除特定的策略分配的用户：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改的 AllowCloudRecording 全局策略中的值，请使用以下 cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|应用场景|步骤 |
|---|---|
|我希望公司能够理赔时启动录制的会议中的所有用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>所有用户都有全局 csTeamsMeetingPolicy 或一个带有 AllowTranscription 的 CsTeamsMeetingPolicy 策略 = = True。 </ol>|
|我希望大多数我用户能够理赔会议录制，但有选择地禁用不允许，理赔特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>大多数用户具有全局 CsTeamsMeetingPolicy 或一个 CsTeamsMeetingPolicy 策略的与 AllowTranscription = True <li>所有其他用户已被授予与 AllowTranscription CsTeamsMeetingPolicy 策略之一 = False </ol>|
|我希望转录为 100%已禁用的录音 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = False <li>所有用户已被都授予全局 CsTeamsMeetingPolicy OR CsTeamsMeetingPolicy 策略之一与 AllowTranscription = False </ol>|
|我希望转录大部分用户禁用，但有选择性地启用允许，理赔特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False <li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或一个 CsTeamsMeetingPolicy 策略的与 AllowCloudRecording = False <li>所有其他用户已被授予与 AllowCloudRecording CsTeamsMeetingPolicy 策略之一 = True </ol>|
|||

### <a name="planning-for-storage"></a>正在计划存储

1 小时录制内容的大小为 400 MB。 请确保您了解要求录制的文件的容量和 Microsoft 流中有足够的存储空间可用。  阅读的[本文](https://docs.microsoft.com/stream/license-overview)以了解订阅以及如何购买额外的存储空间中包含的基存储。

## <a name="manage-meeting-recordings"></a>管理会议录音
会议录制视为租户拥有的内容。 录制的所有者离开公司时，如果管理员在管理模式下可以录制视频 URL Microsoft 流中打开。 管理员可以删除录制、 更新任何记录的元数据，或更改的视频录制的权限。 了解有关[流中的管理功能](https://docs.microsoft.com/stream/manage-content-permissions)的详细信息。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>合规性和会议录音的电子数据展示
在 Microsoft 流中，这是 Office 365 层-C 符合存储会议录制。 若要为合规性管理员感兴趣的 Microsoft 流开会或打电话录制支持电子发现请求，录制已完成的消息中提供了 Microsoft 团队的合规性内容搜索功能。 合规性管理员可以查找"录制"合规性内容搜索预览中的项目的主题行中的关键字和发现会议和呼叫组织中的记录。 用户可以查看所有录制先决条件是，他们将需要设置 Microsoft 流中具有管理员访问权限。 了解有关[流中的分配管理员权限](https://docs.microsoft.com/stream/assign-administrator-user-role)的详细信息。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
- [为 Windows PowerShell 设置计算机](https://go.microsoft.com/fwlink/?LinkId=525038)

