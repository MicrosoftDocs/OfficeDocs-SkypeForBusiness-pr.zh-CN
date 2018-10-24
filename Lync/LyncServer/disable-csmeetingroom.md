---
title: Disable-CsMeetingRoom
TOCTitle: Disable-CsMeetingRoom
ms:assetid: 1bce6b58-484f-4e59-a259-aa315d37d9b0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204723(v=OCS.15)
ms:contentKeyID: 49312169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsMeetingRoom

 

_**上一次修改主题：** 2015-03-09_

Disables a Lync Server 2013 meeting room. A meeting room is a conferencing device designed to address video conferencing and collaboration scenarios in small conference rooms. When you disable a meeting room object you remove all the Lync Server-specific Active Directory attributes assigned to the user account that represents the meeting room. However, the Active Directory user account itself is not deleted. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Disable-CsMeetingRoom -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 disables the meeting room sip:RedmondMeetingRoom@litwareinc.com.

    Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

## Example 2

In Example 2, all the meeting rooms currently in use in the organization are disabled. To do this, the **Get-CsMeetingRoom** cmdlet is first used to retrieve a collection of all the meeting rooms. That collection is then piped to the **Disable-CsMeetingRoom** cmdlet, which disables each meeting room in the collection.

    Get-CsMeetingRoom | Disable-CsMeetingRoom

## Detailed Description

In Lync Server, meeting rooms are self-contained computer appliances that are installed in conference rooms and supply advanced meeting capabilities such as:

  - One touch meeting join experience

  - Multi-view video gallery

  - Touch-enabled white-boarding on the front of room screen

  - Calendar integration to provide access to scheduled meetings

  - Content sharing and switching

In order to manage these new endpoint devices you must, among other things, create and enable a Microsoft Exchange Server 2013 resource mailbox account for the device, then enable that resource account for Lync Server 2013. Note that, for Lync Server, there are no cmdlets for creating or removing meeting rooms. Instead, you use the [Enable-CsMeetingRoom](enable-csmeetingroom.md) cmdlet to enable meeting rooms and the **Disable-CsMeetingRoom** cmdlet to disable meeting rooms. The resource account must already exist in order for you to enable the meeting room, and disabling a meeting room only removes that room from your collection of meeting rooms; it does not delete the resource mailbox account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Disable-CsMeetingRoom"}

**Lync Server 控制面板:** The functions carried out by the **Disable-CsMeetingRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account to be configured as a meeting room. Identities are typically specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).</p>
<p>You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the user who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to disable a meeting room. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a meeting room object through the pipeline that represents the meeting room being disabled. By default, the <strong>Disable-CsMeetingRoom</strong> cmdlet does not pass objects through the pipeline.</p></td>
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

The **Disable-CsMeetingRoom** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## Return Types

None. Instead, the **Disable-CsMeetingRoom** cmdlet deletes instance of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## 另请参阅

#### 其他资源

[Enable-CsMeetingRoom](enable-csmeetingroom.md)  
[Get-CsMeetingRoom](get-csmeetingroom.md)  
[Move-CsMeetingRoom](Move-CsMeetingRoom.md)  
[Set-CsMeetingRoom](set-csmeetingroom.md)

