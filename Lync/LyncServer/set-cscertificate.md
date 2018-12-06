---
title: Set-CsCertificate
TOCTitle: Set-CsCertificate
ms:assetid: 6da0be05-b257-4258-9d6d-7ddf283f1038
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398518(v=OCS.15)
ms:contentKeyID: 49313181
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCertificate

 

_**上一次修改主题：** 2015-03-09_

允许您将证书分配到 Lync Server 服务器或服务器角色。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCertificate -Reference <CertificateReference> -Type <CertType[]> [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsCertificate -Identity <XdsIdentity> -Path <String> -Type <CertType[]> [-Password <String>] <COMMON PARAMETERS>

    Set-CsCertificate -Thumbprint <String> -Type <CertType[]> [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EffectiveDate <DateTime>] [-Force <SwitchParameter>] [-Report <String>] [-Roll <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令将指纹 B142918E463981A76503828BB1278391B716280987B 的证书分配给本地计算机的 WebServicesExternal 角色。

    Set-CsCertificate -Type WebServicesExternal -Thumbprint "B142918E463981A76503828BB1278391B716280987B"

## 示例 2

示例 2 将指纹为 B142918E463981A76503828BB1278391B716280987B 的证书分配给本地计算机上的三个不同角色：默认、WebServicesInternal 和 WebServicesExternal。

    Set-CsCertificate -Type Default, WebServicesInternal, WebServicesExternal -Thumbprint "B142918E463981A76503828BB1278391B716280987B"

## 详细说明

Lync Server 使用证书以供服务器和服务器角色验证其身份，例如，边缘服务器使用证书验证与其通信的计算机是否确实为前端服务器，反之亦然。为了完全实现 Lync Server，您需要将合适的证书分配给合适的服务器角色。

通过 **Set-CsCertificate** cmdlet，管理员可以将证书分配给服务器或服务器角色。请注意，只能对已配置用于 Lync Server 的证书进行分配。要标识哪些证书可用于分配，请使用 **Get-CsCertificate** cmdlet。

谁能运行此 cmdlet：必须是本地管理员才能在本地运行 **Set-CsCertificate** cmdlet。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCertificate"}

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
<td><p>设置为 Global 时，证书可以在全局范围中运行。将会自动复制全局证书并将其分发给相应的计算机。</p></td>
</tr>
<tr class="even">
<td><p><em>Path</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>.PFX 证书文件的完整路径。</p></td>
</tr>
<tr class="odd">
<td><p><em>Reference</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertificateReference</p></td>
<td><p>引用配置用于 Lync Server 的证书的对象。以下命令返回的对象引用（变量 $x）表示指纹为 B142918E463981A76503828BB1278391B716280987B 的证书：</p>
<p>$x = Get-CsCertificate | Where-Object {$_.Thumbprint –eq &quot;B142918E463981A76503828BB1278391B716280987B&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>Thumbprint</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>证书的唯一标识符。证书指纹类似于：B142918E463981A76503828BB1278391B716280987B。</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>所分配的证书的类型。证书类型包括，但不限于：</p>
<p>AccessEdgeExternal</p>
<p>AudioVideoAuthentication</p>
<p>DataEdgeExternal</p>
<p>Default</p>
<p>External</p>
<p>Internal</p>
<p>iPhoneAPNService</p>
<p>iPadAPNService</p>
<p>MPNService</p>
<p>PICWebService（仅 Microsoft Lync Online 2010）</p>
<p>ProvisionService（仅 Microsoft Lync Online 2010）</p>
<p>WebServicesExternal</p>
<p>WebServicesInternal</p>
<p>WsFedTokenTransfer</p>
<p>例如，以下语法分配默认证书：-Type Default。</p>
<p>可以在单个命令中通过用逗号分隔证书类型来指定多种类型：</p>
<p>-Type Internal,External,Default</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EffectiveDate</em></p></td>
<td><p>可选</p></td>
<td><p>System.DateTime</p></td>
<td><p>可首次使用证书的日期和时间。例如，若要将证书配置为在 2012 年 7 月 31 日上午 8:00 首次使用，请在使用美国英语区域和语言设置运行的服务器上使用以下语法：</p>
<p>-EffectiveTime &quot;7/31/2012 8:00 AM&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>取消显示命令运行过程中可能出现的任何非致命错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>证书的密码。</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>可以让您记录有关 <strong>Set-CsCertificate</strong> cmdlet 执行的过程的详细信息。参数值应当是要生成的 HTML 文件的完整路径；例如：-Report C:\Logs\Certificates.html。如果指定的文件已存在，它将被新信息自动覆盖。</p></td>
</tr>
<tr class="odd">
<td><p><em>Roll</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>允许您在由 EffectiveDate 参数指定的日期和时间更新指定证书；从而使您指定新证书成为主证书的日期和时间。请注意，如果您指定 Roll 参数而不包括 EffectiveDate 参数，则您的命令将失败。</p></td>
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

Microsoft.Rtc.Management.Deployment.CertificateReference。

## 返回类型

**Set-CsCertificate** cmdlet 不会返回任何值或对象。

## 另请参阅

#### 其他资源

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)

