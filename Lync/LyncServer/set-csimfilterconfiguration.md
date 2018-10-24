---
title: Set-CsImFilterConfiguration
TOCTitle: Set-CsImFilterConfiguration
ms:assetid: c2b08cc0-8261-4b8b-b2e9-5efa902ceb40
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412960(v=OCS.15)
ms:contentKeyID: 49314144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsImFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改现有即时消息 (IM) 筛选器配置。IM 筛选器设置用于阻止用户发送包含活动（可单击）超链接的即时消息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsImFilterConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsImFilterConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Action <Allow | Block | Warn>] [-AllowMessage <String>] [-BlockFileExtension <$true | $false>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-IgnoreLocal <$true | $false>] [-Prefixes <PSListModifier>] [-WarnMessage <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例中显示的命令对 Identity 为 site:Redmond 的 IM 筛选器配置禁用 URI 筛选。为了执行此任务，在调用 **Set-CsImFilterConfiguration** cmdlet 时指定了值为 $False 的 Enabled 参数。

    Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False

## 示例 2

示例 2 将一个新的 URI 前缀 (urn:) 添加到 site:Redmond 的 IM 筛选器配置禁止的前缀列表中。为添加新前缀，使用了 **Get-CsImFilterConfiguration** cmdlet 来检索 site:Redmond 的配置；表示该配置的返回对象存储在名为 $x 的变量中。检索相应设置后，在第 2 行中调用 Add() 方法来将 urn: 添加到存储在 Prefixes 属性中的前缀集。这会更改对象引用 $x 的值。为更改实际配置本身，第 3 行调用 **Set-CsImFilterConfiguration** cmdlet，并将 $x 作为唯一的参数值传递。

    $x = Get-CsImFilterConfiguration -Identity site:Redmond
    $x.Prefixes.Add("urn:")
    Set-CsImFilterConfiguration -Instance $x

## 示例 3

示例 3 与示例 2 执行完全相同的操作，但它在一行中执行操作。在此命令中，**Set-CsImFilterConfiguration** cmdlet 的 Prefixes 参数用于将 urn: 添加到前缀列表中。add 列表修饰符用于将该值添加到前缀列表中。

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{add="urn:"}

## 示例 4

在此示例中，将从 site:Redmond 的IM 筛选器配置禁止的前缀列表中删除前缀 urn:。此示例与示例 3 相同，不同之处在于，它不是调用 add 列表修饰符将前缀添加到列表中，而是调用 remove 修饰符来删除前缀。

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="urn:"}

## 详细说明

发送即时消息时，用户可能会在该消息文本中嵌入统一资源标识符 (URI)，以便将对话中的其他参与者指引到特定网站或共享。可以将 Lync Server 配置为阻止包含某些前缀的超链接，或者使这类超链接处于非活动状态。（也就是说，只单击该链接，这些参与者将无法转至 URI 所指向的站点；他们必须手动将链接复制并粘贴到浏览器中。）

通过 **Set-CsImFilterConfiguration** cmdlet，可以修改要筛选的 URI 前缀列表，以及在全局范围或特定站点内完全启用和禁用筛选功能。使用此 cmdlet，还可以更新向用户提供警告的各种消息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsImFilterConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsImFilterConfiguration"}

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
<td><p><em>Action</em></p></td>
<td><p>可选</p></td>
<td><p>UrlFilterAction</p></td>
<td><p>此参数的值确定当即时消息中包含超链接时将执行的操作：</p>
<p>Allow - 超链接带有下划线前缀，因此这些链接不再处于活动状态。另外，如果在 AllowMessage 属性中指定了消息，将会在包含超链接的每条即时消息的开头插入一条通知消息。</p>
<p>Block - 阻止发送包含活动超链接的消息，并且 Lync Server 向发送方发送一条错误消息。</p>
<p>Warn - 将包含活动超链接的消息发送给接收参与者，并在这些消息的开头插入一条警告消息。可以使用 WarnMessage 属性指定警告消息。如果指定了 Warn 但未输入 WarnMessage，则尽管 BlockFileExtension 属性的设置仍适用，但 IM 筛选功能将被禁用。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>AllowMessage</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>如果为此参数指定了值，则当 Action 属性的值设置为 Allow 时，将在包含超链接的每条消息的开头插入该字符串。您可以使用此消息来通知用户一些事项，例如单击未知链接的潜在危险，或者您所在组织的相关政策和要求。</p></td>
</tr>
<tr class="odd">
<td><p><em>BlockFileExtension</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果此参数设置为 True，则对于扩展名是由在 Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration 类（通过调用 <strong>Get-CsFileTransferFilterConfiguration</strong> cmdlet 进行检索）中定义的 Extensions 属性所指定的文件路径，当超链接中包含这种文件路径时，系统将阻止该超链接并返回给发送方一条错误消息。如果此参数设置为 False，将不会对文件路径和扩展名进行特殊检查。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>启用或禁用此功能。如果此参数设置为 True，将会对即时消息进行超链接扫描，并且会应用此配置中的规则。如果此参数设置为 False，则不会对消息进行超链接检查。</p>
<p>默认值：True</p></td>
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
<td><p>要修改的 IM 筛选器配置设置的唯一标识符。该值将为 global 或 site:&lt;站点名称&gt;，其中 &lt;站点名称&gt; 是应用配置的站点，例如 site:Redmond。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreLocal</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值控制是否对即时消息中传递的本地 Intranet URI 执行筛选。如果此参数设置为 True，将忽略在本地计算机的 Intranet 区域中定义的任何 URI。（本地计算机是指运行 IM 筛选器应用程序的前端服务器。）如果此参数设置为 False，将对所有超链接应用指定的筛选。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>ImFilterConfiguration</p></td>
<td><p>用于将对某个对象的引用传递到 cmdlet，而不是设置各个参数值。此 cmdlet 接受 Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.ImFilterConfiguration 类型的对象，可通过调用 <strong>Get-CsImFilterConfiguration</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>Prefixes</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>要筛选的 URI 前缀的列表。将根据指定的设置筛选即时消息中前缀与此列表中的一种前缀匹配的任何超链接。</p>
<p>默认值：callto:、file:、ftp.、ftp:、gopher:、href、http:、https:、ldap:、mailto:、news:、nntp:、sip:、sips:、tel:、telnet: 和 www*。</p></td>
</tr>
<tr class="odd">
<td><p><em>WarnMessage</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>当 Action 属性的值设置为 Warn 时，此参数包含将插入到包含超链接的每条即时消息的开头的警告消息。通常，此消息用于说明单击未知链接的潜在危险，或者引用您所在组织的相关政策和要求等事项。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.ImFilterConfiguration 对象。接受通过管道传递的 IM 筛选器配置对象的输入。

## 返回类型

**Set-CsImFilterConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.ImFilterConfiguration 对象的实例。

## 另请参阅

#### 其他资源

[New-CsImFilterConfiguration](new-csimfilterconfiguration.md)  
[Remove-CsImFilterConfiguration](remove-csimfilterconfiguration.md)  
[Get-CsImFilterConfiguration](get-csimfilterconfiguration.md)

