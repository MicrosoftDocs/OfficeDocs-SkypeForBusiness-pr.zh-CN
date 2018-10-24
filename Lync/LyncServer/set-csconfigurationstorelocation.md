---
title: Set-CsConfigurationStoreLocation
TOCTitle: Set-CsConfigurationStoreLocation
ms:assetid: 1c69a872-8e78-4c78-ba27-f20f04dce59f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398258(v=OCS.15)
ms:contentKeyID: 49312176
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConfigurationStoreLocation

 

_**上一次修改主题：** 2015-03-09_

设置中央管理存储的 Active Directory 服务控制点。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsConfigurationStoreLocation -SqlServerFqdn <Fqdn> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalSettingsDomainController <Fqdn>] [-MirrorSqlInstanceName <String>] [-MirrorSqlServerFqdn <Fqdn>] [-Report <String>] [-SkipLookup <SwitchParameter>] [-SqlInstanceName <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令设置 Lync Server中央管理存储的 Active Directory 服务控制点。在此示例中，SCP 指向计算机 atl-sql-001.litwareinc.com 并指向 SQL Server 实例 Rtc。

    Set-CsConfigurationStoreLocation -SqlServerFqdn atl-sql-001.litwareinc.com -SqlInstanceName Rtc

## 示例 2

示例 2 中显示的命令是示例 1 中显示的命令的变体。此命令还设置 Lync Server 中央管理存储的 Active Directory SCP。此外，还将有关此操作的成功（或失败）的信息记录到文件 C:\\Logs\\Store\_Location.html。通过加入 Report 参数后跟日志文件的完整路径来生成此日志。

    Set-CsConfigurationStoreLocation -SqlServerFqdn atl-sql-001.litwareinc.com -SqlInstanceName Rtc -Report C:\Logs\Store_Location.html

## 详细说明

Active Directory 域服务 使用服务控制点 (SCP) 帮助计算机查找服务。例如，安装 Lync Server 时将创建一个服务控制点，它提供用于维护 Lync Server 数据的中央管理存储的位置信息。需要访问该数据库的计算机连接到 Active Directory，并使用 SCP 中包含的信息帮助这些计算机查找正确的计算机和 SQL Server 的正确实例。

如前所述，安装 Lync Server 时，会自动为您创建中央管理存储的 SCP。如果需要将该数据库移至其他计算机或者需要将该数据库移至 SQL Server 的不同实例，将需要更新相应的服务控制点。可使用 **Set-CsConfigurationStoreLocation** cmdlet 执行此任务。运行 **Set-CsConfigurationStoreLocation** cmdlet 时，将在 Active Directory 中搜索由 SqlServer 参数指定的计算机。然后，此 cmdlet 会将存储位置设置为该计算机的 FQDN。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsConfigurationStoreLocation** cmdlet：RTCUniversalServerAdmins。

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
<td><p><em>SqlServerFqdn</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>已安装中央管理存储的计算机的完全限定域名 (FQDN)。例如：-SqlServer atl-sql-001.litwareinc.com。</p></td>
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
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>用于存储全局设置的域控制器的 FQDN。如果全局设置存储在 Active Directory 的“系统”容器中，则此参数必须指向根域控制器。如果全局设置存储在“配置”容器中，则可以使用任何域控制器，并且可以省略此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>MirrorSqlInstanceName</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>包含 Lync Server 镜像数据库表和数据的 SQL Server 实例的名称。例如：-SqlInstanceName &quot;rtc&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>MirrorSqlServerFqdn</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>已安装中央管理存储镜像数据库的计算机的完全限定域名 (FQDN)。例如：-SqlServer atl-mirror-001.litwareinc.com。</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可指定 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>SkipLookup</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果包含此参数，<strong>Set-CsConfigurationStoreLocation</strong> cmdlet 将不验证指定计算机和 SQL Server 的指定实例是否可用，而是只会更改服务控制点。</p>
<p>如果不加入此参数，则指定计算机和 SQL Server 的指定实例必须可用，然后才能更改 SCP。</p></td>
</tr>
<tr class="odd">
<td><p><em>SqlInstanceName</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>包含 Lync Server 表和数据的 SQL Server 实例的名称。例如：-SqlInstanceName &quot;rtc&quot;。</p></td>
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

无。**Set-CsConfigurationStoreLocation** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Set-CsConfigurationStoreLocation** cmdlet 不返回任何对象或值。

## 另请参阅

#### 其他资源

[Get-CsConfigurationStoreLocation](get-csconfigurationstorelocation.md)  
[Remove-CsConfigurationStoreLocation](remove-csconfigurationstorelocation.md)

