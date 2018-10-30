---
title: Set-CsMeetingRoom
TOCTitle: Set-CsMeetingRoom
ms:assetid: 3dd02280-6407-4e17-929c-7070f8d1c3cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204831(v=OCS.15)
ms:contentKeyID: 49312601
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsMeetingRoom

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values of an existing Lync Server 2013 meeting room. A meeting room is a conferencing device designed to address video conferencing and collaboration scenarios in small conference rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsMeetingRoom -Identity <UserIdParameter> [-AcpInfo <MultiValuedProperty>] [-AudioVideoDisabled <$true | $false>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-HostedVoiceMail <$true | $false>] [-LineServerURI <String>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-PrivateLine <String>] [-RemoteCallControlTelephonyEnabled <$true | $false>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command show in Example 1 updates the LineUri assigned to the meeting room RedmondMeetingRoom.

    Set-CsMeetingRoom -Identity "RedmondMeetingRoom" -LineUri "tel:+12065551219"

## Example 2

In Example 2, the meeting room RedmondMeetingRoom is temporarily disabled; this is done by setting the Enabled property to False ($False):

    Set-CsMeetingRoom -Identity "RedmondMeetingRoom" -Enabled $False

To re-enable the room, simply set the Enabled property to True ($True):

    Set-CsMeetingRoom -Identity "RedmondMeetingRoom" -Enabled $True

## Example 3

Example 3 temporarily disables all the meeting rooms in the organization. To do this, the command first calls the **Get-CsMeetingRoom** cmdlet without any parameters; that returns a collection of all the available meeting rooms. That collection is then piped to the **Set-CsMeetingRoom** cmdlet, which temporarily disables each room in the collection.

    Get-CsMeetingRoom | Set-CsMeetingRoom -Enabled $False

## Example 4

In Example 4, all the meeting rooms in the organization are configured to use Lync Server 2013 archiving rather than Microsoft Exchange Server archiving. To carry out this task, the command first uses the **Get-CsMeetingRoom** cmdlet to return a collection of all the available meeting rooms. That collection is then piped to the **Set-CsMeetingRoom** cmdlet, which uses the ExchangeArchivingPolicy cmdlet to configure each room in the collection to use Lync Server archiving.

    Get-CsMeetingRoom | Set-CsMeetingRoom -ExchangeArchivingPolicy "UseLyncArchivingPolicy"

## Detailed Description

In Lync Server, meeting rooms are self-contained computer appliances that are installed in conference rooms and supply advanced meeting capabilities such as:

  - One touch meeting join experience

  - Multi-view video gallery

  - Touch-enabled white-boarding on the front of room screen

  - Calendar integration to provide access to scheduled meetings

  - Content sharing and switching

In order to manage these new endpoint devices you must, among other things, create and enable a Microsoft Exchange Server 2013 resource mailbox account for the device, then enable that resource account for Lync Server 2013. Note that, for Lync Server, there are no cmdlets for creating or removing meeting rooms. Instead, you use the [Enable-CsMeetingRoom](enable-csmeetingroom.md) cmdlet to enable meeting rooms and the [Disable-CsMeetingRoom](disable-csmeetingroom.md) cmdlet to disable meeting rooms. The resource account must already exist in order for you to enable the meeting room, and disabling a meeting room only removes that room from your collection of meeting rooms; it does not delete the resource mailbox account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsMeetingRoom"}

Lync Server 控制面板: The functions carried out by the **Set-CsMeetingRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>UserIdParameter</p></td>
<td><p>Indicates the Identity of the meeting room to be modified. Meeting room Identities are typically specified using one of four formats: 1) the room's SIP address; 2) the room's user principal name (UPN); 3) the room's domain name and logon name, in the form domain\logon (for example, litwareinc\room14); and, 4) the room's Active Directory display name (for example, Room 14). You can also reference a room account by using the room's Active Directory distinguished name.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>AcpInfo</em></p></td>
<td><p>Optional</p></td>
<td><p>MultiValuedProperty</p></td>
<td><p>Enables you to assign one or more third-party audio conferencing providers to a meeting room. However, it is recommended that you use the <strong>Set-UserAcp</strong> cmdlet to assign Audio conferencing providers.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioVideoDisabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the room is allowed to make audio/visual (A/V) calls by using Lync 2013. If set to True, the room will largely be restricted to sending and receiving instant messages.</p>
<p>You cannot disable A/V communications if a room is currently enabled for remote call control, Enterprise Voice, and/or Internet Protocol private branch exchange (IP-PBX) soft phone routing.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve meeting room information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether or not the room has been enabled for Lync Server 2013. If you set this value to False, the room will no longer be able to log on to Lync Server; setting this value to True re-enables the meeting room's logon privileges.</p>
<p>If you disable an account by using the Enabled parameter, the information associated with that account (including assigned policies and whether or not the room is enabled for Enterprise Voice and/or remote call control) is retained. If you later re-enable the account by using the Enabled parameter, the associated account information will be restored. This differs from using the <strong>Disable-CsMeetingRoom</strong> cmdlet to disable a meeting room account. When you run Disable-CsMeetingRoom, all the Lync Server data associated with that account is deleted.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the room has been enabled for Enterprise Voice, which is the Microsoft implementation of Voice over Internet Protocol (VoIP). With Enterprise Voice, rooms can make telephone calls using the Internet rather than using the standard telephone network.</p></td>
</tr>
<tr class="even">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>Indicates how (and where) the room's instant messaging and conferencing sessions will be archived. Allowed values are:</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* NoArchiving</p>
<p>* ArchivingToExchange</p></td>
</tr>
<tr class="odd">
<td><p><em>HostedVoiceMail</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, enables a room's voice mail calls to be routed to a hosted version of Microsoft Exchange Server 2013. In addition, setting this option to True enables rooms to directly place a call to another user’s voice mail.</p></td>
</tr>
<tr class="even">
<td><p><em>LineServerURI</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>The URI of the remote call control telephone gateway assigned to the room. The LineServerUri is the gateway URI, prefaced by &quot;sip:&quot;. For example:</p>
<p>-LineServerUri &quot;sip:rccgateway@litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Phone number assigned to the room. The line Uniform Resource Identifier (URI) must be specified using the E.164 format and use the &quot;TEL:&quot; prefix. For example:</p>
<p>-LineUri &quot;TEL:+14255551297&quot;</p>
<p>Any extension number should be added to the end of the line URI, for example:</p>
<p>-LineUri &quot;TEL:+14255551297;ext=51297”</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Enables you to pass a meeting room object through the pipeline that represents the meeting room being modified. By default, the <strong>Set-CsMeetingRoom</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrivateLine</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Phone number for the room private telephone line. A private line is a phone number that is not published in Active Directory Domain Services (AD DS) and, as a result, is not readily available to other people. In addition, this private line bypasses most in-bound call routing rules; for example, a call to a private line will not be forwarded to a room's delegates. Private lines are often used for personal phone calls or for business calls that should be kept separate from other team members.</p>
<p>The private line value should be specified using the E.164 format, and be prefixed by the &quot;TEL:&quot; prefix. For example:</p>
<p>-PrivateLine &quot;TEL:+14255551297&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>RemoteCallControlTelephonyEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the room has been enabled for remote call control telephony. When enabled for remote call control, a room can employ Lync Server 2013 to answer phone calls made to his or her desk phone. Phone calls can also be made using Lync. These calls all rely on the standard telephone network, also known as the public switched telephone network (PSTN). To make and receive phone calls over the Internet, the room must be enabled for Enterprise Voice. For details, see the parameter EnterpriseVoiceEnabled.</p>
<p>To be enabled for remote call control, a room must also have both a LineUri and a LineServerUri.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Unique identifier (similar to an email address) that allows the room to communicate using SIP devices such as Lync 2013. The SIP address must use the sip: prefix as well as a valid SIP domain; for example:</p>
<p>-SipAddress &quot;sip:room14@litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsMeetingRoom** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## Return Types

None. Instead, the **Set-CsMeetingRoom** cmdlet modifies existing instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## 另请参阅

#### 其他资源

[Disable-CsMeetingRoom](disable-csmeetingroom.md)  
[Enable-CsMeetingRoom](enable-csmeetingroom.md)  
[Get-CsMeetingRoom](get-csmeetingroom.md)  
[Move-CsMeetingRoom](Move-CsMeetingRoom.md)

