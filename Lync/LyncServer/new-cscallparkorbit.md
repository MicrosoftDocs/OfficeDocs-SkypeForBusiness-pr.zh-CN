---
title: New-CsCallParkOrbit
TOCTitle: New-CsCallParkOrbit
ms:assetid: d65a000f-905d-4512-b082-066748719f4c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398936(v=OCS.15)
ms:contentKeyID: 49314384
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsCallParkOrbit

 

_**上一次修改主题：** 2015-03-09_

Creates a new, named range of numbers assigned for parking calls within an organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsCallParkOrbit -Identity <XdsGlobalRelativeIdentity> -CallParkService <String> -NumberRangeEnd <String> -NumberRangeStart <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Type <CallPark | GroupPickup>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a new call park orbit named "Redmond CPO 1" on the Application Server with the service ID ApplicationServer:pool0.litwareinc.com. The available number range for this call park orbit is 100 through 199.

    New-CsCallParkOrbit -Identity "Redmond CPO 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService ApplicationServer:pool0.litwareinc.com

## EXAMPLE 2

This example creates a new call park orbit named "Redmond CPO 2" on the Call Park application server with the FQDN pool0.litwareinc.com. The available range for this call park orbit is \*1000 through \*1999.

    New-CsCallParkOrbit -Identity "Redmond CPO 2" -NumberRangeStart "*1000" -NumberRangeEnd "*1999" -CallParkService pool0.litwareinc.com

## EXAMPLE 3

This example creates a new call park orbit range named "Redmond CPO 3" on the Call Park application server with the service ID ApplicationServer:redmond.litwareinc.com. The available range for this call park orbit is \#1000 through \#1999.

    New-CsCallParkOrbit -Identity "Redmond CPO 3" -NumberRangeStart "#1000" -NumberRangeEnd "#1999"  -CallParkService ApplicationServer:redmond.litwareinc.com

## Detailed Description

Parking a call assigns a received phone call to a specific number for later retrieval. A call park orbit range is the set of call park locations assigned to a specific Call Park service for this purpose. The **New-CsCallParkOrbit** cmdlet defines the numbers for a call park orbit range and applies them to a specific service. Calls parked within the given range will be parked on the specified Call Park service. You can create multiple call park orbits; each must have a globally unique name and a unique range of numbers.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsCallParkOrbit** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsCallParkOrbit"}

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
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The fully qualified domain name (FQDN) or service ID of the Application service that hosts the 呼叫寄存应用程序. All calls parked to numbers within the range specified by the NumberRangeStart and NumberRangeEnd parameters will be routed to this server or pool.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>The name of the call park orbit range. This name must be unique within the Lync Server deployment. This string can be any value, but should be something that allows for easy identification of the particular call park orbit range. All call park orbit ranges are created with a global scope.</p></td>
</tr>
<tr class="odd">
<td><p><em>NumberRangeEnd</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The last number in the range for this call park orbit. The value must be greater than or equal to the NumberRangeStart. The value must also be the same length as the value of the NumberRangeStart. For example, if NumberRangeStart is set to 100, NumberRangeEnd cannot be set to 1001. In addition, if the NumberRangeStart begins with a * or #, then NumberRangeEnd must begin with the same character.</p>
<p>Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). This means that the value must be a string beginning with either the character * or # or a number 1 through 9 (the first character cannot be a zero). If the first character is * or # the following character must be a number 1 through 9 (it cannot be a zero). Subsequent characters can be any number 0 through 9 up to seven additional characters. (For example, #6000, *92000, and *95551212.) If the first character is not * or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9. (For example: 915551212;41212;300)</p></td>
</tr>
<tr class="even">
<td><p><em>NumberRangeStart</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The first number in the range for this call park orbit. The value must be less than or equal to the NumberRangeEnd. The value must also be the same length as the value of the NumberRangeEnd.</p>
<p>Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}). This means that the value must be a string beginning with either the character * or # or a number 1 through 9 (the first character cannot be a zero). If the first character is * or # the following character must be a number 1 through 9 (it cannot be a zero). Subsequent characters can be any number 0 through 9 up to seven additional characters. (For example, #6000, *92000, and *95551212.) The number following the * or # must be greater than 100. If the first character is not * or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9. (For example, 915551212;41212;300)</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Core.OrbitType</p></td>
<td><p>Specifies the type of call park orbit being created. Lync Server 2013 allows for two different types of call park orbits:</p>
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

None.

## Return Types

This cmdlet creates an object of type Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit.

## 另请参阅

#### 其他资源

[Remove-CsCallParkOrbit](remove-cscallparkorbit.md)  
[Set-CsCallParkOrbit](set-cscallparkorbit.md)  
[Get-CsCallParkOrbit](get-cscallparkorbit.md)

