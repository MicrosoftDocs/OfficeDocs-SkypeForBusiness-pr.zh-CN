---
title: Set-CsVoiceConfiguration
TOCTitle: Set-CsVoiceConfiguration
ms:assetid: dbab35ac-9a55-41d2-a726-9a26b2ff8e85
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398967(v=OCS.15)
ms:contentKeyID: 49314458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改语音测试配置列表。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsVoiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-VoiceTestConfigurations <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

修改语音配置中的测试语音配置需要多个步骤。在此示例中，首先通过调用 **Get-CsVoiceConfiguration** cmdlet 来检索语音配置对象。将检索到的对象（只有一个）分配给变量 $a。

在此示例的第 2 行中，从变量 $a 中检索到 VoiceTestConfigurations 属性的内容，即，语音测试配置对象的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，通过该 cmdlet 在集合中搜索 Name 等于字符串 TestConfig2 的语音测试配置对象。将该对象分配给变量 $b。

接下来，通过为 DialedNumber 和 ExpectedTranslatedNumber 属性分配新值来修改 TestConfig2 语音测试配置对象。通过更新该对象，已经在变量 $a 中更新了该对象。但是，该对象仍然只保存在内存中。最后一步，需要将 $a 传递到 **Set-CsVoiceConfiguration** cmdlet 的 Instance 参数来保存所做的更改。

建议不要使用该方法修改语音配置。要修改语音配置，只需使用 **Set-CsVoiceTestConfiguration** cmdlet 更改各个语音测试配置，如下所示：

Set-CsVoiceTestConfiguration -Identity TestConfig2 -DialedNumber 5551212 -ExpectedTranslatedNumber +5551212

此行与示例 1 中完成的任务相同。

    $a = Get-CsVoiceConfiguration
    $b = $a.VoiceTestConfigurations | Where-Object {$_.Name -eq "TestConfig2"}
    $b.DialedNumber = "5551212"
    $b.ExpectedTranslatedNumber = "+5551212"
    Set-CsVoiceConfiguration -Instance $a

## 详细说明

语音测试配置用于针对特定语音策略、路由和拨号计划测试电话号码。此 cmdlet 可用于在包含 Lync Server 部署的所有语音测试配置的列表中修改语音测试配置。

此 cmdlet 可以修改 VoiceConfiguration 类型的对象。此对象只是语音测试配置的容器对象。因此，建议不要使用此 cmdlet。要修改语音配置，请通过调用 **Set-CsVoiceTestConfiguration** cmdlet 来修改各个语音测试配置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsVoiceConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceConfiguration"}

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
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>此对象的范围。此参数的唯一可能值是 Global。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>VoiceConfiguration</p></td>
<td><p>对语音配置 (Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration) 对象的引用。此类型的对象可以通过调用 <strong>Get-CsVoiceConfiguration</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceTestConfigurations</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>为 Lync Server 部署定义的所有语音测试配置（Microsoft.Rtc.Management.WritableConfig.Policy.Voice.TestConfiguration 对象）的列表。</p>
<p>应该使用 <strong>Set-CsVoiceTestConfiguration</strong> cmdlet 修改各个语音测试配置对象。建议使用此方法修改此列表中的配置。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration 对象。**Set-CsVoiceConfiguration** cmdlet 接受通过管道传递的语音配置对象的输入。

## 返回类型

**Set-CsVoiceConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceConfiguration 对象的实例。

## 另请参阅

#### 其他资源

[Remove-CsVoiceConfiguration](remove-csvoiceconfiguration.md)  
[Get-CsVoiceConfiguration](get-csvoiceconfiguration.md)  
[New-CsVoiceTestConfiguration](new-csvoicetestconfiguration.md)  
[Set-CsVoiceTestConfiguration](set-csvoicetestconfiguration.md)  
[Get-CsVoiceTestConfiguration](get-csvoicetestconfiguration.md)

