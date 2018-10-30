---
title: Set-CsXmppGatewayConfiguration
TOCTitle: Set-CsXmppGatewayConfiguration
ms:assetid: 2b90d563-a3fe-45bd-81da-210a7459411b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204769(v=OCS.15)
ms:contentKeyID: 49312341
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsXmppGatewayConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the XMPP gateway configuration settings in use in the organization. The extensible Messaging and Presence Protocol (XMPP) is an open-standard communications protocol for exchanging messages using XML. XMPP gateways enable Lync Server 2013 users to exchange instant message and presence information with users from IM and presence providers that employ XMPP. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsXmppGatewayConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsXmppGatewayConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-ConnectionLimit <UInt32>] [-DialbackPassphrase <String>] [-EnableLoggingAllMessageBodies <$true | $false>] [-Force <SwitchParameter>] [-KeepAliveInterval <UInt32>] [-PartnerConnectionLimit <UInt32>] [-StreamEstablishmentTimeout <UInt32>] [-StreamInactivityTimeout <UInt32>] [-SubscriptionRefreshInterval <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 modifies the ConnectionLimit property for the global collection of XMPP gateway settings.

    Set-CsXmppGatewayConfiguration -Identity "global" -ConnectionLimit 1200

## Detailed Description

The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet. XMPP was originally named Jabber, and is supported by a number of Internet messaging and communication applications, including Google Talk and Facebook Chat.

The XMPP gateway that enables Lync 2013 to communicate with users on an XMPP network was originally released as an add-on to Microsoft Lync Server 2010; in Lync Server 2013, this functionality is built into the software. This means that your users can communicate with XMPP users provided that you:

  -   
    Configure the XMPP gateway settings.

  -   
    Configure the other XMPP network (for example, Google Talk) as an allowed XMPP partner.

Note that Lync Server 2013 provides only a single, global set of XMPP configuration settings: you cannot selectively enable or disable XMPP for a given site or a given Registrar pool. In fact you cannot enable or disable XMPP at all: XMPP is always enabled. If you do not want users communicating with XMPP networks then you should remove all the allowed XMPP partners. Users can only communicate with an XMPP network if that network has been configured as an allowed partner.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsXmppGatewayConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsXmppGatewayConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>ConnectionLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Total number of simultaneous connections allowed for all XMPP partners. The default value is 1000.</p></td>
</tr>
<tr class="odd">
<td><p><em>DialbackPassphrase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Password used when connecting to an XMPP partner over a TCP dialback connection. With TCP dialback, the partner contacts the XMPP gateway and then hangs up. The XMPP gateway calls the partner back, and the communication session can then begin.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableLoggingAllMessageBodies</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Lync Server 2013 will log the actual content of all instant messages. For privacy reasons, message content is typically deleted and only information about the communicating endpoints is included in the log files.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the XMPP gateway configuration settings to be modified. Because you can only have a single, global instance of these settings, you do not need to specify an Identity when calling the <strong>Set-CsXmppGatewayConfiguration</strong> cmdlet. If you prefer, however, you can use the following syntax to reference the global settings:</p>
<p>-Identity global</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>KeepAliveInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of time (in seconds) that can elapse before the partner must send a &quot;keep alive&quot; message. (A keep alive message simply verifies that the connection is still active.) If the time interval expires before a keep alive message is received, the connection will be closed. The default value is 300 seconds.</p></td>
</tr>
<tr class="odd">
<td><p><em>PartnerConnectionLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Total number of simultaneous connections allowed for a single XMPP partner. The default value is 20.</p></td>
</tr>
<tr class="even">
<td><p><em>StreamEstablishmentTimeout</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of time (in seconds) allotted for the XMPP partner to establish an XMPP stream. If this timeout period is surpassed the connection will automatically be terminated. The default value is 60 seconds.</p></td>
</tr>
<tr class="odd">
<td><p><em>StreamInactivityTimeout</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of time (in seconds) that an XMPP stream can be inactive before the connection is automatically terminated. The default value is 600 seconds (10 minutes).</p></td>
</tr>
<tr class="even">
<td><p><em>SubscriptionRefreshInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum amount of time (in seconds) that can elapse before the partner must refresh its presence subscription. The default value is 28800 seconds (8 hours).</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsXmppGatewayConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppGatewaySettings object.

## Return Types

None. Instead, The **Set-CsXmppGatewayConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppGatewaySettings object.

## 另请参阅

#### 其他资源

[Get-CsXmppGatewayConfiguration](get-csxmppgatewayconfiguration.md)

