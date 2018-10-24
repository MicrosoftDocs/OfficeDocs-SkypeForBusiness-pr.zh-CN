---
title: Get-CsMeetingRoom
TOCTitle: Get-CsMeetingRoom
ms:assetid: ce361cb8-042c-4708-8f9c-7e67a34a570d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205277(v=OCS.15)
ms:contentKeyID: 49314286
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsMeetingRoom

 

_**上一次修改主题：** 2015-03-09_

Returns information about all the Lync Server 2013 meeting rooms configured for use in the organization. A meeting room is a conferencing device designed to address video conferencing and collaboration scenarios in small conference rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsMeetingRoom [-Identity <UserIdParameter>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-LdapFilter <String>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the meeting rooms configured for use in your organization.

    Get-CsMeetingRoom

## Example 2

Example 2 returns information for a single meeting room: the system with the SIP address sip:RedmondMeetingRoom@litwareinc.com.

    Get-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

## Example 3

The command shown in Example 3 returns information for all the meeting rooms that have been assigned the per-user voice policy RedmondVoicePolicy. To do this, the command includes the Filter parameter and the filter value {VoicePolicy –eq "RedmondVoicePolicy}. That filter value limits the returned data to meeting rooms where the VoicePolicy property is equal to (-eq) RedmondVoicePolicy.

    Get-CsMeetingRoom -Filter {VoicePolicy -eq "RedmondVoicePolicy"}

## Detailed Description

In Lync Server, meeting rooms are self-contained computer appliances that are installed in conference rooms and supply advanced meeting capabilities such as:

  - One touch meeting join experience

  - Multi-view video gallery

  - Touch-enabled white-boarding on the front of room screen

  - Calendar integration to provide access to scheduled meetings

  - Content sharing and switching

In order to manage these new endpoint devices you must, among other things, create and enable a Microsoft Exchange Server 2013 resource mailbox account for the device, then enable that resource account for Lync Server 2013. Note that, for Lync Server, there are no cmdlets for creating or removing meeting rooms. Instead, you use the [Enable-CsMeetingRoom](enable-csmeetingroom.md) cmdlet to enable meeting rooms and the [Disable-CsMeetingRoom](disable-csmeetingroom.md) cmdlet to disable meeting rooms. The resource account must already exist in order for you to enable the meeting room, and disabling a meeting room only removes that room from your collection of meeting rooms; it does not delete the resource mailbox account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsMeetingRoom"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsMeetingRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the <strong>Get-CsMeetingRoom</strong> cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with contact objects.</p>
<p>To use the Credential parameter, you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve meeting room information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on Lync Server-specific attributes. For example, you can limit returned data to meeting rooms that have been assigned a specific voice policy, or rooms that have not been assigned a specific voice policy.</p>
<p>The Filter parameter uses much the same Windows PowerShell filtering syntax that is used by the Where-Object cmdlet. For example, a filter that returns only rooms that have been assigned the voice policy RedmondVoicePolicy would look like this:</p>
<p>{VoicePolicy -eq &quot;RedmondVoicePolicy&quot;}</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the meeting room to be retrieved. Meeting room Identities are typically specified using one of four formats: 1) the room's SIP address; 2) the room's user principal name (UPN); 3) the room's domain name and logon name, in the form domain\logon (for example, litwareinc\room14); and, 4) the room's Active Directory display name (for example, Room 14).</p>
<p>You can also reference a room account by using the room's Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the room Identity. For example, the Identity &quot;*Redmond*&quot; returns all the rooms that have a display name that includes the string value &quot;Redmond&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>LdapFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on generic Active Directory attributes (that is, attributes that are not specific to Lync Server). For example, you can limit returned data to meeting rooms belonging to a specific department.The LdapFilter parameter uses the LDAP query language when creating filters. For example, a filter that returns only meeting rooms found in the city of Redmond would look like this:</p>
<p>-LdapFilter &quot;l=Redmond&quot;</p>
<p>In that syntax, &quot;l&quot; (a lowercase L) represents the Active Directory attribute (locality); &quot;=&quot; represents the comparison operator (equal to); and &quot;Redmond&quot; represents the filter value.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Enables you to return information about meeting rooms in a specific organizational unit (OU) or container. The OU parameter returns data from both the specified OU and any of its child OUs. For example, if the Finance OU has two child OUs -- AccountsPayable and AccountsReceivable – meeting rooms will be returned from each of these three OUs.</p>
<p>When specifying an OU, use the distinguished name (DN) of that container; for example:</p>
<p>-OU &quot;OU=MeetingRooms,dc=litwareinc,dc=com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven meeting rooms (regardless of the number of meeting rooms that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven meeting rooms will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three meeting rooms in your forest, the command will return those three meeting rooms, and then complete without error.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. The **Get-CsMeetingRoom** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled as a Lync Server 2013 meeting room.

## Return Types

The **Get-CsMeetingRoom** cmdlet returns instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## 另请参阅

#### 其他资源

[Disable-CsMeetingRoom](disable-csmeetingroom.md)  
[Enable-CsMeetingRoom](enable-csmeetingroom.md)  
[Move-CsMeetingRoom](Move-CsMeetingRoom.md)  
[Set-CsMeetingRoom](set-csmeetingroom.md)

