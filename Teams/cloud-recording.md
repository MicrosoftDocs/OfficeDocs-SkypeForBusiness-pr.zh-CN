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
f1.keywords:
- NOCSH
description: 在 Microsoft Teams 中部署云语音功能实践指导
appliesto:
- Microsoft Teams
ms.openlocfilehash: 678e17ed92c0f269e134ac6c23dce29169c0d36d
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42582999"
---
# <a name="teams-cloud-meeting-recording"></a>Teams 云会议录制

> [!IMPORTANT]
> **将来，我们正在进行配置更改**，在这种情况下，将为团队数据存储在全国范围内的客户打开团队会议录制功能，即使 Microsoft Stream 在国内数据派驻区域中不可用。 当此更改生效时，默认情况下，会议录制将存储在最接近的 Microsoft Stream 区域中。 如果你的团队数据存储在国家/地区，并且你希望在国家/地区存储会议录制，我们建议你关闭会议录制，然后在将 Microsoft Stream 部署到你的国内区域后将其打开。 若要了解详细信息，请参阅[会议录制的存储位置](#where-your-meeting-recordings-are-stored)。

在 Microsoft 团队中，用户可以记录其团队会议和群组通话，以捕获音频、视频和屏幕共享活动。 还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制将在云中发生，并保存到[Microsoft Stream](https://docs.microsoft.com/stream/)，以便用户可以安全地在其组织中共享它。

相关：[团队会议录制最终用户文档](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>团队云会议录制的先决条件

对于要录制的团队用户的会议，必须为租户启用 Microsoft Stream。 此外，会议组织者和启动录制的人员需要以下先决条件：

- 用户拥有 Office 365 E1、E3、E5、A1、A3、A5、M365 Business、Business Premium 或 Business Essentials
- 用户需要获得 Microsoft Stream<sup>1</sup>的许可 
- 用户拥有 Microsoft Stream 上载视频权限
- 如果由管理员设置，则用户同意公司指南
- 用户在 Microsoft Stream 中有足够的存储空间，以便保存录制
- 用户已将 TeamsMeetingPolicy-AllowCloudRecording 设置设置为 true
- 用户不是会议中的匿名、来宾或联盟用户

> [!NOTE]
> 此外，若要允许启动录制的人员选择是否自动稍后将录制，用户的 TeamsMeetingPolicy-AllowTranscription 设置必须设置为 true

<sup>1</sup>用户需要获得授权才能将会议上载/下载到 Microsoft Stream，但不需要许可证即可录制会议。 如果您希望阻止用户录制 Microsoft 团队会议，则必须授予 AllowCloudRecording 设置为 $False 的 TeamsMeetingPolicy。

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>为组织中的用户设置团队云会议录制

本部分介绍了如何为录制团队会议进行设置和规划。

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>为组织中的用户启用 Microsoft Stream

Microsoft Stream 作为符合条件的 Office 365 订阅的一部分或作为独立服务提供。  有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。  Microsoft Stream 现已包含在 Microsoft 365 Business、Office 365 商业高级版和 Office 365 Business Essentials 中。

深入了解如何[向 Office 365 中的用户分配许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft Stream。 请确保未阻止用户的 Microsoft Stream，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所述。

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>确保用户在 Microsoft Stream 中有上载视频权限

默认情况下，公司中的每个人都可以在流中创建内容，并为该用户分配了许可证。 Microsoft Stream 管理员可以限制员工在流中[创建内容](https://docs.microsoft.com/stream/restrict-uploaders)。 受限制列表中的用户将无法录制会议。

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>通知员工同意 Microsoft Stream 中的公司指南

如果 Microsoft Stream 管理员已[设置公司指导原则](https://docs.microsoft.com/stream/company-policy-and-consent)，并且要求员工在保存内容之前接受此策略，则用户必须先执行此操作，然后才能在 Microsoft 团队中录制内容。 在组织中推出录制功能之前，请确保用户同意该策略。

### <a name="turn-on-or-turn-off-cloud-recording"></a>打开或关闭云录制

你可以使用 Microsoft 团队管理中心或 PowerShell 设置团队会议策略，以控制是否可以录制用户的会议。

在 Microsoft 团队管理中心，打开或关闭会议策略中的 "**允许云录制**" 设置。 若要了解详细信息，请参阅[管理团队中的会议策略](meeting-policies-in-teams.md#allow-cloud-recording)。

使用 PowerShell，在 TeamsMeetingPolicy 中配置 AllowCloudRecording 设置。 若要了解详细信息，请参阅[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)和[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

请注意，会议组织者和录制发起人都需要拥有录制会议的录制权限。 除非已向用户分配了自定义策略，否则用户将获取全局策略，默认情况下，AllowCloudRecording 禁用该策略。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改全局策略中 AllowCloudRecording 的值，请使用以下 cmdlet：

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 应用场景                                                                 |                                                                                                                                                                         步骤                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    我希望公司中的所有用户都能够录制其会议                                    |                                                                     <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>所有用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一 </ol>                                                                     |
| 我希望大多数用户能够录制他们的会议，但有选择地禁用不允许录制的特定用户 |        <ol><li>确认 GlobalCsTeamsMeetingPolicy 具有 AllowCloudRecording = True<li>大多数用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowCloudRecording = True 的 CsTeamsMeetingPolicy 策略之一<li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一，其中 AllowCloudRecording = False</ol>         |
|                                                   我想将录制的内容禁用100%                                                   |                                                                <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>所有用户均已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一，AllowCloudRecording = False                                                                 |
|      我希望为大多数用户禁用录制，但有选择地启用允许录制的特定用户       | <ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False<li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一，AllowCloudRecording = False<li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一，其中 AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>会议录制的存储位置

会议录制存储在 Microsoft Stream 云存储中。 当前，如果在存储数据的国内数据派驻区域中未提供 Microsoft Stream，则团队数据存储在国家/地区的客户的会议录制功能将处于关闭状态。 将来，如果客户的数据存储在全国，即使 Microsoft Stream 在国内数据派驻区域中不可用，该会议录制功能也将被打开。

当此更改生效时，默认情况下，会议录制将存储在 Microsoft Stream 最近的地理区域中。 如果你的团队数据存储在国家/地区，并且你希望在国家/地区存储会议录制，我们建议你关闭该功能，然后在将 Microsoft Stream 部署到你的国家数据派驻区域后将其打开。 若要为组织中的所有用户关闭该功能，请在 Microsoft 团队管理中心的 "全局团队会议策略" 中关闭 "**允许云录制**" 设置。

下面是当你在此更改生效时打开会议录制时所发生的情况的摘要：

|如果打开会议录制 .。。 |已存储会议录制 .。。  |
|---------|---------|
|在您的国内数据派驻区域中使用 Microsoft Stream 之前    |在最接近的 Microsoft Stream 区域中         |
|Microsoft Stream 在您的国内数据派驻区域中可用后    | 在您所在国家/地区内数据派驻区域        |

对于尚未启用会议录制的新的和现有租户，在国内数据派驻区域中提供 Microsoft Stream 后，新的录制将存储在国家/地区。 但是，在 Microsoft Stream 在国内数据派驻区域中可用之前启用会议录制的任何租户将继续使用 Microsoft Stream 存储（对于现有的和新的录制），即使 Microsoft Stream 在国内数据派驻区域。

若要查找存储 Microsoft Stream 数据的区域，请在 Microsoft Stream 中单击 **？** 在右上角，单击 "**关于 Microsoft Stream**"，然后单击**存储数据**。  若要了解有关 Microsoft Stream 存储数据的地区的详细信息，请参阅[Microsoft STREAM 常见问题](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in)。

若要了解有关在 Office 365 中跨服务存储数据的位置的详细信息，请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>打开或关闭录制脚本

当用户记录其团队会议时，他们可以确认是否应在录制会议后自动生成记录。 如果为会议组织者和录制发起人禁用了脚本功能，则录制发起人将无法选择稍后将会议录制。

你可以使用 Microsoft 团队管理中心或 PowerShell 设置团队会议策略，以控制录制发起人是否可以选择稍后将会议录制。

在 Microsoft 团队管理中心，打开或关闭会议策略中的 "**允许**脚本安装" 设置。 若要了解详细信息，请参阅[管理团队中的会议策略](meeting-policies-in-teams.md#allow-transcription)。

使用 PowerShell，在 TeamsMeetingPolicy 中配置 AllowTranscription 设置。 若要了解详细信息，请参阅[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)和[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

除非已向用户分配了自定义策略，否则用户将获取全局策略，默认情况下，AllowTranscription 禁用该策略。

若要让用户回退到全局策略，请使用以下 cmdlet 删除用户的特定策略分配：

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

若要更改全局策略中 AllowCloudRecording 的值，请使用以下 cmdlet：

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|应用场景|步骤 |
|---|---|
|我希望公司中的所有用户在发起会议录制时能够稍后将 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>所有用户都具有全局 csTeamsMeetingPolicy 或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一。 </ol>|
|我希望大多数用户能够稍后将会议录制，但有选择地禁用不允许稍后将的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = True <li>大多数用户都具有全局 CsTeamsMeetingPolicy 或具有 AllowTranscription = True 的 CsTeamsMeetingPolicy 策略之一 <li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一，其中 AllowTranscription = False </ol>|
|我希望将录制的记录保持为禁用100% |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowTranscription = False <li>所有用户均已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一，AllowTranscription = False </ol>|
|我希望对大多数用户禁用脚本，但有选择地启用允许稍后将的特定用户 |<ol><li>确认全局 CsTeamsMeetingPolicy 具有 AllowCloudRecording = False <li>大多数用户已被授予全局 CsTeamsMeetingPolicy 或 CsTeamsMeetingPolicy 策略之一，AllowCloudRecording = False <li>所有其他用户均已被授予 CsTeamsMeetingPolicy 策略之一，其中 AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>规划存储

1小时录制的大小为 400 MB。 请确保你了解录制的文件所需的容量，并在 Microsoft Stream 中提供足够的存储空间。  阅读[本文](https://docs.microsoft.com/stream/license-overview)以了解订阅中包含的基本存储以及如何购买更多存储空间。

## <a name="manage-meeting-recordings"></a>管理会议录制

会议录制被视为租户拥有的内容。 如果录制的所有者离开公司，管理员可以在 "管理员模式" 下的 Microsoft Stream 中打开录制视频 URL。 管理员可以删除录制、更新任何录制元数据或更改录制视频的权限。 了解有关[流中的管理员功能的](https://docs.microsoft.com/stream/manage-content-permissions)详细信息。

> [!NOTE]
> 有关管理录制和用户访问的其他信息，请参阅在 microsoft stream 中[管理用户数据](https://docs.microsoft.com/stream/managing-user-data)和[microsoft Stream 中的权限和隐私](https://docs.microsoft.com/stream/portal-permissions)。


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>适用于会议录制的合规性和电子数据展示

会议录制存储在 Microsoft Stream 中，该流是 Office 365 与第 C 版兼容的 Office。 若要支持针对 Microsoft 流感兴趣的合规性管理员的电子查询请求，请在 Microsoft 团队的合规性内容搜索功能中提供录制已完成消息。 合规性管理员可以在合规性内容搜索预览中查找项目主题行中的关键字 "录制"，并发现组织中的会议和呼叫录制。 他们查看所有录制的先决条件是需要在 Microsoft Stream 中使用管理员访问设置。 了解有关[在流中分配管理员权限的](https://docs.microsoft.com/stream/assign-administrator-user-role)详细信息。

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
