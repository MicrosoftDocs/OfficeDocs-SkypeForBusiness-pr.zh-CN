---
title: Test-CsCertificateConfiguration
TOCTitle: Test-CsCertificateConfiguration
ms:assetid: 8086bdf7-d283-4666-9f6c-0d5a3a31b3a6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398647(v=OCS.15)
ms:contentKeyID: 49313411
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsCertificateConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回有关本地计算机上正在使用的 Lync Server 证书的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsCertificateConfiguration [-Report <String>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关 Lync Server 当前正在本地计算机上使用的证书的信息。

    Test-CsCertificateConfiguration

## 示例 2

示例 2 中显示的命令是示例 1 中显示的命令的变体。但在此示例中，使用了 Report 参数为运行 **Test-CsCertificateConfiguration** cmdlet 时生成的输出文件指定文件路径 (C:\\Logs\\Certificates.xml)。

    Test-CsCertificateConfiguration -Report "C:\Logs\Certificates.xml"

## 详细说明

**Test-CsCertificateConfiguration** cmdlet 是“综合事务”的一个示例。Lync Server 中使用综合事务来验证用户是否能够成功完成常见任务，如登录系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。这些测试可以由管理员手动执行，也可以通过应用程序（如 Microsoft System Center Operations Manager（以前称为 Microsoft Operations Manager））自动运行。

**Test-CsCertificateConfiguration** cmdlet 返回有关 Lync Server 正在使用的证书的信息。**Test-CsCertificateConfiguration** cmdlet 主要供证书向导使用。建议管理员使用 **Get-CsCertificate** cmdlet 检索证书信息。

谁能运行此 cmdlet：要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsCertificateConfiguration"}

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
<td><p>用于指定在该 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\Certificates.html&quot;如果该文件已存在，运行此 cmdlet 时会将其覆盖。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Test-CsCertificateConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Test-CsCertificateConfiguration** cmdlet 返回 Microsoft.Rtc.Management.Deployment,CertificateExists 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCertificate](get-cscertificate.md)

