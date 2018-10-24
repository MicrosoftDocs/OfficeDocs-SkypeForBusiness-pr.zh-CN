---
title: Set-CsRegistrar
TOCTitle: Set-CsRegistrar
ms:assetid: e0c31acc-179c-4423-910e-8bd7807e6489
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398993(v=OCS.15)
ms:contentKeyID: 49314503
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRegistrar

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify the properties of one or more Registrars. Registrars are used to authenticate logon requests, and to maintain information about user status and availability. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRegistrar [-Identity <XdsGlobalRelativeIdentity>] [-ArchivingDatabase <String>] [-ArchivingServer <String>] [-BackupRegistrar <String>] [-Confirm [<SwitchParameter>]] [-EdgeServer <String>] [-EnableAutomaticFailover <$true | $false>] [-FailbackDetectionInterval <TimeSpan>] [-FailureDetectionInterval <TimeSpan>] [-Force <SwitchParameter>] [-LyssWcfMtlsPort <UInt16>] [-MirrorArchivingDatabase <String>] [-MirrorMonitoringDatabase <String>] [-MonitoringDatabase <String>] [-MonitoringServer <String>] [-Registrar <String>] [-SipHealthPort <UInt16>] [-SipPort <UInt16>] [-SipServerTcpPort <UInt16>] [-UserServer <String>] [-WebPort <UInt16>] [-WebServer <String>] [-WhatIf [<SwitchParameter>]] [-WinFabClientConnectionPort <UInt16>] [-WinFabFederationPort <UInt16>] [-WinFabIPCPort <UInt16>] [-WinFabLeaseAgentPort <UInt16>] [-WinFabReplicationPort <UInt16>] [-XmppGatewaySipPort <UInt16>]

## Examples

## EXAMPLE 1

The command shown in Example 1 sets the SIP port for the Registrar Registrar:atl-cs-001.litwareinc.com to 5072.

    Set-CsRegistrar -Identity "Registrar:atl-cs-001.litwareinc.com" -SipPort 5072

## EXAMPLE 2

Example 2 sets the SIP port for all the Registrars in the organization to 5072. To do this, the command first uses the **Get-CsService** cmdlet and the Registrar parameter to return a collection of all the Registrars currently in use. This collection is then piped to the **ForEach-Object** cmdlet, which takes each Registrar in the collection and runs the **Set-CsRegistrar** cmdlet in order to change the SIP port to 5072.

    Get-CsService -Registrar | ForEach-Object {Set-CsRegistrar -Identity $_.Identity -SipPort 5072}

## EXAMPLE 3

Example 3 configures both a backup Registrar (BackupRegistrar) and automatic failover (EnableAutomaticFailover) for the Registrar Registrar:atl-cs-001.litwareinc.com.

    Set-CsRegistrar -Identity "Registrar:atl-cs-001.litwareinc.com" -BackupRegistrar "Registrar:dublin-cs-001.litwareinc.com" -EnableAutomaticFailover $True

## Detailed Description

The Registrar is perhaps the most important component in Lync Server; without a Registrar, users would not be able to log on to the system, and Lync Server would not be able to keep track of users and their current status. When a user logs on to Lync Server, the endpoint the user is logging on from (be it a computer, a mobile phone, or some other device) sends a REGISTER request to the registration server; in turn the server responds by challenging the client device for authentication credentials. If the client passes the challenge (that is, if the client presents a valid set of credentials), then the user is authenticated and endpoint information such as IP address, port, and user name is logged in the registration database. When a user logs off, this information is then removed from the database. In between log on and log off, the Registrar keeps status information up-to-date and helps to route messages to and from the user.

The **Set-CsRegistrar** cmdlet provides a way for you to modify the properties of one or more Registrars in your organization. These modifications include changing port settings as well as specifying the action that should be taken if a Registrar should become unavailable.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsRegistrar** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRegistrar\\b"}

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
<td><p><em>ArchivingDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the database used by the Archiving service.</p></td>
</tr>
<tr class="even">
<td><p><em>ArchivingServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the 存档服务器 to be associated with the Registrar. For example: -ArchivingServer &quot;ArchivingServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>BackupRegistrar</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the Registrar to be used if this Registrar is not available. For example: -BackupRegistrar &quot;Registrar:dublin-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EdgeServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the 边缘服务器 to be associated with the Registrar. For example: -EdgeServer &quot;EdgeServer:atl-edge-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableAutomaticFailover</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, the backup Registrar will be employed any time the primary Registrar is unavailable. If False, the backup Registrar will not be used if the primary Registrar is not available.</p>
<p>This parameter also affects users who have registered with a backup Registrar. If this parameter is set to True, then those users will be dropped from the backup Registrar and re-registered on the primary Registrar if and when that Registrar becomes available.</p></td>
</tr>
<tr class="odd">
<td><p><em>FailbackDetectionInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the amount of time that the system will wait before checking to see if a Registrar that had become unavailable is now available. If you have set EnableAutomaticFailover to True, the system will &quot;failover&quot; to the backup Registrar any time a Registrar becomes unavailable. That simply means that the system will take users who are logged-on to the failed Registrar and attempt to log them on to the backup Registrar.</p>
<p>The FailbackDetectionInterval property specifies the amount of time that the system will wait before checking to see if the original Registrar is available again. If so, Lync Server will then attempt to &quot;failback&quot; to that Registrar. Failback simply means reverting back to the Registrar initially in use; in other words, logging users back on to their original Registrar.</p>
<p>Note that failback is an automated process only. You cannot manually failback from one Registrar to another.</p>
<p>The detection interval can be set to any value between 30 seconds and 84,400 seconds (24 hours); specify the time span using the format hours:minutes:seconds. For example, this sets the interval to 1 hour and 15 minutes: - FailbackDetectionInterval 01:15:00.</p>
<p>This parameter cannot be used unless you have specified a backup Registrar.</p></td>
</tr>
<tr class="even">
<td><p><em>FailureDetectionInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the time interval that the system will wait before deciding that a Registrar is unavailable. If EnableAutomaticFailover has been set to True, the system will then attempt to log users on to the backup Registrar instead.</p>
<p>The detection interval can be set to any value between 30 seconds and 84,400 seconds (24 hours); specify the time span using the format hours:minutes:seconds. For example, this sets the interval to 1 hour and 15 minutes: - FailureDetectionInterval 01:15:00.</p>
<p>This parameter cannot be used unless you have specified a backup Registrar.</p></td>
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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Service location of the Registrar to be modified. For example: -Identity &quot;Registrar:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that you can leave off the prefix &quot;Registrar:&quot; when specifying a Registrar. For example: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>LyssWcfMtlsPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by the Lync Storage Service (LYSS). The default value is 5077.</p></td>
</tr>
<tr class="even">
<td><p><em>MirrorArchivingDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the mirror database used by the Archiving service.</p></td>
</tr>
<tr class="odd">
<td><p><em>MirrorMonitoringDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the mirror database used by the Monitoring service.</p></td>
</tr>
<tr class="even">
<td><p><em>MonitoringDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the monitoring database associated with the Registrar.</p></td>
</tr>
<tr class="odd">
<td><p><em>MonitoringServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the 监控服务器 to be associated with the Registrar. For example: -MonitoringServer &quot;MonitoringServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Registrar</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the Registrar.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipHealthPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for monitoring server health.</p></td>
</tr>
<tr class="even">
<td><p><em>SipPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for SIP (Session Initiation Protocol) traffic.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipServerTcpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>SIP listening port. The default value is 5060.</p></td>
</tr>
<tr class="even">
<td><p><em>UserServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the 用户服务 server to be associated with the Registrar. For example: -UserServer &quot;UserServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for communicating with Web servers.</p></td>
</tr>
<tr class="even">
<td><p><em>WebServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the Web Server to be associated with the Registrar. For example: -WebServer &quot;WebServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
<tr class="even">
<td><p><em>WinFabClientConnectionPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for client connections to Windows Fabric. The default value is 5092.</p></td>
</tr>
<tr class="odd">
<td><p><em>WinFabFederationPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for Windows Fabric federation. Federation refers to the process by which Windows fabric routes messages. The default value is 5090.</p></td>
</tr>
<tr class="even">
<td><p><em>WinFabIPCPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by Windows Fabric for inter-process communication (IPC). IPC is a technology that allows for multiple threads in a process to exchange data. The default value is 5093.</p></td>
</tr>
<tr class="odd">
<td><p><em>WinFabLeaseAgentPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by the Windows Fabric lease agent. Lease agents are used to interact with the kernel level lease driver. The default value is 5091.</p></td>
</tr>
<tr class="even">
<td><p><em>WinFabReplicationPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for Windows Fabric replication. Lync Server 2013 uses Windows Fabric to replicate conference directories to all the Front End servers within a Registrar pool. The default value is 5094.</p></td>
</tr>
<tr class="odd">
<td><p><em>XmppGatewaySipPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by the XMPP gateway associated with the Registrar. The extensible Messaging and Presence Protocol (XMPP) is an open-standard communications protocol for exchanging messages using XML. An allowed partner is an IM and presence provider whose users are allowed to exchange instant messages and presence information with your Lync Server users. The default value is 5098.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Set-CsRegistrar** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsRegistrar** cmdlet does not return any objects or values. Instead, the command modifies existing instances of the Microsoft.Rtc.Management.Xds.DisplayRegistrar object.

## 另请参阅

#### 其他资源

[Get-CsService](get-csservice.md)

