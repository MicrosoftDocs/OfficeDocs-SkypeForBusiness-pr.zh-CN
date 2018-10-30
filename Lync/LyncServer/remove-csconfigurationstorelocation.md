---
title: Remove-CsConfigurationStoreLocation
TOCTitle: Remove-CsConfigurationStoreLocation
ms:assetid: 141be225-c6e4-4377-913b-ba61528929d4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398214(v=OCS.15)
ms:contentKeyID: 49312086
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConfigurationStoreLocation

 

_**上一次修改主题：** 2015-03-09_

删除中央管理存储的 Active Directory 服务控制点。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsConfigurationStoreLocation [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令删除中央管理存储的 Active Directory 服务控制点。要还原此 SCP（或创建新的 SCP），必须运行 **Set-CsConfigurationStoreLocation** cmdlet。

    Remove-CsConfigurationStoreLocation

## 示例 2

示例 2 也删除中央管理存储的 Active Directory 服务控制点。除了删除 SCP 外，此命令还会将有关该操作成功（或失败）的信息记入日志文件 C:\\Logs\\Store\_Location.html。为了创建该日志文件，此命令使用 Report 参数，后跟应将信息记入的日志文件的路径。如果该文件已存在，运行此命令时将覆盖其内容。如果该文件不存在，则运行此命令时将创建该文件。

    Remove-CsConfigurationStoreLocation -Report C:\Logs\Store_Location.html

## 详细说明

Active Directory 域服务 使用服务控制点 (SCP) 帮助计算机查找服务。例如，安装 Lync Server 时将创建一个 SCP，为中央管理存储提供用于维护 Lync Server 数据的位置信息。需要访问该数据库的计算机连接到 Active Directory，并使用 SCP 中包含的信息帮助这些计算机查找正确的计算机和 SQL Server 的正确实例。

如前所述，安装 Lync Server 时，将自动为您创建中央管理存储的 SCP。通常，您不需要删除该 SCP；如果删除该 SCP，计算机将无法找到数据库。但是，有时（可能是在解决问题时）将需要您删除 SCP。为此，可使用 **Remove-CsConfigurationStoreLocation** cmdlet。删除 SCP 后，可以使用 **Set-CsConfigurationStoreLocation** cmdlet 重新创建它（或者创建一个新的服务控制点）。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsConfigurationStoreLocation** cmdlet：RTCUniversalServerAdmins。

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
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>用于存储全局设置的域控制器的完全限定域名 (FQDN)。如果全局设置存储在 Active Directory 的“系统”容器中，则此参数必须指向根域控制器。如果全局设置存储在“配置”容器中，则可以使用任何域控制器，并且可以省略此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于指定在该 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
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

无。**Remove-CsConfigurationStoreLocation** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Remove-CsConfigurationStoreLocation** cmdlet 不返回任何对象或值。

## 另请参阅

#### 其他资源

[Get-CsConfigurationStoreLocation](get-csconfigurationstorelocation.md)  
[Set-CsConfigurationStoreLocation](set-csconfigurationstorelocation.md)

