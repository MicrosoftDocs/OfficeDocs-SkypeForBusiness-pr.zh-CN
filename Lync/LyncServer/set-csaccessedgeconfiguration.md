---
title: Set-CsAccessEdgeConfiguration
TOCTitle: Set-CsAccessEdgeConfiguration
ms:assetid: f3108b59-1ab2-4288-a470-57d741e7e569
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413017(v=OCS.15)
ms:contentKeyID: 49314718
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAccessEdgeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values of an existing collection of Access Edge configuration settings for computers running the 访问边缘服务. The 访问边缘服务 running on these computers (also known as Edge servers) provides a way for users outside your internal network to communicate with users inside that internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAccessEdgeConfiguration [-AllowAnonymousUsers <$true | $false>] [-AllowFederatedUsers <$true | $false>] [-AllowOutsideUsers <$true | $false>] [-CertificatesDeletedPercentage <UInt32>] [-DiscoveredPartnerReportPeriodMinutes <UInt32>] [-DiscoveredPartnerStandardRate <UInt32>] [-EnableArchivingDisclaimer <$true | $false>] [-EnableDiscoveredPartnerContactsLimit <$true | $false>] [-EnableUserReplicator <$true | $false>] [-Identity <XdsIdentity>] [-KeepCrlsUpToDateForPeers <$true | $false>] [-MarkSourceVerifiableOnOutgoingMessages <$true | $false>] [-MaxAcceptedCertificatesStored <UInt32>] [-MaxContactsPerDiscoveredPartner <UInt32>] [-MaxRejectedCertificatesStored <UInt32>] [-OutgoingTlsCountForFederatedPartners <UInt32>] <COMMON PARAMETERS>

    Set-CsAccessEdgeConfiguration [-AllowAnonymousUsers <$true | $false>] [-AllowFederatedUsers <$true | $false>] [-AllowOutsideUsers <$true | $false>] [-CertificatesDeletedPercentage <UInt32>] [-DefaultRouteFqdn <String>] [-DiscoveredPartnerReportPeriodMinutes <UInt32>] [-DiscoveredPartnerStandardRate <UInt32>] [-EnableArchivingDisclaimer <$true | $false>] [-EnableDiscoveredPartnerContactsLimit <$true | $false>] [-EnableUserReplicator <$true | $false>] [-IsPublicProvider <$true | $false>] [-KeepCrlsUpToDateForPeers <$true | $false>] [-MarkSourceVerifiableOnOutgoingMessages <$true | $false>] [-MaxAcceptedCertificatesStored <UInt32>] [-MaxContactsPerDiscoveredPartner <UInt32>] [-MaxRejectedCertificatesStored <UInt32>] [-OutgoingTlsCountForFederatedPartners <UInt32>] [-UseDefaultRouting <SwitchParameter>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] <COMMON PARAMETERS>

    Set-CsAccessEdgeConfiguration [-AllowAnonymousUsers <$true | $false>] [-AllowFederatedUsers <$true | $false>] [-AllowOutsideUsers <$true | $false>] [-BeClearingHouse <$true | $false>] [-CertificatesDeletedPercentage <UInt32>] [-DiscoveredPartnerReportPeriodMinutes <UInt32>] [-DiscoveredPartnerStandardRate <UInt32>] [-DiscoveredPartnerVerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] [-EnableArchivingDisclaimer <$true | $false>] [-EnableDiscoveredPartnerContactsLimit <$true | $false>] [-EnablePartnerDiscovery <$true | $false>] [-EnableUserReplicator <$true | $false>] [-KeepCrlsUpToDateForPeers <$true | $false>] [-MarkSourceVerifiableOnOutgoingMessages <$true | $false>] [-MaxAcceptedCertificatesStored <UInt32>] [-MaxContactsPerDiscoveredPartner <UInt32>] [-MaxRejectedCertificatesStored <UInt32>] [-OutgoingTlsCountForFederatedPartners <UInt32>] [-UseDnsSrvRouting <SwitchParameter>] <COMMON PARAMETERS>

    Set-CsAccessEdgeConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, two properties of the Access Edge configuration settings are modified: the AllowAnonymousUsers property is set to True and the VerificationLevel property is set to UseSourceVerification.

    Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True -VerificationLevel "UseSourceVerification"

## EXAMPLE 2

The command shown in Example 2 changes the routing method for the Edge server to default routing. In order to do this the command must include both the UseDefaultRouting parameter and the DefaultRouteFqdn parameter, along with a parameter value that specifies the fully qualified domain name of the Edge server.

    Set-CsAccessEdgeConfiguration -UseDefaultRouting -DefaultRouteFqdn "atl-edge-001.litwareinc.com"

## EXAMPLE 3

Example 3 changes the routing method for the Edge server to DNS server routing. This requires the use of two parameters: UseDnsSrvRouting (with no parameter value) and EnablePartnerDiscovery (with the parameter value $True).

    Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## Detailed Description

Edge servers (also known as access proxy servers) provide a way for you to extend the capabilities of Lync Server to people who are not logged on to your internal network. For example, if you have remote users, authenticated users who log on to Lync Server over the Internet rather than through the internal network, you will need to set up an Edge server in order to provide access to these users. Likewise, Edge Servers are required if you want to establish federation with another organization, or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN. Access Edge servers are located on the perimeter network, and are used to make and validate SIP connections between users inside and users outside your internal network.

In Lync Server, the Access Edge servers are managed using a single, global collection of configuration settings; the **Set-CsAccessEdgeConfiguration** cmdlet enables you to modify these global settings. Note that the properties that can be modified depend on the routing type you choose for your Edge Servers. For example, if you choose to use Domain Name System (DNS) service routing, you will see and be able to change the property values BeClearinghouse and EnablePartnerDiscovery. If you use default routing, those two property values will not be available. Instead, you will see and be able to change the property values VerificationLevel and IsPublicProvider.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAccessEdgeConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAccessEdgeConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>AllowAnonymousUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not anonymous users (that is, unauthenticated users) are allowed to cross the firewall and join meetings and conferences. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>AllowFederatedUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario. (In a split domain, some of your users have accounts hosted on-premises, while others have accounts hosted off-premises.) The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowOutsideUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users can access Lync Server across the Internet. This includes both anonymous users and remote users who are trying to log on to the system. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>BeClearingHouse</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether your Edge servers are directly connected to other organizations. The default value is False. This parameter should not be changed unless you are instructed to do so by Microsoft support personnel.</p></td>
</tr>
<tr class="odd">
<td><p><em>CertificatesDeletedPercentage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The default value is 20.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultRouteFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the server used for federation requests. This parameter is required if you use default routing.</p>
<p>Note that you must delete all your hosting providers and all your public providers before you can assign a new default route.</p></td>
</tr>
<tr class="even">
<td><p><em>DiscoveredPartnerReportPeriodMinutes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The default value is 60.</p></td>
</tr>
<tr class="odd">
<td><p><em>DiscoveredPartnerStandardRate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The default value is 20.</p></td>
</tr>
<tr class="even">
<td><p><em>DiscoveredPartnerVerificationLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.VerificationLevelType</p></td>
<td><p>Sets the verification level for messages sent to and from the discovered partner. Allowed values are:</p>
<p>* AlwaysVerifiable</p>
<p>* AlwaysUnverifiable</p>
<p>* UseSourceVerification</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableArchivingDisclaimer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, Edge Servers send an archiving notification header to federated and clearinghouse partners. This notification (which informs people that instant messaging (IM) conversations might be archived) can be displayed in the conversation window of a federated or clearinghouse user. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDiscoveredPartnerContactsLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>The default value is true ($True).</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePartnerDiscovery</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, Lync Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list. If False, Lync Server will only federate with domains found on the AllowedDomains list. This parameter is required if you use DNS service routing. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableUserReplicator</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>The default value is False ($False).</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the Access Edge configuration settings to be returned. Because you can only have a single, global instance of these settings, you do not have to include the Identity when calling the <strong>Set-CsAccessEdgeConfiguration</strong> cmdlet. However, if you prefer, you can use the following syntax to modify the global settings: -Identity global.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DisplayAccessEdgeSettingsDnsSrvRouting object or DisplayAccessEdgeSettingsDefaultRoute object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>IsPublicProvider</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Must be set to True if the default route requires a public instant messaging license.</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepCrlsUpToDateForPeers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether or not Edge servers periodically check the certificate revocation lists (CRLs) for federated domain certificates. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>MarkSourceVerifiableOnOutgoingMessages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, outgoing messages are marked as verifiable; this enables federated domains to determine the verification level for each message. If False, outgoing messages are all marked as unverifiable. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxAcceptedCertificatesStored</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of allowed certificates cached by the Edge Server. The default value is 1000.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxContactsPerDiscoveredPartner</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of contacts allowed per discovered partner. The default value is 1000.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxRejectedCertificatesStored</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of rejected certificates cached by the Edge Server. The default value is 500.</p></td>
</tr>
<tr class="even">
<td><p><em>OutgoingTlsCountForFederatedPartners</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the maximum number of Transport Layer Security (TLS) connections that can be used for each federated partner. The minimum number of TLS connections is 1, and the maximum number is 4. By default, OutgoingTlsCountForFederatedPartners is set to 4. This parameter should not be changed unless you are instructed to do so by Microsoft support personnel.</p></td>
</tr>
<tr class="odd">
<td><p><em>UseDefaultRouting</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indicates that administrators must specify the fully qualified domain name of the server used to send and receive federation requests. If you include the UseDefaultRouting parameter then you must also include the DefaultRouteFqdn parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>UseDnsSrvRouting</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indicates that Edge servers should rely on DNS SRV records when sending and receiving federation requests. This is the default routing method.</p></td>
</tr>
<tr class="odd">
<td><p><em>VerificationLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.VerificationLevelType</p></td>
<td><p>If you are using default routing, the VerificationLevel property is used to monitor and assess the verification level of incoming messages. Valid values are:</p>
<p>AlwaysVerifiable: All requests received on the default route are marked as verified. If a verification header is not present it will automatically be added to the message.</p>
<p>AlwaysUnverifiable: Messages are passed only if the addressee (the user the message is intended for) has configured an Allow ACE (access control entry) for the person who sent the message.</p>
<p>UseSourceVerification: Message verification is based on the verification level included with the message. If no verification header is present then the message will be marked as unverified.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Set-CsAccessEdgeConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsAccessEdgeConfiguration** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Get-CsAccessEdgeConfiguration](get-csaccessedgeconfiguration.md)

