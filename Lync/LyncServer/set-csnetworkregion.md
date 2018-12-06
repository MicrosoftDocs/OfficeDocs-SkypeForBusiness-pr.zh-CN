---
title: Set-CsNetworkRegion
TOCTitle: Set-CsNetworkRegion
ms:assetid: ffa1774b-ac60-4392-ad55-07bb887bf945
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413089(v=OCS.15)
ms:contentKeyID: 49314853
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkRegion

 

_**上一次修改主题：** 2015-03-09_

修改现有的网络区域。网络区域表示企业网络中的网络中心或主干网络。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkRegion [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkRegion [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AudioAlternatePath <$true | $false>] [-BWAlternatePaths <PSListModifier>] [-BypassID <String>] [-CentralSite <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-VideoAlternatePath <$true | $false>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在此示例中，修改名为 NorthAmerica 的网络区域。为 Description 参数提供了值“North American Region”。如果 NorthAmerica 区域已存在 Description，此命令将使用该值覆盖它。如果尚未设置 Description，此命令会进行设置。

    Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"

## 示例 2

此示例修改名为 EMEA 的网络区域，并为其提供一个新的视频备用路径设置。为执行此操作，我们调用 **Set-CsNetworkRegion** cmdlet，并向其传递 Identity EMEA。然后指定 VideoAlternatePath 参数并传递值 $False。将 VideoAlternatePath 设置为 False 表明，如果没有足够的可用带宽，视频呼叫将不会路由至备用路径，最终无法完成。

    Set-CsNetworkRegion -Identity EMEA -VideoAlternatePath $False

## 示例 3

示例 3 向 Asia 网络区域分配与 NorthAmerica 区域相同的备用路径设置集。此示例中的第一行检索网络区域 NorthAmerica 的一个实例，并将其分配给变量 $a。第二行首先检索 BWAlternatePaths 属性或 NorthAmerica 区域（存储在变量 $a 中）的内容：$a.BWAlternatePaths。检索结果应该是 NorthAmerica 区域中所有备用路径设置的集合。

接下来，我们将此设置集合通过管道传递到 foreach 函数。foreach 每次循环选择该集合中的一项，并执行后面的花括号中的操作。在此示例中，该操作是调用 Identity 为 Asia 的 **Set-CsNetworkRegion** cmdlet 以设置 Asia 区域的属性。下一个参数是 BWAlternatePaths。向此参数传递值 @{add=$\_}。变量 $\_ 代表该集合中的当前项，在此示例中是当前备用路径。值的 @{add=} 部分会将该项添加到 Asia 区域的 BWAlternatePaths 集合。

    $a = Get-CsNetworkRegion -Identity NorthAmerica
    $a.BWAlternatePaths | foreach {Set-CsNetworkRegion -Identity Asia -BWAlternatePaths @{add=$_}}

## 详细说明

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。使用此 cmdlet 可修改现有的网络区域，包括确定是否允许音频和视频连接使用备用路径以及将区域内的站点与媒体旁路配置相关联的设置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkRegion** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkRegion\\b"}

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
<td><p><em>AudioAlternatePath</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数确定当主要路径带宽不足时，是否通过备用路径路由音频呼叫。</p>
<p>此参数填充 BWAlternatePaths 属性。为此参数提供的值存储在 BWPolicyModality 值为 Audio 的备用路径元素的 AlternatePath 属性中。</p>
<p>如果为此参数提供值，则不能为 BWAlternatePaths 参数指定值。</p>
<p>如果您的某一呼叫是 Internet 呼叫，则无论带宽设置为何，该值必须设置为 True。</p></td>
</tr>
<tr class="even">
<td><p><em>BWAlternatePaths</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>对象列表，这些对象包含有关当无法通过首选路径完成媒体请求时（例如，已超过该路径的限制），是否允许使用备用连接路径的信息。备用路径对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWAlternatePathType。可以通过调用 <strong>New-CsNetworkBWAlternatePath</strong> cmdlet 创建此类型的对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>BypassID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>全局唯一标识符 (GUID)。此 GUID 用于将网络区域映射到 CAC 或增强型 9-1-1 (E9-1-1) 网络配置中的媒体旁路设置。（请在调用 <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet 时使用此 BypassID 值。）</p>
<p>此参数可以在创建区域（通过调用 <strong>New-CsNetworkRegion</strong> cmdlet）时自动生成。建议不要更改此值。如果确实要指定一个值，那么该值必须采用 GUID 形式（例如 3b24a047-dce6-48b2-9f20-9fbff17ed62a）。您将收到确认，提示您确认是否要手动设置该值。</p></td>
</tr>
<tr class="even">
<td><p><em>CentralSite</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>运行带宽策略服务的中央站点。必须启用该服务才能使用 CAC。此服务在前端服务器或 Standard Edition Server 上运行。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于描述区域的字符串。此参数可用于说明区域的用途，与只用 Identity 表示相比，该说明更具描述性。</p></td>
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
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的网络区域的唯一标识符。Identity 将采用唯一标识该区域的字符串的形式。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>PSObject</p></td>
<td><p>对网络区域对象的引用。该对象的类型必须是 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType，可以通过调用 <strong>Get-CsNetworkRegion</strong> cmdlet 来检索该对象类型。</p></td>
</tr>
<tr class="even">
<td><p><em>VideoAlternatePath</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数确定当主要路径带宽不足时，是否通过备用路径路由视频呼叫。</p>
<p>此参数填充 BWAlternatePaths 属性。为此参数提供的值存储在 BWPolicyModality 值为 Video 的备用路径元素的 AlternatePath 属性中。</p>
<p>如果为此参数提供值，则不能为 BWAlternatePaths 参数指定值。</p>
<p>如果您的某一呼叫是 Internet 呼叫，则无论带宽设置为何，该值必须设置为 True。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType 对象。接受通过管道传递的网络区域对象的输入。

## 返回类型

此 cmdlet 不会返回值。它可修改类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Remove-CsNetworkRegion](remove-csnetworkregion.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[New-CsNetworkBWAlternatePath](new-csnetworkbwalternatepath.md)

