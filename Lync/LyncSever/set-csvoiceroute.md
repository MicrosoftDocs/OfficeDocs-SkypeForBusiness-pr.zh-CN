---
title: Set-CsVoiceRoute
TOCTitle: Set-CsVoiceRoute
ms:assetid: b786aec0-946e-4ce5-812e-25e5d8cfa4d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412893(v=OCS.15)
ms:contentKeyID: 49314049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceRoute

 

_**上一次修改主题：** 2015-03-09_

修改语音路由。语音路由包含一些说明，指示 Lync Server 如何将来自企业语音用户的呼叫路由到公用电话交换网 (PSTN) 或专用交换机 (PBX) 上的电话号码。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsVoiceRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceRoute [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AlternateCallerId <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-NumberPattern <String>] [-Priority <Int32>] [-PstnGatewayList <PSListModifier>] [-PstnUsages <PSListModifier>] [-SuppressCallerId <$true | $false>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此命令将语音路由 Route1 的 Description 设置为“Test Route”。

    Set-CsVoiceRoute -Identity Route1 -Description "Test Route"

## 示例 2

此示例中的命令修改标识为 Route1 的语音路由，以将 PSTN 用法 Long Distance 添加到此语音路由的用法列表中。Long Distance 必须在全局 PSTN 用法列表中（可以通过调用 **Get-CsPstnUsage** cmdlet 检索该列表）。

    Set-CsVoiceRoute -Identity Route1 -PstnUsages @{add="Long Distance"}

## 示例 3

此示例修改名为 Route1 的语音路由，并使用组织的所有现有用法来填充该路由的 PSTN 用法列表。此示例中的第一个命令可检索全局 PSTN 用法的列表。请注意，对 **Get-CsPstnUsage** cmdlet 的调用位于括号中，这意味着将首先检索包含 PSTN 用法信息的对象。（由于只有一个全局 PSTN 用法，因此只会检索一个对象。）然后，该命令检索此对象的 Usage 属性。该属性（包含 PSTN 用法列表）将被分配给变量 $x。在此示例的第二行中，调用 **Set-CsVoiceRoute** cmdlet 以修改标识为 Route1 的语音路由。请注意传递给 PstnUsages 参数的值：@{replace=$x}。此值表示使用 $x 的内容替换该路由的 PstnUsages 列表中的所有内容，$x 包含在第 1 行中检索到的 PSTN 用法列表。

    $x = (Get-CsPstnUsage).Usage
    Set-CsVoiceRoute -Identity Route1 -PstnUsages @{replace=$x}

## 示例 4

这组命令将标识为 Route1 的语音路由的 Name 属性更改为 RouteA。更改 Name 属性将自动更改 Identity 属性，在此示例中，更改为 RouteA。

在第一行中，调用 **Get-CsVoiceRoute** cmdlet 以检索标识为 Route1 的语音路由。返回的对象存储在变量 $x 中。接下来，为该对象的 Name 属性分配字符串值“RouteA”。最后，将该对象（包含在变量 $x 中）传递到 **Set-CsVoiceRoute** cmdlet 的 Instance 参数，以执行更改。

    $x = Get-CsVoiceRoute -Identity Route1
    $x.Name = "RouteA"
    Set-CsVoiceRoute -Instance $x

## 示例 5

此示例修改名为 Route1 的语音路由，并使用标识为 PstnGateway:192.168.0.100 的网关的服务器角色来填充该路由的 PSTN 网关列表 (PstnGatewayList)。在此示例的第一行中，调用 **Get-CsVoiceRoute** cmdlet 检索要修改的语音路由，在此示例中为 Route1。接下来，针对 Route1 的 PstnGatewayList 属性调用 Add 方法。将要添加的服务的 Identity 传递给 Add 方法。最后，调用 **Set-CsVoiceRoute** cmdlet，将变量 $y 传递给 Instance 参数，该变量会使用新添加的 PSTN 网关更新 Route1（存储在 $y 中）。

    $y = Get-CsVoiceRoute -Identity Route1
    $y.PstnGatewayList.Add("PstnGateway:192.168.0.100")
    Set-CsVoiceRoute -Instance $y

## 详细说明

使用此 cmdlet 可修改现有的语音路由。语音路由通过公用电话交换网 (PSTN) 用法与语音策略相关联。语音路由包括一个正则表达式，用于标识要通过给定语音路由进行路由的电话号码：与该正则表达式匹配的电话号码将通过该路由进行路由。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsVoiceRoute** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceRoute"}

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
<td><p><em>AlternateCallerId</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>如果 SuppressCallerId 参数设置为 True，会将 AlternateCallerId 参数的值显示给接收方，而不是呼叫者的实际号码。该号码应该是一个有效的号码，可以用来代表组织中的部门，例如技术支持部或人力资源部。</p>
<p>如果 SuppressCallerId 参数设置为 False，则将忽略 AlternateCallerId 参数。</p>
<p>该值必须与正则表达式 (\+)?[1-9]\d*(;ext=[1-9]\d*)? 匹配。换句话说，该值可以（但非必须）以一个加号 (+) 开头；必须包含任意位数字；可后跟一个由 ;ext= 开头并后接任意位数字的分机。（请注意，如果要包含一个分机，则必须用双引号将字符串括起来。）</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>该电话路由用途的描述。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>语音路由的唯一标识。（如果路由名称中包含空格，例如“Test Route”，则必须用圆括号将整个字符串括起来。）</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>路由</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。此对象的类型必须是 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route，并且可以通过调用 <strong>Get-CsVoiceRoute</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="odd">
<td><p><em>NumberPattern</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于指定应用该路由的电话号码的正则表达式。将根据其余路由设置对与此模式匹配的号码进行路由。例如，默认号码模式 [0-9]{10} 指定一个由数字 0-9 组成的 10 位数号码。</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>数字可以解析为多个语音路由。如果可能有多个路由，则优先级确定将应用路由的顺序。</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnGatewayList</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>一个中介服务器可以与多个网关关联。该参数包含由与此语音路由关联的网关组成的列表。该列表的每个成员必须是 PSTN 网关或中介服务器的服务标识。仅当为 Microsoft Office Communications Server 2007 或 Microsoft Office Communications Server 2007 R2 配置中介服务器时，该值才可以引用中介服务器。对于 Lync Server，必须使用 PSTN 网关。服务标识是一个格式为 ServiceRole:FQDN 的字符串，其中 ServiceRole 是服务角色的名称 (PSTNGateway)，FQDN 是池的完全限定域名 (FQDN) 或服务器的 IP 地址。例如，PSTNGateway:redmondpool.litwareinc.com。通过调用命令 Get-CsService | Select-Object Identity 可以检索服务标识。</p>
<p>如果更改语音路由并将 PstnGatewayList 列表留空，或者所做的更改会删除该列表中的所有项，您将收到警告消息，提示您用户将无法进行 PSTN 呼叫。</p></td>
</tr>
<tr class="even">
<td><p><em>PstnUsages</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>可应用到该语音路由的 PSTN 用法（如 Local 或 Long Distance）的列表。PSTN 用法必须是现有用法。（可以通过调用 <strong>Get-CsPstnUsage</strong> cmdlet 来检索 PSTN 用法。）</p>
<p>如果更改语音路由并将 PstnUsages 列表留空，或者所做的更改会删除该列表中的所有 PSTN 用法，您将收到警告消息，提示您用户将无法进行 PSTN 呼叫。</p></td>
</tr>
<tr class="odd">
<td><p><em>SuppressCallerId</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>确定是否在出站呼叫中显示呼叫者的 ID。如果此参数设置为 True，将隐藏呼叫者 ID。将在实际 ID 的位置显示 AlternateCallerId 的值。当 SuppressCallerId 设置为 True 时，必须为 AlternateCallerId 提供值。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route 对象。**Set-CsVoiceRoute** cmdlet 接受通过管道传递的语音路由对象的输入。

## 返回类型

**Set-CsVoiceRoute** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.Route 对象的实例。

## 另请参阅

#### 其他资源

[New-CsVoiceRoute](new-csvoiceroute.md)  
[Remove-CsVoiceRoute](remove-csvoiceroute.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)  
[Test-CsVoiceRoute](test-csvoiceroute.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsService](get-csservice.md)

