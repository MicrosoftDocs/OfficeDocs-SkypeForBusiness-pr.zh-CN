---
title: 设置中的 Microsoft 团队的实时事件
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 了解 live 事件中的 Microsoft 团队，准备您的网络，包括分配许可证，启用 live 事件计划的用户，并设置 eCDN 提供商的设置的步骤。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296377"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>设置中的 Microsoft 团队的实时事件
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Live 事件的设置时, 有以下几个您必须采取的步骤：

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>步骤 1： 设置您的网络中的 Microsoft 团队的实时事件
快速入门 live 事件要求您[准备贵组织的网络中的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>第 2 步：获取和分配许可证
确保您具有正确的许可证分配[谁可以创建和安排 live 事件？](#who-can-create-and-schedule-live-events)和[谁可以观看 live 事件？](#who-can-watch-live-events)。

## <a name="step-3-enable-live-event-scheduling-for-users"></a>步骤 3： 启用的用户安排 live 事件
默认情况下，为团队用户，但如果您希望用户能够安排外部编码器事件，必须执行其他步骤情况下，启用 live 事件计划。

### <a name="for-quick-start-events"></a>快速入门事件
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

#### <a name="user-scenarios"></a>用户方案
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

### <a name="for-external-encoder-events"></a>外部编码器事件
您必须执行以下操作以启用实时计划为这些用户的事件。

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>步骤 1： 在您的组织 * * 中为用户启用 Microsoft 流
Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。 有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。

> ![注意]业务 Essentials 或企业高级版计划中不包含 Microsoft 流。  

了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。 确保 Microsoft 流的用户不进行阻止，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所定义。

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>步骤 2： 确保用户具有 live 事件创建权限中 Microsoft 流 * *
默认情况下，管理员可以创建外部编码器 live 事件。 Microsoft 流管理员可以流中[启用 live 事件创建的其他用户](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>步骤 3： 确保组织者同意设置流管理员 * * 的公司策略的实时事件
如果 Microsoft 流管理员[设置的公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，然后用户必须这样做团队在创建 （具有外部编码器生产） 的实时事件之前。 之前您推出组织中的实时事件功能，请确保将创建这些 live 事件的用户同意策略。 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>步骤 4： 设置 eCDN 提供程序中的 Microsoft 团队的实时事件 
Live 事件视频播放使用流式处理 (ABR) 的自适应比特率，但它并单播流，这意味着每个查看器从 internet 获取其自己的视频流。 对于 live 事件或发送到您的组织的大部分内容的视频，可能有大量的 internet 带宽使用查看器。 对于希望减少 live 事件此 internet 通信的组织，与 Microsoft 的集成解决方案的实时事件受信任提供软件的视频传送合作伙伴定义网络 (SDNs) 或企业内容交付网络 (eCDNs)。 这些 SDN / eCDN 平台启用组织牺牲最终用户查看体验的情况下优化网络带宽。 我们的合作伙伴可帮助您在企业网络中启用多可扩展且高效的视频分布。

**购买和安装您的解决方案的 Microsoft 团队之外**获取与通过利用 Microsoft 的受信任的视频传送合作伙伴缩放视频传递专家的帮助。 启用与团队一起使用的视频传输提供程序之前，您必须购买和安装 SDN/eCDN 解决方案外部和分开团队。

以下 SDN/eCDN 解决方案前集成，可以为安装程序将与 Microsoft 流一起使用。

- **配置单元流式处理**提供 live 和点播企业视频分布的简单且强大的解决方案。 配置单元是一种基于软件的解决方案，不需要额外的硬件或带宽，并提供了一种启用数千个并发视频查看器，而不会影响您的网络安全方法。 对于希望了解影响视频具有其购买 SDN/eCDN 解决方案之前的网络上的客户，配置单元流还提供基于浏览器的分析解决方案的 Microsoft 客户。 [了解更多](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective**是一个基于云的、 智能对等分发平台，利用您现有的网络基础结构来提供多个窗体中的内容，、 (live 视频流，按需视频、 软件更新、 安全修补程序，等等) 更快、 更多可靠地及较少的带宽。 我们安全平台是受信任的世界最大金融机构及任何其他硬件、 设置和维护很容易。 [了解更多](http://www.kollective.com)。
 
- **提升 OmniCache**提供下一代网络通讯组和跨全局 Wan 确保视频内容的无缝传递，帮助事件生产者优化网络带宽和支持成功 live 事件广播和按需流式处理。 快速入门 live 事件提升 OmniCache 支持即将提供。  [了解更多](http://www.ramp.com)。 
 
> [!NOTE] 
> 选的 eCDN 解决方案受制于所选**的服务和隐私策略的第三方提供程序的条款**，哪些将控制您使用 eCDN 提供程序的解决方案。 您使用 eCDN 提供程序的解决方案不会受到的 Microsoft 批量许可条款或联机服务条款。 如果您不同意**第三方提供程序的术语**，然后不启用团队中的 eCDN 解决方案。 

**设置为"快速启动"eCDN live 事件**使用 PowerShell 团队中，您可以配置 live 事件 eCDN 提供程序。 

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

## <a name="next-steps"></a>后续步骤
转到[配置团队 live 事件](configure-teams-live-events.md)。
