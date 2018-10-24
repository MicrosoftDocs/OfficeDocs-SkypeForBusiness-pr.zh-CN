---
title: New-CsClientVersionConfiguration
TOCTitle: New-CsClientVersionConfiguration
ms:assetid: e7aac850-9e29-4d18-8929-74a89e9355cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399029(v=OCS.15)
ms:contentKeyID: 49314589
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsClientVersionConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建新客户端版本配置设置的集合。客户端版本配置设置确定 Lync Server 是否将检查登录到系统的每个客户端应用程序的版本号。如果已启用客户端版本筛选功能，则该客户端应用程序能否访问系统将基于相应客户端版本策略中配置的设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsClientVersionConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-DefaultAction <Allow | AllowWithUrl | Block | BlockWithUrl>] [-DefaultURL <String>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令为 Redmond 站点创建一个新的客户端版本配置设置集合。在此命令中，Enabled 参数设置为 False；这表示将对 Redmond 站点禁用客户端筛选功能。

    New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False

## 示例 2

示例 2 说明如何在内存中创建一个新的客户端版本配置设置集合、如何修改该集合，以及随后如何将这些虚拟设置转换为应用于 Redmond 站点的实际设置集合。为执行此操作，该命令首先使用 **New-CsClientVersionConfiguration** cmdlet 和 InMemory 参数创建一个 Identity 为 site:Redmond 且仅保存在内存中的设置集合。该集合存储在一个名为 $x 的变量中，并且仅存在于内存中：如果您终止 Windows PowerShell 会话或者删除变量 $x，则这些客户端版本配置设置将会消失，并且不会应用于 Redmond 站点。

在命令 2 中，将虚拟设置的 DefaultAction 属性的值设置为 Block。在命令 3 中，使用了 **Set-CsClientVersionConfiguration** cmdlet 将虚拟设置转换为一个应用于 Redmond 站点的实际的客户端版本配置设置集合。

    $x = New-CsClientVersionConfiguration -Identity site:Redmond -InMemory
    $x.DefaultAction = "Block" 
    Set-CsClientVersionConfiguration -Instance $x

## 详细说明

当管理员在指定用户可用于登录到系统的客户端软件（该软件的版本号同样重要）时，Lync Server 可使管理员有较大的选择余地。例如，不存在技术原因要求用户使用 Lync Server 登录到 Lync；没有技术限制可阻止用户使用 Microsoft Office Communicator 2007 R2 进行登录。

但是，可能存在一些非技术性原因，使您更希望用户不使用 Office Communicator 2007 R2 进行登录。例如，Office Communicator 2007 R2 并不支持 Lync 中的所有功能；因此，使用 Office Communicator 2007 R2 登录的用户与使用 Lync 登录的用户将具有不同的体验。这会给用户带来难题；对于必须为许多不同的客户端应用程序提供支持的技术支持人员来说，这也会是难题。

如果这对您的组织是个问题，则您可以使用客户端版本筛选功能，以指定可用于登录到 Lync Server 的客户端应用程序。在安装 Lync Server 时，将会安装和启用一组全局客户端版本配置设置。这些设置用于确定是否启用客户端版本筛选功能。

除了全局设置外，**New-CsClientVersionConfiguration** cmdlet 还可用于在站点范围创建客户端版本配置设置。在站点范围应用客户端版本配置设置时，这些设置将优先于全局设置。例如，假设您在全局范围启用了客户端版本筛选功能，然后为 Redmond 站点创建了一个单独的设置集合，并且已对该集合禁用客户端版本筛选功能。在这种情况下，将对在 Redmond 站点中具有帐户的所有用户禁用客户端版本筛选功能。

但请注意，匿名用户只受全局设置的影响。这是因为匿名用户不与网站关联。

请注意，客户端版本配置不是一种安全功能。该技术依赖于客户端应用程序的自我报告，它不会尝试验证一个应用程序是否确实是该应用程序，也不会尝试验证该应用程序的版本号是否与所声称的版本号相同。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsClientVersionConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsClientVersionConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>表示要分配给新的客户端版本配置设置集合的唯一标识符。由于您只能在站点范围中创建新集合，因此 Identity 将始终为前缀“site:”后跟站点名称；例如，“site:Redmond”。请注意，如果已存在 Identity 为 site:Redmond 的设置集合，上述命令将失败。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultAction</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.DefaultAction</p></td>
<td><p>指示当用户尝试从在相应客户端版本策略中未找到其版本号的客户端应用程序登录时要采取的操作。DefaultAction 必须设置为下列值之一：</p>
<p>Allow。允许客户端应用程序登录。</p>
<p>AllowWithUrl。允许客户端应用程序登录。此外，还会向用户显示一个消息框，其中包括一个网页的 URL，用户可以在该网页中下载已批准的客户端应用程序。应将该网页的 URL 指定为 DefaultUrl 属性的值。</p>
<p>Block。阻止客户端应用程序登录。</p>
<p>BlockWithUrl。阻止客户端应用程序登录。但是，向用户显示的“访问被拒绝”消息框将包括一个网页的 URL，用户可以在该网页中下载已批准的客户端应用程序。应将该网页的 URL 指定为 DefaultUrl 属性的值。</p>
<p>如果 Enabled 属性设置为 False，将忽略该属性。当 Enabled 属性设置为 False 时，将不会进行任何类型的客户端版本筛选。</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultURL</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>指定用户可在其中下载已批准客户端应用程序的网页的 URL。如果指定了该 URL，并且将 DefaultAction 设置为 BlockWithURL，则无论何时用户尝试使用不受支持的客户端应用程序进行登录，此 URL 都会出现在“访问被拒绝”消息框中。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>指示是启用还是禁用客户端版本筛选功能。如果 Enabled 属性设置为 True，则服务器将检查尝试登录的每个客户端应用程序的版本号；然后，服务器将根据相应的客户端版本策略允许或拒绝访问。如果 Enabled 属性设置为 False，则将允许能够登录的任何客户端应用程序进行登录。</p>
<p>默认值为 True。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

无。**New-CsClientVersionConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

创建 Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration 对象的新实例。

## 另请参阅

#### 其他资源

[Get-CsClientVersionConfiguration](get-csclientversionconfiguration.md)  
[Remove-CsClientVersionConfiguration](remove-csclientversionconfiguration.md)  
[Set-CsClientVersionConfiguration](set-csclientversionconfiguration.md)

