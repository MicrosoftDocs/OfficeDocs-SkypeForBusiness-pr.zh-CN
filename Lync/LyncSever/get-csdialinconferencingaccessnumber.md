---
title: Get-CsDialInConferencingAccessNumber
TOCTitle: Get-CsDialInConferencingAccessNumber
ms:assetid: f2c78377-ad21-4a9f-bef9-e9ef97316c85
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413015(v=OCS.15)
ms:contentKeyID: 49314715
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDialInConferencingAccessNumber

 

_**上一次修改主题：** 2015-03-09_

Returns information about all the dial-in conferencing access numbers configured for use in your organization. Dial-in conferencing provides a way for users to use a "regular" telephone mobile phone, or device on the public switched telephone network (PSTN) to join the audio portion of an online conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDialInConferencingAccessNumber [-Region <String>] <COMMON PARAMETERS>

    Get-CsDialInConferencingAccessNumber -EmptyRegion <SwitchParameter> <COMMON PARAMETERS>

    Get-CsDialInConferencingAccessNumber [-Identity <UserIdParameter>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the dial-in conferencing access numbers configured for use in the organization. Calling the **Get-CsDialInConferencingAccessNumber** cmdlet without any additional parameters always returns a collection of all the available dial-in access numbers.

    Get-CsDialInConferencingAccessNumber

## EXAMPLE 2

In Example 2, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is returned. Because identities must be unique, this command will never return more than one access number.

    Get-CsDialInConferencingAccessNumber -Identity sip:RedmondDialIn@litwareinc.com

## EXAMPLE 3

Example 3 uses the Region parameter to return all the dial-in conferencing access numbers associated with the Redmond region. To do this, the **Get-CsDialInConferencingAccessNumber** cmdlet is called along with the Region parameter. Specifying "Redmond" as the parameter value causes the **Get-CsDialInConferencingAccessNumber** cmdlet to return all the numbers where "Redmond" appears in the list of associated regions. For example, an access number that only listed Redmond as a region would be returned, as would an access number that listed both Redmond and Portland.

    Get-CsDialInConferencingAccessNumber -Region "Redmond"

## EXAMPLE 4

Example 4 returns all the dial-in conferencing access numbers that are not associated with a region (that is, where the Regions property is empty).

    Get-CsDialInConferencingAccessNumber -Region $Null

## EXAMPLE 5

The command shown in Example 5 returns all the dial-in conferencing access numbers for the Redmond region that have been scoped to the USA site (that is, the site with the SiteId site:USA).

    Get-CsDialInConferencingAccessNumber -Region site:USA/Redmond

## EXAMPLE 6

In Example 6, the Filter parameter is used in order to return a collection of all the dial-in conferencing access numbers that include the string value "Seattle" somewhere in their DisplayName. The filter value {DisplayName -like "\*Seattle\*"} limits the returned data to access numbers where the DisplayName includes the word "Seattle" (for example, Seattle Access Number; Dial-In Number for Seattle; Tacoma/Seattle Access Number; etc.).

    Get-CsDialInConferencingAccessNumber -Filter {DisplayName -like "*Seattle*"}

## EXAMPLE 7

Example 7 returns all the dial-in conferencing access numbers where the line Uri begins with tel:+1425; that effectively returns all the access numbers in the U.S. area code 425. To do this, the **Get-CsDialInConferencingAccessNumber** cmdlet is called along with the Filter parameter; the filter value {LineUri -like "tel:+1425\*"} limits the returned data to line Uris that begin with the string value "tel:+1425". To return all the phone numbers for area code 425 or for the area code 206, use this filter value:

{LineUri -like "tel:+1425\*" -or LineUri -like "tel:+1206\*"}

    Get-CsDialInConferencingAccessNumber -Filter {LineUri -like "tel:+1425*"}

## EXAMPLE 8

Example 8 returns a collection of all the dial-in conferencing access numbers where the primary language is set to Italian. To carry out this task, the **Get-CsDialInConferencingAccessNumber** cmdlet is first called in order to return a collection of all the access numbers configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those numbers where the PrimaryLanguage property is equal to Italian ("it-It").

    Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"}

## EXAMPLE 9

The command shown in Example 9 returns all the dial-in conferencing access numbers where French is listed as one of the secondary languages. To accomplish this task, the **Get-CsDialInConferencingAccessNumber** cmdlet is first called without any parameters; that returns a complete collection of the access numbers configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those numbers where the SecondaryLanguages property includes a listing for French (fr-FR).

    Get-CsDialInConferencingAccessNumber  | Where-Object {$_.SecondaryLanguages -contains "fr-FR"}

## Detailed Description

Dial-in conferencing enables users to use any kind of telephone (such as a standard "land line", a mobile phone, or a Voice over Internet Protocol (VoIP) phone) to join the audio portion of an online conference. This enables users to participate in the meeting even if they do not have a computer or an Internet connection. Users have full audio capabilities: they can speak to other participants and hear everything that takes place. However, they won’t be able to see shared slides, video feeds, or other visual elements.

In order to provide users with dial-in conferencing capabilities, you must create dial-in conferencing access numbers: phone numbers that users can call in order to be connected to a meeting. Dial-in conferencing access numbers are created by using the **New-CsDialInConferencingAccessNumber** cmdlet. When you create a new dial-in conferencing access number, you are actually creating a new contact object in Active Directory 域服务; this contact object is used to represent the access number and all its properties. Contact numbers can be retrieved by using the **Get-CsDialInConferencingAccessNumber** cmdlet.

If you have imported dial-in conferencing access numbers from Microsoft Office Communications Server 2007 these numbers will also be retrieved by running the **Get-CsDialInConferencingAccessNumber** cmdlet and including the Region parameter. (Imported numbers will not be displayed unless you use the Region parameter.) Note, however, that a warning message will be displayed alongside the imported number’s Uniform Resource Identifiers (URIs). This is simply the way the cmdlet handles imported dial-in conferencing access numbers.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDialInConferencingAccessNumber** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDialInConferencingAccessNumber"}

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
<td><p><em>EmptyRegion</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the dial plans that are associated with a region that is not associated with at least one dial-in conferencing access number. For example, suppose the Bellevue dial plan is associated with the Bellevue region, but no access numbers have been configured for the Bellevue region. The Bellevue region would thus be considered an empty region.</p>
<p>This parameter cannot be used in conjunction with any other parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the <strong>Get-CsDialInConferencingAccessNumber</strong> cmdlet under alternate credentials; this might be required if the account you used to log on to Windows does not have the necessary privileges required to work with contact objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve contact information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-mcs-001) or its fully qualified domain name (for example, atl-mcs-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on specific attributes for Lync Server. For example, you can limit returned data to dial-in conferencing numbers that have the string value &quot;Redmond&quot; in their display name, or toll-free dial-in conferencing numbers that use the 1-800 prefix.</p>
<p>The Filter parameter uses the same Windows PowerShell filtering syntax that is used by the <strong>Where-Object</strong> cmdlet. For example, a filter that returns only access numbers that have the 1-800 prefix would look like this: {LineUri -like &quot;tel:+1800*&quot;}, withLineUri representing the Active Directory attribute, -like representing the comparison operator, and &quot;tel:+1800*&quot; representing the filter value.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>SIP address of the dial-in conferencing access number (that is, the contact object that represents the number) to be retrieved. You must include the &quot;sip:&quot; prefix when specifying the Identity; for example: -Identity sip:RedmondDialIn@litwareinc.com.</p>
<p>If this parameter is not specified, then the <strong>Get-CsDialInConferencingAccessNumber</strong> cmdlet will return all the dial-in conferencing access numbers configured for use in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Enables you to return access numbers from a specific Active Directory organizational unit (OU). This includes data from both the specified OU and any of its child OUs. For example, if the Finance OU has two child OUs, AccountsPayable and AccountsReceivable, access number information will be returned from each of these three OUs.</p>
<p>When specifying an OU, use the distinguished name of that container; for example: -OU &quot;OU=Finance,dc=litwareinc,dc=com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Region</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns all the dial-in conferencing access numbers associated with the specified dial plan region. For example, to return all the dial-in numbers for the Northwest region, use this syntax: -Region Northwest.</p>
<p>You can also return access numbers that have been scoped to a particular site (or to the global scope) by including the scope in the parameter value. For example, to return access numbers that use the Northwest region, and that have been scoped to the Redmond site, use this syntax: -Region site:Redmond/Northwest. Note that, when referencing the site scope, you must use the SiteId property. You can retrieve SiteId values by using the <strong>Get-CsSite</strong> cmdlet.</p>
<p>To return a list of access numbers that are not associated with a dial plan, set the Region parameter value to $Null: -Region $Null.</p>
<p>Note that dial-in conferencing access numbers are only returned in order of their assigned priority if this parameter is specified. Priority order is the same order in which the numbers appear in meeting invitations and on the dial-in conferencing webpage. For details, see the <a href="set-csdialinconferencingaccessnumber.md">Set-CsDialInConferencingAccessNumber</a> cmdlet help topic.</p></td>
</tr>
<tr class="even">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by a command. For example, to return just seven access numbers (regardless of how many access numbers are in your forest), simply include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven items will be returned. If you set the ResultSize to 7 but you have only three access numbers in your forest, the command will return those three numbers and then complete without error.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. The **Get-CsDialInConferencingAccessNumber** cmdlet accepts a string value representing the Identity of the access number.

## Return Types

The **Get-CsDialInConferencingAccessNumber** cmdlet returns instances of the Microsoft.Rtc.Management.Xds.AccessNumber object.

## 另请参阅

#### 其他资源

[New-CsDialInConferencingAccessNumber](new-csdialinconferencingaccessnumber.md)  
[Remove-CsDialInConferencingAccessNumber](remove-csdialinconferencingaccessnumber.md)  
[Set-CsDialInConferencingAccessNumber](set-csdialinconferencingaccessnumber.md)

