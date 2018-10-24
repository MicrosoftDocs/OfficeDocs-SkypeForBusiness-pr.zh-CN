---
title: Test-CsVoiceTestConfiguration
TOCTitle: Test-CsVoiceTestConfiguration
ms:assetid: 1c87ef27-0542-49b0-9125-512fd6ed187d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398260(v=OCS.15)
ms:contentKeyID: 49312180
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsVoiceTestConfiguration

 

_**上一次修改主题：** 2015-03-09_

Runs test voice configurations to ensure voice routing and policies work as expected. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsVoiceTestConfiguration -TestCaseInputObject <TestConfiguration> [-Dialplan <LocationProfile>] [-RouteSettings <PstnRoutingSettings>] [-VoicePolicy <VoicePolicy>] <COMMON PARAMETERS>

    Test-CsVoiceTestConfiguration -DialedNumber <String> -Dialplan <LocationProfile> -VoicePolicy <VoicePolicy> [-RouteSettings <PstnRoutingSettings>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>]

## Examples

## EXAMPLE 1

This example runs a voice configuration test against configuration TestConfig1. First the **Get-CsVoiceTestConfiguration** cmdlet is run to retrieve the configuration with the Identity TestConfig1. That configuration object is then piped to the **Test-CsVoiceTestConfiguration** cmdlet.

    Get-CsVoiceTestConfiguration -Identity TestConfig1 | Test-CsVoiceTestConfiguration

## EXAMPLE 2

Example 2 is identical to Example 1 except that instead of piping the results of the Get operation directly to the Test cmdlet, the object is first stored in the variable $a, and then is passed as the value to the parameter TestCaseInputObject to be used as the test configuration.

    $a = Get-CsVoiceTestConfiguration -Identity TestConfig1
    Test-CsVoiceTestConfiguration -TestCaseInputObject $a

## EXAMPLE 3

This example runs a test configuration without first having to define it with the **New-CsVoiceTestConfiguration** cmdlet. Instead of passing a TestConfiguration object created ahead of time, this example shows how to set up a test as you go by specifying the dialed number to test, and the dial plan and voice policy against which to perform the test.

The first line in this example calls the **Get-CsDialPlan** cmdlet to retrieve the Global dial plan. The dial plan object retrieved is assigned to the variable $dp. In the second line, we do the same thing with the voice policy by calling the **Get-CsVoicePolicy** cmdlet to retrieve the Global voice policy, and then assigning that policy to the variable $vp.

Finally, we’re ready to run the test. We call the **Test-CsVoiceTestConfiguration** cmdlet, passing the phone number to test to the DialedNumber parameter, the dial plan we retrieved in line 1 (stored in $dp) to the Dialplan parameter, and the voice policy we retrieved in line 2 (stored in $vp) to the VoicePolicy parameter.

Note that the output for Example 3 will not include status for expected results. If you want to test the results against expectations you must define those expectations by using the **New-CsVoiceTestConfiguration** cmdlet and call the **Test-CsVoiceTestConfiguration** cmdlet as shown in Examples 1 and 2.

    $dp = Get-CsDialPlan -Identity Global
    $vp = Get-CsVoicePolicy -Identity Global
    Test-CsVoiceTestConfiguration -DialedNumber 4255551212 -Dialplan $dp -VoicePolicy $vp

## Detailed Description

Before implementing voice routes and voice policies, it's a good idea to test them out on various phone numbers to ensure the results are what you're expecting. Running this cmdlet with the appropriate parameter settings allows you to run these tests.

This cmdlet tests a phone number against a voice route, usage, dial plan, and voice policy to enable you to verify intended outcomes or to compare the actual outcome to the expected outcome. The voice configurations to be tested can be defined by entering the appropriate parameters individually, or by using the **New-CsVoiceTestConfiguration** cmdlet.

If you enter values for DialedNumber, DialPlan, and VoicePolicy, the output will include the translated number, the normalization rule used to create that translation, the route that was used, and the PSTN usage. If instead you enter a value for the TestCaseInputObject parameter, you can also retrieve status on whether the results matched expected results that you supplied to the test object when you created it with the **New-CsVoiceTestConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsVoiceTestConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsVoiceTestConfiguration"}

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
<td><p><em>DialedNumber</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The phone number to run the test against. Based on the dial plan, route, and policy, this number will be normalized and displayed as output.</p>
<p>This parameter is required unless the TestCaseInputObject parameter is supplied with a value. You cannot supply a DialedNumber and a TestCaseInputObject. (The TestCaseInputObject already contains a DialedNumber within that object.)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Dialplan</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile</p></td>
<td><p>A reference to a dial plan object of the dial plan to use when running the test. Dial plan objects can be retrieved by calling the <strong>Get-CsDialPlan</strong> cmdlet.</p>
<p>This parameter is required if you’ve also specified the DialedNumber parameter. Do not use this parameter if you are using the TestCaseInputObject parameter. If you do, the object in this parameter must match the dial plan specified in the TestCaseInputObject, making the use of this parameter redundant.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>TestCaseInputObject</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration</p></td>
<td><p>An object containing a reference to the voice configuration to test. This object reference can be retrieved by calling the <strong>Get-CsVoiceTestConfiguration</strong> cmdlet.</p>
<p>If you call the cmdlet with this parameter, you cannot specify a DialedNumber. You should also not specify a Dialplan or VoicePolicy, as those would be redundant with the values in the voice test configuration object.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>VoicePolicy</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy</p></td>
<td><p>A reference to a voice policy object of the voice policy to use when running the test. Voice policy objects can be retrieved by calling the <strong>Get-CsVoicePolicy</strong> cmdlet.</p>
<p>This parameter is required if you’ve also specified the DialedNumber parameter. Do not use this parameter if you are using the TestCaseInputObject parameter. If you do, the object in this parameter must match the voice policy specified in the TestCaseInputObject, making the use of this parameter redundant.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>RouteSettings</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnRoutingSettings</p></td>
<td><p>A reference to an object containing all the voice routes available on the Lync Server installation. You can retrieve this object by calling the <strong>Get-CsRoutingConfiguration</strong> cmdlet.</p>
<p>You can use this parameter with either the DialedNumber parameter or with the TestCaseInputObject parameter.</p>
<p></p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration object. Accepts pipelined input of a voice test configuration object.

## Return Types

This cmdlet returns an object of type Microsoft.Rtc.Management.Voice.OcsVoiceTestResult.

## 另请参阅

#### 其他资源

[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Remove-CsVoiceTestConfiguration](remove-csvoicetestconfiguration.md)  
[Set-CsVoiceTestConfiguration](set-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Get-CsRoutingConfiguration](get-csroutingconfiguration.md)

