---
title: Test-CsVoicePolicy
TOCTitle: Test-CsVoicePolicy
ms:assetid: 4d631e36-3a9d-4ca2-913f-8c9f4e93183d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398310(v=OCS.15)
ms:contentKeyID: 49312793
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsVoicePolicy

 

_**上一次修改主题：** 2015-03-09_

针对语音策略测试电话号码，并针对该号码的策略确定将使用的语音路由。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsVoicePolicy -TargetNumber <PhoneNumber> -VoicePolicy <VoicePolicy> [-Force <SwitchParameter>] [-RouteSettings <PstnRoutingSettings>]

## 示例

## 示例 1

此示例针对 Identity 为 site:Redmond 的语音策略运行语音策略测试。首先，运行 **Get-CsVoicePolicy** cmdlet，以检索 Identity 为 site:Redmond 的策略。该策略对象随后将通过管道传递到 **Test-CsVoicePolicy** cmdlet，它将针对电话号码 +14255559999 测试策略。输出将是号码模式与 TargetNumber 值匹配，且电话用法与策略中的电话用法匹配的第一个语音路由（基于路由的 Priority 属性）。如果没有发现匹配的路由（例如，如果号码模式与 11 位数字号码的模式匹配，且您提供了 7 位数字的号码），则将返回空值。

    Get-CsVoicePolicy -Identity site:Redmond | Test-CsVoicePolicy -TargetNumber "+14255559999"

## 示例 2

示例 2 与示例 1 相同，但不是将 Get 操作的结果直接通过管道传递到 **Test-CsVoicePolicy** cmdlet，而是先将此对象存储在变量 $a 中，然后作为参数 VoicePolicy 的值传入，用作针对其运行测试的策略。

    $a = Get-CsVoicePolicy -Identity site:Redmond
    Test-CsVoicePolicy -TargetNumber "+14255559999" -VoicePolicy $a

## 示例 3

此示例针对 Lync Server 部署中定义的所有语音策略运行语音策略测试。首先，运行 **Get-CsVoicePolicy** cmdlet（无参数），检索所有语音策略。返回的策略集合随后将通过管道传递到 **Test-CsVoicePolicy** cmdlet，在此，根据所提供的目标电话号码 (+12065559999) 和电话用法，检查集合中的每个策略是否存在匹配的路由。输出将是匹配路由以及匹配电话用法的列表。

    Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065559999"

## 详细说明

语音策略通过公用电话交换网 (PSTN) 用法与语音路由相关联。对于来自分配有特定语音策略的用户的呼叫，只能通过 PSTN 用法与策略用法匹配，以及号码模式与已拨号码匹配的路由发送。调用 **Test-CsVoicePolicy** cmdlet 以确定将用于路由具有特定语音策略的用户的呼叫（如果存在），以及将策略关联到路由所使用的电话用法。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsVoicePolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsVoicePolicy"}

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
<td><p><em>TargetNumber</em></p></td>
<td><p>必需</p></td>
<td><p>PhoneNumber</p></td>
<td><p>针对其运行测试的电话号码。此号码的格式应为 E.164 格式（例如 +14255551212）。</p></td>
</tr>
<tr class="even">
<td><p><em>VoicePolicy</em></p></td>
<td><p>必需</p></td>
<td><p>VoicePolicy</p></td>
<td><p>对照其运行测试的语音策略对象的引用。您可以调用 <strong>Get-CsVoicePolicy</strong> cmdlet 来检索语音策略对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示运行此 cmdlet 时可能出现的任何确认提示或非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>RouteSettings</em></p></td>
<td><p>可选</p></td>
<td><p>PstnRoutingSettings</p></td>
<td><p>要针对其运行测试的路由设置。路由设置可以通过对 <strong>Get-CsRoutingConfiguration</strong> cmdlet 的调用进行检索。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoicePolicy 对象。接受通过管道传递的语音策略对象的输入。

## 返回类型

返回一个类型为 Microsoft.Rtc.Management.Voice.VoicePolicyTestResult 的对象。

## 另请参阅

#### 其他资源

[New-CsVoicePolicy](new-csvoicepolicy.md)  
[Remove-CsVoicePolicy](remove-csvoicepolicy.md)  
[Set-CsVoicePolicy](set-csvoicepolicy.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Grant-CsVoicePolicy](grant-csvoicepolicy.md)

