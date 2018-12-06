---
title: Export-CsConfiguration
TOCTitle: Export-CsConfiguration
ms:assetid: 7da7e133-e405-466c-a852-06a4fb678c59
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398627(v=OCS.15)
ms:contentKeyID: 49313382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsConfiguration

 

_**上一次修改主题：** 2015-03-09_

将您的 Lync Server 拓扑、策略和配置设置导出至文件。在升级、硬件故障或一些其他问题导致数据丢失后，此文件的功能之一是可用于将该信息恢复到中央管理存储。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Export-CsConfiguration [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>

    Export-CsConfiguration -FileName <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令将 Lync Server 数据从中央管理存储导出至名为 C:\\Config.zip 的文件。

    Export-CsConfiguration -FileName "C:\Config.zip"

## 详细说明

运行 Lync Server 服务或服务器角色的计算机必须具有当前拓扑的副本、当前配置设置和当前策略，然后才能以指定的角色进行工作。Lync Server 负责确保将该信息传递给需要它的每台计算机。

**Export-CsConfiguration** cmdlet 和 **Import-CsConfiguration** cmdlet 用于在中央管理存储升级期间备份和恢复您的 Lync Server 拓扑、配置设置和策略。**Export-CsConfiguration** cmdlet 可用于将数据导出到 .ZIP 文件，然后，您可使用 **Import-CsConfiguration** cmdlet 读取该 .ZIP 文件，并将拓扑、配置设置和策略恢复到中央管理存储。此后，Lync Server 的复制服务会将恢复的信息复制到运行 Lync Server 服务的其他计算机。

最初配置外围网络中的计算机（例如，边缘服务器）时，也会使用导出和导入配置数据功能。配置外围网络中的计算机时，必须首先使用 CsConfiguration cmdlet 执行手动复制：您将需要使用 **Export-CsConfiguration** cmdlet 导出配置数据，然后将 .ZIP 文件复制到外围网络中的计算机。此后，您就可以使用 **Import-CsConfiguration** cmdlet 和 LocalStore 参数导入该数据。您仅需要执行此操作一次；此后，将会自动执行复制。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Export-CsConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsConfiguration"}

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
<td><p><em>FileName</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>运行 <strong>Export-CsConfiguration</strong> cmdlet 时要创建的 .ZIP 文件的路径。例如：-FileName &quot;C:\Config.zip&quot;。请注意，调用 <strong>Export-CsConfiguration</strong> cmdlet 时，必须包括 FileName 或 AsBytes 参数，但不能同时包括二者。</p></td>
</tr>
<tr class="even">
<td><p><em>AsBytes</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>将拓扑信息作为字节数组返回；之后，返回的数据必须存储于变量中，以便供 <strong>Import-CsConfiguration</strong> cmdlet 使用。不能在同一个命令中同时使用 AsBytes 和 FileName。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。要将 Force 参数设置为 True，请使用以下语法：</p>
<p>-Force:$True</p></td>
</tr>
<tr class="even">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从本地计算机而不是从中央管理存储本身检索配置数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Export-CsConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

如果调用时带有 AsBytes 参数，则 **Export-CsConfiguration** cmdlet 将返回字节数组格式的配置信息。

## 另请参阅

#### 其他资源

[Import-CsConfiguration](import-csconfiguration.md)

