---
title: Set-CsDialInConferencingAccessNumber
TOCTitle: Set-CsDialInConferencingAccessNumber
ms:assetid: 2b640607-ee83-4962-865d-ed74ddd17649
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425770(v=OCS.15)
ms:contentKeyID: 49312338
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsDialInConferencingAccessNumber

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values of an existing dial-in conferencing access number. Dial-in conferencing provides a way for users to use a "regular" telephone, mobile phone or other device on the public switched telephone network (PSTN) to join the audio portion of a conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsDialInConferencingAccessNumber -Identity <UserIdParameter> [-DisplayName <String>] [-DisplayNumber <String>] [-LineUri <String>] [-PrimaryLanguage <String>] [-Regions <MultiValuedProperty>] [-ScopeToGlobal <SwitchParameter>] [-ScopeToSite <SwitchParameter>] [-SecondaryLanguages <MultiValuedProperty>] <COMMON PARAMETERS>

    Set-CsDialInConferencingAccessNumber -Identity <UserIdParameter> -Priority <Int32> -ReorderedRegion <String> <COMMON PARAMETERS>

    Set-CsDialInConferencingAccessNumber -Instance <AccessNumber> [-ScopeToGlobal <SwitchParameter>] [-ScopeToSite <SwitchParameter>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number".

    Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"

## EXAMPLE 2

In Example 2, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.

    Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"

## EXAMPLE 3

In Example 3, all the dial-in conferencing access numbers where the primary language is French are modified to use French Canadian as the secondary language. To carry out this task, the **Get-CsDialInConferencingAccessNumber** cmdlet is first called to return a collection of all the dial-in access numbers configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out the access numbers where the PrimaryLanguage property is equal to French ("fr-FR"). This filtered collection is then piped to the **Set-CsDialInConferencingAccessNumber** cmdlet, which sets the value of the SecondaryLanguages property to French Canadian ("fr-CA").

    Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "fr-FR"}| Set-CsDialInConferencingAccessNumber -SecondaryLanguages "fr-CA"

## EXAMPLE 4

The command shown in Example 4 changes the Active Directory display name for the specified dial-in conferencing access number. To do this, the command first uses the **Get-CsDialInConferencingAccessNumber** cmdlet and the Filter parameter to return the dial-in access number where the DisplayName property is equal to "Default DialIn Access Number". That access number is then piped to the **Set-CsDialInConferencingAccessNumber** cmdlet, which changes the display name to Litwareinc Conferencing.

    Get-CsDialInConferencingAccessNumber -Filter {DisplayName -eq "Default DialIn Access Number"} | Set-CsDialInConferencingAccessNumber -DisplayName "Litwareinc Conferencing"

## EXAMPLE 5

In Example 5, both the display number and the line Uniform Resource Identifier (URI) are modified for the specified dial-in conferencing access number. To retrieve the number to be modified, the command first uses the **Get-CsDialInConferencingAccessNumber** cmdlet and the Filter parameter; the accompanying filter value limits the returned data to the access number where the LineUri property is equal to TEL:+14255558715. That access number is then piped to the **Set-CsDialInConferencingAccessNumber** cmdlet, which modifies both the DisplayNumber and LineUri properties of the access number.

    Get-CsDialInConferencingAccessNumber -Filter {LineUri -eq "TEL:+14255558715"} | Set-CsDialInConferencingAccessNumber -DisplayNumber "1-425-555-1298" -LineUri "tel:+14255551298"

## EXAMPLE 6

Example 6 assigns a pair of secondary languages to all the dial-in conferencing access numbers that do not use U.S. English as their primary language. To do this, the command first calls the **Get-CsDialInConferencingAccessNumber** cmdlet to return a collection of all the dial-in conferencing access numbers configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which selects only those numbers where the PrimaryLanguage property is not equal to U.S. English (en-US). The filtered collection is then piped to the **Set-CsDialInConferencingAccessNumber** cmdlet, which uses the -SecondaryLanguages parameter to assign each number in the collection the secondary languages French (fr-FR) and Italian (it-IT).

    Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -ne "en-US"} | Set-CsDialInConferencingAccessNumber -SecondaryLanguages "fr-FR","it-IT"

## EXAMPLE 7

The command shown in Example 7 assigns the dial-in conferencing access number "sip:RedmondDialIn@litwareinc.com" the highest priority in the Redmond region; that results in the number being listed first in meeting invitations and on the dial-in conferencing webpage. To set the priority, the Priority parameter is included along with the parameter value 0. (The highest priority access number has a Priority value of 0, the second-highest priority number has a Priority value of 1, and so on.) In addition, the ReorderedRegion parameter is included to indicate that access number priorities are to be changed within the Redmond region.

    Get-CsDialInConferencingAccessNumber -Identity ""sip:RedmondDialIn@litwareinc.com"" -Priority 0 -ReorderedRegion Redmond

## Detailed Description

Dial-in conferencing enables users to use any kind of telephone (for example, a standard "land line," a mobile phone, or a Voice over Internet Protocol (VoIP) phone) to join the audio portion of a conference. This enables users to participate in the meeting even if they do not have a computer or an Internet connection. Dial-in users have full audio capabilities: they can speak to other participants and hear everything that takes place; they just aren’t able to see shared slides, video feeds, or other visual elements.

In order to provide users with dial-in conferencing capabilities, you must create dial-in conferencing access numbers: phone numbers users can call in order to be connected to a meeting. Dial-in conferencing access numbers are created by using the **New-CsDialInConferencingAccessNumber** cmdlet. When you create a new dial-in conferencing access number, you actually create a new contact object in Active Directory 域服务. This contact object is used to represent the access number and all its properties.

After a dial-in conferencing number has been created, you can use the **Set-CsDialInConferencingAccessNumber** cmdlet to modify the properties of that number. For example, you can change such things as the phone number (LineUri) itself or the display name for the contact object that represents that number. In addition, the **Set-CsDialInConferencingAccessNumber** cmdlet enables you to modify the scope of the number; for example, you can use this cmdlet to take a number that has been assigned to the global scope and reassign it to the site scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsDialInConferencingAccessNumber** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsDialInConferencingAccessNumber"}

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
<td><p>SIP address of the contact object that represents the dial-in conferencing number. When specifying the Identity you must include the &quot;sip:&quot; prefix; for example: -Identity &quot; sip:RedmondDialIn@litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.AccessNumber</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Enables you to change the order in which dial-in conferencing numbers are presented to users in meeting invitations or when they access the Dial-In Conferencing Settings webpage. Lower numbers are given a higher priority; to have a number appear at the beginning of the list set the priority to 0. Note that if you change the priority of a given number you must also use the ReorderedRegion parameter to indicate the region where the modified priority should take effect.</p></td>
</tr>
<tr class="even">
<td><p><em>ReorderedRegion</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Used with the Priority parameter when changing the priority of a dial-in conferencing number with a region. The ReorderedRegion parameter indicates the region where the priority reordering is to take place; for example: -ReorderedRegion &quot;Redmond&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Active Directory display name for the new contact object. This is the name that will also be displayed in Lync.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Phone number as displayed in meeting invitations and on the Dial-in Conferencing Settings webpage. The DisplayNumber can be formatted any way you prefer; for example 1-800-555-1234; 1-(800)-555-1234; or 1.800.555.1234.</p></td>
</tr>
<tr class="even">
<td><p><em>LineUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The actual dial-in conferencing phone number. The LineUri must be specified by using the following syntax: the tel: prefix followed by a plus sign (+) followed by the country/region calling code, area code, and phone number. For example: tel:+18005551234. Spaces, hyphens, parentheses and other characters are not allowed.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a contact object through the pipeline that represents the modified dial-in conferencing access number. By default, the <strong>Set-CsDialInConferencingAccessNumber</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="even">
<td><p><em>PrimaryLanguage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Primary language used for making dial-in conferencing announcements. The language must be configured by using one of the available dial-in conferencing language codes; for example, en-US for U.S. English or fr-FR for French. To return a list of the available language codes, type the following command at the Windows PowerShell prompt:</p>
<p>Get-CsDialInConferencingLanguageList | Select-Object -ExpandProperty Languages.</p></td>
</tr>
<tr class="odd">
<td><p><em>Regions</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>Dial plan regions associated with the dial-in number. If a region is not included in at least one dial plan, then it cannot be associated with a dial-in conferencing access number. To specify multiple regions, use a comma-separated list: -Regions &quot;Northwest&quot;, &quot;Southwest&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ScopeToGlobal</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, the dial-in conferencing number will be assigned to the global scope.</p></td>
</tr>
<tr class="odd">
<td><p><em>ScopeToSite</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, the dial-in conferencing number will be scoped to the site where the contact object’s Registrar pool resides.</p></td>
</tr>
<tr class="even">
<td><p><em>SecondaryLanguages</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.MultiValuedProperty</p></td>
<td><p>Optional collection of languages that can also be used for making dial-in conferencing announcements. Secondary languages must be configured as a comma-separated list of language codes; for example, the following syntax sets French Canadian and French as secondary languages; -SecondaryLanguages &quot;fr-CA&quot;, &quot;fr-FR&quot;.</p>
<p>An access number can be associated with as many as four secondary languages.</p></td>
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

Microsoft.Rtc.Management.Xds.AccessNumber object. The **Set-CsDialInConferencingAccessNumber** cmdlet accepts pipelined input of the access number object.

## Return Types

The **Set-CsDialInConferencingAccessNumber** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.Xds.AccessNumber object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingAccessNumber](get-csdialinconferencingaccessnumber.md)  
[New-CsDialInConferencingAccessNumber](new-csdialinconferencingaccessnumber.md)  
[Remove-CsDialInConferencingAccessNumber](remove-csdialinconferencingaccessnumber.md)

