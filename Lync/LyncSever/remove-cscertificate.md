---
title: Remove-CsCertificate
TOCTitle: Remove-CsCertificate
ms:assetid: b7a83a58-9d3f-458a-867e-44466c9817dc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412895(v=OCS.15)
ms:contentKeyID: 49314025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCertificate

 

_**上一次修改主题：** 2015-03-09_

删除先前标记为可供 Lync Server 使用的证书。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsCertificate -Type <CertType[]> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Identity <XdsIdentity>] [-Previous <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令删除 Lync Server 可用的所有 WebServicesExternal 证书。如果当前正在使用其中任何证书，**Remove-CsCertificate** cmdlet 将会询问您是否确定要删除该证书；您必须响应该提示，才能完成命令。要绕过确认提示，请使用 Force 参数：

Remove-CsCertificate –Type WebServicesExternal -Force

    Remove-CsCertificate -Type WebServicesExternal

## 详细说明

Lync Server 使用证书以供服务器和服务器角色验证其身份，例如，边缘服务器使用证书验证与其通信的计算机是否确实为前端服务器，反之亦然。为了完全实现 Lync Server，您需要将合适的证书分配给合适的服务器角色。

**Remove-CsCertificate** cmdlet 提供了一种删除 Lync Server 当前正在使用的证书的方法。**Remove-CsCertificate** cmdlet 实际上不会删除证书本身，而只将证书标记为无法再供 Lync Server 使用，删除所有证书绑定并撤消对证书的访问权限（假设没有其他服务正在使用证书）。此外，这还意味着当您运行 **Get-CsCertificate** cmdlet 时，将不再显示该证书。

要再次将该证书与 Lync Server 组合使用，您需要使用 **Set-CsCertificate** cmdlet 重新将证书分配给 Lync Server。

如果尝试删除当前正在使用的证书，**Remove-CsCertificate** cmdlet 将会询问您是否确定要删除该证书；在响应该提示之前，无法删除证书。要绕过提示并以静默方式删除证书（即使证书当前正在使用），请将 Force 参数添加到命令中：

Remove-CsCertificate –Type WebServicesExternal -Force

谁能运行此 cmdlet：必须是本地管理员，并且是域成员，才能在本地运行 **Remove-CsCertificate** cmdlet。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCertificate"}

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
<td><p><em>Type</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>要删除的证书类型。证书类型包括（但不限于）：</p>
<p>AccessEdgeExternal</p>
<p>AudioVideoAuthentication</p>
<p>DataEdgeExternal</p>
<p>Default</p>
<p>External</p>
<p>Internal</p>
<p>PICWebService（仅 Microsoft Lync Online 2010）</p>
<p>ProvisionService（仅 Microsoft Lync Online 2010）</p>
<p>WebServicesExternal</p>
<p>WebServicesInternal</p>
<p>WsFedTokenTransfer</p>
<p>例如，以下语法将删除 Default 证书：-Type Default。</p>
<p>可以在单个命令中通过用逗号分隔证书类型来删除多种类型：</p>
<p>-Type Internal,External,Default</p></td>
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
<td><p>绕过尝试删除当前正在使用的证书时通常会出现的确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>如果设置为 Global，则删除全局范围中的证书。如果未指定，则删除本地计算机中的证书。</p></td>
</tr>
<tr class="odd">
<td><p><em>Previous</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果指定此参数，则删除之前分配的证书而不是当前分配的证书。</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以记录有关由 <strong>Remove-CsCertificate</strong> cmdlet 执行的过程的详细信息。参数值应该为要生成的 HTML 文件的完整路径，例如：-Report C:\Logs\Certificates.html。如果指定的文件已存在，则该文件将自动被新信息覆盖。</p></td>
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

无。Remove-CsCertificate cmdlet 不接受通过管道传递的输入。

## 返回类型

无。但 **Remove-CsCertificate** cmdlet 会删除 Microsoft.Rtc.Management.Deployment.CertificateReference 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

