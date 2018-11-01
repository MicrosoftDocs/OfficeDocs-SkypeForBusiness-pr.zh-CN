---
title: Get-CsConfigurationStoreLocation
TOCTitle: Get-CsConfigurationStoreLocation
ms:assetid: abfda147-02fa-46a5-a988-d83daf4cc455
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412814(v=OCS.15)
ms:contentKeyID: 49313927
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConfigurationStoreLocation

 

_**上一次修改主题：** 2015-03-09_

报告返回中央管理存储的 Active Directory 服务控制点的位置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsConfigurationStoreLocation [-GlobalSettingsDomainController <Fqdn>] [-Report <String>]

## 示例

## 示例 1

示例 1 中显示的命令将 SQL Server 路径返回到托管中央管理存储的计算机（或池）。

    Get-CsConfigurationStoreLocation

## 示例 2

示例 2 是示例 1 中显示的命令的变体；但是，此示例加入了 Report 参数以便为运行 **Get-CsConfigurationStoreLocation** cmdlet 时生成的报告指定路径。

    Get-CsConfigurationStoreLocation -Report "C:\Logs\ConfigurationStore.html"

## 详细说明

Active Directory 域服务 使用服务控制点 (SCP) 帮助计算机查找服务。例如，安装 Lync Server 时将创建一个服务控制点，它提供用于维护 Lync Server 数据的中央管理存储的位置信息。需要访问该数据库的计算机连接到 Active Directory，并使用 SCP 中包含的信息帮助这些计算机查找正确的计算机和 SQL Server 的正确实例。

**Get-CsConfigurationStoreLocation** cmdlet 用于向运行中央管理存储的计算机报告返回 SQL Server 路径（例如，atl-sql-001.litwareinc.com/rtc）。

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
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>用于存储全局设置的域控制器的完全限定域名 (FQDN)。如果全局设置存储在 Active Directory 的“系统”容器中，则此参数必须指向根域控制器。如果全局设置存储在“配置”容器中，则可以使用任何域控制器，并且可以省略此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以指定在该 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\ConfigurationStore.html&quot;</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsConfigurationStoreLocation** cmdlet 不接受通过管道传递的输入。

## 返回类型

字符串。**Get-CsConfigurationStoreLocation** cmdlet 报告返回配置存储的位置。

## 另请参阅

#### 其他资源

[Remove-CsConfigurationStoreLocation](remove-csconfigurationstorelocation.md)  
[Set-CsConfigurationStoreLocation](set-csconfigurationstorelocation.md)

