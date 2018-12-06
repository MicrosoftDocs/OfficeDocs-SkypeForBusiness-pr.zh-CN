---
title: Get-CsDiagnosticConfiguration
TOCTitle: Get-CsDiagnosticConfiguration
ms:assetid: f642bdca-82bb-4c72-9558-7e5ec43565fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413034(v=OCS.15)
ms:contentKeyID: 49314759
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDiagnosticConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the diagnostic configuration settings currently in use in your organization. Diagnostic configuration settings are used to determine whether traffic to or from a given domain or Uniform Resource Identifier (URI) is recorded in your Lync Server log files. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDiagnosticConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsDiagnosticConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

In Example 1, information is returned for all of the diagnostic configuration settings currently in use in the organization. This is done by calling the **Get-CsDiagnosticConfiguration** cmdlet without any parameters.

    Get-CsDiagnosticConfiguration

## EXAMPLE 2

Example 2 returns information for the diagnostic configuration settings applied to the Redmond site (-Identity site:Redmond).

    Get-CsDiagnosticConfiguration -Identity site:Redmond

## EXAMPLE 3

The command shown in Example 3 displays the information about the individual filters contained within the diagnostic configuration settings for the Redmond site. To do this, the command first uses the **Get-CsDiagnosticConfiguration** cmdlet to return the settings for the Redmond site. This information is then piped to the **Select-Object** cmdlet, which uses the ExpandProperty parameter to "expand" the value of the Filter property. Expanding the Filter property enables you to access the properties and property values for the individual filters maintained in the diagnostic configuration settings.

    Get-CsDiagnosticConfiguration -Identity site:Redmond | Select-Object -ExpandProperty Filter

## EXAMPLE 4

The command shown in Example 4 returns a subset of the filters found in the global diagnostic configuration settings; in particular, it returns filters where the Uri property includes the SIP address sip:diagnostics@litwareinc.com. To do this, the command first uses the **Get-CsDiagnosticConfiguration** cmdlet to return all the filter information for the global instance of the diagnostic configuration settings. This information is then piped to the **Select-Object** cmdlet, which expands the Filter property. The individual filter objects are then piped to the **Select-Object** cmdlet, which extracts only those filters where the Uri property includes the SIP address sip:diagnostics@litwareinc.com.

    Get-CsDiagnosticConfiguration -Identity global | Select-Object -ExpandProperty Filter | Where-Object {$_.Uri -contains "sip:diagnostics@litwareinc.com"}

## EXAMPLE 5

Example 5 is a variation of the command shown in Example 4; in Example 5, however, filters are returned only if the Uri property does not include the SIP address sip:diagnostics@litwareinc.com. To carry out this task, the command calls the **Get-CsDiagnosticConfiguration** cmdlet to return all the diagnostic configuration information for the global instance of the configuration settings. This information is then piped to the **Select-Object** cmdlet, which expands the Filter property. Those filter objects are then piped to the **Select-Object** cmdlet, which selects only those filters where the Uri property does not include the SIP address sip:diagnostics@litwareinc.com.

    Get-CsDiagnosticConfiguration -Identity global | Select-Object -ExpandProperty Filter | Where-Object {$_.Uri -notcontains "sip:diagnostics@litwareinc.com"}

## Detailed Description

If you enable logging for Lync Server, then, by default, traffic traveling to or from any domain or URI is included in those log files. This ensures that as much information as possible is recorded in the log files.

However, this can occasionally result in too much information. For example, if you are experiencing connectivity problems with a particular domain, you might want to limit logging to traffic between your network and that domain; that makes it easier for you to identify the relevant records and, in turn, might make it easier for you to diagnose and correct the problem.

Diagnostic configuration settings make it possible for you to specify the domains or URIs that will be recorded in the log files. Lync Server enables you to create diagnostic configuration settings at the site scope. In turn, this enables you to apply different settings to the Redmond site while than you do on your other sites.

The **Get-CsDiagnosticConfiguration** cmdlet enables you to return information about the diagnostic configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDiagnosticConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDiagnosticConfiguration"}

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
<td><p>Enables you to use wildcard characters when specifying the settings collection (or collections) to be returned. For example, this syntax returns all the settings configured at the site scope: -Filter &quot;site:*&quot;.</p>
<p>Note that you cannot use both the Filter and the Identity parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the diagnostic configuration settings to be returned. To return settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To return the global settings, use this syntax: -Identity global.</p>
<p>If this parameter is not specified, then all of the diagnostics configuration settings currently in use will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the diagnostic configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDiagnosticConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDiagnosticConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticFilterSettings object.

## 另请参阅

#### 其他资源

[New-CsDiagnosticConfiguration](new-csdiagnosticconfiguration.md)  
[Remove-CsDiagnosticConfiguration](remove-csdiagnosticconfiguration.md)  
[Set-CsDiagnosticConfiguration](set-csdiagnosticconfiguration.md)

