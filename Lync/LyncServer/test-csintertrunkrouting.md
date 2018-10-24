---
title: Test-CsInterTrunkRouting
TOCTitle: Test-CsInterTrunkRouting
ms:assetid: 2248d29a-8a2a-42b1-ab6b-a6c1d74b0455
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204741(v=OCS.15)
ms:contentKeyID: 49312240
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsInterTrunkRouting

 

_**上一次修改主题：** 2015-03-09_

Verifies the route and the PSTN usage used when routing a phone call made from a specified SIP trunk. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsInterTrunkRouting -TargetNumber <PhoneNumber> -TrunkConfiguration <TrunkConfiguration> [-Force <SwitchParameter>] [-RouteSettings <PstnRoutingSettings>]

## Examples

## Example 1

The commands shown in Example 1 return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

## Detailed Description

The Test-CsInterTrunkRouting verifies that calls can be routed from one SIP to another. To do this, the cmdlet is given a phone number and a trunk configuration; Test-CsInterTrunkRouting will then report back matching routes and matching PSTN usages for the specified number. Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsInterTrunkRouting"}

**Lync Server 控制面板:** The functions carried out by the Test-CsInterTrunkRouting cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>TargetNumber</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
<td><p>PSTN telephone number to be called when conducting the test. The target phone number should specified using the E.164 format, which means that the number will look something like this:</p>
<p>-TargetNumber &quot;tel:+12065551219&quot;</p>
<p>The phone number should include the &quot;tel:&quot; prefix followed by a plus sign (+), the country/region calling code (1), the area code (206) and the phone number (5551219). Do not use dashes, parentheses, or any other characters when specifying the phone number.</p></td>
</tr>
<tr class="even">
<td><p><em>TrunkConfiguration</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration</p></td>
<td><p>Object reference to the trunk configuration being tested. To create this object reference, use a command similar to this:</p>
<p>$trunk = Get-CsTrunkConfiguration –Identity &quot;site:Redmond&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>RouteSettings</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnRoutingSettings</p></td>
<td><p>Object reference that enables you to specify a collection of voice routing configuration settings when calling Test-CsInterTrunkRouting. To create this object reference, use a command similar to this:</p>
<p>$route = Get-CsRoutingConfiguration –Identity &quot;global&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. Test-CsInterTrunkRouting does not accept pipelined input.

## Return Types

Test-CsInterTrunkRouting returns instances of the Microsoft.Rtc.Management.Voice.InterTrunkRoutingTestResult object.

## 另请参阅

#### 其他资源

[Get-CsTrunk](get-cstrunk.md)  
[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)

