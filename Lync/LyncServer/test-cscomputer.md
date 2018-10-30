---
title: Test-CsComputer
TOCTitle: Test-CsComputer
ms:assetid: 0b33d951-510d-445c-9b01-c6431fda6d47
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398162(v=OCS.15)
ms:contentKeyID: 49311959
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsComputer

 

_**上一次修改主题：** 2015-03-09_

**Test-CsComputer** cmdlet 验证在本地计算机上运行的 Lync Server 服务的状态。此 cmdlet 还验证是否已将适当的 Lync Server Active Directory 组添加到计算机上相应的本地组，以及是否已打开必要的计算机防火墙端口。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsComputer [-Report <String>]

## 示例

## 示例 1

示例 1 中显示的命令验证本地计算机的服务激活状态。命令中加入 Verbose 参数以确保在屏幕上完整报告成功（或失败）的操作。

    Test-CsComputer -Verbose

## 示例 2

示例 2 还验证本地计算机的服务激活状态。此外，此命令将有关激活状态的详细信息写入文件 C:\\Logs\\Computer.html。通过加入 Report 参数，后跟应记录信息的日志文件的完整路径生成此日志。

    Test-CsComputer -Verbose -Report C:\Logs\Computer.html

## 详细说明

**Test-CsComputer** cmdlet 是 Lync Server“综合事务”的一个示例。在 Lync Server 中使用综合事务可验证用户能否成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

**Test-CsComputer** cmdlet 只能在本地计算机上运行，用于验证该计算机上所有 Lync Server 服务的状态。此 cmdlet 还查看是否已在计算机上打开适当的防火墙端口，并确定是否已将在安装 Lync Server 时创建的 Active Directory 组添加到相应的本地组。例如，**Test-CsComputer** cmdlet 将验证是否已将 Active Directory 组 RTCUniversalUserAdmins 添加到本地 Administrators 组。

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
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可指定 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\Computer.html&quot;。如果此文件已存在，则运行此 cmdlet 时将覆盖此文件。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsComputer** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsComputer** cmdlet 将返回 Microsoft.Rtc.SyntheticTransactions.TaskOutput 对象的实例。

## 另请参阅

#### 其他资源

[Disable-CsComputer](disable-cscomputer.md)  
[Enable-CsComputer](enable-cscomputer.md)  
[Get-CsComputer](get-cscomputer.md)

