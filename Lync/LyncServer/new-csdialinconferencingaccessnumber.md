---
title: New-CsDialInConferencingAccessNumber
TOCTitle: New-CsDialInConferencingAccessNumber
ms:assetid: c6d0536c-0ba3-45e0-affe-7ee00a070435
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398818(v=OCS.15)
ms:contentKeyID: 49314194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDialInConferencingAccessNumber

 

_**上一次修改主题：** 2015-03-09_

Creates a new dial-in conferencing access number. Dial-in conferencing provides a way for users to use a "regular" telephone, cell phone or other device on the public switched telephone network (PSTN) to join the audio portion of a conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDialInConferencingAccessNumber -Pool <Fqdn> -Regions <MultiValuedProperty> <COMMON PARAMETERS>

    New-CsDialInConferencingAccessNumber -HostingProviderProxyFqdn <Fqdn> <COMMON PARAMETERS>

    COMMON PARAMETERS: -DisplayNumber <String> -LineURI <String> -PrimaryLanguage <String> -PrimaryUri <String> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-PassThru <SwitchParameter>] [-ScopeToSite <SwitchParameter>] [-SecondaryLanguages <MultiValuedProperty>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new dial-in conferencing access number with the primary URI sip:RedmondDialIn@litwareinc.com. In addition to the PrimaryUri parameter, the command also includes parameters that configure the telephone number as displayed in Lync (DisplayNumber); the telephone number in the E.164 format (LineUri); the Registrar pool the new number is assigned to (-Pool): the primary language for the number (PrimaryLanguage); and the region the new number is assigned to (Regions).

    New-CsDialInConferencingAccessNumber -PrimaryUri "sip:RedmondDialIn@litwareinc.com" -DisplayNumber "1-800-555-1234" -LineUri "tel:+18005551234" -Pool atl-cs-001.litwareinc.com -PrimaryLanguage "en-US" -Regions "Redmond"

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1; the only difference is that the command shown in this example also assigns two secondary languages (French Canadian and French) to the new dial-in conferencing access number. To assign these secondary languages, the SecondaryLanguages parameter is included, along with a comma-separated list of the languages to be assigned (fr-CA and fr-FR).

    New-CsDialInConferencingAccessNumber -PrimaryUri "sip:RedmondDialIn@litwareinc.com" -DisplayNumber "1-800-555-1234" -LineUri "tel:+18005551234" -Pool atl-cs-001.litwareinc.com -PrimaryLanguage "en-US" -Regions "Redmond" -SecondaryLanguages "fr-CA", "fr-FR"

## EXAMPLE 3

Example 3 creates a new dial-in conferencing access number that is scoped to the site where the contact object’s home pool is located. To do this, the command includes the parameter ScopeToSite.

    New-CsDialInConferencingAccessNumber -PrimaryUri "sip:RedmondDialIn@litwareinc.com" -DisplayNumber "1-800-555-1234" -LineUri "tel:+18005551234" -Pool atl-cs-001.litwareinc.com -PrimaryLanguage "en-US" -Regions "Redmond" -ScopeToSite

## Detailed Description

Dial-in conferencing enables users to use any kind of telephone (such as standard "land line," a mobile phone, or a Voice over Internet Protocol (VoIP) phone) to join the audio portion of an online conference. This enables users to participate in the meeting even if they do not have a computer or an Internet connection. Users have full audio capabilities: they can speak to other participants and hear everything that takes place. They just aren’t able to see shared slides, video feeds, or other visual elements.

In order to provide users with dial-in conferencing capabilities, you must create dial-in conferencing access numbers: phone numbers users can call in order to be connected to a meeting. Dial-in conferencing access numbers are created by using the **New-CsDialInConferencingAccessNumber** cmdlet. When you create a new dial-in conferencing access number, you actually create a new contact object in Active Directory 域服务; this contact object is used to represent the access number and all its properties.

When creating a new dial-in number you must include the following parameters: PrimaryUri; LineURI; Pool; DisplayNumber; PrimaryLanguage; and Regions. All of these parameters (and their parameter values) are reasonably straightforward, with perhaps one exception: Regions. When you create a new access number, that number must be associated with one or more regions. In turn, a region cannot be associated with a dial-in conferencing number unless that region appears in at least one dial plan. If a region appears in the DialInConferencingRegion property of at least one dial plan, then it can be associated with an access number. If not, then the region cannot be associated with an access number. That simply means you must first create a dial plan, and specify a region for that dial plan, before you can create a dial-in conferencing access number.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDialInConferencingAccessNumber** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDialInConferencingAccessNumber"}

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
<td><p><em>DisplayNumber</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Phone number as displayed in meeting invitations and on the dial-in conferencing webpage. The DisplayNumber can be formatted any way you prefer; for example 1-800-555-1234; 1-(800)-555-1234; or 1.800.555.1234.</p></td>
</tr>
<tr class="even">
<td><p><em>HostingProviderProxyFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the hosting provider that hosts your dial-in conferencing service.</p></td>
</tr>
<tr class="odd">
<td><p><em>LineURI</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The actual dial-in conferencing phone number. The LineURI must be specified using the following syntax: the tel: prefix followed by a plus sign (+) followed by the country/region calling code, area code, and phone number. For example: tel:+18005551234. Note that spaces, hyphens, parentheses and other characters are not allowed.</p>
<p>LineURIs must be unique throughout Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><em>Pool</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Home pool for the new contact object.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrimaryLanguage</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Primary language used for making dial-in conferencing announcements. The language must be configured using one of the available dial-in conferencing language codes; for example, en-US for U.S. English; fr-FR for French; etc. To return a list of the available language codes, type the following command at the Windows PowerShell prompt:</p>
<p>Get-CsDialInConferencingLanguageList | Select-Object -ExpandProperty Languages.</p></td>
</tr>
<tr class="even">
<td><p><em>PrimaryUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Unique SIP address to be assigned to the new contact object. When specifying the PrimaryUri you must include the &quot;sip:&quot; prefix. For example: -PrimaryUri &quot;sip:RedmondDialIn@litwareinc.com&quot;. Note that the sip: prefix must be entered in all lowercase letters.</p></td>
</tr>
<tr class="odd">
<td><p><em>Regions</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>Dial plan regions associated with the dial-in number. If a region is not included in at least one dial plan, then it cannot be associated with a dial-in conferencing access number. To specify multiple regions, use a comma-separated list: -Regions &quot;Northwest&quot;, &quot;Southwest&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Active Directory display name for the new contact object. This is the name that will also be displayed in Lync.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a contact object through the pipeline that represents the new dial-in conferencing access number. By default, the <strong>New-CsDialInConferencingAccessNumber</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>ScopeToSite</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, the new number will be scoped to the same site as the contact object’s home pool. If the ScopeToSite parameter is not included, the new number will be assigned to the global scope.</p></td>
</tr>
<tr class="even">
<td><p><em>SecondaryLanguages</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>Optional collection of languages that can also be used for making dial-in conferencing announcements. Secondary languages must be configured as a comma-separated list of language codes; for example, the following syntax sets French Canadian and French as secondary languages; -SecondaryLanguages &quot;fr-CA&quot;, &quot;fr-FR&quot;.</p>
<p>A single access number can have as many as four secondary languages.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new dial-in conferencing access number is being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

None. The **New-CsDialInConferencingAccessNumber** cmdlet does not accept pipelined input.

## Return Types

The **New-CsDialInConferencingAccessNumber** cmdlet creates new instances of the Microsoft.Rtc.Management.Xds.AccessNumber object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingAccessNumber](get-csdialinconferencingaccessnumber.md)  
[Remove-CsDialInConferencingAccessNumber](remove-csdialinconferencingaccessnumber.md)  
[Set-CsDialInConferencingAccessNumber](set-csdialinconferencingaccessnumber.md)

