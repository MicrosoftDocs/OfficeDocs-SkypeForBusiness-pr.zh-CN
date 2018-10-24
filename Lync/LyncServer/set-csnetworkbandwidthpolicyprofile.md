---
title: Set-CsNetworkBandwidthPolicyProfile
TOCTitle: Set-CsNetworkBandwidthPolicyProfile
ms:assetid: 519916b9-d5a0-476e-a516-9b8a3058daf2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398338(v=OCS.15)
ms:contentKeyID: 49312843
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkBandwidthPolicyProfile

 

_**上一次修改主题：** 2015-03-09_

修改现有的网络带宽策略配置文件。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkBandwidthPolicyProfile [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkBandwidthPolicyProfile [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AudioBWLimit <String>] [-AudioBWSessionLimit <String>] [-BWPolicy <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-VideoBWLimit <String>] [-VideoBWSessionLimit <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例修改 Identity 为 LowBWProfile 的带宽策略配置文件的描述。这是通过调用带有以下两个参数的 **Set-CsNetworkBandwidthPolicyProfile** cmdlet 实现的：Identity 参数，用于指定要修改的配置文件的名称；以及 Description 参数，用于指定配置文件的新描述。

    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile -Description "Policy for links of less than 10MB"

## 示例 2

示例 2 修改 Identity 为 LowBWLimit 的带宽策略配置文件的视频传输的总体限制和会话限制。指定要修改的配置文件的 Identity 后，接下来我们使用 VideoBWLimit 参数将总体视频限制设置为 2500。然后，使用 VideoBWSessionLimit 参数将单个会话限制设置为 300。此命令将添加一个视频配置文件或者更新 LowBWLimit 带宽策略配置文件的现有视频配置文件。所有现有的音频配置文件都不受影响。

    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300

## 示例 3

在此示例中，将创建一个新的带宽策略并将其分配给 Identity 为 LowBWLimit 的带宽策略配置文件。此示例中的第一行调用 **New-CsNetworkBWPolicy** cmdlet。此 cmdlet 用于创建一个新的配置文件；在此示例中，创建了一个总体限制为 5000 kbps (-BWLimit 5000) 且会话限制为 200 kbps (-BWSessionLimit 200) 的视频配置文件（-BWPolicyModality 视频）。此新配置文件对象存储在变量 $bp 中。此示例中的下一行调用 **Set-CsNetworkBandwidthPolicyProfile** cmdlet 以修改配置文件 LowBWLimit (-Identity LowBWLimit)。BWPolicy 参数与 $bp 的值一起使用。这会将此配置文件中的任何现有策略替换为新创建且存储在 $bp 变量中的策略。

    $bp = New-CsNetworkBWPolicy -BWLimit 5000 -BWSessionLimit 200 -BWPolicyModality video
    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -BWPolicy $bp

## 示例 4

示例 4 将一个新的音频带宽策略添加到配置文件 LowBWProfile 中的现有策略集。在第 1 行中，我们调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet 以检索 Identity 为 LowBWProfile 的配置文件。该配置文件存储在变量 $a 中。在下一行中，调用 **New-CsNetworkBWPolicy** cmdlet 以创建一个新的带宽策略。此策略是一个音频策略（-BWPolicyModality 音频），其总体限制为 2000 kbps (-BWLimit 2000)，会话限制为 300 kbps (-BWSessionLimit 300)。此新策略存储在变量 $ap 中。

在第 3 行中，将这个新的音频策略（存储在 $ap 中）添加至在第 1 行中检索到的配置文件（存储在变量 $a 中）。这是通过对该配置文件的 BWPolicy 属性调用 Add 方法并传递 $ap 的值实现的。这可以理解为“将存储在 $ap 中的新策略添加到配置文件 LowBWProfile（存储在 $a 中）的 BWPolicy”。

最后，调用 **Set-CsNetworkBandwidthPolicyProfile** cmdlet 以更新 LowBWProfile 配置文件。我们使用 Instance 参数并传递 $a 的值，该值包含已修改的配置文件。

    $a = Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
    $ap = New-CsNetworkBWPolicy -BWLimit 2000 -BWSessionLimit 300 -BWPolicyModality audio
    $a.BWPolicy.Add($ap)
    Set-CsNetworkBandwidthPolicyProfile -Instance $a

## 示例 5

示例 5 在功能上与示例 4 完全相同：它将一个新的音频策略添加到配置文件 LowBWProfile 的现有策略列表中。此方法所需要的代码行更少，但可能不太清晰。此处列出该方法只是为了说明可以用不同方法实现相同的功能。

在第一行中，我们创建一个新的音频带宽策略，并设置带宽限制 (2000) 和会话限制 (300)，以及将新对象存储在变量 $ap 中。接下来，调用 **Set-CsNetworkBandwidthPolicyProfile** cmdlet 以修改 Identity 为 LowBWProfile 的配置文件。我们使用 BWPolicy 参数来修改该配置文件中的策略列表。请注意传递给此参数的值：@{add=$ap}。这只是 Windows PowerShell 中一种用于向列表中添加对象的方法。该参数值以 @ 符号开头，后跟一组大括号 {}。在这些大括号中，可以指定要对列表执行的操作，在此示例中是将对象添加到列表。（您也可以执行删除或替换操作。）操作 (add) 后面跟有一个等号，然后是要添加到列表的对象，在此示例中为存储在变量 $ap 中的新策略。

    $ap = New-CsNetworkBWPolicy -BWLimit 2000 -BWSessionLimit 300 -BWPolicyModality audio
    Set-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile -BWPolicy @{add=$ap}

## 详细说明

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。（在 Lync Server 中，只能为音频和视频形式指定带宽限制。）此 cmdlet 可修改这些策略的容器配置文件。

重要提示：如果配置文件包含多个策略（例如，一个音频策略和一个视频策略），则通过 AudioBWLimit、AudioBWSessionLimit、VideoBWLimit 或 VideoBWSessionLimit 属性来修改配置文件将删除配置文件中的所有现有策略，并将它们替换为新的值。如果配置文件中包含一个用于限制视频的策略，但您仅设置了 AudioBWLimit 参数，则会删除该视频策略并创建一个音频策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkBandwidthPolicyProfile** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkBandwidthPolicyProfile"}

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
<td><p><em>AudioBWLimit</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要为所有音频连接分配的最大带宽大小。如果某个音频会话将导致超过音频带宽限制，则不允许启动该会话。</p>
<p>此参数以 kbps 表示。例如，值 1000 表示 1000 kbps。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 AudioBWSessionLimit 参数提供值，而不为 AudioBWLimit 提供值，AudioBWLimit 将使用默认值 0。</p></td>
</tr>
<tr class="even">
<td><p><em>AudioBWSessionLimit</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要为每个音频会话分配的最大带宽大小。此参数以 kbps 表示。值必须为 40 或更大。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 AudioBWLimit 参数提供值，而不为 AudioBWSessionLimit 提供值，AudioBWSessionLimit 将使用默认值 175。</p></td>
</tr>
<tr class="odd">
<td><p><em>BWPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>包含带宽策略配置文件的对象列表。该列表中的每个对象都由带宽形式（音频或视频）、带宽限制和带宽会话限制组成。</p>
<p>如果为此参数提供值，则不能为 AudioBWLimit、AudioBWSessionLimit、VideoBWLimit 或 VideoBWSessionLimit 参数提供值。</p>
<p>该列表中的对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyType。可以通过调用 <strong>New-CsNetworkBWPolicy</strong> cmdlet 来创建此类型的对象，然后可以通过将生成的策略作为值分配给此参数来将该策略添加到配置文件。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>带宽策略配置文件的描述。例如，可以使用此参数阐明配置文件的期望用途。</p></td>
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
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一标识要修改的带宽策略配置文件的字符串值。此参数与配置文件的 BWPolicyProfileID 属性相同，并且可以通过更改该属性的值来进行更改。这等效于“剪切和粘贴”操作：配置文件的所有属性均保持不变，只是名称发生更改。但是，如果已将配置文件分配给网络站点，则不能更改该值。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>BWPolicyProfileType</p></td>
<td><p>对包含要用于修改配置文件的设置的带宽策略配置文件对象（类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 的对象）的引用。可以通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 来检索此对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoBWLimit</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要为所有视频连接分配的最大带宽大小。如果某个视频会话将导致超过视频带宽限制，则不允许启动该会话。</p>
<p>此参数以 kbps 表示。例如，值 1000 表示 1000 kbps。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 VideoBWSessionLimit 参数提供值，而不为 VideoBWLimit 提供值，VideoBWLimit 将使用默认值 0。</p></td>
</tr>
<tr class="even">
<td><p><em>VideoBWSessionLimit</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要为每个视频会话分配的最大带宽大小。此参数以 kbps 表示。值必须为 100 或更大。</p>
<p>如果为此参数提供值，则不能为 BWPolicy 参数提供值。</p>
<p>默认值：如果为 VideoBWLimit 参数提供值，而不为 VideoBWSessionLimit 提供值，VideoBWSessionLimit 将使用默认值 700。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 对象。接受通过管道传递的网络带宽策略配置文件对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkBWPolicy](new-csnetworkbwpolicy.md)

