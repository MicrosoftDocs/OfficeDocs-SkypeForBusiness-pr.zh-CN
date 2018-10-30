---
title: Get-CsVoiceTestConfiguration
TOCTitle: Get-CsVoiceTestConfiguration
ms:assetid: c23235db-500c-4303-8c75-b4ae341b3807
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412957(v=OCS.15)
ms:contentKeyID: 49314158
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoiceTestConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves a test scenario you can use to test phone numbers against specified routes and rules. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsVoiceTestConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsVoiceTestConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Retrieves all the voice test configuration settings.

    Get-CsVoiceTestConfiguration

## EXAMPLE 2

This example retrieves all the voice test configuration settings, displaying only the Identity, DialedNumber, and ExpectedTranslatedNumber parameter of each. The settings returned by the **Get-CsVoiceTestConfiguration** cmdlet are piped to the **Select-Object** cmdlet, where the output is narrowed down to the Identity, DialedNumber, and ExpectedTranslatedNumber properties.

    Get-CsVoiceTestConfiguration | Select-Object Identity, DialedNumber, ExpectedTranslatedNumber

## EXAMPLE 3

This example uses the Filter parameter to retrieve all the voice test configuration settings with Identities that contain the string "test". The wildcard characters (\*) at the beginning and end of the filter value indicate that the string "test" can be located anywhere within the Identity, with any characters before or after that string. For example, this command would return voice test configurations with names such as TestConfig, VoiceNumberTest, and VoiceTest1.

    Get-CsVoiceTestConfiguration -Filter *test*

## Detailed Description

This cmdlet retrieves the voice route, usage, dial plan, and voice policy against which to test a specified phone number. Before implementing voice routes and voice policies, it's a good idea to test them out on various phone numbers to ensure the results are what you're expecting. You can do this testing by retrieving a test configuration with this cmdlet, and then running that scenario with the **Test-CsVoiceConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsVoiceTestConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoiceTestConfiguration"}

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
<td><p>This parameter provides a way to do a wildcard search of the defined voice test configurations. (For details, see the examples in this topic.)</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>A string uniquely identifying the test configuration you want to retrieve.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the voice test configuration from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns one of more objects of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration.

## 另请参阅

#### 其他资源

[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Remove-CsVoiceTestConfiguration](remove-csvoicetestconfiguration.md)  
[Set-CsVoiceTestConfiguration](set-csvoicetestconfiguration.md)  
[Test-CsVoiceTestConfiguration](test-csvoicetestconfiguration.md)

