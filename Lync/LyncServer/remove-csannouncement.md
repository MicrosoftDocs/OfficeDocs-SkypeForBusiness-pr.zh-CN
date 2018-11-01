---
title: Remove-CsAnnouncement
TOCTitle: Remove-CsAnnouncement
ms:assetid: a3c62d15-1b0a-49d3-973f-abc06c730bb2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412766(v=OCS.15)
ms:contentKeyID: 49313800
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsAnnouncement

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Lync Server announcement. Announcements are played when users dial a valid but unassigned phone number. An announcement can be a message (such as "This number is temporarily out of service") or a busy signal. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsAnnouncement -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes the announcement that has the Identity "ApplicationServer:Redmond.litwareinc.com/1951f734-c80f-4fb2-965d-51807c792b90". Because Identities must be unique, this command will remove, at most, a single announcement.

    Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.litwareinc.com/1951f734-c80f-4fb2-965d-51807c792b90"

## EXAMPLE 2

In Example 2, all the announcements that have been applied to the service ApplicationServer:Redmond.litwareinc.com are deleted. To do this, the **Remove-CsAnnouncement** cmdlet is called along with the Identity parameter. Specifying the parameter value "ApplicationServer:Redmond.litwareinc.com" (without the appended GUID that identifies a unique announcement) removes all the announcements configured for the specified service.

    Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.litwareinc.com"

## Detailed Description

An organization can own phone numbers that are not assigned to users or phones, but that are still valid numbers that can be called. By default when someone dials one of those numbers, that person will receive a busy signal and the call may result in an error returned to the SIP client. By applying announcement settings to unassigned numbers, administrators have the option of playing a message, returning a busy signal, or redirecting the call. This cmdlet removes one or more of these announcement settings.

If you attempt to remove an announcement that is associated with an unassigned number range, by default you’ll receive a prompt asking if you really want to remove the announcement. If you delete the announcement, the AnnouncementName property of that range will be displayed as Null and no announcement will be played when those numbers are reached, only a busy signal will be heard. However, the AnnouncementId property value (the GUID of the Announcement that was removed) will remain visible.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsAnnouncement** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsAnnouncement"}

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
<td><p>A unique identifier for the Announcement you want to remove. The value for the Identity parameter can be supplied in one of two ways:</p>
<p>- Enter the Identity of the 应用程序服务 for the announcements you want to remove. This will remove all announcements configured with the given service Identity. For example, ApplicationServer:Redmond.litwareinc.com.</p>
<p>- Enter the full Identity of the single announcement you want to remove. This value will always be in the format &lt;serviceID&gt;/&lt;GUID&gt;, where serviceID is the Identity of the Application Server running the Announcement Service and GUID is a globally unique identifier associated with this announcement. For example: ApplicationServer:Redmond.litwareinc.com/bef5fa3b-3c97-4af0-abe7-611deee7616c.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.AnnouncementServiceSettings.Announcement object.

## 另请参阅

#### 其他资源

[New-CsAnnouncement](new-csannouncement.md)  
[Set-CsAnnouncement](set-csannouncement.md)  
[Get-CsAnnouncement](get-csannouncement.md)

