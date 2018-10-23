---
title: Get-CsDiagnosticHeaderConfiguration
TOCTitle: Get-CsDiagnosticHeaderConfiguration
ms:assetid: a5b247b8-621a-463b-8034-f2f6970706fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412774(v=OCS.15)
ms:contentKeyID: 49313823
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDiagnosticHeaderConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the diagnostic header configuration settings currently in use in your organization. Diagnostic header configuration settings determine whether SIP messages are accompanied by header information. This information can be useful in troubleshooting and error reporting. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDiagnosticHeaderConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsDiagnosticHeaderConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The preceding command returns information about all the diagnostic header configuration settings currently in use in the organization. This is done by calling the **Get-CsDiagnosticHeaderConfiguration** cmdlet without any parameters.

    Get-CsDiagnosticHeaderConfiguration

## EXAMPLE 2

In Example 2, a single collection of diagnostic header configuration settings is returned: the collection that has the Identity site:Redmond.

    Get-CsDiagnosticHeaderConfiguration -Identity site:Redmond

## EXAMPLE 3

The command shown in Example 3 returns all the diagnostic header settings that have been configured at the service scope. This is done by calling the **Get-CsDiagnosticHeaderConfiguration** cmdlet and the Filter parameter; the filter value "service:\*" ensures that the only settings that are returned are those that have an Identity that begins with the characters "service:".

    Get-CsDiagnosticHeaderConfiguration -Filter "service:*"

## EXAMPLE 4

Example 4 returns all the diagnostic header configuration settings that allow sending to external networks. To perform this task, the command first calls the **Get-CsDiagnosticHeaderConfiguration** cmdlet without any parameters; this returns a collection of all the diagnostic header settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the SendToExternalNetworks property is equal to True.

    Get-CsDiagnosticHeaderConfiguration | Where-Object {$_.SendToExternalNetworks -eq $True}

## EXAMPLE 5

The command shown in Example 5 returns information about the diagnostic header configuration settings that meet at least one of the following criteria: 1) the SendToExternalNetworks property is equal to True; and/or 2) the SendToOutsideUnauthenticatedUsers is equal to True. To do this, the command first uses the **Get-CsDiagnosticHeaderConfiguration** cmdlet to return a collection of all the diagnostic header settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out those settings where the SendToExternalNetworks property and/or the SendToOutsideUnauthenticatedUsers property is equal to True.

The -or operator specifies that, to be returned, settings only have to meet one of the specified criteria. To require that settings meet both of the specified criteria, use the -and operator instead:

Where-Object {$\_.SendToExternalNetworks -eq $True -and $\_.SendToOutsideUnauthenticatedUsers -eq $True}

    Get-CsDiagnosticHeaderConfiguration | Where-Object {$_.SendToExternalNetworks -eq $True -or $_.SendToOutsideUnauthenticatedUsers -eq $True}

## Detailed Description

When you send SIP (Session Initiation Protocol) messages, you have the option of attaching an ms-diagnostics header to each message. This message (which is not visible to end users) contains information that might be useful in troubleshooting connection problems or in reporting errors. For example, the diagnostic header might contain error codes that enable the client application (for example, Lync 2013) to take a predetermined course of action should a specific situation arise.

For SIP messages sent within your internal network, there’s little reason not to include these diagnostic headers: they have a minimal impact on message size and can be an invaluable tool for administrators trying to troubleshoot connectivity problems. However, diagnostic headers also contain information, such as the fully qualified domain names (FQDNs) of your SIP servers, that you might not want to make available to people outside the internal network. Because of this, the diagnostic header configuration settings enable you to decide whether you want diagnostic headers sent to users on external networks (such as users in a federated domain) and/or to outside users. (Outside users are users who have connected from outside the internal network and have not yet been authenticated.)

By default, headers are not included in messages sent either to external networks or to unauthenticated users. However, you can modify the global diagnostic header settings to include headers to external networks and/or unauthenticated users. Alternatively, you can create custom settings at the site scope or at the service scope (for the 边缘服务器 or Registrar service). That way, you can choose to include diagnostic headers on messages sent from one site, or through one 边缘服务器, while disallowing headers on messages sent from other sites or through other Edge Servers.

The **Get-CsDiagnosticHeaderConfiguration** cmdlet provides a way for you to retrieve information about the diagnostic header configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDiagnosticHeaderConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDiagnosticHeaderConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when specifying the settings collection (or collections) to be returned. For example, this syntax returns all the settings configured at the site scope: -Filter &quot;site:*&quot;. This syntax returns all the settings configured at the service scope: -Filter &quot;service:*&quot;.</p>
<p>Note that you cannot use both the Filter and the Identity parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the diagnostic header configuration settings to be returned. To return settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To return settings configured at the service scope, use syntax like this: -Identity &quot;service:EdgeServer:atl-edge-001.litwareinc.com&quot;. To return the global settings, use this syntax: -Identity global.</p>
<p>If this parameter is not specified, then all the diagnostic header configuration settings currently in use will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the diagnostic header configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDiagnosticHeaderConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDiagnosticHeaderConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticHeaderSettings object.

## 另请参阅

#### 其他资源

[New-CsDiagnosticHeaderConfiguration](new-csdiagnosticheaderconfiguration.md)  
[Remove-CsDiagnosticHeaderConfiguration](remove-csdiagnosticheaderconfiguration.md)  
[Set-CsDiagnosticHeaderConfiguration](set-csdiagnosticheaderconfiguration.md)

