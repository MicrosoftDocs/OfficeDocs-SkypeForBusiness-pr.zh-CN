---
title: Disable-CsComputer
TOCTitle: Disable-CsComputer
ms:assetid: e64128f1-2b53-4569-bf37-90cbbba01b36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399023(v=OCS.15)
ms:contentKeyID: 49314570
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsComputer

 

_**上一次修改主题：** 2015-03-09_

禁用已从运行 Lync Server 的计算机中删除的服务或服务器角色。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Disable-CsComputer [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-Scorch <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令禁用本地计算机。

    Disable-CsComputer 

## 示例 2

示例 2 中显示的命令也将禁用本地计算机。但是除了禁用计算机之外，此命令还将有关该任务的成功（或失败）的信息记录到文件 C:\\Logs\\Disable.html 中。通过添加 Report 参数并后跟要将信息记录到其中的日志文件的路径，将生成此日志文件。

    Disable-CsComputer -Report C:\Logs\Disable.html

## 详细说明

从计算机中删除服务或服务器角色不会自动更新 Lync Server 拓扑。在拓扑中完全更新这些更改之前，必须禁用该服务或角色。**Disable-CsComputer** cmdlet 为管理员提供了一种方法，用于禁用已从本地计算机中删除的所有服务或服务器角色。

如果不使用 Scorch 参数，**Disable-CsComputer** cmdlet 不会卸载 Lync Server 软件；这只会使计算机停止以先前分配的角色运行。

谁能运行此 cmdlet：只有本地管理员和域成员才能在本地运行 **Disable-CsComputer** cmdlet。

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
<td><p><em>GlobalCatalog</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>域中的全局编录服务器的完全限定域名 (FQDN)。如果使用域中的帐户在计算机上运行 <strong>Disable-CsComputer</strong> cmdlet，则不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>用于存储全局设置的域控制器的 FQDN。如果全局设置存储在 Active Directory 域服务 的“系统”容器中，则此参数必须指向根域控制器。如果全局设置存储在“配置”容器中，则可以使用任何域控制器，并且可以省略此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于指定在该 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\DisableComputer.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Scorch</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>卸载本地计算机的所有 Lync Server 服务和服务器角色。</p></td>
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

无。**Disable-CsComputer** cmdlet 不接受通过管道传递的输入。

## 返回类型

无。但 **Disable-CsComputer** cmdlet 禁用 Microsoft.Rtc.Management.Deploy.Internal.Machine 对象的实例。

## 另请参阅

#### 其他资源

[Enable-CsComputer](enable-cscomputer.md)  
[Get-CsComputer](get-cscomputer.md)  
[Test-CsComputer](test-cscomputer.md)

