---
title: Set-CsRoutingConfiguration
TOCTitle: Set-CsRoutingConfiguration
ms:assetid: ab69c6e8-262a-4ecb-b1af-513383c494fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412811(v=OCS.15)
ms:contentKeyID: 49313894
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRoutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改语音路由列表。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRoutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsRoutingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-Route <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

修改路由配置中的语音路由需要若干步骤。在此示例中，首先通过调用 **Get-CsRoutingConfiguration** cmdlet 检索路由配置对象。将检索到的对象（只有一个）分配给变量 $a。

在此示例的第 2 行中，从变量 $a 中检索 Route 属性的内容，它是语音路由对象的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，通过该 cmdlet 在集合中搜索 Name 与字符串 LocalRoute 匹配的所有语音路由对象。将该对象分配给变量 $b。

接下来，通过为 SuppressCallerId 属性分配 $False 值来修改 LocalRoute 语音路由对象。通过更新该对象，已经在变量 $a 中更新了该对象。但是，该对象仍然只保存在内存中。最后，需要将 $a 传递到 **Set-CsRoutingConfiguration** cmdlet 的 Instance 参数来保存所做的更改。

建议不要使用该方法修改路由配置。要修改路由配置，只需使用 **Set-CsVoiceRoute** cmdlet 更改各个语音路由，如下所示：

Set-CsVoiceRoute -Identity LocalRoute -SuppressCallerId $False

此行与示例 1 中完成的任务相同。

    $a = Get-CsRoutingConfiguration
    $b = $a.Route | Where-Object {$_.Name -match "LocalRoute"}
    $b.SuppressCallerId = $False
    Set-CsRoutingConfiguration -Instance $a

## 详细说明

语音路由包含一些说明，指示 Lync Server 如何将来自企业语音用户的呼叫路由到公用电话交换网 (PSTN) 或专用交换机 (PBX) 上的电话号码。使用此 cmdlet 可以修改在 Lync Server 部署中定义的所有语音路由的设置。

建议不要使用此 cmdlet。要修改路由配置，请通过调用 **Set-CsVoiceRoute** cmdlet 来修改各个语音路由。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsRoutingConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRoutingConfiguration"}

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
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>当设置为 True 时，将根据用户发出呼叫和用户接收呼叫的位置来管理语音路由。默认值为 False。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>路由配置的范围。此值必须为 Global。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>PstnRoutingSettings</p></td>
<td><p>路由配置 (Microsoft.Rtc.Management.WritablConfig.Policy.Voice.PstnRoutingSettings) 对象。此类型的对象可以通过调用 <strong>Get-CsRoutingConfiguration</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>Route</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>为 Lync Server 部署定义的所有语音路由（Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route 对象）的列表。</p>
<p>应该使用 <strong>Set-CsVoiceRoute</strong> cmdlet 修改各个语音路由对象。建议使用此方法修改此列表中的路由。</p></td>
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

Microsoft.Rtc.WritableConfig.Management.Policy.Voice.PSTNRoutingSettings 对象。接受通过管道传递的路由配置对象的输入。

## 返回类型

**Set-CsRoutingConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnRoutingSettings 对象的实例。

## 另请参阅

#### 其他资源

[New-CsRoutingConfiguration](new-csroutingconfiguration.md)  
[Remove-CsRoutingConfiguration](remove-csroutingconfiguration.md)  
[Get-CsRoutingConfiguration](get-csroutingconfiguration.md)  
[Set-CsVoiceRoute](set-csvoiceroute.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

