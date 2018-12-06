---
title: New-CsImFilterConfiguration
TOCTitle: New-CsImFilterConfiguration
ms:assetid: 1964cbf9-d7f1-4b4e-99d1-951ac42d82fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398244(v=OCS.15)
ms:contentKeyID: 49312145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsImFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建新的即时消息 (IM) 筛选器配置。IM 筛选器用于阻止用户发送包含活动超链接的即时消息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsImFilterConfiguration -Identity <XdsIdentity> [-Action <Allow | Block | Warn>] [-AllowMessage <String>] [-BlockFileExtension <$true | $false>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-IgnoreLocal <$true | $false>] [-InMemory <SwitchParameter>] [-Prefixes <PSListModifier>] [-WarnMessage <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在示例 1 中，使用 **New-CsImFilterConfiguration** cmdlet 创建一个 Identity 为 site:Redmond 的新 IM 筛选器配置。（由于未指定其他参数，因此将使用默认值创建这些设置。）

    New-CsImFilterConfiguration -Identity site:Redmond

## 示例 2

在此命令中，使用 **New-CsImFilterConfiguration** cmdlet 创建一个 Identity 为 site:Redmond 的新 IM 筛选器配置。由于指定了 Prefixes 参数，因此新配置将包含所有默认值（包括要筛选的默认前缀）以及两个附加 URI 前缀：rtsp:和 urn:。我们通过使用 add 列表修饰符将这些前缀添加到默认列表中，来添加这些前缀。

    New-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{add="rtsp:","urn:"}

## 示例 3

在此命令中，使用 **New-CsFileTransferFilterConfiguration** cmdlet 创建一个 Identity 为 site:Redmond 的新 IM 筛选器配置。除了使用的是 replace 而不是 add 列表修饰符外，此示例与示例 2 类似。这意味着所有默认 URI 前缀都将被替换为以下两个前缀（rtsp: 和 urn:）。因此，对于站点 Redmond，将只筛选即时消息中前缀为 rtsp: 或 urn: 的 URI。

    New-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{replace="rtsp:","urn:"}

## 详细说明

发送即时消息时，用户可能会在该消息文本中嵌入统一资源标识符 (URI)，以便将对话中的其他参与者指引到特定网站或共享。可以将 Lync Server 配置为阻止包含某些前缀的超链接，或者使这类超链接处于非活动状态。（也就是说，只单击该链接，这些参与者将无法转至 URI 所指向的站点；他们必须手动将链接复制并粘贴到浏览器中。）

通过 **New-CsImFilterConfiguration** cmdlet，可以定义要筛选的 URI 前缀的列表，此外还可以在特定站点内完全启用和禁用筛选功能。调用仅指定了 Identity 的 **New-CsImFilterConfiguration** cmdlet 时，将创建一个具有该标识的新配置，并使用一组将筛选的默认前缀填充该站点的前缀列表。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsImFilterConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsImFilterConfiguration"}

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
<td><p>XdsIdentity</p></td>
<td><p>用于指定 IM 筛选器配置的范围的唯一标识符。全局设置默认已存在，不能使用 <strong>New-CsImFilterConfiguration</strong> cmdlet 重新创建，但您可以通过将 Identity 指定为 site:&lt;站点名称&gt; 创建站点级设置（其中，&lt;站点名称&gt; 是将应用这些设置的站点的名称，例如 site:Redmond）。</p>
<p>完整数据类型：Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
</tr>
<tr class="even">
<td><p><em>Action</em></p></td>
<td><p>可选</p></td>
<td><p>UrlFilterAction</p></td>
<td><p>此参数的值确定当即时消息中包含超链接时将执行的操作：</p>
<p>Allow - 超链接带有下划线前缀，因此这些链接不再处于活动状态。如果在 AllowMessage 属性中指定了消息，将会在包含超链接的每条即时消息的开头插入该消息。</p>
<p>Block - 阻止发送包含活动超链接的消息，并且 Lync Server 向发送方发送一条错误消息。</p>
<p>Warn - 将包含活动超链接的消息发送给接收参与者，并在这些消息的开头插入一条警告消息。可以使用 WarnMessage 属性指定警告消息。如果指定了 Warn 但未输入 WarnMessage，则尽管 BlockFileExtension 属性的设置仍适用，但 IM 筛选功能将被禁用。</p>
<p>默认值：Allow，除非一条消息中包含的 URL 数目超过 1,000 个，在这种情况下默认值为 Block。</p>
<p>完整数据类型：Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.UrlFilterAction</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowMessage</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>如果为此参数指定了值，则当 Action 属性的值设置为 Allow 时，将在包含超链接的每条消息的开头插入该字符串。您可以使用此消息来通知用户一些事项，例如单击未知链接的潜在危险，或者您所在组织的相关政策和要求。</p></td>
</tr>
<tr class="even">
<td><p><em>BlockFileExtension</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果此参数设置为 True，则对于扩展名是由在适用的文件传输筛选器配置（通过调用 <strong>Get-CsFileTransferFilterConfiguration</strong> cmdlet 进行检索）中定义的 Extensions 属性所指定的文件路径，当超链接中包含这种文件路径时，系统将阻止该超链接并返回给发送方一条错误消息。如果此参数设置为 False，将不会对文件扩展名进行特殊检查。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>启用或禁用此功能。如果此参数设置为 True，将会对即时消息进行超链接扫描，并且会应用此配置中的规则。如果此参数设置为 False，则不会对消息进行超链接检查。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreLocal</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值控制是否对即时消息中传递的本地 Intranet URI 执行筛选。如果此参数设置为 True，将忽略在本地计算机的 Intranet 区域中定义的任何 URI。（本地计算机是指运行 IM 筛选器应用程序的前端服务器。）如果此参数设置为 False，将对所有超链接应用指定的筛选。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.ImFilterConfiguration 的对象。

## 另请参阅

#### 其他资源

[Remove-CsImFilterConfiguration](remove-csimfilterconfiguration.md)  
[Set-CsImFilterConfiguration](set-csimfilterconfiguration.md)  
[Get-CsImFilterConfiguration](get-csimfilterconfiguration.md)

