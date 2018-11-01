---
title: Move-CsMeetingRoom
TOCTitle: Move-CsMeetingRoom
ms:assetid: 4ea6b8bd-b134-4453-9ae4-6118330a62ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204889(v=OCS.15)
ms:contentKeyID: 49312807
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsMeetingRoom

 

_**上一次修改主题：** 2015-03-09_

Moves a Lync Server 2013 meeting room object from one Registrar pool to another. A meeting room is a conferencing device designed to address video conferencing and collaboration scenarios in small conference rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Move-CsMeetingRoom -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-IgnoreBackendStoreException <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 moves the meeting room with the display name "Room 14" to the pool atl-cs-001.litwareinc.com.

    Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

## Example 2

Example 2 moves all the meeting rooms in the organization to the pool atl-cs-001.litwareinc.com. To do this, the command first calls the **Get-CsMeetingRoom** cmdlet without any parameters; that returns a collection of all the meeting rooms configured for use in the organization. That collection is then piped to the **Move-CsMeetingRoom** cmdlet, which moves each meeting room in the collection to the new pool.

    Get-CsMeetingRoom | Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com"

## Detailed Description

In Lync Server, meeting rooms are self-contained computer appliances that are installed in conference rooms and supply advanced meeting capabilities such as:

  - One touch meeting join experience

  - Multi-view video gallery

  - Touch-enabled white-boarding on the front of room screen

  - Calendar integration to provide access to scheduled meetings

  - Content sharing and switching

In order to manage these new endpoint devices you must, among other things, create and enable a Microsoft Exchange Server 2013 resource mailbox account for the device, then enable that resource account for Lync Server 2013. Note that, for Lync Server, there are no cmdlets for creating or removing meeting rooms. Instead, you use the [Enable-CsMeetingRoom](enable-csmeetingroom.md) cmdlet to enable meeting rooms and the [Disable-CsMeetingRoom](disable-csmeetingroom.md) cmdlet to disable meeting rooms. The resource account must already exist in order for you to enable the meeting room, and disabling a meeting room only removes that room from your collection of meeting rooms; it does not delete the resource mailbox account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsMeetingRoom"}

Lync Server 控制面板: The functions carried out by the **Move-CsMeetingRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Indicates the Identity of the meeting room to be moved. Meeting rooms can be specified using one of four formats: 1) the room's SIP address; 2) the room's user principal name (UPN); 3) the room's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the room's Active Directory display name (for example, Main Conference Room). User Identities can also be referenced by using the room's Active Directory distinguished name.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The FQDN (for example, atl-cs-001.litwareinc.com) of the Registrar pool where the meeting room should be moved.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to move a meeting room. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, instructs the <strong>Move-CsMeetingRoom</strong> cmdlet to ignore all errors that might occur when carrying out the move operation. As a general rule, you should avoid using the Force parameter unless absolutely necessary.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, instructs the computer to ignore any errors that might occur with the backend database and attempt to the move meeting room despite those errors.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a meeting room object through the pipeline that represents the meeting room being moved. By default, the <strong>Move-CsMeetingRoom</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is not used with the on-premises version of Lync Server 2013.</p></td>
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

The Moves-CsMeetingRoom cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## Return Types

None.

## 另请参阅

#### 其他资源

[Disable-CsMeetingRoom](disable-csmeetingroom.md)  
[Enable-CsMeetingRoom](enable-csmeetingroom.md)  
[Get-CsMeetingRoom](get-csmeetingroom.md)  
[Set-CsMeetingRoom](set-csmeetingroom.md)

