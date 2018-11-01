---
title: Set-CsCallParkOrbit
TOCTitle: Set-CsCallParkOrbit
ms:assetid: 9a159a9a-69a6-4e4d-8224-49aa42092ea8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398796(v=OCS.15)
ms:contentKeyID: 49313713
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCallParkOrbit

 

_**上一次修改主题：** 2015-03-09_

Sets the properties for an existing call park orbit range within an organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCallParkOrbit [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsCallParkOrbit [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-CallParkService <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] [-Type <CallPark | GroupPickup>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example changes the range of numbers for the call park orbit named "Redmond CPO 1" to 500 through 699. All values within this range must be unique among all call park orbit ranges within the organization.

    Set-CsCallParkOrbit -Identity "Redmond CPO 1" -NumberRangeStart 500 -NumberRangeEnd 699

## EXAMPLE 2

This example changes the range of numbers for the call park orbit named "Redmond CPO 2" to \*7000 through \*7100. All values within this range must be unique among all call park orbit ranges within the organization. Note that, unlike the preceding example, double quote marks were included around the values assigned to NumberRangeStart and NumberRangeEnd. If these values begin with a \* or \# (the only non-numeric values allowed) you must enclose the value in double quotes.

    Set-CsCallParkOrbit -Identity "Redmond CPO 2" -NumberRangeStart "*7000" -NumberRangeEnd "*7100"

## Detailed Description

Parking a call assigns a received phone call to a number within a specific range for later retrieval. A call park orbit is the set of numbers defined for this purpose. The **Set-CsCallParkOrbit** cmdlet enables you to change the number ranges and the ID of the Call Park service. The new range of numbers must be unique among all call park orbits defined within the organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsCallParkOrbit** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCallParkOrbit"}

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
<td><p><em>CallParkService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The fully qualified domain name (FQDN) or service ID of the Application service that hosts the 呼叫寄存应用程序. All calls parked to numbers within the range specified by the NumberRangeStart and NumberRangeEnd parameters will be routed to this server or pool.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>The unique identifier of the call park orbit range to be modified. If the Identity includes spaces, this value must be included within double quotes.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DisplayCallParkOrbit</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。 This object must be of type DisplayCallParkOrbit, which can be retrieved by calling the <strong>Get-CsCallParkOrbit</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>NumberRangeEnd</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The last number in the range for this call park orbit. The value must be greater than or equal to the NumberRangeStart. The value must also be the same length as the value of the NumberRangeStart. For example, if NumberRangeStart is set to 100, NumberRangeEnd cannot be set to 1001. In addition, if the NumberRangeStart begins with a * or #, then NumberRangeEnd must begin with the same character.</p>
<p>Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). This means that the value must be a string beginning with either the character * or # or a number 1 through 9 (the first character cannot be a zero). If the first character is * or # the following character must be a number 1 through 9 (it cannot be a zero). Subsequent characters can be any number 0 through 9 up to seven additional characters. (For example, &quot;#6000&quot;, &quot;*92000&quot;, and &quot;*95551212&quot;.) If the first character is not * or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9. (For example, 915551212;41212;300.)</p></td>
</tr>
<tr class="odd">
<td><p><em>NumberRangeStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The first number in the range for this call park orbit. The value must be less than or equal to the NumberRangeEnd. The value must also be the same length as the value of the NumberRangeEnd.</p>
<p>Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). This means that the value must be a string beginning with either the character * or # or a number 1 through 9 (the first character cannot be a zero). If the first character is * or # the following character must be a number 1 through 9 (it cannot be a zero). Subsequent characters can be any number 0 through 9 up to seven additional characters. (For example, &quot;#6000&quot;, &quot;*92000&quot;, and &quot;*95551212&quot;.) The number following the * or # must be greater than 100. If the first character is not * or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9. (For example, 915551212;41212;300.)</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Core.OrbitType</p></td>
<td><p>Specifies the type of call park orbit. Lync Server 2013 allows for two different types of call park orbits:</p>
<p>CallPark. This is the standard call park orbit, in which a user places a call on hold and then can retrieve that call from any phone by dialing the specified call park number. CallPark is the default orbit type and will be used if the Type parameter is not specified.</p>
<p>GroupPickup. With group pickup, users can answer any incoming call that is made to any member of their call pickup group. Call pickup groups are configured by administrators.</p>
<p>To specify a call park orbit type, use syntax similar to this:</p>
<p>-Type GroupPickup</p>
<p>This parameter was introduced in the February 2013 release of Lync Server 2013.</p></td>
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

Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit object. Accepts pipelined input of call park orbit objects.

## Return Types

This cmdlet modifies an object of type Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit.

## 另请参阅

#### 其他资源

[New-CsCallParkOrbit](new-cscallparkorbit.md)  
[Remove-CsCallParkOrbit](remove-cscallparkorbit.md)  
[Get-CsCallParkOrbit](get-cscallparkorbit.md)

