---
title: New-CsNetworkBandwidthPolicyProfile
TOCTitle: New-CsNetworkBandwidthPolicyProfile
ms:assetid: 84940891-37a6-45fc-972d-05b95aa71ba9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398675(v=OCS.15)
ms:contentKeyID: 49313461
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBandwidthPolicyProfile

 

_**上一次修改主题：** 2015-03-09_

创建新的网络带宽策略配置文件。此 cmdlet 还可用于设置配置文件中的带宽策略。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkBandwidthPolicyProfile -Identity <XdsGlobalRelativeIdentity> [-AudioBWLimit <String>] [-AudioBWSessionLimit <String>] [-BWPolicy <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-VideoBWLimit <String>] [-VideoBWSessionLimit <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 创建一个名为 LowBWLimits 的新带宽策略配置文件。此新配置文件将分配有两个策略，即一个音频策略和一个视频策略（Lync Server 中只可能存在这两个策略）。音频策略将通过以下操作添加到配置文件中：使用 AudioBWLimit 参数为总体音频连接分配限制（在此示例中为 2000 kbps），以及使用 AudioBWSessionLimit 参数分配 200 kbps 作为对单个音频会话的限制。创建视频会话限制所执行的操作相同，不过使用的是 VideoBWLimit 和 VideoBWSessionLimit 参数。

    New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500

## 详细说明

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。（在 Lync Server 中，只能为音频和视频形式指定带宽限制。）此 cmdlet 可为这些策略创建一个容器配置文件。调用此 cmdlet 时，可以通过指定音频和视频带宽限制来定义容器内的各个策略。

通过调用 **New-CsNetworkSite** cmdlet 或 **Set-CsNetworkSite** cmdlet，可将带宽策略配置文件应用于网络站点。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsNetworkBandwidthPolicyProfile** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBandwidthPolicyProfile"}

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
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一标识策略的字符串值。所有带宽策略配置文件都是在全局范围创建的。因此，该范围是隐式的，在创建新的带宽策略配置文件时只需指定一个唯一名称。请注意，该值还会填充配置文件的 BWPolicyProfileID 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>AudioBWLimit</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要为所有音频连接分配的最大带宽大小。如果某个音频会话将导致超过音频带宽限制，则不允许启动该会话。</p>
<p>此参数以 kbps 表示。例如，值 1000 表示 1000 kbps。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 AudioBWSessionLimit 参数提供值，而不为 AudioBWLimit 提供值，AudioBWLimit 将使用默认值 0。</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioBWSessionLimit</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要为每个音频会话分配的最大带宽大小。此参数以 kbps 表示。值必须为 40 或更大。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 AudioBWLimit 参数提供值，而不为 AudioBWSessionLimit 提供值，AudioBWSessionLimit 将使用默认值 175。</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>包含带宽策略配置文件的对象列表。该列表中的每个对象都由带宽形式（音频或视频）、带宽限制和带宽会话限制组成。</p>
<p>如果为此参数提供值，则不能为 AudioBWLimit、AudioBWSessionLimit、VideoBWLimit 或 VideoBWSessionLimit 参数提供值。</p>
<p>通过调用 <strong>New-CsNetworkBWPolicy</strong> cmdlet，可以创建列表中的对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>带宽策略配置文件的描述。例如，可以使用此参数阐明配置文件的期望用途。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoBWLimit</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要为所有视频连接分配的最大带宽大小。如果某个视频会话将导致超过视频带宽限制，则不允许启动该会话。</p>
<p>此参数以 kbps 表示。例如，值 1000 表示 1000 kbps。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 VideoBWSessionLimit 参数提供值，而不为 VideoBWLimit 提供值，VideoBWLimit 将使用默认值 0。</p></td>
</tr>
<tr class="even">
<td><p><em>VideoBWSessionLimit</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要为每个视频会话分配的最大带宽大小。此参数以 kbps 表示。值必须为 100 或更大。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 VideoBWLimit 参数提供值，而不为 VideoBWSessionLimit 提供值，VideoBWSessionLimit 将使用默认值 700。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 的对象。

## 另请参阅

#### 其他资源

[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkBWPolicy](new-csnetworkbwpolicy.md)

