---
title: Lync Server 2013：查看林的全局设置状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ce07a106e583f3ea0d4b523e1cf882677c19b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>在 Lync Server 2013 中查看林的全局设置状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-20_

管理员应每月查看 Lync Server 2013 部署的全局设置。 目标是查看针对一组已知配置实施的设置，这是一种基准配置，可帮助确保设置有效，并确定是否应更新基准文档。 对全局设置所做的更改应通过应包括记录新设置的更改控制过程实现。

应查看的全局设置将在以下各节中介绍：

<div>

## <a name="check-general-settings"></a>检查常规设置

检查常规设置，包括 Lync Server 2013 支持的会话初始协议（SIP）域。

SIP 域信息可以通过使用 Windows PowerShell 和**CsSipDomain** cmdlet 返回。 若要返回此信息，请`Get-CsSipDomain`运行 Windows PowerShell 命令。

对于所有授权的 SIP 域，CsSipDomain 将返回与以下内容类似的信息：

标识名称 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

如果 IsDefault 属性设置为 True，则相应的域是默认的 SIP 域。 您可以使用 CsSipDomain cmdlet 更改组织的默认 SIP 域。 但是，不能只删除默认的 SIP 域，因为这样做会导致没有默认域。 如果要删除 fabrikam.com 域（如前面的示例中所示），则必须首先将 na.fabrikam.com 配置为默认域。

</div>

<div>

## <a name="check-meeting-settings"></a>检查会议设置

会议设置包括会议策略定义以及在会议中参与匿名用户的支持。

可以使用 Windows PowerShell 和**get-csmeetingconfiguration** cmdlet 检索会议配置设置。 例如，以下命令将返回有关全局会议配置设置的信息：

Get-csmeetingconfiguration –标识 "全局" 会议配置设置也可以在站点范围中进行配置。 因此，您可能需要使用以下命令，该命令将返回有关所有会议配置设置的信息：

`Get-CsMeetingConfiguration`

**Get-csmeetingconfiguration** cmdlet 将返回类似于以下内容的信息：

标识：全局

PstnCallersBypassLobby： True

EnableAssignedConferenceType： True

DesignateAsPresenter：公司

AssignedConferenceTypeByDefault： True

AdmitAnonymousUsersByDefault： True

同样，列表中的最后一项**AdmitAnonymousUsersByDefault**，启用或禁用匿名用户参与会议的功能。

检查会议配置设置时，您可能会发现将当前设置与默认等效项进行比较非常有用。 您可以通过运行以下命令来查看默认会议配置设置：

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

上一个命令创建全局会议配置设置的仅内存内部实例，该实例使用每个属性的默认值。 运行命令时，不会创建实际会议配置设置。 但是，所有默认属性值都将显示在屏幕上。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>检查边缘服务器及其设置

可以使用 Windows PowerShell 检索边缘服务器信息。 此命令返回有关配置为在组织中使用的所有边缘服务器的信息：

`Get-CsService -EdgeServer`

返回的信息包括每台边缘服务器的所有 FQDN 和端口设置：

Identity： EdgeServer： dc.fabrikam.com

注册器：注册器： LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort：5061

AccessEdgeExternalSipPort：5061

AccessEdgeClientPort：443

DataPsomServerPort：8057

DataPsomClientPort：444

MediaRelayAuthEdgePort：5062

MediaRelayAuthInternalTurnTcpPort：443

MediaRelayAuthExternalTurnTcpPort：445

MediaRelayAuthInternalTurnUdpPort：3478

MediaRelayAuthExternalTurnUdpPort：3478

MediaCommunicationPortStart：50000

MediaComunicationPortCount：10000

AccessEdgeExternalFqdn： dc.fabrikam.com

DataEdgeExternalFqdn： dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn： dc.fabrikam.com

DependentServiceList： {注册器： LYNC-SE.fabrikam.com，

ConferencingServer： LYNC-SE. fabrikam

com，MediationServer： LYNC-SE。

fabrikam.com}

ServiceId： fabrikam.com-EdgeServer-2

SiteId： site:fabrikam

PoolFqdn： dc.fabrikam.com

版本：5

Role： EdgeServer

<div>

## <a name="check-federation-settings"></a>检查联合身份验证设置

检查联合身份验证设置，如是否配置了联合身份验证设置，如果答案为 "是"，则为 FQDN 和端口。 联合身份验证是通过使用访问边缘配置设置的全局集合启用和禁用的。 在其他情况下，这意味着联合是在全或无基础上配置的：为整个组织启用联盟或为整个组织禁用联盟

您可以使用 Windows PowerShell 返回您的访问边缘配置设置。 为此，请运行以下 Windows PowerShell 命令：

`Get-CsAccessEdgeConfiguration`

反过来，该命令将返回类似于以下内容的数据：

标识：全局

AllowAnonymousUsers： False

AllowFederatedUsers： False

AllowOutsideUsers： False

BeClearingHouse： False

EnablePartnerDiscovery： False

EnableArchivingDisclaimer： False

KeepCrlsUpToDateForPeers： True

MarkSourceVerifiableOnOutgoingMessages： True

OutgoingTlsCountForFederatedPartners：4

RoutingMethod : UseDnsSrvRouting

如果将**AllowFederatedUsers**属性设置为 True，则表示已为您的组织启用联盟。 （将**AllowFederatedUsers**设置为 True 也意味着，在拆分域方案中，您的本地用户将能够与您的云中用户无缝通信。）

若要检索边缘服务器的 FQDN 和端口设置，请参阅上一任务（边缘服务器及其设置）。

在全局范围内启用联合仅意味着用户可以与联合用户进行通信。 若要确定任何单个用户是否可以实际与联合用户通信，需要检查分配给该用户的外部用户访问策略。

可以使用 Windows PowerShell 返回外部用户访问信息。 例如，以下命令将返回全局外部用户访问策略的信息：

`Get-CsExternalAccessPolicy -Identity "Global"`

此命令将返回所有外部用户访问策略的信息：

`Get-CsExternalAccessPolicy`

返回的信息将如下所示：

标识： False

产品介绍

EnableFederationAccess： False

EnablePublicCloudAccess： False

EnablePublicCloudAccessAudioVideoAccess： False

EnableOutsideAccess： False

如果将**EnableFederationAccess**设置为 True，则由给定策略管理的用户可以与联盟用户通信。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>检查存档设置

检查内部和联合通信的存档设置。在验证内部存档和外部存档的设置之前，应验证是否已启用存档。

可以使用 Windows PowerShell 和 Set-csarchivingconfiguration cmdlet 来验证存档配置设置：

`Get-CsArchivingConfiguration -Identity "Global"`

请注意，也可以在站点范围内配置存档设置。 若要返回有关所有存档设置的信息，请使用以下命令：

`Get-CsArchivingConfiguration`

Set-csarchivingconfiguration cmdlet 返回与以下内容类似的数据：

标识：全局

EnableArchiving： False

EnablePurging： False

PurgeExportedArchivesOnly： False

BlockOnArchiveFailure： False

KeepArchivingDataForDays：14

PurgeHourOfDay：2

ArchiveDuplicateMessages： True

CachePurgingInterval：24

如果将 EnableArchiving 属性设置为 False，则意味着将不会存档任何通信会话。 如果只想存档即时消息会话，请使用如下所示的命令来启用 IM 会话的存档：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

若要存档会议会话和即时消息会话，请使用以下命令：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

如果您想要将当前存档设置与默认设置进行比较，请运行以下 Windows PowerShell 命令：

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

该命令将创建全局存档配置设置的仅内存中的实例。 这不是由 Lync Server 使用的真实设置集合。 但是，它确实显示所有存档配置属性的默认值。

您还可以使用此命令返回存档服务器的 FQDN：

`Get-CsService -ArchivingServer`

验证是否已启用存档后，可以查看存档策略，以确定是否正在存档内部和外部通信会话。

可以使用 New-csarchivingpolicy cmdlet 检索存档策略信息。 例如，以下命令将返回有关全局存档策略的信息：

`Get-CsArchivingPolicy -Identity "Global"`

由于还可以在网站和每用户范围中配置存档策略，因此您可能还需要使用此命令，该命令将返回有关所有存档策略的信息：

`Get-CsArchivingPolicy`

从 New-csarchivingpolicy 接收到的信息将与以下内容类似：

标识：全局

产品介绍

ArchiveInternal： False

ArchiveExternal： False

请注意，默认情况下，在存档策略中禁用内部存档和外部存档。

</div>

<div>

## <a name="check-cdr-settings"></a>检查 CDR 设置

检查对等、会议和语音呼叫详细记录的呼叫详细信息记录（CDR）设置。 可以使用**set-cscdrconfiguration** cmdlet 返回有关 CDR 设置的详细信息。 例如，以下命令将返回有关 CDR 配置设置的全局集合的信息：

`Get-CsCdrConfiguration -Identity "Global"`

由于也可以在站点范围配置 CDR，因此您可能还需要运行以下命令，该命令将返回有关所有 CDR 配置设置的信息：

`Get-CsCdrConfiguration`

Set-cscdrconfiguration cmdlet 为每个 CDR 配置设置集合返回类似于以下内容的信息：

标识：全局

EnableCDR： True

EnablePurging： True

KeepCallDetailForDays：60

KeepErrorReportForDays：60

PurgeHourOfDay：2

可以通过使用 New-csqoeconfiguration cmdlet 为 QoE 监视返回类似的信息。 例如，以下命令将返回有关 QoE 配置设置的全局集合的信息：

`Get-QoEConfiguration -Identity "Global"`

该信息将类似于以下内容：

标识：全局

ExternalConsumerIssuedCertId :

EnablePurging： True

KeepQoEDataForDays：60

PurgeHourOfDay：1

EnableExternalConsumer： False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE： True

如果要将当前 CDR 设置与默认 CDR 设置进行比较，可以通过运行以下命令来查看默认值：

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同样，可以使用以下命令检索 QoE monitoring 的默认值：

`New-CsQoEConfiguration -Identity "Global" -InMemory`

您还可以通过运行以下命令返回您的监视服务器的 FQDN：

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>检查语音设置

语音设置对于管理员来说通常很重要的信息包含在语音策略和语音路由中：语音策略包含用于确定向单个用户公开的功能的设置（例如，转发或转移呼叫的能力），同时语音路由决定了在 PSTN 中路由呼叫的方式（和 if）。

可以使用 Windows PowerShell 检索语音策略信息。 例如，以下命令将返回有关全局语音策略的信息：

`Get-CsVoicePolicy -Identity "Global"`

此命令将返回有关已配置为在组织中使用的所有语音策略的信息：

`Get-CsVoicePolicy`

Set-csvoicepolicy cmdlet 返回的信息类似于以下内容：

标识：全局

PstnUsages{}

产品介绍

AllowSimulRing： True

AllowCallForwarding： True

AllowPSTNReRouting： True

名称： DefaultPolicy

EnableDelegation： True

EnableTeamCall： True

EnableCallTransfer： True

EnableCallPark： False

EnableMaliciousCallTracing： False

EnableBWPolicyOverride： False

PreventPSTNTollBypass： False

您还可以创建返回语音策略子集的查询。 例如，以下命令将返回所有允许呼叫转接的语音策略：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

此命令将返回不允许呼叫转接的所有语音策略：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

在 Windows PowerShell 中，使用 CsVoiceRouting cmdlet 可返回有关语音路由的信息：

`Get-CsVoiceRoute`

该命令将返回类似于所有语音路由的信息，如下所示：

标识： LocalRoute

优先级：0

产品介绍

NumberPattern： ^ （\\+ 1\[0-9\]{10}） $

PstnUsages{}

PstnGatewayList :{}

名称： LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server 允许您创建没有 PSTN 用法且未指定 PSTN 网关的语音路由。 但是，不能实际通过未配置这两个属性值的语音路由路由呼叫。 因此，您可能会发现，定期运行此命令会很有用，后者将返回没有 PSTN 用法的任何语音路由的标识：

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同样，此命令将返回尚未配置为具有 PSTN 网关的任何语音路由的标识：

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>检查会议助理设置

检查 PSTN 电话拨入式会议的会议助理设置。 只能使用**set-csdialinconferencingconfiguration** cmdlet 来检索会议助理设置。 这些设置在 "Lync Server 控制面板" 中不可用。 若要查看会议助理设置，请使用与以下内容类似的 Windows PowerShell 命令，该命令将返回全局会议助理设置集合：

`Get-CsDialInConferencingConfiguration -Identity "Global"`

请注意，还可以在站点范围内配置会议助理设置。 若要返回有关所有会议助理设置的信息，请改为使用此命令：

`Get-CsDialInConferencingConfiguration`

Set-csdialinconferencingconfiguration cmdlet 返回与以下内容类似的数据：

标识：全局

EntryExitAnnouncementsType : UseNames

EnableNameRecording： True

EntryExitAnnouncementsEnabledByDefault： False

如果 EntryExitAnnouncementsEnabledByDefault 设置为 False，则表示已禁用会议通知。 若要启用进入和退出通知，请运行与以下内容类似的 Windows PowerShell 命令：

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-csservice](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Set-csaccessedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[New-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Set-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

