﻿---
title: Move-CsConferenceDirectory
TOCTitle: Move-CsConferenceDirectory
ms:assetid: c43207fa-06dd-4360-ae32-b2f17f7100d2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412968(v=OCS.15)
ms:contentKeyID: 49314176
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsConferenceDirectory

 

_**上一次修改主题：** 2015-05-28_

Moves an existing conference directory from one pool to another. Conference directories are used to help dial-in conferencing users locate conference information. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -TargetPool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 moves the conference directory with the Identity 3 to the pool atl-cs-002.litwareinc.com.

    Move-CsConferenceDirectory -Identity 3 -TargetPool atl-cs-002.litwareinc.com

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1. In this case, however, the Force parameter is included to ensure that the move takes place even if the target pool is currently unavailable.

    Move-CsConferenceDirectory -Identity 3 -TargetPool atl-cs-002.litwareinc.com -Force

## EXAMPLE 3

Example 3 moves all the existing conference directories to the target pool atl-cs-002.litwareinc.com. To carry out this task the command first uses the **Get-CsConferenceDirectory** cmdlet to return a collection of all the conference directories currently in use in the organization. This collection is then piped to the **Move-CsConferenceDirectory** cmdlet, which moves each directory in the collection to the target pool.

    Get-CsConferenceDirectory | Move-CsConferenceDirectory -TargetPool atl-cs-002.litwareinc.com 

## Detailed Description

When you create a dial-in conferencing Uniform Resource Identifier (URI), those URIs are assigned unique SIP addresses. However, SIP addresses are difficult to translate to devices that are not SIP-aware; for example, a public switched telephone network (PSTN) telephone can’t translate a SIP address. Because of that, Lync Server uses conference directories as a way to help these devices locate, and connect to, dial-in conferences. This is done by creating a SIP conference directory that is associated with each dial-in conferencing URI, and is identified by an integer value rather than a SIP URI. PSTN telephones and other devices can then use these numbers instead of a SIP URI when connecting to conferences; the directory number is included in the PSTN conference identification users enter when connecting to a dial-in conference.

Occasionally, you might need to move a conference directory from one pool to another; for example, if you decommission a pool you might need to move your existing conference directories to a new location. The **Move-CsConferenceDirectory** cmdlet enables you to move conference directories to a different pool.

> [!IMPORTANT]
> Before you move a conference directory it is highly recommended that you make a backup copy of that directory. This can be done by using the Export-CsUserData cmdlet and the ConferenceDirectoryFilter parameter. For example, this command backs up conference directory 3 to the file C:\Logs\ConferenceDirectory3.zip:<br />
> Export-CsUserData –PoolFqdn &quot;atl-cs-001.litwareinc.com&quot; –ConferenceFilterDirectory 3 –FileName &quot;C:\Logs\ConferenceDirectory3.zip&quot;


Who can run this cmdlet: By default, members of the following groups are authorized to run the **Move-CsConferenceDirectory** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsConferenceDirectory"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Numeric identity of the conference directory to be moved.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetPool</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool where the conference directory is to be moved. For example: -Identity atl-cs-002.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, moves the conference directory even if the target pool is currently unavailable. By default, the <strong>Move-CsConferenceDirectory</strong> cmdlet will not move directories if the target pool cannot be contacted.</p>
<p>Before running the <strong>Move-CsConferenceDirectory</strong> cmdlet, note that if you use the -Force parameter, the dial-in code for existing meetings will be lost. Users will still be able to join meetings using a Lync client, but unable to dial-in to meetings by phone dial in.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Move-CsConferenceDirectory** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsConferenceDirectory](get-csconferencedirectory.md)  
[New-CsConferenceDirectory](new-csconferencedirectory.md)  
[Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

