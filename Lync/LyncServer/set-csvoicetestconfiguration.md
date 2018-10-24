---
title: Set-CsVoiceTestConfiguration
TOCTitle: Set-CsVoiceTestConfiguration
ms:assetid: 7b95fc95-ec0e-4bb3-aed1-e8b72e305999
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398614(v=OCS.15)
ms:contentKeyID: 49313342
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceTestConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改可用于根据指定路由和规则测试电话号码的测试方案。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsVoiceTestConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceTestConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-DialedNumber <String>] [-ExpectedRoute <String>] [-ExpectedTranslatedNumber <String>] [-ExpectedUsage <String>] [-Force <SwitchParameter>] [-TargetDialplan <String>] [-TargetVoicePolicy <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将 TestConfig1 的语音测试配置的拨打号码设置为 14255551212。将针对语音策略和路由检查该号码，以确保按照预期进行规范化，并确保应用正确的路由和拨号计划。

    Set-CsVoiceTestConfiguration -Identity TestConfig1 -DialedNumber 14255551212

## 示例 2

此示例修改语音测试配置 TestConfig1 的设置。该命令将 TargetDialplan 设置为 site:Redmond1 的拨号计划。由于拨号计划更改可能意味着规范化规则更改，因此也更改了 ExpectedTranslationNumber 以反映该拨号计划的规范化规则的预期结果。

    Set-CsVoiceTestConfiguration -Identity TestConfig1 -TargetDialplan site:Redmond1 -ExpectedTranslatedNumber "+912065551212"

## 详细说明

在实现语音路由和语音策略之前，建议用各种电话号码测试这些路由和策略，以确保达到预期的效果。要执行此测试，可以使用此 cmdlet 修改测试方案。

**Set-CsVoiceTestConfiguration** cmdlet 可修改语音路由、用法、拨号计划和语音策略，以根据其测试指定的电话号码。所有这些信息都可以使用本主题的参数描述部分中指定的其他 cmdlet 进行定义和检索。

使用此 cmdlet 修改的配置需要使用 **Test-CsVoiceTestConfiguration** cmdlet 进行测试。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsVoiceTestConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceTestConfiguration"}

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
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DialedNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要用于测试策略、用法等的电话号码。</p>
<p>不得超过 512 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>ExpectedRoute</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>预期在配置测试过程中使用的语音路由的名称。基于目标拨号计划和语音策略，如果使用了不同的路由，测试将失败。可以通过调用 <strong>Get-CsVoiceRoute</strong> cmdlet 来检索可用的语音路由。</p>
<p>不得超过 256 个字符。</p></td>
</tr>
<tr class="even">
<td><p><em>ExpectedTranslatedNumber</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>预期在转换后所采用的格式的电话号码。这是规范化后 DialedNumber 参数的值。如果运行 <strong>Test-CsVoiceTestConfiguration</strong> cmdlet，而 DialedNumber 没有产生 ExpectedTranslatedNumber 中的值，则测试将报告为 Fail。</p>
<p>不得超过 512 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>ExpectedUsage</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>预期在配置测试过程中使用的 PSTN 用法的名称。基于目标拨号计划和语音策略，如果使用了不同的 PSTN 用法，测试将失败。可以通过调用 <strong>Get-CsPstnUsage</strong> cmdlet 来检索可用的用法。</p>
<p>不得超过 256 个字符。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一地标识要修改的测试方案的字符串。</p>
<p>由于此对象只能在全局范围创建，因此此参数的值不包含范围，因此只需一个名称。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>TestConfiguration</p></td>
<td><p>一个类型为 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration 的对象，包含现有语音测试配置以及要对该配置所做的更改。通过调用 <strong>Get-CsVoiceTestConfiguraton</strong> cmdlet，可以检索此类型的对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetDialplan</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要用于此测试的拨号计划的 Identity。可以通过调用 <strong>Get-CsDialPlan</strong> cmdlet 来检索拨号计划。</p>
<p>不得超过 40 个字符。</p></td>
</tr>
<tr class="even">
<td><p><em>TargetVoicePolicy</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要针对其运行此测试的语音策略的 Identity。可以通过调用 <strong>Get-CsVoicePolicy</strong> cmdlet 来检索语音策略。</p>
<p>不得超过 40 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration 对象。接受通过管道传递的语音测试配置对象的输入。

## 返回类型

此 cmdlet 返回一个类型为 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration 的对象。

## 另请参阅

#### 其他资源

[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Remove-CsVoiceTestConfiguration](remove-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)  
[Test-CsVoiceTestConfiguration](test-csvoicetestconfiguration.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)

