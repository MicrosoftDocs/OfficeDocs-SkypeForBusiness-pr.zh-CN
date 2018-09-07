---
title: 什么是团队 live 事件？
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
description: 了解如何 Live 事件使用户能够广播视频和 Microsoft 团队、 Yammer 和 Microsoft 流中的大型联机访问群体的内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfdee5d1cf43c358d2b6a36aad66c38d3e9d8ec9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870584"
---
# <a name="what-are-teams-live-events"></a>什么是团队 live 事件？
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>概述
Microsoft 365 中的实时事件使用户能够广播视频和大型联机访问群体的内容。 Microsoft 365 live 事件使 live 视频流到新的级别，鼓励连接在整个项目生命周期与与会者之前、 升级期间和之后 live 事件。 您可以创建 live 事件，只要在访问群体、 团队或社区驻留，使用 Microsoft 流，Microsoft 团队或 Yammer。  

Microsoft 团队提供基于聊天的协作、 呼叫、 会议和 live 事件，因此您可以展开您的会议的访问群体。 Microsoft 团队 live 事件是一种扩展的团队会议，使用户能够为大型联机访问群体广播视频和会议内容。 通过这些方法，其中的事件宿主前导之间的交互和访问群体参与主要是为了查看共享的主机的内容-一对多通信。 与会者可以观看 Yammer、 团队和/或 Microsoft 流的活动或录制事件，并可与演示者使用仲裁的 Q & A 或 Yammer 对话进行交互。 

团队 live 事件视为 Skype 会议广播的下一个版本和最终将替换 Skype 会议广播中提供的功能。 期间团队 live 事件的公共预览发布，我们将继续支持服务的新的或将来事件不会中断的 Skype 会议广播。 但是，我们建议您试用团队 live 事件可以利用的所有新的和令人兴奋功能包括屏幕共享，attendee 计数和外部的硬件软件编码器的支持。 

因此，就可以开始。 首先，看看演示高级别的组件在 Microsoft 365 live 事件和连接方式所涉及的以下图表。 

![团队 live 事件](../media/teams-live-events.png)

## <a name="key-components"></a>主要组件
因此，您可以看到上面图片中有四个主要组件，也可用于 Microsoft 团队中的实时事件。

### <a name="scheduling"></a>日程安排
团队提供的组织者与相应的与会者权限创建事件、 指定事件的工作组成员、 选择生产方法，并邀请与会者的功能。 如果从 Yammer 组内创建的实时事件，live 事件与会者都将能够使用 Yammer 对话与事件中的人员进行交互。 

### <a name="production"></a>生产
Microsoft 365 中的实时事件支持生产方案提供了一系列，包括使用和网络摄像机快速入门事件或使用 studio 质量设备外部编码器事件。 视频是 Live 事件的基础，这可以因而异单个网络摄像机到多照相机专业人员视频生产环境。 您可以选择以下选项，具体取决于其项目要求和预算。 有两种方法将生成事件：

- **快速入门生产**： 快速入门生产方法允许用户生成使用团队会议其 live 事件。 此选项是最佳，如果您想要使用的音频和视频设备的最快选项连接到 PC，或参与事件邀请远程演示者。 此选项允许用户能够轻松地使用其和网络摄像机和共享其屏幕作为输入到的事件。 


- **外部编码器生产**： 外部编码器允许用户产生直接从外部硬件或与[Microsoft 流](https://stream.microsoft.com)基于软件的编码器其 live 事件。 此选项将是最佳如果您已有 studio 质量设备 （例如，媒体混音器） 到实时消息协议 (RTMP) 服务的支持流式处理。 如 executive 城镇大厅 – 从媒体混音器为单个流将广播到该访问群体其中的大型事件通常用于生产此类型。 

### <a name="streaming-platform"></a>流式平台
Live 事件流式平台由以下四个部分组成：

- **Azure 媒体服务**  [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/)为您提供了广播质量视频流的服务访问今天的最常用的移动设备上的较大访问群体。 Media Services 增强辅助功能、 分发和可伸缩性，并使其简单且经济高效流内容到您的本地或全球访问群体 — 同时保护您的内容。
- **Azure 内容交付网络 (CDN)** 一旦您流投入，它被通过[Azure 内容交付网络 (CDN)](https://docs.microsoft.com/azure/cdn/)。 Azure Media Services 提供集成的 CDN 流终结点。 这样世界各地查看与无缓冲的流。
- **企业内容交付网络 (eCDN)** ECDN 的目标是从 internet 视频内容并不会影响网络性能分布在整个企业的内容。 您可以使用下列选项之一认证 eCDN 合作伙伴优化您的网络保留组织内的实时事件：
    - 配置单元
    - Kollective
    - 提升
- **Attendee 体验** 参与者的体验是 live 事件的最重要方面和很重要，与会者可以参加的实时事件无任何问题。 参与者的体验使用 Azure 媒体播放器并跨桌面、 浏览器中，和 mobile (iOS，Android) 的工作方式。 Office 365 提供 Yammer 和团队为两个协作集线器和 live attendee 体验集成到这些协作工具。 也可以通过在[管理工具](#administrative-tools)中的与会者访问的基于外部编码器 live 事件。

## <a name="planning-for-live-events"></a>规划 live 事件
在规划团队要保留在您生成组织中的大型会议的实时事件时，有需要启动所有最多设置之前，需要考虑的几个因素。 

### <a name="who-can-create-and-schedule-live-events"></a>谁可以创建和安排 live 事件？ 
以下必备组件所需的用户安排的团队 live 事件。

下面是必须分配的许可证：  
- Office 365 企业版 E3 或 E5 的许可证。 
- Microsoft 工作组和 Skype for Business，以及 Microsoft 流许可证。

务必要了解 Office 365 许可证需要参与作为经过身份验证的用户的实时事件，但这取决于所使用的生产方法：

- **为快速开始生产** 必须为用户分配的 Microsoft 团队许可证。
- **为外部编码器生产**必须为用户分配 Microsoft 流许可证。

有关许可的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。

用户必须拥有：
- 在启用的团队中的专用会议计划 (*TeamsMeetingPolicy AllowPrivateMeetingScheduling 参数 = True*)。
- Live 事件计划中启用的团队 (*TeamsMeetingBroadcastPolicy AllowBroadcastScheduling 参数 = True*)。
- 在 Microsoft 流中的实时事件创建 （针对[外部编码器生产](#production)） 的权限。

> [!IMPORTANT]
> Office 365 来宾，联盟和匿名用户不能为生产者或团队 live 事件中的演示者邀请。 但是，来宾和联盟的用户可以作为匿名 Live 事件与会者加入。 
 
### <a name="who-can-watch-live-events"></a>谁可以观看 live 事件？

|**Attendee 可见性**           |**快速入门** |**外部编码器**  |
|------------------------------|-------------|------------------|
|公共 （匿名用户）      |  是        |  否              |
|来宾用户                   |  否         |  否              |
|联盟的公司中的所有人 |  否         |  否              |
|公司中的所有人           |  是        |  是             |
|特定于组 / 人员      |  是        |  是             |
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>团队 live 事件和 Skype 会议广播
下表重点介绍的核心功能和实时事件和它们与 Skype 会议广播的不同方式中提供的功能。 

|**功能**   |**Skype 会议直播** |**团队 live 事件 （快速入门）** |**团队 live 事件 （外部编码器）** |
|---------|---------|---------|---------|
|最大访问群体大小 |10,000 与会者 |10,000 与会者 * |10,000 与会者 * |
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
|合作伙伴 eCDN 支持 |& #x 2714;（配置单元，Kollective，提升） |& #x 2714;（配置单元，Kollective） |& #x 2714;（配置单元，Kollective，提升） |
|生产者后广播出席情况报告 |& #x 2714; |& #x 2714;（功能发行版） |X |
|访问群体的观点分析 – Live 投票和投票 |& #x 2714;（Microsoft 脉冲） |X |X |

> [!IMPORTANT]
> 可能更改设置的限制。

### <a name="regional-availability"></a>区域的可用性
您可以使用团队 live 事件中的多个区域遍及世界各地。 以下信息显示事件工作组成员和与会者的可用性。 

> [!IMPORTANT]
> 根据组织者和 Office 365 组织情况下自动选择的区域的事件。

**在这些区域中可用**
- 美国
- 欧洲/非洲
- 亚太地区
- 转到本地加拿大

**排除和注意事项**
- **转局部变量：** 当前不支持 Unitied Kingdom （英国）、 印度和其他 Microsoft 团队转局部变量。
- **中国：** 事件团队成员和与会者将不能使用团队 live 事件，因为 Azure CDN 不是在中国可访问。 解决方法是使用公司 VPN 连接，获取通过客户的企业网络连接到 CDN 的客户端。

## <a name="setting-up-for-live-events"></a>设置的实时事件
Live 事件的设置时, 有以下几个您必须采取的步骤：

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>步骤 1： 设置您的网络中的 Microsoft 团队的实时事件
快速入门 live 事件要求您[准备贵组织的网络中的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/prepare-network)。  

### <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
确保您具有正确的许可证分配[谁可以创建和安排 live 事件？](#who-can-create-and-schedule-live-events)和[谁可以观看 live 事件？](#who-can-watch-live-events)。

### <a name="step-3-enable-live-event-scheduling-for-users"></a>步骤 3： 启用的用户安排 live 事件
默认情况下，为团队用户，但如果您希望用户能够安排外部编码器事件，必须执行其他步骤情况下，启用 live 事件计划。

#### <a name="for-quick-start-events"></a>快速入门事件
用户能否团队在创建 live 事件，或不使用*AllowBroadcastScheduling* **TeamsMeetingBroadcastPolicy**团队 powershell 中设置来控制。 您可以了解有关管理 TeamsMeetingBroadcastPolicy[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 如果尚未分配自定义策略分配给用户，用户会收到*全局*策略，具有默认情况下启用录制。

验证*AllowBroadcastScheduling*参数设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后将该用户分配到*全局*策略中，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>用户方案
**您希望能够创建 live 事件，公司内的所有用户。**

如果用户分配*Glocal*策略，运行并验证该*AllowBroadcastScheduling* * 设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果用户分配*全局*策略之外的策略，运行以下命令并验证 *-AllowBroadcastScheduling*设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**您希望 live 事件安排在整个组织为 100%已禁用。**

禁用广播计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
组织中的所有用户都分配*全局*策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您希望大量用户能够创建 live 事件，但希望阻止一组用户创建它们。**

将*全局*策略的用户 （即您希望启用） 的一些使用**授予 CsTeamsMeetingBroadcastPolicy**分配但首先运行以下命令并验证*AllowBroadcastScheduling*设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后将一个用户分配到*全局*策略中，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建和分配用于禁用计划使用**授予 CsTeamsMeetingBroadcastPolicy** cmdlet 向其他用户 （您希望禁用） 的策略。 

创建新策略禁用它，运行：
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
禁用计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
然后将用户分配给此策略，请运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**您希望 live 事件要禁用的大量的用户，但希望允许一组用户创建这些。**

禁用广播计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然后将这些用户分配*全局*策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建和分配策略启用计划，请运行：
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
启用计划排定，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然后将用户分配给此策略，请运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>外部编码器事件
您必须执行以下操作来启用 Live 事件计划为这些用户。

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>步骤 1： 在您的组织 * * 中为用户启用 Microsoft 流
Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。 有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。

> ![注意]业务 Essentials 或企业高级版计划中不包含 Microsoft 流。  

了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。 确保 Microsoft 流的用户不进行阻止，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所定义。

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>步骤 2： 确保用户具有 live 事件创建权限中 Microsoft 流 * *
默认情况下，管理员可以创建外部编码器 live 事件。 Microsoft 流管理员可以流中[启用 live 事件创建的其他用户](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>步骤 3： 确保组织者同意设置流管理员 * * 的公司策略的实时事件
如果 Microsoft 流管理员[设置的公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，然后用户必须这样的 Microsoft 团队在创建 （具有外部编码器生产） 的实时事件之前。 之前您推出组织中的实时事件功能，请确保将创建这些 live 事件的用户同意策略。 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>步骤 4： 设置 eCDN 提供程序中的 Microsoft 团队的实时事件 
Live 事件视频播放使用流式处理 (ABR) 的自适应比特率，但它并单播流，这意味着每个查看器从 internet 获取其自己的视频流。 对于 live 事件或发送到您的组织的大部分内容的视频，可能有大量的 internet 带宽使用查看器。 对于希望减少 live 事件此 internet 通信的组织，与 Microsoft 的集成解决方案的实时事件受信任提供软件的视频传送合作伙伴定义网络 (SDNs) 或企业内容交付网络 (eCDNs)。 这些 SDN / eCDN 平台启用组织牺牲最终用户查看体验的情况下优化网络带宽。 我们的合作伙伴可帮助您在企业网络中启用多可扩展且高效的视频分布。

**购买和安装您的解决方案的 Microsoft 团队之外**获取与通过利用 Microsoft 的受信任的视频传送合作伙伴缩放视频传递专家的帮助。 启用用于 Microsoft 团队的视频传输提供程序之前，您必须购买和安装 SDN/eCDN 解决方案外部和分开的 Microsoft 团队。

以下 SDN/eCDN 解决方案前集成，可以为安装程序将与 Microsoft 流一起使用。

- **配置单元流式处理**提供 live 和点播企业视频分布的简单且强大的解决方案。 配置单元是一种基于软件的解决方案，不需要额外的硬件或带宽，并提供了一种启用数千个并发视频查看器，而不会影响您的网络安全方法。 对于希望了解影响视频具有其购买 SDN/eCDN 解决方案之前的网络上的客户，配置单元流还提供基于浏览器的分析解决方案的 Microsoft 客户。 [了解更多信息](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective**是一个基于云的、 智能对等分发平台，利用您现有的网络基础结构来提供多个窗体中的内容，、 (live 视频流，按需视频、 软件更新、 安全修补程序，等等) 更快、 更多可靠地及较少的带宽。 我们安全平台是受信任的世界最大金融机构及任何其他硬件、 设置和维护很容易。 [了解更多信息](http://www.kollective.com)
 
- **提升 OmniCache**提供下一代网络通讯组和跨全局 Wan 确保视频内容的无缝传递，帮助事件生产者优化网络带宽和支持成功 live 事件广播和按需流式处理。 快速入门 live 事件提升 OmniCache 支持即将提供。  [了解更多信息](http://www.ramp.com) 
 
> [!NOTE] 
> 选的 eCDN 解决方案受制于所选**的服务和隐私策略的第三方提供程序的条款**，哪些将控制您使用 eCDN 提供程序的解决方案。 您使用 eCDN 提供程序的解决方案不会受到的 Microsoft 批量许可条款或联机服务条款。 如果您不同意**第三方提供程序的术语**，然后不启用 eCDN 解决方案中的 Microsoft 团队。 

**设置为"快速启动"eCDN live 事件**您可以使用 PowerShell 的 Microsoft 团队中配置 live 事件 eCDN 提供程序。 

> [!NOTE] 
> 可以为组织配置的单个 eCDN 提供程序。 

***配置单元***您可以使用[集 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet 配置 eCDN 提供程序。 首先获取来自您配置单元联系人，然后运行以下许可证 ID 和 API 模板 URL:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective***您可以使用[集 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet 配置 eCDN 提供程序。 首先获取 API 令牌和 API 模板 URL 从 Kollective 联系人，然后运行以下命令：
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**设置为"外部编码器"live 事件 eCDN** 

如果您计划来创建使用外部编码器的实时事件，您将需要以及[配置与 Microsoft 流您 eCDN 提供商](https://docs.microsoft.com/stream/network-caching)。 

## <a name="configure-live-events"></a>配置 live 事件

### <a name="set-up-event-support-link"></a>设置事件支持链接
这是将向 live 事件与会者显示的链接。 

在 Windows PowerShell 中，运行以下命令：
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>配置 attendee 可见性选项
这将允许 live 事件组织者具有适当的与会者可见性创建事件。

|**值**  |**行为**  |
|---------|---------|
|所有人     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公共，公司和特定人员中的每个人。 |
|EveryoneInCompany     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公司和特定人员中的每个人。 用户无法创建可由匿名用户参加的实时事件。|
|InvitedUsers |用户只能创建 live 被限制为特定的某个人，如输入的事件管理器的事件。 用户不能与公共和公司身份验证中的每个人创建 live 事件。 |

使用 BroadcastAttendeeVisibility TeamsMeetingBroadcastPolicy 在 PowerShell 中设置来控制是否用户可以安排可以监视通过匿名与会者的广播的事件。 

除非您的自定义策略分配给用户，用户将获得全局策略，具有默认设置为 EveryoneInCompany。 
 
在 Windows PowerShell 中，运行以下内容以允许用户在全局策略中创建匿名事件：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>配置录制选项
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

始终记录的实时事件，从不记录，还是事件组织者可以决定记录事件，这样，管理员控制。  

|**值**  |**行为**  |
|---------|---------|
|始终启用 |始终记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，事件团队成员能够下载录制后事件，并且与会者可以观看后的事件是通过的事件。 |
|AlwaysDisabled |永远不会记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，为事件团队成员，创建不录制并与会者无法观看结束后的事件。 |
|UserOverride |用户可以决定 live 事件记录，以便在录制文件可以创建为事件工作组成员，并且与会者可以观看后的事件是通过的事件。 |

使用录制选项创建的实时事件管理器的实时事件的控件设置*BroadcastRecordingMode* **TeamsMeetingBroadcastPolicy**在 PowerShell 中。

在 Windows PowerShell 中，运行以下 cmdlet 以更新全局策略中的记录模式：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>配置实时转录和转换团队 live 事件 （即将推出）
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

这将允许 live 事件组织者，以启用实时标题和转换为 live 事件与会者。 

使用中的设置*AllowBroadcastTranscription* **TeamsMeetingBroadcastPolicy**在 PowerShell 中控制是否 live 事件与会者都将能够看到转录和转换。 您可以了解有关在此处管理**TeamsMeetingBroadcastPolicy**与 Office 365 PowerShell 的详细信息。  

除非您的自定义策略分配给用户，用户将获得全局策略，具有转录和默认情况下禁用的转换。

在 Windows PowerShell 中，运行以下 cmdlet，以在全局策略中打开转录和上的事件与会者的转换：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>管理工具 
虽然 Microsoft 直接控制所有 Office 365 Online 数据中心，并负责整体系统性能，但它可以控制仅结合为 Office 365 用户提供的总体体验的元素的一部分。 组织自己负责网络连接到数据中心，客户的广域网 (WAN) 和客户的局域网 (Lan)。 此外，它们是负责用户设备和其配置。边缘服务器还负责维护所需的授权每个用户的任何所需的功能，包括，但不是限于到，只要用户需要访问功能的管理这些功能的功能。

客户可以使用以下工具来管理的各种工作组 live 事件相关的任务。
- [Microsoft Office 365 管理中心](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft 团队和 Skype 的业务 Online 管理中心](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft 流管理中心](https://stream.microsoft.com)
- [远程 Windows PowerShell](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？
当谈到 Windows PowerShell，它的所有有关管理用户和用户允许或不允许执行的操作。 使用 Windows PowerShell，您可以管理 Office 365 和 Skype 业务 online 使用单点具有多个要执行的任务时，可以简化您的日常工作的管理。 若要开始使用 Windows PowerShell，请参阅下列主题：
 - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
 - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>相关的主题： 
- [跨 Yammer、 Microsoft 团队和 Microsoft 流中的 Microsoft 365 live 事件](https://docs.microsoft.com/stream/live-event-m365)
- [中的 Microsoft 团队的实时事件](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer 中的实时事件](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft 流中的实时事件](https://docs.microsoft.com/stream/live-event-overview)
