---
title: Get-CsVoiceRoute
TOCTitle: Get-CsVoiceRoute
ms:assetid: 422abb2d-bff3-4b9a-b18c-d8202b01f69b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425926(v=OCS.15)
ms:contentKeyID: 49312664
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoiceRoute

 

_**上一次修改主题：** 2015-03-09_

返回有关配置为在组织中使用的语音路由的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsVoiceRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsVoiceRoute [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

检索组织内定义的所有语音路由的属性。

    Get-CsVoiceRoute

## 示例 2

检索 Route1 语音路由的属性。

    Get-CsVoiceRoute -Identity Route1

## 示例 3

此命令显示标识值的任意位置包含字符串“test”的语音路由设置。要查找字符串 test 仅出现在标识结尾的情况，请使用值 \*test。与此类似，要查找字符串 test 仅出现在标识开头的情况，请指定值 test\*。

    Get-CsVoiceRoute -Filter *test*

## 示例 4

此命令检索尚未分配任何 PSTN 网关的所有语音路由。首先，使用 **Get-CsVoiceRoute** cmdlet 检索所有语音路由。然后，将这些语音路由通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 可缩小 Get 操作的结果范围。在此示例中，我们将查看每个语音路由（通过 $\_ 表示），并检查 PstnGatewayList 属性的 Count 属性。如果 PSTN 网关的计数为 0，则列表为空，没有为路由定义任何网关。

    Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList.Count -eq 0}

## 详细说明

使用此 cmdlet 可检索一个或多个现有的语音路由。语音路由包含一些说明，指示 Lync Server 如何将来自企业语音用户的呼叫路由到公用电话交换网 (PSTN) 或专用交换机 (PBX) 上的电话号码。

此 cmdlet 可用于检索语音路由信息，例如与路由关联的 PSTN 网关（如果有）、与路由关联的 PSTN 用法、识别路由所应用到的电话号码的模式（采用正则表达式形式）以及呼叫者 ID 设置。PSTN 用法将语音路由与某个语音策略相关联。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsVoiceRoute** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoiceRoute"}

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>此参数根据传递给它的通配符值筛选 Get 操作的结果。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一标识语音路由的字符串。如果未提供标识，则将返回组织的所有语音路由。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而非中央管理存储本身检索语音路由。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

此 cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route 对象的实例。

## 另请参阅

#### 其他资源

[New-CsVoiceRoute](new-csvoiceroute.md)  
[Remove-CsVoiceRoute](remove-csvoiceroute.md)  
[Set-CsVoiceRoute](set-csvoiceroute.md)  
[Test-CsVoiceRoute](test-csvoiceroute.md)

