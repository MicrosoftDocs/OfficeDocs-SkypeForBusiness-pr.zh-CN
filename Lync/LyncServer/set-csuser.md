---
title: Set-CsUser
TOCTitle: Set-CsUser
ms:assetid: 6c452df7-75c9-4d94-86bc-4990d718ffe9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398510(v=OCS.15)
ms:contentKeyID: 49313155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUser

 

_**上一次修改主题：** 2015-03-09_

Modifies Lync Server properties for an existing user account. Properties can be modified only for accounts that have been enabled for use with Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUser -Identity <UserIdParameter> [-AcpInfo <MultiValuedProperty>] [-AudioVideoDisabled <$true | $false>] [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Enabled <$true | $false>] [-EnterpriseVoiceEnabled <$true | $false>] [-ExchangeArchivingPolicy <Uninitialized | UseLyncArchivingPolicy | NoArchiving | ArchivingToExchange>] [-HostedVoiceMail <$true | $false>] [-LineServerURI <String>] [-LineURI <String>] [-PassThru <SwitchParameter>] [-PrivateLine <String>] [-RemoteCallControlTelephonyEnabled <$true | $false>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Set-CsUser** cmdlet is used to modify the user account with the Identity Pilar Ackerman. In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP. This task is carried out by adding the EnterpriseVoiceEnabled parameter, and then setting the parameter value to $True.

    Set-CsUser -Identity "Pilar Ackerman" -EnterpriseVoiceEnabled $True

## EXAMPLE 2

In Example 2, all the users in the Finance department have their accounts enabled for Enterprise Voice. In this command, the **Get-CsUser** cmdlet and the LdapFilter parameter are first used to return a collection of all the users who work in the Finance department. That information is then piped to the **Set-CsUser** cmdlet, which enables Enterprise Voice for each account in the collection.

    Get-CsUser -LdapFilter "Department=Finance" | Set-CsUser -EnterpriseVoiceEnabled $True

## Detailed Description

The **Set-CsUser** cmdlet enables you to modify the Lync Server-related user account attributes that are stored in Active Directory 域服务. For example, you can disable or re-enable a user for Lync Server; enable or disable a user for audio/video (A/V) communications; or modify a user’s private line and line URI numbers. The **Set-CsUser** cmdlet can be used only for users who have been enabled for Lync Server.

The only attributes you can modify using the **Set-CsUser** cmdlet are attributes related to Lync Server. Other user account attributes, such as the user’s job title or department, cannot be modified by using this cmdlet. Keep in mind, however, that the Lync Server attributes should only be modified by using the Set-CsUser cmdlet or the Lync Server Control Panel. You should not attempt to manually configure these attributes.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUser** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUser\\b"}

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
<td><p>Indicates the Identity of the user account to be modified. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be referenced by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the display name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>AcpInfo</em></p></td>
<td><p>Optional</p></td>
<td><p>MultiValuedProperty</p></td>
<td><p>Enables you to assign one or more third-party audio conferencing providers to a user. However, it is recommended that you use the <strong>Set-UserAcp</strong> cmdlet to assign Audio conferencing providers.</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioVideoDisabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the user is allowed to make audio/visual (A/V) calls by using Lync. If set to True, the user will largely be restricted to sending and receiving instant messages.</p>
<p>You cannot disable A/V communications if a user is currently enabled for remote call control, Enterprise Voice, and/or Internet Protocol private branch exchange (IP-PBX) soft phone routing.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Fqdn</p></td>
<td><p>Enables you to specify a domain controller to connect to when modifying a user account. If this parameter is not included then the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether or not the user has been enabled for Lync Server. If you set this value to False, the user will no longer be able to log on to Lync Server; setting this value to True re-enables the user's logon privileges.</p>
<p>If you disable an account by using the Enabled parameter, the information associated with that account (including assigned policies and whether or not the user is enabled for Enterprise Voice and/or remote call control) is retained. If you later re-enable the account by using the Enabled parameter, the associated account information will be restored. This differs from using the <strong>Disable-CsUser</strong> cmdlet to disable a user account. When you run the <strong>Disable-CsUser</strong> cmdlet, all the Lync Server data associated with that account is deleted.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnterpriseVoiceEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the user has been enabled for Enterprise Voice, which is the Microsoft implementation of Voice over Internet Protocol (VoIP). With Enterprise Voice, users can make telephone calls using the Internet rather than using the standard telephone network.</p></td>
</tr>
<tr class="even">
<td><p><em>ExchangeArchivingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>ExchangeArchivingPolicyOptionsEnum</p></td>
<td><p>Indicates where the user's instant messaging sessions are archived. Allowed values are:</p>
<p>* Uninitialized</p>
<p>* UseLyncArchivingPolicy</p>
<p>* ArchivingToExchange</p>
<p>* NoArchiving</p></td>
</tr>
<tr class="odd">
<td><p><em>HostedVoiceMail</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, enables a user’s voice mail calls to be routed to a hosted version of Microsoft Exchange Server. In addition, setting this option to True enables Lync users to directly place a call to another user’s voice mail.</p></td>
</tr>
<tr class="even">
<td><p><em>LineServerURI</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>The URI of the remote call control telephone gateway assigned to the user. The LineServerUri is the gateway URI, prefaced by &quot;sip:&quot;. For example: sip:rccgateway@litwareinc.com</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Phone number assigned to the user. The line Uniform Resource Identifier (URI) must be specified using the E.164 format and use the &quot;TEL:&quot; prefix. For example: TEL:+14255551297. Any extension number should be added to the end of the line URI, for example: TEL:+14255551297;ext=51297.</p>
<p>It is important to note that Lync Server treats TEL:+14255551297 and TEL:+14255551297;ext=51297 as two different numbers. If you assign Ken Myer the line URI TEL:+14255551297 and later try to assign Pilar Ackerman the line URI TEL:+14255551297;ext=51297, that assignment will succeed; the number assigned to Pilar will not be flagged as a duplicate number. This is due to the fact that, depending on your setup, those two numbers could actually be different. For example, in some organizations dialing 1-425-555-1297 routes your call to an Exchange Auto Attendant. Conversely, dialing just the extension (51297) or using Lync to dial the number 1-425-555-1297 extension 51297 will route your call directly to the user.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user whose account is being modified. By default, the <strong>Set-CsUser</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrivateLine</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Phone number for the user's private telephone line. A private line is a phone number that is not published in Active Directory 域服务 and, as a result, is not readily available to other people. In addition, this private line bypasses most in-bound call routing rules; for example, a call to a private line will not be forwarded to a person's delegates. Private lines are often used for personal phone calls or for business calls that should be kept separate from other team members.</p>
<p>The private line value should be specified using the E.164 format, and be prefixed by the &quot;TEL:&quot; prefix. For example: TEL:+14255551297.</p></td>
</tr>
<tr class="even">
<td><p><em>RemoteCallControlTelephonyEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>Indicates whether the user has been enabled for remote call control telephony. When enabled for remote call control, a user can employ Lync Server to answer phone calls made to his or her desk phone. Phone calls can also be made using Lync. These calls all rely on the standard telephone network, also known as the public switched telephone network (PSTN). To make and receive phone calls over the Internet, the user must be enabled for Enterprise Voice. For details, see the parameter EnterpriseVoiceEnabled.</p>
<p>To be enabled for remote call control, a user must have both a LineUri and a LineServerUri.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Unique identifier (similar to an email address) that allows the user to communicate using SIP devices such as Lync. The SIP address must use the sip: prefix as well as a valid SIP domain; for example: -SipAddress sip:kenmyer@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Set-CsUser** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

The **Set-CsUser** cmdlet does not return any objects.

## 另请参阅

#### 其他资源

[Disable-CsUser](disable-csuser.md)  
[Enable-CsUser](enable-csuser.md)  
[Get-CsUser](get-csuser.md)  
[Move-CsUser](move-csuser.md)

