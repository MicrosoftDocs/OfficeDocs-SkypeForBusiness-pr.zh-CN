---
title: Get-CsFileTransferFilterConfiguration
TOCTitle: Get-CsFileTransferFilterConfiguration
ms:assetid: 6f43c203-acd6-4dbf-a071-752bf0c1727c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398527(v=OCS.15)
ms:contentKeyID: 49313194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsFileTransferFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns the file transfer filter configurations in your organization. These configurations are used to block a user’s ability to transfer certain types of files (for example, files with a .vbs or .ps1 file extension) using a Lync Server client. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsFileTransferFilterConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsFileTransferFilterConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the file transfer filter configurations in use in your organization. This is the default behavior any time you call the **Get-CsFileTransferFilterConfiguration** cmdlet without any additional parameters.

    Get-CsFileTransferFilterConfiguration

## EXAMPLE 2

Example 2 returns a single file transfer filter configuration: the configuration that has the Identity site:Redmond. Because identities must be unique, this command can never return more than one configuration.

    Get-CsFileTransferFilterConfiguration -Identity site:Redmond

## EXAMPLE 3

Example 3 uses the Filter parameter to return a collection of all the file transfer filter configurations at the site level. The Filter value "site:\*" instructs the **Get-CsFileTransferFilterConfiguration** cmdlet to return only those configurations that have an Identity that begins with the string value "site:".

    Get-CsFileTransferFilterConfiguration -Filter site:*

## EXAMPLE 4

The command shown in Example 4 returns only those file transfer filter configurations that include .xls in their list of prohibited file extensions. To do this, the **Get-CsFileTransferFilterConfiguration** cmdlet is first used to return a collection of all the configurations in use in your organization. That collection is then piped to the **Where-Object** cmdlet, which applies a filter that restricts the returned data to those configurations where the Extensions property includes (-contains) the string value ".xls".

    Get-CsFileTransferFilterConfiguration | Where-Object {$_.Extensions -contains ".xls"}

## EXAMPLE 5

Example 5 returns all the file transfer filter configurations that are currently disabled. To accomplish this task, the **Get-CsFileTransferFilterConfiguration** cmdlet is used to return a collection of all the configurations in use in your organization. This collection is then piped to the **Where-Object** cmdlet, which, in turn, selects only those configuration where the Enabled property is equal to (-eq) False ($False).

    Get-CsFileTransferFilterConfiguration | Where-Object {$_.Enabled -eq $False}

## EXAMPLE 6

Example 6 shows a complete list of the file extensions prohibited by the global file transfer filter configuration. The command begins with a call to the **Get-CsFileTransferFilterConfiguration** cmdlet, specifying the Global configuration. The returned information is then piped to the **Select-Object** cmdlet, which uses the ExpandProperty parameter to "expand" the value of the Extensions property. That results in the complete list of file extensions being displayed on the screen, one file extension per line.

    Get-CsFileTransferFilterConfiguration -Identity Global | Select-Object -ExpandProperty Extensions

## Detailed Description

When sending instant messages, users can attach and send files to the other participants in the conversation. Lync Server can be configured so that files with certain extensions--typically extensions of file types that could potentially prove harmful--are not allowed to be sent using the Lync client.

The **Get-CsFileTransferFilterConfiguration** cmdlet provides a way for you to retrieve a particular collection of settings (these settings can be configured at the global scope or at the site scope). File transfer filter configurations include the list of file extensions that are blocked from transfers, to what degree filtering is enabled (all file transfers are blocked or only files with the specified extensions), and whether file transfer filtering is enabled.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsFileTransferFilterConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsFileTransferFilterConfiguration"}

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
<td><p>Enables you to use wildcards when specifying the file transfer filter configurations to be returned. For example, to return all the file transfer filter configurations at the site scope, use this syntax: -Filter &quot;site:*&quot;. By design, file transfer filter configurations that have an Identity (the only property you can filter for) that begins with the string value &quot;site:&quot; were configured at the site scope.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the file transfer filter configuration you want to retrieve. To refer to the global settings, use this syntax: -Identity global. To refer to settings configured at the site scope, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcard values when specifying an Identity. If you want to use wildcards, use the Filter parameter instead.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the file transfer filter configuration from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsFileTransferFilterConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object.

## 另请参阅

#### 其他资源

[New-CsFileTransferFilterConfiguration](new-csfiletransferfilterconfiguration.md)  
[Remove-CsFileTransferFilterConfiguration](remove-csfiletransferfilterconfiguration.md)  
[Set-CsFileTransferFilterConfiguration](set-csfiletransferfilterconfiguration.md)

