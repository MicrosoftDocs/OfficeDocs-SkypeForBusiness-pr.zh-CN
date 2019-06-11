---
title: 'Lync Server 2013: 查看林全局设置的状态'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>查看 Lync Server 2013 中的林全局设置的状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-20_

管理员应每月查看 Lync Server 2013 部署的全局设置。 目标是针对一组已知的配置查看实施的设置-基准配置, 以帮助确保设置有效, 并确定是否应更新基准文档。 对全局设置所做的更改应通过更改控制过程实现, 该过程应包括记录新设置。

应查看的全局设置将在以下部分中介绍:

<div>

## <a name="check-general-settings"></a>检查常规设置

检查常规设置, 包括 Lync Server 2013 受支持的会话初始协议 (SIP) 域。

SIP 域信息可通过使用 Windows PowerShell 和**CsSipDomain** cmdlet 返回。 若要返回此信息, 请`Get-CsSipDomain`运行 Windows PowerShell 命令。

对于所有授权 SIP 域, CsSipDomain 将返回与以下内容类似的信息:

标识名称 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

如果 IsDefault 属性设置为 True, 则相应的域是默认 SIP 域。 你可以使用 CsSipDomain cmdlet 更改你的组织的默认 SIP 域。 但是, 不能只是删除默认 SIP 域, 因为这样做将不使用默认域。 如果想要删除 fabrikam.com 域 (如前面的示例所示), 则必须首先将 na.fabrikam.com 配置为默认域。

</div>

<div>

## <a name="check-meeting-settings"></a>检查会议设置

会议设置包括会议策略定义和在会议中参与匿名用户的支持。

可使用 Windows PowerShell 和**CsMeetingConfiguration** cmdlet 检索会议配置设置。 例如, 以下命令将返回有关全局会议配置设置的信息:

CsMeetingConfiguration –标识 "全局" 会议配置设置也可以在网站范围内进行配置。 因此, 你可能需要使用以下命令, 该命令将返回有关所有会议配置设置的信息:

`Get-CsMeetingConfiguration`

**CsMeetingConfiguration** cmdlet 返回类似于以下内容的信息:

标识: 全局

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

DesignateAsPresenter: 公司

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

同样, **AdmitAnonymousUsersByDefault**列表中的最后一个项目可启用或禁用匿名用户参与会议的能力。

检查会议配置设置时, 你可能会发现将当前设置与默认等效项进行比较非常有用。 可以通过运行以下命令来查看默认会议配置设置:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

上一个命令创建全局会议配置设置的仅内存实例, 该实例使用每个属性的默认值。 运行命令时, 不会创建实际会议配置设置。 但是, 所有默认属性值都将显示在屏幕上。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>检查边缘服务器及其设置

可以使用 Windows PowerShell 检索边缘服务器信息。 此命令将返回有关所有配置为在你的组织中使用的边缘服务器的信息:

`Get-CsService -EdgeServer`

返回的信息包括每台边缘服务器的所有 FQDN 和端口设置:

标识: EdgeServer: dc.fabrikam.com

注册机构: 注册机构: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {注册机构: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE

com, MediationServer: LYNC-SE。

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:fabrikam

PoolFqdn: dc.fabrikam.com

版本: 5

角色: EdgeServer

<div>

## <a name="check-federation-settings"></a>检查联盟设置

检查联盟设置, 例如是否已配置, 如果答案为 "是", 则为 FQDN 和端口。 通过使用访问边缘配置设置的全局集合启用和禁用联盟。 在其他情况下, 这些意味着联盟是在全或全基础上配置的: 为整个组织启用联盟或对整个组织禁用联盟

你的访问边缘配置设置可通过使用 Windows PowerShell 返回。 若要执行此操作, 请运行以下 Windows PowerShell 命令:

`Get-CsAccessEdgeConfiguration`

因此, 该命令将返回类似于以下内容的数据:

标识: 全局

AllowAnonymousUsers: False

AllowFederatedUsers: False

AllowOutsideUsers: False

BeClearingHouse: False

EnablePartnerDiscovery: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod : UseDnsSrvRouting

如果**AllowFederatedUsers**属性设置为 True, 则表示已为你的组织启用联盟。 (将**AllowFederatedUsers**设置为 True 还意味着, 在拆分域方案中, 你的本地用户将能够与云用户无缝通信。)

若要检索 Edge 服务器的 FQDN 和端口设置, 请参阅上一任务 (边缘服务器及其设置)。

在全局范围内启用联盟意味着用户可能与联盟用户进行通信。 若要确定任何单个用户是否可以与联盟用户进行实际通信, 需要检查分配给该用户的外部用户访问策略。

可使用 Windows PowerShell 返回外部用户访问信息。 例如, 此命令返回全局外部用户访问策略的信息:

`Get-CsExternalAccessPolicy -Identity "Global"`

此命令返回所有外部用户访问策略的信息:

`Get-CsExternalAccessPolicy`

返回的信息将如下所示:

标识: False

介绍

EnableFederationAccess: False

EnablePublicCloudAccess: False

EnablePublicCloudAccessAudioVideoAccess: False

EnableOutsideAccess: False

如果**EnableFederationAccess**设置为 True, 则由给定策略管理的用户可以与联盟用户通信。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>检查存档设置

检查内部和联盟通信的存档设置。在验证内部和外部存档的设置之前, 应验证是否已启用存档。

可以使用 Windows PowerShell 和 CsArchivingConfiguration cmdlet 验证存档配置设置:

`Get-CsArchivingConfiguration -Identity "Global"`

请注意, 也可以在网站范围内配置存档设置。 若要返回有关所有存档设置的信息, 请使用以下命令:

`Get-CsArchivingConfiguration`

CsArchivingConfiguration cmdlet 返回与以下内容类似的数据:

标识: 全局

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

BlockOnArchiveFailure: False

KeepArchivingDataForDays:14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: True

CachePurgingInterval:24

如果 EnableArchiving 属性设置为 False, 则表示不会存档任何通信会话。 如果只想存档即时消息会话, 请使用如下所示的命令来启用 IM 会话的存档:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

若要将会议会话和即时消息会话存档, 请使用以下命令:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

如果你想要将当前存档设置与默认设置进行比较, 请运行以下 Windows PowerShell 命令:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

该命令将创建全局存档配置设置的仅内存内部实例。 这不是由 Lync Server 使用的真实设置集合。 但是, 它会显示所有存档配置属性的默认值。

你还可以使用此命令返回存档服务器的 FQDN:

`Get-CsService -ArchivingServer`

验证已启用存档后, 您可以查看存档策略以确定是否正在存档内部和外部通信会话。

可通过使用 CsArchivingPolicy cmdlet 检索存档策略信息。 例如, 此命令返回有关全局存档策略的信息:

`Get-CsArchivingPolicy -Identity "Global"`

由于还可以在网站和每用户范围内配置存档策略, 因此你可能还希望使用此命令, 该命令将返回有关所有存档策略的信息:

`Get-CsArchivingPolicy`

从 CsArchivingPolicy 接收的信息将如下所示:

标识: 全局

介绍

ArchiveInternal: False

ArchiveExternal: False

请注意, 默认情况下, 存档策略中禁用内部和外部存档。

</div>

<div>

## <a name="check-cdr-settings"></a>检查 CDR 设置

检查对等、会议和语音呼叫详细记录的呼叫详细记录 (CDR) 设置。 可通过使用**CsCdrConfiguration** cmdlet 返回有关 CDR 设置的详细信息。 例如, 此命令返回有关 CDR 配置设置的全局集合的信息:

`Get-CsCdrConfiguration -Identity "Global"`

由于 CDR 也可以在网站范围内配置, 因此你可能还希望运行此命令, 该命令将返回有关所有 CDR 配置设置的信息:

`Get-CsCdrConfiguration`

CsCdrConfiguration cmdlet 针对 CDR 配置设置的每个集合返回类似于以下内容的信息:

标识: 全局

EnableCDR: True

EnablePurging: True

KeepCallDetailForDays:60

KeepErrorReportForDays:60

PurgeHourOfDay: 2

通过使用 CsQoEConfiguration cmdlet, 可以为 QoE 监视返回类似信息。 例如, 此命令返回有关 QoE 配置设置的全局集合的信息:

`Get-QoEConfiguration -Identity "Global"`

该信息将如下所示:

标识: 全局

ExternalConsumerIssuedCertId :

EnablePurging: True

KeepQoEDataForDays:60

PurgeHourOfDay: 1

EnableExternalConsumer: False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: True

如果要将当前 CDR 设置与默认的 CDR 设置进行比较, 可以通过运行以下命令来查看默认值:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同样, 可以使用以下命令检索 QoE 监视的默认值:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

您也可以通过运行以下命令返回监视服务器的 FQDN:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>检查语音设置

语音设置通常对管理员非常重要, 因为它包含在语音策略和语音路由中: 语音策略包含确定向单个用户公开的功能 (如转发或转移呼叫能力) 的设置。语音路由确定如何 (和 if) 呼叫通过 PSTN 路由。

可以使用 Windows PowerShell 检索语音策略信息。 例如, 此命令返回有关全局语音策略的信息:

`Get-CsVoicePolicy -Identity "Global"`

此命令将返回有关已配置为在组织中使用的所有语音策略的信息:

`Get-CsVoicePolicy`

CsVoicePolicy cmdlet 返回的信息如下所示:

标识: 全局

PstnUsages :{}

介绍

AllowSimulRing: True

AllowCallForwarding: True

AllowPSTNReRouting: True

名称: DefaultPolicy

EnableDelegation: True

EnableTeamCall: True

EnableCallTransfer: True

EnableCallPark: False

EnableMaliciousCallTracing: False

EnableBWPolicyOverride: False

PreventPSTNTollBypass: False

您还可以创建返回您的语音策略子集的查询。 例如, 此命令返回允许呼叫转接的所有语音策略:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

此命令将返回不允许呼叫转接的所有语音策略:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

在 Windows PowerShell 中, 使用 CsVoiceRouting cmdlet 返回有关语音路由的信息:

`Get-CsVoiceRoute`

该命令将为所有语音路线返回如下信息:

标识: LocalRoute

优先级: 0

介绍

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

名称: LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server 允许你创建没有 PSTN 使用的语音路由, 不指定 PSTN 网关。 但是, 您实际上无法通过没有配置这两个属性值的语音路线路由呼叫。 出于此原因, 你可能会发现定期运行此命令非常有用, 该命令将返回没有 PSTN 使用的任何语音路由的标识:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同样, 此命令返回尚未配置为具有 PSTN 网关的任何语音路由的标识:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>检查会议助理设置

检查 PSTN 电话拨入式会议的会议助理设置。 只能使用**CsDialInConferencingConfiguration** cmdlet 来检索会议助理设置。 这些设置在 Lync Server "控制面板" 中不可用。 若要查看会议助理设置, 请使用与以下内容类似的 Windows PowerShell 命令, 它可返回全局会议助理设置的全局集合:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

请注意, 还可以在网站范围内配置会议助理设置。 若要返回有关所有会议助理设置的信息, 请改用此命令:

`Get-CsDialInConferencingConfiguration`

CsDialInConferencingConfiguration cmdlet 返回与以下内容类似的数据:

标识: 全局

EntryExitAnnouncementsType : UseNames

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

如果 EntryExitAnnouncementsEnabledByDefault 设置为 False, 则表示已禁用会议通知。 若要启用进入和退出通知, 请运行如下所示的 Windows PowerShell 命令:

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

