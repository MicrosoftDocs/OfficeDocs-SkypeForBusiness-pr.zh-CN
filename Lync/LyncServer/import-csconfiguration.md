---
title: Import-CsConfiguration
TOCTitle: Import-CsConfiguration
ms:assetid: 9a9c27f2-313c-4327-aeed-c47852a831ec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398800(v=OCS.15)
ms:contentKeyID: 49313722
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsConfiguration

 

_**上一次修改主题：** 2015-03-09_

将您的 Lync Server 拓扑、策略和配置设置导入到中央管理存储或本地计算机中。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Import-CsConfiguration -ByteInput <Byte[]> <COMMON PARAMETERS>

    Import-CsConfiguration -FileName <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令将当前拓扑、配置设置和策略从名为 C:\\Config.zip 的文件导入到中央管理存储中。

    Import-CsConfiguration -FileName "C:\Config.zip"

## 示例 2

示例 2 说明最初如何将数据复制到外围网络中的计算机。在此示例中，配置数据已导出到名为 Config.zip 的文件中；然后，该文件被复制到了位于外围网络中的计算机上的 C:\\ 文件夹下。接下来，使用带有 LocalStore 参数的 Import-CsConfiguration 导入该数据，这将使该数据导入到本地计算机而不是中央管理存储中。

    Import-CsConfiguration -FileName "C:\Config.zip" -LocalStore

## 示例 3

示例 3 中显示的两个命令导出当前拓扑、配置设置和策略，然后将该数据导入到本地计算机中，所有操作均未使用 .ZIP 文件。为执行此操作，第一个命令使用 **Export-CsConfiguration** cmdlet 和 AsBytes 参数以字节数组的形式导出当前拓扑、配置设置和策略；此字节数组存储在名为 $x 的变量中。在第二个命令中，使用 **Import-CsConfiguration** cmdlet 和 ByteInput 参数导入存储在 $x 中的信息。LocalStore 参数使数据导入到本地计算机而不是中央管理存储中。最终结果是数据从中央管理存储复制到了本地计算机中。

    $x = Export-CsConfiguration -AsBytes
    Import-CsConfiguration -ByteInput $x -LocalStore

## 详细说明

运行 Lync Server 服务或服务器角色的计算机必须具有当前拓扑的副本、当前配置设置和当前策略等，然后才能以指定的角色进行工作。Lync Server 负责确保将该信息传递给需要它的每台计算机。

Import-CsConfiguration cmdlet 和 Export-CsConfiguration cmdlet 用于在中央管理存储升级期间备份和恢复您的 Lync Server 拓扑、配置设置和策略。**Export-CsConfiguration** cmdlet 可用于将数据导出到 .ZIP 文件，然后，您可使用 **Import-CsConfiguration** cmdlet 读取该 .ZIP 文件，并将拓扑、设置和策略恢复到 中央管理存储。此后，Lync Server 的复制服务会将恢复的信息复制到运行服务的计算机。

最初配置外围网络中的计算机（例如，边缘服务器）时，也会使用导出和导入配置数据功能。配置外围网络中的计算机时，必须首先使用 CsConfiguration cmdlet 执行手动复制：您将需要使用 **Export-CsConfiguration** cmdlet 导出配置数据，然后将 .ZIP 文件复制到外围网络中的计算机。此后，您就可以使用 **Import-CsConfiguration** cmdlet 和 LocalStore 参数导入该数据。您仅需要执行此操作一次；此后，将会自动执行复制。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Import-CsConfiguration** cmdlet：RTCUniversalServerAdmins。除了是 RTCUniversalServerAdmins 的成员，您还必须是本地管理员或有本地配置复制程序权限才能运行此 cmdlet。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsConfiguration"}

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
<td><p><em>ByteInput</em></p></td>
<td><p>必需</p></td>
<td><p>System.Byte[]</p></td>
<td><p>从变量中存储的字节数组读取拓扑信息。此字节数组是在调用 <strong>Export-CsConfiguration</strong> cmdlet 时，通过使用 ByteInput 参数创建的。</p>
<p>不能在同一个命令中同时使用 ByteInput 参数和 FileName 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>FileName</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>由 Export-CsConfiguration 创建的 .ZIP 文件的路径。例如：-FileName &quot;C:\Config.zip&quot;。请注意，在调用 <strong>Import-CsConfiguration</strong> cmdlet 时，您必须包括 FileName 或 ByteInput 参数，但不能同时包括二者。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果在运行此命令时出现非致命错误，请绕过因这些错误而显示的任何提示。要将 Force 参数设置为 True，请使用以下语法：</p>
<p>-Force:$True</p></td>
</tr>
<tr class="even">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>将配置数据复制到本地计算机而不是中央管理存储。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Import-CsConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Import-CsConfiguration** cmdlet 不会返回任何值或对象。

## 另请参阅

#### 其他资源

[Export-CsConfiguration](export-csconfiguration.md)

