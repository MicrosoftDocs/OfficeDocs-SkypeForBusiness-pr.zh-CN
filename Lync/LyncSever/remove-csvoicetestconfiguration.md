---
title: Remove-CsVoiceTestConfiguration
TOCTitle: Remove-CsVoiceTestConfiguration
ms:assetid: abe27005-8325-47d7-8c7c-12bb831b87c7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412813(v=OCS.15)
ms:contentKeyID: 49313926
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsVoiceTestConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes a voice test configuration that was used to test phone numbers against specified routes and rules. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsVoiceTestConfiguration -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the voice test configuration settings with the Identity TestConfig1.

    Remove-CsVoiceTestConfiguration -Identity TestConfig1

## EXAMPLE 2

This example removes all voice test configuration settings for any configuration with an Identity containing the string test. The command first calls the **Get-CsVoiceTestConfiguration** cmdlet with the Filter parameter to retrieve all voice test configurations that have an Identity with the string "test" anywhere in its value. The resulting set of configurations is then piped to the **Remove-CsVoiceTestConfiguration** cmdlet and removed.

    Get-CsVoiceTestConfiguration -Filter *test* | Remove-CsVoiceTestConfiguration

## Detailed Description

Before implementing voice routes and voice policies, it's a good idea to test them out on various phone numbers to ensure the results are what you're expecting. When you’re done with those tests and won’t need them again, use this cmdlet to remove them.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsVoiceTestConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsVoiceTestConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>A string uniquely identifying the test configuration you want to remove.</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration object. Accepts pipelined input of voice test configuration objects.

## Return Types

Removes an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration.

## 另请参阅

#### 其他资源

[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Set-CsVoiceTestConfiguration](set-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)  
[Test-CsVoiceTestConfiguration](test-csvoicetestconfiguration.md)

