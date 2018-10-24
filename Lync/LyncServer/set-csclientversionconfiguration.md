---
title: Set-CsClientVersionConfiguration
TOCTitle: Set-CsClientVersionConfiguration
ms:assetid: 7cd2e86f-2d31-4db2-9d0f-f1418fd4aba2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398623(v=OCS.15)
ms:contentKeyID: 49313374
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientVersionConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改指定的客户端版本配置设置的集合。客户端版本配置设置确定 Lync Server 是否将检查登录到系统的每个客户端应用程序的版本号。如果已启用客户端版本筛选功能，则该客户端应用程序能否访问系统将基于相应客户端版本策略中配置的设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsClientVersionConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClientVersionConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-DefaultAction <Allow | AllowWithUrl | Block | BlockWithUrl>] [-DefaultURL <String>] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在示例 1 中，**Set-CsClientVersionConfiguration** cmdlet 用于修改 Identity 为“site:Redmond”的设置集合。在此情况下，Enabled 参数设置为 False 以禁用客户端版本配置设置。

    Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False

## 示例 2

在示例 2 中，修改了组织中当前正在使用的所有客户端版本配置设置的 DefaultUrl 属性。为执行此操作，命令首先会调用不带任何其他参数的 **Get-CsClientVersionConfiguration** cmdlet，以返回所有客户端版本配置设置。然后，将该信息通过管道传递到 **Set-CsClientVersionConfiguration** cmdlet，从而将每个配置集合的 DefaultUrl 值设置为 https://litwareinc.com/csclients。

    Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"

## 示例 3

在示例 3 中，对 DefaultAction 当前设置为 Block 的所有客户端版本配置设置进行了修改。为完成此任务，该命令首先使用 **Get-CsClientVersionConfiguration** cmdlet 返回当前使用的所有客户端版本配置设置。然后，将该信息通过管道传递到 **Where-Object** cmdlet，后者会仅挑选 DefaultAction 属性等于“Block”的项目。反过来，将筛选出的集合通过管道传递到 **Set-CsClientVersionConfiguration** cmdlet，后者将对集合中的每个项执行两种操作：1) 将 DefaultAction 设置为 BlockWithUrl；和 2) 将 DefaultUrl 设置为 https://litwareinc.com/csclients。

    Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block"} | Set-CsClientVersionConfiguration -DefaultAction "BlockWithUrl" -DefaultURL "https://litwareinc.com/csclients"

## 详细说明

在指定用户可用于登录到系统的客户端软件和该软件的版本号（二者同等重要）时，Lync Server 为管理员提供了相当大的灵活性。例如，不存在技术原因要求用户使用 Lync Server 登录到 Lync；没有技术限制可阻止用户使用 Microsoft Office Communicator 2007 R2 进行登录。

另一方面，可能有一些非技术原因，您会更希望用户不使用 Office Communicator 2007 R2 进行登录。例如，Office Communicator 2007 R2 并不支持 Lync 中的所有功能；因此，使用 Office Communicator 2007 R2 登录的用户与使用 Lync 登录的用户将具有不同的体验。这会对用户造成困扰，同时也会困扰必须为各种不同的客户端应用程序提供支持的技术支持人员。

如果您的组织中可能存在此问题，可以使用客户端版本筛选功能，以指定可使用哪些客户端应用程序登录到 Lync Server。在安装 Lync Server 时，将会安装和启用一组全局客户端版本配置设置。这些设置可用于确定是否启用客户端版本筛选。除了全局设置之外，客户端版本配置设置也可在站点范围应用；在这些情况中，站点设置将优先于全局设置。

通过 **Set-CsClientVersionConfiguration** cmdlet，可以修改客户端版本配置设置的现有集合。

请注意，客户端版本配置不是安全功能。该技术依赖于客户端应用程序的自我报告，它不会尝试验证一个应用程序是否确实是该应用程序，也不会尝试验证该应用程序的版本号是否与所声称的版本号相同。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsClientVersionConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClientVersionConfiguration"}

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
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultAction</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.DefaultAction</p></td>
<td><p>指示当用户尝试从在相应客户端版本策略中未找到其版本号的客户端应用程序登录时要采取的操作。DefaultAction 必须设置为下列值之一：</p>
<p>Allow。允许客户端应用程序登录。</p>
<p>AllowWithUrl。允许客户端应用程序登录。此外，还会向用户显示一个消息框，其中包括一个网页的 URL，用户可以在该网页中下载已批准的客户端应用程序。应将该网页的 URL 指定为 DefaultUrl 属性的值。</p>
<p>Block。阻止客户端应用程序登录。</p>
<p>BlockWithUrl。阻止客户端应用程序登录。但是，向用户显示的“访问被拒绝”消息框将包括一个网页的 URL，用户可以在该网页中下载已批准的客户端应用程序。应将该网页的 URL 指定为 DefaultUrl 属性的值。</p>
<p>如果 Enabled 属性设置为 False，则忽略此属性。当 Enabled 属性设置为 False 时，将不会进行任何类型的客户端版本筛选。</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultURL</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>指定用户可在其中下载已批准客户端应用程序的网页的 URL。如果指定了该 URL，并且将 DefaultAction 设置为 BlockWithURL，则无论何时用户尝试使用不受支持的客户端应用程序进行登录，此 URL 都会出现在“访问被拒绝”消息框中。</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>表示是启用还是禁用客户端版本筛选。如果 Enabled 属性为 True，则服务器将对每个尝试登录的客户端应用程序进行版本号检查；然后，服务器将允许或拒绝访问，具体取决于相应的客户端版本号策略。如果 Enabled 属性设置为 False，则将允许能够登录的任何客户端应用程序进行登录。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>表示要修改的客户端版本配置设置的唯一标识符。要修改全局设置，请使用此类语法：-Identity global。要修改分配到站点范围的设置，请使用类似语法：&quot;site:Redmond&quot;。</p>
<p>如果不包括此参数，<strong>Set-CsClientVersionConfiguration</strong> cmdlet 将自动配置全局设置。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>客户端版本策略对象</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration 对象。**Set-CsClientVersionConfiguration** cmdlet 接受通过管道传递的客户端版本配置对象的实例。

## 返回类型

**Set-CsClientVersionConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsClientVersionConfiguration](get-csclientversionconfiguration.md)  
[New-CsClientVersionConfiguration](new-csclientversionconfiguration.md)  
[Remove-CsClientVersionConfiguration](remove-csclientversionconfiguration.md)

