---
title: Get-CsCertificate
TOCTitle: Get-CsCertificate
ms:assetid: 15b8f019-1d00-4389-9abe-18deb8cbf2ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398227(v=OCS.15)
ms:contentKeyID: 49312105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCertificate

 

_**上一次修改主题：** 2015-03-09_

返回有关本地计算机上已配置为与 Lync Server 配合使用的证书的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsCertificate [-Identity <XdsIdentity>] [-Report <String>] [-Type <CertType[]>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关当前分配给 Lync Server 组件的证书的信息。这是通过调用不带任何其他参数的 **Get-CsCertificate** cmdlet 实现的。

    Get-CsCertificate

## 示例 2

示例 2 检索所有用于内部 Web 服务的 Lync Server 证书。为此，加入了 Type 参数以及参数值 WebServicesInternal。

    Get-CsCertificate -Type WebServicesInternal

## 示例 3

示例 3 返回在 2012 年 9 月 1 日之前到期的所有 Lync Server 证书。为完成此任务，该命令首先使用 **Get-CsCertificate** cmdlet 返回当前正在使用的所有 Lync Server 证书的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅选择在 2012 年 9 月 1 日之前到期的证书。此示例中指定的日期 (9/1/2012) 使用美国英语格式指定日期时间值。应使用与“区域和语言选项”兼容的格式指定日期。

    Get-CsCertificate | Where-Object {$_.NotAfter -lt "9/1/2012"}

## 示例 4

示例 4 返回有关证书颁发机构 (CA) MyCa 颁发的所有 Lync Server 证书的信息。为执行此操作，该命令首先调用不带任何参数的 **Get-CsCertificate** cmdlet，以返回当前正在使用的所有证书的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将选取 Issuer 属性等于 (-eq) "Cn=MyCa" 的所有证书。

    Get-CsCertificate | Where-Object {$_.Issuer -eq "Cn=MyCa"}

## 示例 5

示例 5 中显示的命令返回已将 Subject 属性设置为 CN=atl-cs-001.litwareinc.com 的所有 Lync Server 证书。为执行此操作，该命令使用 **Get-CsCertificate** cmdlet 返回所有 Lync Server 证书的集合，然后将该集合通过管道传递到 **Where-Object** cmdlet。然后，**Where-Object** cmdlet 将仅选择 Subject 属性等于“CN=atl-cs-001.litwareinc.com”的那些证书。

    Get-CsCertificate | Where-Object {$_.Subject -eq "CN=atl-cs-001.litwareinc.com"}

## 详细说明

Lync Server 使用证书以供服务器和服务器角色验证其身份，例如，边缘服务器使用证书验证与其通信的计算机是否确实为前端服务器，反之亦然。要完整地实施 Lync Server，需要向相应的服务器角色分配相应的证书。

**Get-CsCertificate** cmdlet 提供了一种检索有关已配置为与 Lync Server 结合使用的证书的详细信息的方式。请注意，此 cmdlet 仅返回有关 Lync Server 证书的信息。如果尚未使用 **Set-CsCertificate** cmdlet 将证书配置为与 Lync Server 结合使用，那么在您运行 **Get-CsCertificate** cmdlet 时将不返回该证书。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsCertificate** cmdlet：RTCUniversalServerAdmins。

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
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>允许您检索在全局范围配置的证书（全局证书将复制和分发到适当的计算机）。使用以下语法可返回有关全局证书的信息：</p>
<p>Get-CsCertificate –Identity &quot;global&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以记录有关 <strong>Get-CsCertificate</strong> cmdlet 执行的过程的详细信息。此参数值应为将生成的 HTML 文件的完整路径，例如：-Report C:\Logs\Certificates.html。如果指定的文件已存在，将使用新信息自动覆盖该文件。</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>所请求的证书的类型。证书类型包括，但不限于：</p>
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
<p>例如，以下语法返回有关默认证书的信息：-Type Default。</p>
<p>可以在单个命令中通过用逗号分隔证书类型来指定多种类型：</p>
<p>-Type Internal,External,Default</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsCertificate** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsCertificate** cmdlet 将返回 Microsoft.Rtc.Management.Deployment.CertificateReference 对象的实例。

## 另请参阅

#### 其他资源

[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

