---
title: 什么是团队 live 事件？
author: TonySmith
ms.author: tonysmit
manager: serdars
ms.date: 7/11/2018
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: 了解如何 Live 事件使用户能够广播视频和 Microsoft 团队、 Yammer 和 Microsoft 流中的大型联机访问群体的内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d259231709b7b9a16afc6d10afbcc9b9a7ed410
ms.sourcegitcommit: b9f33329cbf3352bfe3741717abcf871e7395657
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "20412301"
---
# <a name="what-are-teams-live-events"></a>什么是团队 live 事件？
**摘要**： 了解如何 live 事件使用户能够广播视频和 Microsoft 团队、 Yammer 和 Microsoft 流中的大型联机访问群体的内容。

## <a name="overview"></a>概述
Microsoft 365 中的实时事件使用户能够广播视频和 Microsoft 团队、 Yammer 和[Microsoft 流](https://docs.microsoft.com/en-us/stream/)中的大型联机访问群体的内容。 

Microsoft 团队提供了基于聊天的协作，调用，会议和 live 事件，您可以展开您的会议的访问群体。 Microsoft 团队 live 事件是一种扩展的团队会议，使用户能够为大型联机访问群体广播视频和会议内容。 通过这些方法，其中的事件宿主前导之间的交互和访问群体参与主要是为了查看共享的主机的内容-一对多通信。 与会者可以观看 Yammer、 团队和/或 Microsoft 流的活动或录制事件，并可以与通过仲裁 Q & A 演示者进行交互或 Yammer 对话。 

团队 live 事件被视为 Skype 会议广播的下一个版本和最终将替换 Skype 会议广播中提供的功能。 对于 live 事件的公共预览版本，Microsoft 将继续支持服务的新的或将来事件不会中断的 Skype 会议广播。 我们建议您试用团队利用新功能包括屏幕共享，attendee 计数中的实时事件和外部的硬件软件编码器的支持。 

相关： [Microsoft 团队 live 事件概述](https://support.office.com/en-us/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US)。

## <a name="key-components"></a>主要组件
下图显示了高级别组件参与 Microsoft 365 live 事件。 

![团队 live 事件](media/teams-live-events.png)

### <a name="scheduling"></a>日程安排
团队提供的组织者要与相应的与会者权限创建事件指定事件的工作组成员、 选择生产方法邀请与会者的功能。 如果从 Yammer 组内创建的实时事件，live 事件与会者都将能够使用 Yammer 对话与事件团队进行交互。 

### <a name="production"></a>生产
Microsoft 365 中的实时事件支持生产方案提供了一系列，包括使用和网络摄像机快速入门事件或使用 studio 质量设备外部编码器事件。 视频是 live 事件的基础，这可以因而异单个网络摄像机到多照相机专业人员视频生产环境。 客户可以选择以下选项，具体取决于其项目要求和预算。 
- **快速入门**： 快速入门方法允许用户生成使用团队会议其 live 事件。 如果您想要使用音频和视频设备连接到 PC 和/或正在邀请远程演示者，此选项是最佳 / 的参与事件中的小组。 此选项允许用户轻松地使用其和网络摄像机和作为输入到广播共享其屏幕。 
- **外部编码器 （即将推出）**： 外部编码器允许用户产生直接从外部硬件或与 Microsoft 流基于软件的编码器其 live 事件。 如果您已有 studio 质量设备 （如媒体混音器） 的支持流 RTMP 服务最佳此选项。 如 executive 城镇大厅 – 其中从媒体混音器为单个流广播到该访问群体的大型事件通常使用此选项。 

### <a name="streaming-platform"></a>流式平台
这是组成的以下部分。

#### <a name="azure-media-services"></a>Azure 媒体服务
[Azure Media Services](https://docs.microsoft.com/en-us/azure/media-services/previous/)为您提供了广播质量视频流的服务访问今天的最常用的移动设备上的较大访问群体。 Media Services 增强辅助功能、 分发和可伸缩性，并使其简单且经济高效流内容到您的本地和全球访问群体 — 同时保护您的内容。

#### <a name="azure-content-delivery-network-cdn"></a>Azure 内容交付网络 (CDN)
一旦您流投入，它被通过[Azure 内容交付网络 (CDN)](https://docs.microsoft.com/en-us/azure/cdn/)。 Azure Media Services 提供集成的 CDN 流终结点。 这样您与无缓冲全世界范围内查看的流。 

### <a name="enterprise-content-delivery-network-ecdn"></a>企业内容交付网络 (eCDN) 
ECDN 的目标是从 internet 视频内容并不会影响网络性能分布在整个企业的内容。 您可以使用以下认证的合作伙伴优化您的网络的实时事件： 
- 配置单元
- Kollective
- 提升 （即将推出快速开始到）

### <a name="attendee-experience"></a>参与者的体验
参与者的体验是 live 事件的最重要方面和很重要的与会者可以参加的实时事件毫无问题。 参与者的体验使用 Azure 媒体播放器并跨桌面、 浏览器中，和 mobile (iOS，Android) 的工作方式。 Microsoft 365 提供 Yammer 和团队为两个协作集线器和 live attendee 体验集成到这些协作工具。 也可以通过 Microsoft 流门户中的与会者访问的基于外部编码器 live 事件。

## <a name="prerequisites"></a>先决条件

### <a name="who-can-create-live-events"></a>谁可以创建 live 事件
以下必备组件所需的用户安排的预览时间段中的实时事件：  
- 用户具有的 Office 365 企业版 E3 或 E5 许可证。 
- 用户启用了业务 Online 和 Microsoft 流 Skype 的 Microsoft 团队。
- 用户启用了专用会议安排在工作组 （TeamsMeetingPolicy AllowPrivateMeetingScheduling 设置为 True）。
- 用户启用了在工作组中计划 live 事件 （TeamsMeetingBroadcastPolicy AllowBroadcastScheduling 设置为 True）。
- 用户具有权限 （对于外部编码器生产） 在 Microsoft 流中创建 live 事件。

> [!NOTE]
> O365 来宾，联盟和匿名用户不能为生产者或团队 live 事件中的演示者邀请。 
 
### <a name="who-can-watch-live-event"></a>谁可以观看 live 事件
查看下查看谁可以参加的实时事件表。 

|Attendee 可见性           |快速入门  |外部编码器  |
|------------------------------|-------------|------------------|
|公共 （匿名用户）      |  是        |  否              |
|来宾用户 *                   |  否         |  否              |
|联盟公司 * 中的所有人 |  否         |  否              |
|公司中的所有人           |  是        |  是             |
|特定于组 / 人员      |  是        |  是             |
* 来宾和联盟用户可以加入作为匿名 live 事件与会者。

Office 365 许可证需要参加的实时事件作为经过身份验证的用户，具体取决于生产方法。

- **为快速开始生产**： 用户必须是团队用户。
- **为外部编码器生产**： 用户必须是流用户。
 
## <a name="capabilities"></a>功能
下表重点介绍 live 事件以及它们如何与 Skype 会议广播不同中提供的核心功能。 

|功能   |Skype 会议直播 |团队 live 事件 （快速入门） |团队 live 事件 （外部编码器） |
|---------|---------|---------|---------|
|最大访问群体大小 |10,000 与会者 |10,000 与会者 |10,000 与会者 |
|创建 live 事件 |   Skype 会议广播的门户 |通过团队 Yammer 团队 | 通过团队流 Yammer 团队 |
|访问群体合作 – Yammer |& #x 2714; |& #x 2714;（集成的体验） |& #x 2714;（集成的体验） |
|访问群体合作 – 仲裁 Q & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|不对 Windows 上的客户端 |& #x 2714;(For Business 的 Skype) |& #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|在 Mac 上不对客户端 |X  | & #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|不对用户界面中的与会者计数 |X  |& #x 2714;（工作组） |& #x 2714;（流，通过流团队嵌入） |
|允许多个演示者 |& #x 2714;(For Business 的 Skype) |& #x 2714;（工作组） |不适用  |
在会议期间邀请演示者 |& #x 2714;(For Business 的 Skype) |X |不适用 |
|Web 和移动设备上的演示者加入 |& #x 2714;(For Business 的 Skype)  |X |不适用 |
|演示者 – PSTN 访问 |X |& #x 2714;（工作组） |不适用 |
|显示一个屏幕 |X |& #x 2714;（工作组） |不适用 |
|演示 PowerPoint （PPT 共享） |& #x 2714; |X （通过屏幕共享缓解） |不适用 |
|基于云的会议录制 |& #x 2714; |& #x 2714; |& #x 2714; |
|自动将记录发布到 Microsoft 流 |X |X |& #x 2714; |
|实时标题和转换 |& #x 2714; |& #x 2714;（即将推出） |X |
|在 live 事件录制的标题 |& #x 2714; |& #x 2714;（即将推出） |& #x 2714; |
|Attendee DVR 控件 （暂停、 后退） |& #x 2714; |& #x 2714; |& #x 2714; |
|合作伙伴 eCDN 支持 |& #x 2714;（配置单元，Kollective，提升） |& #x 2714;（即将推出） |& #x 2714;（配置单元，Kollective，提升） |
|生产者后广播出席情况报告 |& #x 2714; |& #x 2714;（即将推出） |X |
|访问群体的观点分析 – Live 投票和投票 |& #x 2714;（Microsoft 脉冲） |X |X |

## <a name="planning--setup"></a>规划和安装程序
本文介绍了您的组织中，您就可以设置与团队 live 事件的用户。

1. 检查[团队区域可用性 live 事件](#configure-live-events)了解 live 事件是中当前可用的区域。
2. 如果您没有这样做，为组织设置[业务 online Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e) 。
3. 如果您有与会者加入从企业网络内部，请考虑入职培训和[Microsoft 建议 eCDN 提供程序的设置](#set-up-ecdn-provider-for-teams-live-events)，以优化您的网络带宽。 
4. 确保您具有正确的许可证分配[谁可以创建 live 事件](#who-can-create-live-events)和[谁可以观看 live 事件](#who-can-watch-live-event)。 
5. [启用 live 事件计划](#enable-live-event-scheduling-for-the-user)应能够在您的公司中创建 live 事件的用户。 这是必需的快速入门和外部编码器事件。 
6. 对于外部编码器事件，[使 Microsoft 流管理门户中的实时事件创建的用户](#enable-microsoft-stream-for-users-in-the-organization)。  

### <a name="regional-availability-for-teams-live-events"></a>区域可用于团队 live 事件
您可以在多个区域中使用团队 live 事件。 以下信息显示事件工作组成员和与会者的可用性。 根据组织者和 Office 365 租户自动选择的区域的事件。

#### <a name="regions-available"></a>可用的区域
- 美国
- 欧洲/非洲
- 亚太地区

#### <a name="exclusions"></a>排除
- 转局部变量
  - 当前不支持英国、 印度和其他 Microsoft 团队转局部变量。
- 加拿大转本地- 
  - 在预览中，客户可以创建事件，但他们的数据将驻留在北美区域。
- 中国
  - 事件团队成员和与会者将不能使用团队 live 事件，因为 Azure CDN 不是在中国可访问。 解决方法是使用公司 VPN 连接，获取通过客户的企业网络连接到 CDN 的客户端。

### <a name="set-up-your-network-for-teams-live-events"></a>设置您的网络团队 live 事件 
即将推出。

### <a name="set-up-ecdn-provider-for-teams-live-events"></a>设置团队 eCDN 提供程序 live 事件
即将推出。

### <a name="enable-live-event-scheduling-for-the-user"></a>启用的用户安排 live 事件
默认情况下，为团队用户启用 live 事件计划时。  

用户能否团队在创建 live 事件，或不使用 AllowBroadcastScheduling TeamsMeetingBroadcastPolicy 团队 powershell 中设置来控制。 您可以了解有关管理 Office 365 PowerShell 中使用的 TeamsMeetingBroadcastPolicy[此处](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 除非您的自定义策略分配给用户，用户将获得全局策略，其中包含默认情况下启用录制。 

 为了向回退到全局策略的用户，使用以下 cmdlet 删除特定的策略分配关系的用户。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
若要更改的 AllowBroadcastScheduling 全局策略中的值，请使用以下 cmdlet:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Scenarios
**我希望公司能创建实时事件中的所有用户。**
1. 确认全局 CsTeamsMeetingBroadcastPolicy 具有 AllowBroadcastScheduling = True。
2. 确认所有用户都有全局 CsTeamsMeetingBroadcastPolicy 或与 AllowBroadcastScheduling CsTeamsMeetingBroadcastPolicy 策略之一 = True。

**我希望大多数我用户能够创建 live 事件，但希望用户不允许有选择地禁用特定用户。**
1. 确认全局 CsTeamsMeetingBroadcastPolicy 具有 AllowBroadcastScheduling = True。
2. 确认大多数用户具有全局 CsTeamsMeetingBroadcastPolicy 或与 AllowBroadcastScheduling CsTeamsMeetingBroadcastPolicy 策略之一 = True。
3. 确认所有其他用户已被授予与 AllowBroadcastScheduling CsTeamsMeetingBroadcastPolicy 策略之一 = False。

**我希望 live 事件计划为 100%已禁用。**
1. 确认全局 CsTeamsMeetingBroadcastPolicy 具有 AllowBroadcastScheduling = False。
2. 确认所有用户已被都授予全局 CsTeamsMeetingBroadcastPolicy OR CsTeamsMeetingBroadcastPolicy 策略之一与 AllowBroadcastScheduling = False。

**我想要禁用的大多数用户，但有选择性地启用 live 事件的特定用户的 live 事件。** 
1. 确认全局 CsTeamsMeetingBroadcastPolicy 具有 AllowBroadcastScheduling = False。
2. 确认大多数用户已被授予全局 CsTeamsMeetingBroadcastPolicy OR CsTeamsMeetingBroadcastPolicy 策略之一与 AllowBroadcastScheduling = False。
3. 确认所有其他用户已被授予与 AllowBroadcastScheduling CsTeamsMeetingBroadcastPolicy 策略之一 = True。

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>启用的用户的外部基于编码器的实时事件的创建

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>为组织中的用户启用 Microsoft 流
Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。 有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/en-us/stream/license-overview)。 请注意业务 Essentials 中不包含 Microsoft 流或企业高级版计划。  

了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。 确保 Microsoft 流的用户不进行阻止，如[本文](https://docs.microsoft.com/en-us/stream/disable-user-organization)中所定义。

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>确保用户具有 Microsoft 流中的实时事件创建权限
默认情况下，公司中的所有人都可以在流中，创建内容后启用流和许可证分配给用户。 Microsoft 流管理员可以[限制用于创建内容的员工](https://docs.microsoft.com/en-us/stream/restrict-uploaders)对流中。 此限制的列表中的用户将无法录制会议。

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>确保组织者同意流管理设置的公司策略的实时事件
如果 Microsoft 流管理员[设置的公司准则策略](https://docs.microsoft.com/en-us/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，然后用户必须这样的 Microsoft 团队在创建 （具有外部编码器生产） 的实时事件之前。 之前您推出组织中的实时事件功能，请确保将创建这些 live 事件的用户同意策略。 

## <a name="configure-live-events"></a>配置 live 事件

### <a name="set-up-event-support-link-coming-soon"></a>设置事件支持链接 （即将推出）
这是将向 live 事件与会者显示的链接。 

PowerShell

在 Windows PowerShell 中，运行以下 cmdlet:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>配置 attendee 可见性选项
这将允许 live 事件组织者具有适当的与会者可见性创建事件。

|值  |行为  |
|---------|---------|
|所有人     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公共，公司和特定人员中的每个人。 |
|EveryoneInCompany     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公司和特定人员中的每个人。 用户无法创建可由匿名用户参加的实时事件。|
|InvitedUsers |用户只能创建 live 被限制为特定的某个人，如输入的事件管理器的事件。 用户不能与公共和公司身份验证中的每个人创建 live 事件。 |

PowerShell

使用 BroadcastAttendeeVisibility TeamsMeetingBroadcastPolicy 在 PowerShell 中设置来控制是否用户可以安排可以监视通过匿名与会者的广播的事件。 您可以了解有关管理 Office 365 PowerShell 中使用的 TeamsMeetingBroadcastPolicy 此处的详细信息。  

除非您的自定义策略分配给用户，用户将获得全局策略，具有默认设置为 EveryoneInCompany。 
 
在 Windows PowerShell 中，运行以下 cmdlet，以允许用户在全局策略中创建匿名事件：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>配置录制选项
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

始终记录的实时事件，从不记录还是事件组织者可以决定记录事件，这样，管理员控制。  

|值  |行为  |
|---------|---------|
|始终启用 |始终记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，事件团队成员是否能够下载事件之后录制并与会者可以观看后的事件是通过的事件。 |
|AlwaysDisabled |永远不会记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，事件工作组成员创建不录制并与会者无法观看结束后的事件。 |
|UserOverride |用户可以决定是否 live 事件将记录，以便为事件工作组成员可以创建一个录制文件和与会者可以观看后的事件是通过的事件。 |

PowerShell

使用录制选项创建的实时事件管理器的实时事件的控件设置 BroadcastRecordingMode TeamsMeetingBroadcastPolicy 在 PowerShell 中。

在 Windows PowerShell 中，运行以下 cmdlet 以更新全局策略中的记录模式：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>配置实时转录和转换团队 live 事件 （即将推出）
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

这将允许 live 事件组织者，以启用实时标题和转换为 live 事件与会者。 

PowerShell

使用中的设置 AllowBroadcastTranscription TeamsMeetingBroadcastPolicy 在 PowerShell 中控制是否 live 事件与会者都将能够看到转录和转换。 您可以了解有关管理 Office 365 PowerShell 中使用的 TeamsMeetingBroadcastPolicy 此处的详细信息。  

除非您的自定义策略分配给用户，用户将获得全局策略，具有转录和默认情况下禁用的转换。

在 Windows PowerShell 中，运行以下 cmdlet，以在全局策略中打开转录和上的事件与会者的转换：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="self-service-administration-tools"></a>自助服务管理工具 
虽然 Microsoft 直接控制所有 Office 365 Online 数据中心，并负责整体系统性能，但它可以控制仅结合为 Office 365 用户提供的总体体验的元素的一部分。 组织自己负责网络连接到数据中心，客户的广域网 (WAN) 和客户的局域网 (Lan)。 此外，它们是负责用户设备和其配置。边缘服务器还负责维护所需的授权每个用户的任何所需的功能，包括，但不是限于到，只要用户需要访问功能的管理这些功能的功能。

客户可以使用以下工具来管理的各种工作组 live 事件相关的任务。
- [Microsoft Office 365 管理中心](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft 团队和 Skype 的业务 Online 管理中心](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Microsoft 流管理中心
- [远程 Windows PowerShell](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？
- 当谈到 Windows PowerShell，它的所有有关管理用户和用户允许或不允许执行的操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)

- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

