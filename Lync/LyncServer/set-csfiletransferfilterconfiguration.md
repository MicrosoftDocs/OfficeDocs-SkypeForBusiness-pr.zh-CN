---
title: Set-CsFileTransferFilterConfiguration
TOCTitle: Set-CsFileTransferFilterConfiguration
ms:assetid: 2697d3a0-d920-4a1d-9adc-7a8c754d8977
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425736(v=OCS.15)
ms:contentKeyID: 49312290
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsFileTransferFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies a collection of file transfer filter configuration settings. File transfer filter settings are used to block a user’s ability to transfer certain types of files (for example, files with a .vbs or .ps1 file extension) by using Lync Server clients. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsFileTransferFilterConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsFileTransferFilterConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Action <BlockAll | Block>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Extensions <PSListModifier>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 disables file transfer filtering for the Redmond site (that is, the file transfer filtering configuration that has the Identity site:Redmond). To carry out this task, the Enabled parameter is included in the command and is set to $False.

    Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Enabled $False

## EXAMPLE 2

The commands shown in Example 2 add a new file extension (.ps1, the file extension for Windows PowerShell scripts) to the list of file extensions prohibited in the Redmond site. To add the new file extension, the **Set-CsFileTransferFilterConfiguration** cmdlet uses the Extensions parameter and the Add list modifier. The modifier adds the specified file extension--.ps1--to the list of prohibited extensions. To add multiple extensions by using a single command, simply separate the file extensions using commas: @{Add=".ps1",".ps2",".ps3"}. Note that you must include the period when specifying a file extension.

    Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}

## EXAMPLE 3

In Example 3, the .ps1 file extension is added to the Extensions list of all the file transfer filter configurations currently in use in the organization. To do this, the **Get-CsFileTransferFilterConfiguration** cmdlet is first called, without any additional parameters, in order to return a collection of all the file transfer filter configurations currently in use. That collection is then piped to the **Set-CsFileTransferFilterConfiguration** cmdlet, which adds the .ps1 file extension to each item in the collection.

    Get-CsFileTransferFilterConfiguration | Set-CsFileTransferFilterConfiguration -Extensions @{Add=".ps1"}

## EXAMPLE 4

In Example 4, the file extension .ps1 is removed from the list of extensions blocked by the file transfer filter configuration for the Redmond site. This example is identical to Example 3 except that, instead of calling the Add list modifier to add an extension to the list, the Remove list modifier is called to remove an extension from that list.

    Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Remove=".ps1"}

## EXAMPLE 5

Example 5 performs the same action as Example 4: it removes the .ps1 extension from the list of file transfer filter extensions for the Redmond site. However, in this case we first retrieve the file transfer filter configuration for site:Redmond and assign the output to the variable $a; $a now contains the configuration for the Redmond site. Next, we retrieve the Extensions property of $a, which is the Extensions property of site:Redmond ($a.Extensions). This property contains the list of file extensions. Following the Extensions property is a call to the Remove method ($a.Extensions.Remove). We pass the value .ps1 to the Remove method; this will remove that extension from the list in the Extensions property. However, this has removed the extension only from the configuration stored in memory in the variable $a. To make the change to the database, we need to call the **Set-CsFileTransferFilterConfiguration** cmdlet, passing $a to the Instance parameter.

    $a = Get-CsFileTransferFilterConfiguration -Identity site:Redmond
    $a.Extensions.Remove(".ps1")
    Set-CsFileTransferFilterConfiguration -Instance $a

## Detailed Description

When sending instant messages, users can attach files and send them to the other participants in the conversation. Lync Server can be configured so that files with certain extensions--typically extensions of file types that could potentially prove harmful--are not allowed to be sent from the client.

The ability of users to transfer files using Lync Server clients is determined by the file transfer filter configuration settings applied at the global or (optionally) the site scopes. The **Set-CsFileTransferFilterConfiguration** cmdlet allows you to modify an existing file transfer filter configuration. You can modify the list of extensions that will be blocked by adding or removing extensions, or by creating a new list altogether. You can also use this cmdlet to change whether or not file transfer filtering is enabled, and at what level (block only the files with extensions matching those in the Extensions list, or block all files).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsFileTransferFilterConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsFileTransferFilterConfiguration"}

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
<td><p><em>Action</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileFilterAction</p></td>
<td><p>Determines the action to be taken if this file transfer filter configuration is enabled. If set to BlockAll then all file transfers will be prohibited, regardless of file extension. If set to Block (the default value) file transfers will be allowed unless the file extension appears as one of the prohibited file types listed in the Extensions property.</p>
<p>To allow unrestricted file transfers (that is, to allow users to exchange any type of file, regardless of file extension), set the Enabled property of this policy to False.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Enables or disables file transfer filtering. If this parameter is set to True, files with the specified extensions (or all files, depending on the value of the Action property) cannot be transferred from the client. If this parameter is set to False, any file can be transferred.</p>
<p>Default: True.</p></td>
</tr>
<tr class="even">
<td><p><em>Extensions</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>List of file extensions that will be blocked. If you attempt to use a Lync Server client to transfer a file that has a file extension matching one of the extensions in this list, that transfer will be blocked and the file will not be transferred. This list is ignored if Action is set to BlockAll (all file transfers are blocked) or if Enabled is set to False (no file transfers are blocked).</p>
<p>By default, the following file extensions are included in the Extensions property Default: .ade, .adp, .app, .asp, .bas, .bat, .cer, .chm, .cmd, .com, .cpl, .crt, .csh, .exe, .fxp, .grp, .hlp, .hta, .inf, .ins, .isp, .its, .js, .jse, .ksh, .lnk, .mad, .maf, .mag, .mam, .maq, .mar., mas., .mat, .mau, .mav, .maw, .mda, .mdb. .mde, .mdt, .mdw, .mdz, .msc, .msi, .msp, .mst, .ocx, .ops, .pcd, .pif, .pl, .pnp, .prf, .prg, .pst, .reg, .scf, .scr, .sct, .shb, .shs, .tmp, .url, .vb, .vbe, .vbs, .vsd, .vsmacros, .vss, .vst, .vsw, .ws, .wsc. .wsf, .wsh</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the file transfer configuration you want to modify. This value will be either global or site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site to which the settings apply, such as site:Redmond.</p>
<p>If this parameter is not specified, then the <strong>Set-CsFileTransferFilterConfiguration</strong> cmdlet will, by default, update the global settings.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>FileTransferFilterConfiguration</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values. This object must be of type FileTransferFilterConfiguration and can be retrieved by calling the <strong>Get-CsFileTransferFilterConfiguration</strong> cmdlet.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object. Accepts pipelined input of file transfer filter configuration objects.

## Return Types

This cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object.

## 另请参阅

#### 其他资源

[New-CsFileTransferFilterConfiguration](new-csfiletransferfilterconfiguration.md)  
[Remove-CsFileTransferFilterConfiguration](remove-csfiletransferfilterconfiguration.md)  
[Get-CsFileTransferFilterConfiguration](get-csfiletransferfilterconfiguration.md)

