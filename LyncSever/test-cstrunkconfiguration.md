---
title: Test-CsTrunkConfiguration
TOCTitle: Test-CsTrunkConfiguration
ms:assetid: 07f2ef04-49aa-4857-b213-fa98506c0427
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398137(v=OCS.15)
ms:contentKeyID: 49311912
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsTrunkConfiguration

 

_**上一次修改主题：** 2015-03-09_

Validates a trunk configuration against a phone number. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsTrunkConfiguration -TrunkConfiguration <TrunkConfiguration> [-CallingNumber <PhoneNumber>] [-DialedNumber <PhoneNumber>]

## Examples

## EXAMPLE 1

This example runs a test against the trunk configuration defined for the Redmond site. The first line in this example calls the **Get-CsTrunkConfiguration** cmdlet to retrieve the configuration for the Redmond site (the configuration with the Identity site:Redmond). The trunk configuration object retrieved is assigned to the variable $tc.

In line 2 we call the **Test-CsTrunkConfiguration** cmdlet, passing the phone number to test to the DialedNumber parameter, and the trunk configuration we retrieved in line 1 (stored in $tc) to the TrunkConfiguration parameter.

    $tc = Get-CsTrunkConfiguration -Identity Site:Redmond
    Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $tc

## Detailed Description

Use this cmdlet to verify that a trunking configuration performs as expected against a dialed phone number. Each configuration contains specific settings defining the relationship and capabilities between the 中介服务器 and the public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider. These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsTrunkConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsTrunkConfiguration"}

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
<td><p><em>TrunkConfiguration</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration</p></td>
<td><p>A reference to a trunk configuration object against which to run the test. Trunk configuration objects can be retrieved by calling the <strong>Get-CsTrunkConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>CallingNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
<td><p>When specified, returns the matched outbound translation rules for the specified phone number. For example:</p>
<p>-CallingNumber &quot;tel:+14255551219&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>DialedNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
<td><p>The phone number against which to test the configuration.</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration object. Accepts pipelined input of a trunk configuration object.

## Return Types

Returns a value of type Microsoft.Rtc.Management.Voice.TrunkConfigurationTestResult.

## 另请参阅

#### 其他资源

[New-CsTrunkConfiguration](new-cstrunkconfiguration.md)  
[Remove-CsTrunkConfiguration](remove-cstrunkconfiguration.md)  
[Set-CsTrunkConfiguration](Set-CsTrunkConfiguration.md)  
[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)

