---
title: Set-CsUserAcp
TOCTitle: Set-CsUserAcp
ms:assetid: f3138d9f-fa3e-4a3c-aa8e-f6dbdda8a834
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413018(v=OCS.15)
ms:contentKeyID: 49314726
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUserAcp

 

_**上一次修改主题：** 2015-03-09_

Adds a new audio conferencing provider to a user or group of users, or modifies an existing audio conferencing provider already assigned to a user. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUserAcp -Identity <UserIdParameter> -Domain <String> -Name <String> -ParticipantPasscode <String> -TollNumber <String> [-Confirm [<SwitchParameter>]] [-IsDefault <$true | $false>] [-PassThru <SwitchParameter>] [-TollFreeNumbers <String[]>] [-Url <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Set-CsUserAcp** cmdlet is used to assign a new audio conferencing provider to the user Ken Myer. To do this, the Identity parameter is used to indicate the user account to be modified. In addition, the required parameters TollNumber, ParticipantPassCode, Domain, and Name are included, along with the appropriate parameter values.

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

## EXAMPLE 2

The command shown in Example 2 assigns the same audio conferencing provider to all the users who work in the Finance department. To do this, the command first uses the **Get-CsUser** cmdlet and the LdapFilter (with the filter value "Department=Finance") to return a collection of all the users who work in the Finance department. This collection is then piped to the **Set-CsUserAcp** cmdlet, which assigns the same audio conferencing provider (Fabrikam ACP) to each user in the collection.

    Get-CsUser -LdapFilter "Department=Finance" | Set-CsUserAcp -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

## EXAMPLE 3

Example 3 assigns the Fabrikam ACP audio conferencing provider to the user Ken Myer. In addition to specifying the TollNumber, ParticipantPassCode, Domain, and Name, this command also includes a pair of toll-free phone numbers. To assign these two values, include the TollFreeNumbers parameter followed by the two phone numbers, separated from one another by a comma.

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP" -TollFreeNumbers "18005551010", "18005551020"

## Detailed Description

An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers offer a way for users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often include high-end services such as live translation, transcription, and live per-conference operator assistance.

Lync Server does not allow for complete integration with audio conferencing providers. The **CsUserAcp** cmdlets enable administrators to set a phone number and passcode, and to configure other information that can be used for audio conferencing provider integration any time a user schedules a meeting. However, because these cmdlets were not designed for the on-premises version of Lync Server (instead, they are only intended for use with Lync Online) no additional audio conferencing provider integration is provided beyond assigning property values.

Audio conferencing providers can be assigned to a user account by using the **Set-CsUserAcp** cmdlet. (Note that a user can be assigned multiple audio conferencing providers.) The **Set-CsUserAcp** cmdlet is also used to modify the properties of an existing audio conferencing provider. If you call the **Set-CsUserAcp** cmdlet, the cmdlet uses the parameter information included in the call to check the existing audio conferencing providers assigned to the user. If a match is found, then the existing provider is modified. For example, supposed you issue the following command:

Set-CsUserAcp –Identity "Ken Myer" –TollNumber "15554251298" –ParticipantPassCode 13761 –Domain "fabrikam.com" –Name "Fabrikam ACP"

Further suppose that Ken Myer has already been assigned an audio conferencing provider named Fabrikam ACP that has the same TollNumber and Domain as those specified in the command. (In other words, the only difference is the ParticipantPassCode,) In that case, the **Set-CsUserAcp** cmdlet will modify the existing Fabrikam ACP provider. If a match is not found, then a new provider will be added to Ken Myer’s user account.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUserAcp** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUserAcp"}

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
<td><p><em>Domain</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Domain name of the audio conferencing provider. For example: -Domain &quot;fabrikam.com&quot;.</p>
<p>The domain name will be given to you by the audio conferencing provider.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account to be modified. You can specify a user's identity using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory 域服务 display name (for example, Ken Myer). User identities can also be referenced by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users with a display name that ends in the string value &quot;Smith&quot;.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the audio conferencing provider. For example: -Name &quot;Fabrikam Conference Services&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>ParticipantPasscode</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Passcode required when connecting to a conference by using the audio conferencing provider. For example: -PassCode &quot;0712&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>TollNumber</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Non-toll-free phone number used for audio conferences. For example: -TollNumber &quot;14255551298&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>IsDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not this is the default audio conferencing provider for the user. Each user can only have one default provider.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass an object through the pipeline that represents the user whose account properties are being configured. The PassThru parameter is required in such cases because, by default, the <strong>Set-CsUserAcp</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>TollFreeNumbers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Collection of toll-free phone number used for audio conferences. For example: -TollFreeNumbers &quot;18005551298&quot;. To add multiple toll-free numbers, separate the individual numbers by using commas: -TollFreeNumber &quot;18005551298&quot;, &quot;18005559876&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Url</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Web URL for the audio conferencing provider; for example: -Url &quot;http://acp.fabrikam.com&quot;. The web URL enables audio conferencing providers to point users to a webpage containing additional dial-in phone numbers, as well as information about the services offered by the audio conferencing provider.</p></td>
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

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Set-CsUserAcp** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsUserAcp](get-csuseracp.md)  
[Remove-CsUserAcp](remove-csuseracp.md)

