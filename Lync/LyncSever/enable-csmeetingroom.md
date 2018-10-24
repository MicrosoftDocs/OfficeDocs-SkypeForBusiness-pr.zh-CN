---
title: Enable-CsMeetingRoom
TOCTitle: Enable-CsMeetingRoom
ms:assetid: 88af3267-80c5-46c0-aaef-135843b42a04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205062(v=OCS.15)
ms:contentKeyID: 49313493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsMeetingRoom

 

_**上一次修改主题：** 2015-09-22_

Enables a Lync Server 2013 meeting room. A meeting room is a conferencing device designed to address video conferencing and collaboration scenarios in small conference rooms. To enable a meeting room you must first create an Active Directory user account that will represent that system. Note that, although meeting room objects are based on user accounts, these objects will not show up when you run the **Get-CsUser** cmdlet. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Enable-CsMeetingRoom -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-HostingProviderProxyFqdn <Fqdn>] [-OriginatorSid <SecurityIdentifier>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-RegistrarPool <Fqdn>] [-SipAddress <String>] [-SipAddressType <FirstLastName | EmailAddress | UserPrincipalName | SAMAccountName | None>] [-SipDomain <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 enables the meeting room that has the Identity (in this case, the Active Directory display name) Redmond Meeting room. The new meeting room is homed on the Registrar pool arl-cs-001.litwareinc.com and given the SIP address sip:RedmondMeetingRoom@litwareinc.com.

    Enable-CsMeetingRoom -Identity "Redmond Meeting room" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Example 2

Example 2 enables all the meeting rooms found in the MeetingsRoom OU. (In other words, this command enables all the user accounts in the MeetingsRoom OU.) To do this, the command first calls the **Get-CsAdUser** cmdlet along with the OU parameter; the parameter value "OU=MeetingRooms,dc=litwareinc,dc=com" limits returned data to user accounts found in the MeetingRooms OU. Those accounts are then piped to the **Enable-CsMeetingRoom** cmdlet, which takes each account in the collection and enables that account as a meeting room. Each new meeting rooms will be home on the Registrar pool atl-cs-001.litwareinc.com and will have a SIP address composed of the account's SamAccountName parameter (for example, room14) and the SIP domain litwareinc.com.

    Get-CsAdUser -OU "OU=MeetingRooms,dc=litwareinc,dc=com" | Enable-CsMeetingRoom -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddressType "SamAccountName" -SipDomain "litwareinc.com"

## Detailed Description

In Lync Server, meeting rooms are self-contained computer appliances that are installed in conference rooms and supply advanced meeting capabilities such as:

  - One touch meeting join experience

  - Multi-view video gallery

  - Touch-enabled white-boarding on the front of room screen

  - Calendar integration to provide access to scheduled meetings

  - Content sharing and switching

In order to manage these new endpoint devices you must, among other things, create and enable a Microsoft Exchange Server 2013 resource mailbox account for the device, then enable that resource account for Lync Server 2013. Note that, for Lync Server, there are no cmdlets for creating or removing meeting rooms. Instead, you use the **Enable-CsMeetingRoom** cmdlet to enable meeting rooms and the [Disable-CsMeetingRoom](disable-csmeetingroom.md) cmdlet to disable meeting rooms. The resource account must already exist in order for you to enable the meeting room, and disabling a meeting room only removes that room from your collection of meeting rooms; it does not delete the resource mailbox account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Enable-CsMeetingRoom"}

**Lync Server 控制面板:** The functions carried out by the **Enable-CsMeetingRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Indicates the Identity of the user account to be configured as a meeting room. Identities are typically specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\room14); and, 4) the user's Active Directory display name (for example, Room 14).</p>
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
<td><p>Enables you to connect to the specified domain controller in order to enable a meeting room. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>HostingProviderProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the hosting provider proxy server. This parameter is used only with Microsoft Lync Online.</p></td>
</tr>
<tr class="odd">
<td><p><em>OriginatorSid</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Security.Principal.SecurityIdentifier</p></td>
<td><p>Value of the msRTCSIP-OriginatorSID attribute. This Active Directory attribute is used to enable single sign-on. This parameter is used only with Microsoft Lync Online.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a meeting room object through the pipeline that represents the meeting room being enabled for Lync Server. By default, the <strong>Enable-CsMeetingRoom</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Proxy pool name. This parameter is used only with Microsoft Lync Online.</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Indicates the Registrar pool where the meeting room's Lync Server account will be homed.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to assign the meeting room a specific SIP address. When specifying the SIP address, preface the address with &quot;sip:&quot;. That means the value supplied to the SipAddress parameter should look something like this :</p>
<p>sip:room14@litwareinc.com</p>
<p>The SipAddress parameter should not be used if you use the SipAddressType parameter in order to have Lync Server automatically generate a SIP address for the meeting room.</p>
<p>The SipAddress parameter cannot be used if you are attempting to enable multiple meeting rooms at the same time. Instead, you must auto-generate SIP address for those rooms by using the SipAddressType parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddressType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.Cmdlets.AddressType</p></td>
<td><p>Instructs Lync Server to auto-generate a SIP address for the new meeting room. In order to have Lync Server auto-generate the SIP address, you must include the SipAddressType parameter and use one of the following parameter values:</p>
<p>* FirstLastName. The SIP address is the user's first name and a period followed by the user's last name and the SIP domain. For example, the user Room 14 would have a SIP address similar to this: Room.14@litwareinc.com. If you use this address type then you must also include the SipDomain parameter.</p>
<p>* EmailAddress. The user's email address (as defined in Active Directory) is used as the SIP address.</p>
<p>UserPrincipalName. The user's UPN is used as the SIP address.</p>
<p></p>
<p>* SamAccountName. The SIP address is the user's SamAccountName (logon name) followed by the SIP domain. For example, the user with the SamAccountName room14 will have a SIP address similar to this: room14@litwareinc.com. If you use this address type then you must also include the SipDomain parameter.</p>
<p>The SipAddressType parameter is not required if you use the SIPAddress parameter and explicitly assign the user a SIP address.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipDomain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The SIP domain for the meeting room being enabled. This parameter is required if you use the SIPAddressType parameter to have Lync Server auto-generate a SIP address for the user and you based SIP addresses on the SamAccountName or the user’s first name and last name. This parameter is not required if you base SIP addresses on the user’s email address or UPN; that’s because the domain name is already included in those attribute values.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Enable-CsMeetingRoom** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

The **Enable-CsMeetingRoom** cmdlet creates new instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADMeetingRoom object.

## 另请参阅

#### 其他资源

[Disable-CsMeetingRoom](disable-csmeetingroom.md)  
[Get-CsMeetingRoom](get-csmeetingroom.md)  
[Move-CsMeetingRoom](Move-CsMeetingRoom.md)  
[Set-CsMeetingRoom](set-csmeetingroom.md)

