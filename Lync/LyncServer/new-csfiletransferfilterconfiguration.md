---
title: New-CsFileTransferFilterConfiguration
TOCTitle: New-CsFileTransferFilterConfiguration
ms:assetid: 3d1050fb-5df9-4186-94b9-8ef8a9103958
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425897(v=OCS.15)
ms:contentKeyID: 49312576
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsFileTransferFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new file transfer filter configuration. File transfer filter configurations are used to block a user’s ability to transfer certain types of files (for example, files with a .vbs or .ps1 file extension) using a Lync Server client. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsFileTransferFilterConfiguration -Identity <XdsIdentity> [-Action <BlockAll | Block>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Extensions <PSListModifier>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **New-CsFileTransferFilterConfiguration** cmdlet is used to create a new instant message file transfer filter configuration with the Identity site:Redmond. Because no additional parameters were specified, the configuration will be created using the default values.

    New-CsFileTransferFilterConfiguration -Identity site:Redmond

## EXAMPLE 2

In this command, the **New-CsFileTransferFilterConfiguration** cmdlet is used to create a new file transfer filter configuration with the Identity site:Redmond. Because the Extensions parameter has been specified, the new configuration will contain all the default values plus an additional file extension: .ps1. This new extension is added by using the Extensions parameter and the list modifier Add followed by the file extension to be added. (Note that you must include the period as part of the file extension.) To add multiple file extensions, simply separate those extensions by using commas: @{Add=".ps1",".ps2",".ps3"}

    New-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}

## EXAMPLE 3

In Example 3, the **New-CsFileTransferFilterConfiguration** cmdlet is used to create a new file transfer filter configuration with the Identity site:Redmond. This example is similar to Example 2 except that the Replace list modifier has been used instead of the Add modifier. This means that the complete set of file extensions will be replaced by the two specified file extensions: .vbs and .ps1. In this case the only files blocked at the Redmond site will be .vbs and .ps1.

    New-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Replace=".vbs",".ps1"}

## EXAMPLE 4

Example 4 demonstrates the use of the InMemory parameter to create a file transfer filter configuration that initially resides in memory only. To do this the first command in the example uses the **New-CsFileTransferFilterConfiguration** cmdlet and the InMemory parameter to create a new file transfer filter configuration with the Identity site:Redmond. At this point in time, the new settings exist only in memory; users in the Redmond site will still be governed by the global file transfer filter settings.

In the second command, the value of the Action property for this in-memory instance is set to BlockAll. Finally, the third command in the example uses the **Set-CsFileTransferFilterConfiguration** cmdlet to create the new collection of settings and apply them to the Redmond site.

Note that this same task can be accomplished in one step with the following command:

    New-CsFileTransferFilterConfiguration -Identity site:Redmond -Action "BlockAll"
    $x = New-CsFileTransferFilterConfiguration -Identity site:Redmond -InMemory 
    $x.Action = "BlockAll"
    Set-CsFileTransferFilterConfiguration -Instance $x

## Detailed Description

When sending instant messages, users can attach and send files to the other participants in the conversation. Lync Server can be configured so that files with certain extensions--typically extensions of file types that could potentially prove harmful--are not allowed to be sent using a Lync Server client.

When you install Lync Server, a single file transfer filter configuration (which is configured at the global scope) is created for you. By default, the global configuration applies to all the users in your organization. In addition, you can use the **New-CsFileTransferFilterConfiguration** cmdlet to create custom file transfer filter configurations for individual sites. If a configuration exists for a given site then those file transfer settings will be applied to all the users in that site. If no such collection exists for a site then the global settings will be applied instead.

Note that you cannot create new a file transfer filter configuration at the global scope; however, you can use the **Set-CsFileTransferFilterConfiguration** cmdlet to modify the global settings. Likewise, you cannot create a new configuration for a site that already has one defined; if you try that, your command will fail.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsFileTransferFilterConfiguration** cmdlet locally: RTCUniversalServerAdministrator. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsFileTransferFilterConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier to be given to the file transfer filter configuration. The Identity for the new configuration is simply the prefix &quot;site:&quot; followed by the site name. For example, to create a new configuration for the Redmond site, you would use this syntax: -Identity site:Redmond.</p></td>
</tr>
<tr class="even">
<td><p><em>Action</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileFilterAction</p></td>
<td><p>Determines the action to be taken if file transfer filtering is enabled. If set to BlockAll then all file transfers will be prohibited, regardless of file extension. If set to Block (the default value) file transfers will be allowed unless the file extension appears as one of the prohibited file types listed in the Extensions property.</p>
<p>To allow unrestricted file transfers (that is, to allow users to exchange any type of file, regardless of file extension), set the Enabled property of this policy to False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Enables or disables file transfer filtering. If this parameter is set to True, files with the specified extensions (or all files, depending on the value of the Action property) cannot be transferred by a Lync Server client. If this parameter is set to False, any file can be transferred.</p>
<p>Default: True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Extensions</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>List of file extensions that will be blocked. If you attempt to use a Lync Server client to transfer a file that has a file extension matching one of the extensions in this list, that transfer will be blocked and the file will not be transferred. This list is ignored if Action is set to BlockAll (all file transfers are blocked) or if Enabled is set to False (no file transfers are blocked).</p>
<p>By default, the following file extensions are included in the Extensions property: .ade, .adp, .app, .asp, .bas, .bat, .cer, .chm, .cmd, .com, .cpl, .crt, .csh, .exe, .fxp, .grp, .hlp, .hta, .inf, .ins, .isp, .its, .js, .jse, .ksh, .lnk, .mad, .maf, .mag, .mam, .maq, .mar., mas., .mat, .mau, .mav, .maw, .mda, .mdb. .mde, .mdt, .mdw, .mdz, .msc, .msi, .msp, .mst, .ocx, .ops, .pcd, .pif, .pl, .pnp, .prf, .prg, .pst, .reg, .scf, .scr, .sct, .shb, .shs, .tmp, .url, .vb, .vbe, .vbs, .vsd, .vsmacros, .vss, .vst, .vsw, .ws, .wsc. .wsf, .wsh</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

None.

## Return Types

The **New-CsFileTransferFilterConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object.

## 另请参阅

#### 其他资源

[Remove-CsFileTransferFilterConfiguration](remove-csfiletransferfilterconfiguration.md)  
[Set-CsFileTransferFilterConfiguration](set-csfiletransferfilterconfiguration.md)  
[Get-CsFileTransferFilterConfiguration](get-csfiletransferfilterconfiguration.md)

