---
title: Import-CsCertificate
TOCTitle: Import-CsCertificate
ms:assetid: 87bdafce-f4b9-4c44-ad8f-86c2deb680a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398688(v=OCS.15)
ms:contentKeyID: 49313507
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsCertificate

 

_**上一次修改主题：** 2015-03-09_

导入证书以与 Lync Server 结合使用。如果证书不是使用 **Request-CsCertificate** cmdlet 获取的，那么只有导入该证书后，才能将其分配给 Lync Server 服务器角色。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Import-CsCertificate -Identity <XdsIdentity> -Type <CertType[]> <COMMON PARAMETERS>

    Import-CsCertificate [-PrivateKeyExportable <$true | $false>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Path <String> [-Confirm [<SwitchParameter>]] [-EffectiveDate <DateTime>] [-Force <SwitchParameter>] [-Password <String>] [-Report <String>] [-Roll <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令导入证书 C:\\Certificates\\WebServer.pfx。命令完成后，该证书即可供分配给服务器角色。

    Import-CsCertificate -Path "C:\Certificates\WebServer.pfx" -PrivateKeyExportable $True

## 详细说明

Lync Server 使用证书以供服务器和服务器角色验证其身份，例如，边缘服务器使用证书验证与其通信的计算机是否确实为前端服务器，反之亦然。为了完全实现 Lync Server，您需要将相应的证书分配给相应的服务器角色。

为了将证书分配给 Lync Server 角色，必须使 Lync Server 了解这些证书。通过 **Request-CsCertificate** cmdlet，可以提出联机和脱机请求以获取新证书。如果提出联机请求，则证书将自动下载并保存在本地证书存储中；同样重要的是，该证书可以立即供 Lync Server 使用。如果提出脱机请求，则会向您发送证书文件。在这种情况下，可以使用 **Import-CsCertificate** cmdlet 导入证书，此过程将使证书可供分配给 Lync Server 服务器角色。

谁能运行此 cmdlet：只有本地管理员才能在本地运行 **Import-CsCertificate** cmdlet。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsCertificate"}

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
<td><p>当设置为 Global 时，允许证书在全局范围下发挥作用。全局证书将自动复制并分发到相应的计算机。</p></td>
</tr>
<tr class="even">
<td><p><em>Path</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>要导入的证书文件的完整路径。例如：–Path &quot;C:\Certificates\WebServer.cer&quot;。</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>所请求的证书的类型。证书类型包括，但不限于：</p>
<p>* AccessEdgeExternal</p>
<p>* AudioVideoAuthentication</p>
<p>* DataEdgeExternal</p>
<p>* Default</p>
<p>* External</p>
<p>* Internal</p>
<p>* iPadAPNService</p>
<p></p>
<p>* iPhoneAPNService</p>
<p>* LogRetentionService</p>
<p>* MPNService</p>
<p>* OAuthTokenIssuer</p>
<p>* PICWebService</p>
<p>* ProvisionService</p>
<p>* SMPDNSWebService</p>
<p>* TenantAdmin</p>
<p>* UpgradeEngineService</p>
<p>* WebServicesExternal</p>
<p>* WebServicesInternal</p>
<p>* WsFedTokenTransfer</p>
<p>* XMPPServer</p></td>
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
<td><p>首次可使用的证书的日期和时间。例如，要将证书配置为首次在 2012 年 7 月 31 日上午 8:00 使用，请在美国英语区域和语言设置下运行的服务器上使用此语法：</p>
<p>-EffectiveTime &quot;7/31/2012 8:00 AM&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>与证书文件关联的密码。</p></td>
</tr>
<tr class="even">
<td><p><em>PrivateKeyExportable</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果设置为 True，请确保 Network Service 帐户可以读取证书的私钥部分。</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用于指定在该 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\Certificates.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Roll</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>可使您在通过 EffectiveDate 参数指定的日期和时间更新指定的证书；这可在新证书将成为主证书时指定日期和时间。请注意，如果指定 Roll 参数而不包括 EffectiveDate 参数，那么命令将失败。</p></td>
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

无。**Import-CsCertificate** cmdlet 不接受通过管道传递的输入。

## 返回类型

无。

## 另请参阅

#### 其他资源

[Get-CsCertificate](get-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Request-CsCertificate](request-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

