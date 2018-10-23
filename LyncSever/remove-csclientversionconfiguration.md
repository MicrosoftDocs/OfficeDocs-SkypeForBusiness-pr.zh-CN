---
title: Remove-CsClientVersionConfiguration
TOCTitle: Remove-CsClientVersionConfiguration
ms:assetid: 42065d1d-a0ef-4fa4-826b-d65b14b343c9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425925(v=OCS.15)
ms:contentKeyID: 49312662
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClientVersionConfiguration

 

_**上一次修改主题：** 2015-03-09_

删除指定的客户端版本配置设置集合。客户端版本配置设置确定 Lync Server 是否将检查登录到系统的每个客户端应用程序的版本号。如果已启用客户端版本筛选功能，则该客户端应用程序能否访问系统将基于相应客户端版本策略中配置的设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsClientVersionConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令删除 Identity 为“site:Redmond”的客户端版本配置设置。

    Remove-CsClientVersionConfiguration -Identity site:Redmond

## 示例 2

在示例 2 中，将删除在站点范围应用的所有客户端版本配置设置。为完成此任务，该命令首先调用带有 Filter 参数的 **Get-CsClientVersionConfiguration** cmdlet；筛选器值“site:\*”可确保仅返回 Identity 以字符串值“site:”开头的客户端版本配置设置设置。然后，将筛选出的集合通过管道传递到 **Remove-CsClientVersionConfiguration** cmdlet，后者会删除集合中的每一项。

    Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## 示例 3

在示例 3 中，将删除当前已禁用的所有客户端版本配置设置。为执行此操作，该命令首先使用 **Get-CsClientVersionConfiguration** cmdlet 返回组织中当前使用的所有客户端版本配置设置的集合。返回这些数据后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅挑选 Enabled 属性等于 False 的设置。接下来，将筛选出的集合通过管道传递到 **Remove-CsClientVersionConfiguration** cmdlet，后者会删除集合中的每一项。

    Get-CsClientVersionConfiguration | Where-Object {$_.Enabled -eq $False} | Remove-CsClientVersionConfiguration

## 详细说明

当管理员在指定用户可用于登录到系统的客户端软件（该软件的版本号同样重要）时，Lync Server 可使管理员有较大的选择余地。例如，不存在技术原因要求用户使用 Lync Server 登录到 Lync；从技术角度来看，没有方法可阻止用户使用 Microsoft Office Communicator 2007 R2 进行登录。

但是，可能存在一些非技术性原因，使您更希望用户不使用 Office Communicator 2007 R2 进行登录。例如，Office Communicator 2007 R2 并不支持 Lync 中的所有功能；因此，使用 Office Communicator 2007 R2 登录的用户与使用 Lync 登录的用户将具有不同的体验。这会给用户带来难题；对于必须为许多不同的客户端应用程序提供支持的技术支持人员来说，这也会是难题。

如果您的组织中可能存在此问题，可以使用客户端版本筛选功能，以指定可使用哪些客户端应用程序登录到 Lync Server。在安装 Lync Server 时，将会安装和启用一组全局客户端版本配置设置。除了全局设置，客户端版本配置设置也可应用到站点范围。

可在以后使用 **Remove-CsClientVersionConfiguration** cmdlet 删除所创建的任何站点设置。请注意，您也可以针对全局设置运行 **Remove-CsClientVersionConfiguration** cmdlet。在这种情况下，不会删除全局设置，而会将全局属性重置为其默认值。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsClientVersionConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClientVersionConfiguration"}

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
<td><p>要删除的客户端版本配置设置的集合的唯一标识符。要删除全局集合，请使用以下语法：-Identity global。（请记住，此命令实际上不会删除全局设置，而是将全局属性全部重置为其默认值。）要删除一个站点集合，请使用类似如下的语法：-Identity site:Redmond。请注意，在指定 Identity 时不能使用通配符。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration 对象。**Remove-CsClientVersionConfiguration** cmdlet 接受通过管道传递的客户端版本配置对象的实例。

## 返回类型

无。但此 cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionConfiguration 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsClientVersionConfiguration](get-csclientversionconfiguration.md)  
[New-CsClientVersionConfiguration](new-csclientversionconfiguration.md)  
[Set-CsClientVersionConfiguration](set-csclientversionconfiguration.md)

