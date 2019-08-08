---
title: Teams 云会议录制
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: 在 Microsoft Teams 中部署云语音功能实践指导
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd749e00966c21677019d5d68d12e88287e96b45
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237026"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

在 Microsoft 团队中, 用户可以记录其团队会议和群组通话, 以捕获音频、视频和屏幕共享活动。 还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制将在云中发生, 并保存到[Microsoft Stream](https://docs.microsoft.com/stream/), 以便用户可以安全地在其组织中共享它。

相关:[团队会议录制最终用户文档](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>团队云会议录制的先决条件

对于要录制的团队用户的会议, 必须为租户启用 Microsoft Stream。 此外, 会议组织者和启动录制的人员需要以下先决条件:

- 用户拥有 Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium 或 Business Essentials
- 用户需要获得 Microsoft Stream 的许可
- 用户拥有 Microsoft Stream 上载视频权限
- 如果由管理员设置, 则用户同意公司指南
- 用户在 Microsoft Stream 中有足够的存储空间, 以便保存录制
- 用户已将 TeamsMeetingPolicy-AllowCloudRecording 设置设置为 true
- 用户不是会议中的匿名、来宾或联盟用户

> [!NOTE]
> 此外, 若要允许启动录制的人员选择是否自动稍后将录制, 用户的 TeamsMeetingPolicy-AllowTranscription 设置必须设置为 true

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>为组织中的用户设置团队云会议录制

本部分介绍了如何为录制团队会议进行设置和规划。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>为组织中的用户启用 Microsoft Stream

Microsoft Stream 作为符合条件的 Office 365 订阅的一部分或作为独立服务提供。  有关详细信息, 请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 现已包含在 Microsoft 365 Business、Office 365 商业高级版和 Office 365 Business Essentials 中。

深入了解如何[向 Office 365 中的用户分配许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC), 以便用户可以访问 Microsoft Stream。 请确保未阻止用户的 Microsoft Stream, 如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所述。

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>确保用户在 Microsoft Stream 中有上载视频权限

默认情况下, 公司中的每个人都可以在流中创建内容, 并为该用户分配了许可证。 Microsoft Stream 管理员可以限制员工在流中[创建内容](https://docs.microsoft.com/stream/restrict-uploaders)。 受限制列表中的用户将无法录制会议。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知员工同意 Microsoft Stream 中的公司指南

如果 Microsoft Stream 管理员已[设置公司指导原则](https://docs.microsoft.com/stream/company-policy-and-consent), 并且要求员工在保存内容之前接受此策略, 则用户必须先执行此操作, 然后才能在 Microsoft 团队中录制内容。 在组织中推出录制功能之前, 请确保用户同意该策略。

### <a name="turn-on-or-turn-off-cloud-recording"></a>打开或关闭云录制

使用团队 PowerShell 中 TeamsMeetingPolicy 中的设置 AllowCloudRecording 来控制是否允许录制用户的会议。 你可以在[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)了解有关管理 TeamsMeetingPolicy 365 的详细信息。

请注意, 会议组织者和录制发起人都需要拥有录制会议的录制权限。 除非已向用户分配了自定义策略, 否则用户将获取全局策略, 默认情况下, AllowTranscription 禁用该策略。

若要让用户回退到全局策略, 请使用以下 cmdlet 删除用户的特定策略分配:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改全局策略中 AllowCloudRecording 的值, 请使用以下 cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 应用场景                                                                 |                                                                                                                                                                         步骤                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我希望公司中的所有用户都能够录制其会议                                    |                                                                     <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>所有用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 </ol>                                                                     |
| 我希望大多数用户能够录制他们的会议, 但有选择地禁用不允许录制的特定用户 |        <ol><li>确认 GlobalCsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>大多数用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一<li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一, 其中 AllowCloudRecording = False</ol>         |
|                                                   我想将录制的内容禁用 100%                                                   |                                                                <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>所有用户均已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一, AllowCloudRecording = False                                                                 |
|      我希望为大多数用户禁用录制, 但有选择地启用允许录制的特定用户       | <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一, AllowCloudRecording = False<li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一, 其中 AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>打开或关闭录制脚本

当用户记录其团队会议时, 他们可以确认是否应在录制会议后自动生成记录。 如果管理员已禁用会议组织者和录制发起人的脚本功能, 则录制发起人将不会获得稍后将会议录制的选择。

使用团队 PowerShell 中 TeamsMeetingPolicy 中的设置 AllowTranscription 来控制录制发起人是否可以选择稍后将会议录制。 你可以在[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)了解有关管理 TeamsMeetingPolicy 365 的详细信息。

除非已向用户分配了自定义策略, 否则他们将获得全局策略, 默认情况下, AllowTranscription 禁用该策略。

若要让用户回退到全局策略, 请使用以下 cmdlet 删除用户的特定策略分配:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改全局策略中 AllowCloudRecording 的值, 请使用以下 cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|应用场景|步骤 |
|---|---|
|我希望公司中的所有用户在发起会议录制时能够稍后将 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>所有用户都具有全局 csTeamsMeetingPolicy 或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|我希望大多数用户能够稍后将会议录制, 但有选择地禁用不允许稍后将的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>大多数用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一 <li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一, 其中 AllowTranscription = False </ol>|
|我希望将录制的记录保持为禁用 100% |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = False <li>所有用户均已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一, AllowTranscription = False </ol>|
|我希望对大多数用户禁用脚本, 但有选择地启用允许稍后将的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False <li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一, AllowCloudRecording = False <li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一, 其中 AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>规划存储

1小时录制的大小为 400 MB。 请确保你了解录制的文件所需的容量, 并在 Microsoft Stream 中提供足够的存储空间。  阅读[本文](https://docs.microsoft.com/stream/license-overview)以了解订阅中包含的基本存储以及如何购买更多存储空间。

## <a name="manage-meeting-recordings"></a>管理会议录制
会议录制被视为租户拥有的内容。 如果录制的所有者离开公司, 管理员可以在 "管理员模式" 下的 Microsoft Stream 中打开录制视频 URL。 管理员可以删除录制、更新任何录制元数据或更改录制视频的权限。 了解有关[流中的管理员功能的](https://docs.microsoft.com/stream/manage-content-permissions)详细信息。

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>适用于会议录制的合规性和电子数据展示
会议录制存储在 Microsoft Stream 中, 该流是 Office 365 与第 C 版兼容的 Office。 若要支持针对 Microsoft 流感兴趣的合规性管理员的电子查询请求, 请在 Microsoft 团队的合规性内容搜索功能中提供录制已完成消息。 合规性管理员可以在合规性内容搜索预览中查找项目主题行中的关键字 "录制", 并发现组织中的会议和呼叫录制。 他们查看所有录制的先决条件是需要在 Microsoft Stream 中使用管理员访问设置。 了解有关[在流中分配管理员权限的](https://docs.microsoft.com/stream/assign-administrator-user-role)详细信息。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 365 管理中心, 例如当你为多个用户同时进行设置更改时。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
- [为 Windows PowerShell 设置计算机](https://go.microsoft.com/fwlink/?LinkId=525038)

