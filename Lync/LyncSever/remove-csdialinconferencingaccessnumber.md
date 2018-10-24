---
title: Remove-CsDialInConferencingAccessNumber
TOCTitle: Remove-CsDialInConferencingAccessNumber
ms:assetid: a6d5a6f4-5ad1-4253-b1c4-27f81851046f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412782(v=OCS.15)
ms:contentKeyID: 49313840
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDialInConferencingAccessNumber

 

_**上一次修改主题：** 2015-03-09_

Removes an existing dial-in conferencing access number. Dial-in conferencing provides a way for users to use a "regular" telephone or mobile phone (that is, a device on the public switched telephone network (PSTN)) to join the audio portion of a conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDialInConferencingAccessNumber -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the dial-in conferencing access number that has the Identity sip:RedmondDialIn@litwareinc.com.

    Remove-CsDialInConferencingAccessNumber -Identity sip:RedmondDialIn@litwareinc.com

## EXAMPLE 2

Example 2 deletes all the toll free dial-in conferencing access numbers; in this example, that means any numbers that have a LineUri that begins with "tel:+1800". To do this, the command uses the **Get-CsDialInConferencingAccessNumber** cmdlet and the Filter parameter to return a collection of all the toll free access numbers configured for use in the organization; the filter value {LineUri -like "tel:+1800\*"} limits the returned data to those numbers where the LineUri property begins with the string value "tel:+1800". This filtered collection is then piped to the **Remove-CsDialInConferencingAccessNumber** cmdlet, which deletes each number in the collection.

    Get-CsDialInConferencingAccessNumber -Filter {LineUri -like "tel:+1800*"} | Remove-CsDialInConferencingAccessNumber

## EXAMPLE 3

In Example 3, all the dial-in conferencing access numbers for the Redmond region are deleted. To carry out this task, the **Get-CsDialInConferencingAccessNumber** cmdlet and the Region parameter are first called in order to return a collection of all the access numbers for the Redmond region. (That is, any access number that includes Redmond in its list of regions.) This collection is then piped to the **Remove-CsDialInConferencingAccessNumber** cmdlet, which deletes all the access numbers in the collection.

    Get-CsDialInConferencingAccessNumber -Region "Redmond" | Remove-CsDialInConferencingAccessNumber

## EXAMPLE 4

In Example 4, all the dial-in conferencing access numbers that are not associated with a region are deleted. To do this, the **Get-CsDialInConferencingAccessNumber** cmdlet is called along with the Region parameter and the parameter value $Null; this returns a collection of access numbers where the Regions property is empty. That collection is then piped to the **Remove-CsDialInConferencingAccessNumber** cmdlet, which deletes all the numbers in the collection.

    Get-CsDialInConferencingAccessNumber -Region $Null | Remove-CsDialInConferencingAccessNumber

## EXAMPLE 5

The command shown in Example 5 deletes any dial-in conferencing access numbers where the primary language is not set to Italian. To do this, the **Get-CsDialInConferencingAccessNumber** cmdlet is first called without any parameters in order to return a collection of all the dial-in conferencing access numbers configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out any numbers where the PrimaryLanguage property is not equal to Italian ("it-IT"). Finally, the filtered collection is piped to the **Remove-CsDialInConferencingAccessNumber** cmdlet, which deletes all the access numbers in the collection.

    Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -ne "it-IT"} | Remove-CsDialInConferencingAccessNumber

## EXAMPLE 6

In Example 6, the dial-in conferencing access number with the display name "Default Dial-In Access Number" is deleted. To accomplish this task, the **Get-CsDialInConferencingAccessNumber** cmdlet is called along with the Filter parameter and the filter value {DisplayName -eq "Default Dial-In Access Number"}; this filter value limits the returned data to the access number where the DisplayName property is equal to "Default Dial-In Access Number". The returned object is then piped to the **Remove-CsDialInConferencingAccessNumber** cmdlet, which deletes the corresponding access number.

    Get-CsDialInConferencingAccessNumber -Filter {DisplayName -eq "Default Dial-In Access Number"} | Remove-CsDialInConferencingAccessNumber

## Detailed Description

Dial-in conferencing enables users to use any kind of telephone (such as a standard "land line," a mobile phone, or a Voice over Internet Protocol phone) to join the audio portion of a conference. This enables users to participate in the meeting even if they do not have a computer or an Internet connection. Users have full audio capabilities: they can speak to other participants and hear everything that takes place. They just aren’t able to see shared slides, video feeds, or other visual elements.

In order to provide users with dial-in conferencing capabilities, you must create dial-in conferencing access numbers: phone numbers users can call in order to be connected to a meeting. Dial-in conferencing access numbers are created by using the **New-CsDialInConferencingAccessNumber** cmdlet. When you create a new dial-in conferencing access number, you actually create a new contact object in Active Directory 域服务; this contact object is used to represent the access number and all its properties. The **Remove-CsDialInConferencingAccessNumber** cmdlet enables you to delete any of the dial-in conferencing numbers created by using the **New-CsDialInConferencingAccessNumber** cmdlet. When you run the **Remove-CsDialInConferencingAccessNumber** cmdlet, the cmdlet not only deletes the number from the collection of dial-in conferencing access numbers but also deletes the Active Directory contact object that represents the given access number.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDialInConferencingAccessNumber** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDialInConferencingAccessNumber"}

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
<td><p>SIP address of the dial-in conferencing access number (that is, the contact object that represents that number) to be removed. You must include the sip: prefix when specifying the Identity; for example: -Identity &quot;sip:RedmondDialIn@litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
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

Microsoft.Rtc.Management.Xds.AccessNumber object. The **Remove-CsDialInConferencingAccessNumber** cmdlet accepts pipelined input of the access number object.

## Return Types

The **Remove-CsDialInConferencingAccessNumber** cmdlet deletes instances of the Microsoft.Rtc.Management.Xds.AccessNumber object.

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingAccessNumber](get-csdialinconferencingaccessnumber.md)  
[New-CsDialInConferencingAccessNumber](new-csdialinconferencingaccessnumber.md)  
[Set-CsDialInConferencingAccessNumber](set-csdialinconferencingaccessnumber.md)

