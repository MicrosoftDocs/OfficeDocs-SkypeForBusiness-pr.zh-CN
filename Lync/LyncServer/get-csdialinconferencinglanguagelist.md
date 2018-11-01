---
title: Get-CsDialInConferencingLanguageList
TOCTitle: Get-CsDialInConferencingLanguageList
ms:assetid: 39355144-c8de-4ad3-9568-6426d3b97ccb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425869(v=OCS.15)
ms:contentKeyID: 49312546
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsDialInConferencingLanguageList

 

_**上一次修改主题：** 2015-03-09_

Returns a list of languages, including regional/minority languages, supported for use with Lync Server dial-in conferences. These languages are used to relay audio messages and instructions to users participating in a conference by using a telephone. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsDialInConferencingLanguageList [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsDialInConferencingLanguageList [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 demonstrates how you can query the **Get-CsDialInConferencingLanguageList** cmdlet to see if a particular language appears in the list of supported languages. In this example, the **Get-CsDialInConferencingLanguageList** cmdlet is called in order to return information about all the supported languages; the Windows PowerShell operator -contains is then used to see if the language code "en-US" is contained within that list of supported languages. If it is, the **Get-CsDialInConferencingLanguageList** cmdlet will report back the value "True". If "en-US" cannot be found in the list of supported languages, then the cmdlet will report back the value "False".

    (Get-CsDialInConferencingLanguageList).Languages -contains "en-US"

## EXAMPLE 2

The command shown in Example 2 returns the complete list of supported languages. The DialInConferencingLanguageList object stores this information in the Languages property. In order to display each language on the screen, this command first uses the **Get-CsDialInConferencingLanguageList** cmdlet to return a collection of all the language lists and their properties. This call to the **Get-CsDialInConferencingLanguageList** cmdlet is enclosed in parentheses to ensure that Windows PowerShell carries out this operation before doing anything else. After the information has been returned, standard "dot notation" (the object name followed by a period followed by a property name) is used to display all the values stored in the Languages property.

    (Get-CsDialInConferencingLanguageList).Languages

## Detailed Description

Lync Server enables users to join conferences by using a telephone; these dial-in users cannot view video or exchange instant messages, but they can participate fully in the audio portion of the meeting. When users connect to a conference over the phone, they first hear a welcome message and then are given instructions on how to join the meeting. (For example, depending on how the conference has been configured, they might be asked to state their name and then press the pound (\#) key.) At various times Lync Server might need to issue additional messages or instructions; for example, if a user presses 1 on their telephone keypad the system will read a list of all the other keypad options available to them.

Administrators can configure the language, or languages, used in a dial-in conference to relay messages and instructions. The **Get-CsDialInConferencingLanguageList** cmdlet returns a list of the supported languages. The list itself is returned using 5-character language codes (for example, ca-ES to indicate Catalan).

The supported language list is read-only. There is no way for you to add new languages to the list; that’s because there is no way for you to add a new, supported language to dial-in conferencing. Note, too that the list of available languages is configured at the global scope; you cannot assign different lists to different sites. (However, you can assign different languages to different dial-in conferencing access numbers.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsDialInConferencingLanguageList** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsDialInConferencingLanguageList"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when specifying a dial-conferencing language list. Because there is only one such object (global), you can return the language list without using either the Filter or the Identity parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the dial-in conferencing language list to be returned. At this point in time there is only one such object: global. Because of this, you do not need to include this parameter when calling the <strong>Get-CsDialInConferencingLanguageList</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the languages list from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsDialInConferencingLanguageList** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsDialInConferencingLanguageList** cmdlet returns an instance of the Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingLanguageList object.

## 另请参阅

#### 其他资源

[New-CsDialInConferencingAccessNumber](new-csdialinconferencingaccessnumber.md)  
[Set-CsDialInConferencingAccessNumber](set-csdialinconferencingaccessnumber.md)

