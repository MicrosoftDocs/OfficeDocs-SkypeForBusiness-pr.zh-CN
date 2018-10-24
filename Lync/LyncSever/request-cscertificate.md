---
title: Request-CsCertificate
TOCTitle: Request-CsCertificate
ms:assetid: 24e8ba6f-6023-4c03-a594-5b40784fd16a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425723(v=OCS.15)
ms:contentKeyID: 49312268
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Request-CsCertificate

 

_**上一次修改主题：** 2015-03-09_

提供一种方法以请求与运行 Lync Server 的服务器和服务器角色配合使用的证书。此外还提供一种方法来检查现有证书请求的状态，如果需要，还可以取消任何（或所有）这些请求。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Request-CsCertificate -New <SwitchParameter> -Type <CertType[]> [-AllSipDomain <SwitchParameter>] [-CA <String>] [-CaAccount <String>] [-CaPassword <String>] [-City <String>] [-ClientEKU <$true | $false>] [-ComputerFqdn <Fqdn>] [-Country <String>] [-DomainName <String>] [-FriendlyName <String>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-KeyAlg <RSA | ECDH_P256 | ECDH_P384 | ECDH_P521>] [-KeySize <Int32>] [-Organization <String>] [-OU <String>] [-Output <String>] [-PrivateKeyExportable <$true | $false>] [-State <String>] [-Template <String>] <COMMON PARAMETERS>

    Request-CsCertificate -List <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    Request-CsCertificate -Retrieve <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    Request-CsCertificate -Clear <SwitchParameter> [-RequestId <Int32>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令创建一个新的证书请求：它联系 CA atl-ca-001.litwareinc.com\\myca 并请求一个新的 WebServicesExternal 证书。

    Request-CsCertificate -New -Type WebServicesExternal -CA "atl-ca-001.litwareinc.com\myca"

## 示例 2

示例 2 列出使用 **Request-CsCertificate** cmdlet 生成的所有待处理证书请求。

    Request-CsCertificate -List

## 示例 3

示例 3 使用 Output 参数创建了一个脱机证书请求。

    Request-CsCertificate -New -Type WebServicesExternal -Output C:\Certificates\WebServicesExternal.cer

## 示例 4

示例 4 是有关如何使用 Request-CsCertificate cmdlet 的更详细（且更直观的）示例。此示例请求一个适用于 Lync Server 标准版的证书。

    Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -ComputerFqdn "atl-cs-001.litwareinc.com" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Standard Edition Certficate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-cs-001.litwareinc.com,atl-ext.litwareinc.com"

## 示例 5

在示例 5 中，请求了一个池证书以供与 Lync Server 标准版配合使用。

    Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -ComputerFqdn "atl-cs-001.litwareinc.com" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Enterprise Edition Pool Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "pool1.litwareinc.com,pool1int.litwareinc.com,pool1ext.litwareinc.com"

## 示例 6

示例 6 说明了如何为内部边缘服务器请求证书。

    Request-CsCertificate -New -Type Internal -ComputerFqdn "atl-edge-001" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "Internal Edge Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-edge-001.litwareinc.com, ap.litwareinc.com"

## 示例 7

示例 7 是示例 6 中显示的命令的变体。但在此例中，该请求针对外部边缘服务器。

    Request-CsCertificate -New -Type AccessEdgeExternal,DataEdgeExternal,AudioVideoAuthentication -ComputerFqdn "atl-edge-001" -CA "atl-ca-001.litwareinc.com\myca" -FriendlyName "External Edge Certificate" -Template jcila -PrivateKeyExportable $True -DomainName "atl-edge-001.litwareinc.com,ap.litwareinc.com,dp.litwareinc.com,atl-edge-001"

## 详细说明

Lync Server 使用证书作为服务器和服务器角色验证其身份的方法，例如，边缘服务器使用证书验证与其通信的计算机是否确实为前端服务器，反之亦然。要完整地实施 Lync Server，您需要为适当的服务器角色分配适当的证书。

要请求适用于 Lync Server 的证书，可调用 **Request-CsCertificate** cmdlet。尽管可以使用其他标准 Windows 工具请求适用于 Lync Server 的证书，但使用 **Request-CsCertificate** cmdlet 的一个主要优势是此 cmdlet 将先分析拓扑，然后再与证书颁发机构 (CA) 联系。根据该分析，**Request-CsCertificate** cmdlet 会自动请求“使用者名称”和“使用者可选名称”字段正确的证书。

**Request-CsCertificate** cmdlet 用于请求专门适用于 Lync Server 的证书。它不能作为通用的证书管理工具。

除了请求新证书之外，还可使用 **Request-CsCertificate** cmdlet 查看任何待处理的证书请求，只要这些请求是用此 cmdlet 生成的即可。**Request-CsCertificate** cmdlet 还可用于删除待处理的证书请求，只要这些请求是用此 cmdlet 生成的即可。

尝试检索证书请求时，如果有任何已撤消的请求，可能会收到错误消息；**Request-CsCertificate** cmdlet 当前仅支持以下请求类型：Issued、Denied 和 Pending。如果由于存在已吊销的证书而遇到问题，请使用如下命令清除已撤消的请求（其中 224 是已吊销证书请求的 RequestID）：

Request-CsCertificate –Clear –RequestID 224

执行该操作之后，应能够检索证书请求。

谁能运行此 cmdlet：只有具有指定证书颁发机构的权限的本地管理员才能在本地运行 **Request-CsCertificate** cmdlet。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Request-CsCertificate"}

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
<td><p><em>Clear</em></p></td>
<td><p>必需</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>包含此参数时，将删除使用 <strong>Request-CsCertificate</strong> 生成的所有待处理证书请求。</p></td>
</tr>
<tr class="even">
<td><p><em>List</em></p></td>
<td><p>必需</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>包含此参数时，将列出使用 <strong>Request-CsCertificate</strong> cmdlet 生成的所有待处理证书请求。</p></td>
</tr>
<tr class="odd">
<td><p><em>New</em></p></td>
<td><p>必需</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>有此参数时，表示您要请求新的证书。</p></td>
</tr>
<tr class="even">
<td><p><em>Retrieve</em></p></td>
<td><p>必需</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>包含此参数时，将检索使用 <strong>Request-CsCertificate</strong> cmdlet 生成的所有待处理证书请求，并尝试完成该操作和导入所请求的证书。</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.CertType[]</p></td>
<td><p>所请求的证书的类型。证书类型包括（但不限于）：</p>
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
<p>例如，以下语法请求一个新的 Default 证书：-Type Default。</p>
<p>可以在单个命令中通过用逗号分隔证书类型来指定多种类型：</p>
<p>-Type Internal,External,Default</p></td>
</tr>
<tr class="even">
<td><p><em>AllSipDomain</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果存在此参数，所有 SIP 域都将自动添加到证书的“使用者替代名称”字段中。如果不存在此参数，默认情况下只添加主 SIP 域。但是，可以使用 DomainName 参数指定其他域。</p></td>
</tr>
<tr class="odd">
<td><p><em>CA</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>指向证书颁发机构的完全限定域名 (FQDN)。例如：-CA &quot;atl-ca-001.litwareinc.com\myca&quot;。要获取已知 CA 的列表，请在 Windows PowerShell 提示符下键入以下命令，然后按 ENTER：</p>
<p>certutil</p>
<p>Certutil 返回的 Config 属性将指示 CA 的位置。</p></td>
</tr>
<tr class="even">
<td><p><em>CaAccount</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>请求新证书的用户的帐户名，格式为“域名\用户名”。例如：-CaAccount &quot;litwareinc\kenmyer&quot;。如果不指定此参数，则在请求新证书时，<strong>Request-CsCertificate</strong> cmdlet 将使用已登录用户的凭据。</p></td>
</tr>
<tr class="odd">
<td><p><em>CaPassword</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>请求新证书的用户的密码（使用 CaAccount 参数指定）。</p></td>
</tr>
<tr class="even">
<td><p><em>City</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将部署证书的城市。</p></td>
</tr>
<tr class="odd">
<td><p><em>ClientEKU</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果证书要用于客户端身份验证，则将此参数设置为 True。如果希望用户能够与具有 AOL 帐户的人交换即时消息，则必须进行此类型的身份验证。参数名称的 EKU 部分是扩展密钥用法的简称；扩展密钥用法字段列出了证书的各种有效用法。</p></td>
</tr>
<tr class="even">
<td><p><em>ComputerFqdn</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>为其请求证书的计算机的 FQDN。包含此参数时，它将强制 <strong>Request-CsCertificate</strong> cmdlet 连接到中央管理存储，以定位到指定的计算机。在请求证书时，甚至在请求池证书时，应始终使用计算机名称。<strong>Request-CsCertificate</strong> cmdlet 会自动将池名称添加到使用此 cmdlet 获取的任何证书的使用者名称中。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Country</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将部署证书的国家/地区。</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainName</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>完全限定的域名的逗号分隔列表应该添加到证书的“使用者替代名称”字段。例如：</p>
<p>-DomainName &quot;atl-cs-001.litwareinc.com, atl-cs-002.litwareinc.com,atl-cs-003.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>FriendlyName</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>用户指定的名称，可更加便于标识证书。</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>域中全局编录服务器的 FQDN。如果要在计算机上使用您的域中的帐户运行 <strong>Request-CsCertificate</strong>，则不需要指定此参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>用于存储全局设置的域控制器的 FQDN。如果全局设置存储在 Active Directory 域服务 的“系统”容器中，则此参数必须指向根域控制器。如果全局设置存储在“配置”容器中，则可以使用任何域控制器，此参数可以省略。</p></td>
</tr>
<tr class="even">
<td><p><em>KeyAlg</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deployment.X509Certificates.KeyAlgorithmIdentifier</p></td>
<td><p>指示在生成新证书的公钥和私钥时要使用的加密算法的类型。有效的密钥算法包括：</p>
<p>RSA</p>
<p>ECDH_P256</p>
<p>ECDH_P384</p>
<p>ECDH_P521</p></td>
</tr>
<tr class="odd">
<td><p><em>KeySize</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>指示证书使用的私钥的大小（以位为单位）。越大的密钥大小会越安全，但进行解密需要更大的处理开销。</p>
<p>有效的密钥大小包括 1024、2048 和 4096。例如：-KeySize 2048。</p></td>
</tr>
<tr class="even">
<td><p><em>Organization</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>请求新证书的组织的名称。例如：-Organization &quot;Litwareinc&quot;。</p></td>
</tr>
<tr class="odd">
<td><p><em>OU</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将获得新证书的计算机所在的 Active Directory 组织单位。</p></td>
</tr>
<tr class="even">
<td><p><em>Output</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>证书文件的路径。如果要创建脱机证书请求，可使用 Output 参数指定证书请求的文件路径；例如：-Output C:\Certificates\NewCertificate.pfx。这将创建一个证书请求文件，然后可以通过电子邮件将该文件发送到证书颁发机构进行处理。</p></td>
</tr>
<tr class="odd">
<td><p><em>PrivateKeyExportable</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果要使证书的私钥可以导出，则将此参数设置为 True。如果私钥可以导出，便可在多台计算机上复制和使用证书。</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可指定 cmdlet 运行时创建的日志文件的文件路径。例如：-Report &quot;C:\Logs\Certificates.html&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>RequestId</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>与证书请求关联的标识号。RequestID 参数提供了一种列出、检索或清除单个证书的方法。</p></td>
</tr>
<tr class="even">
<td><p><em>State</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将部署证书的美国各州。例如：-State WA。</p></td>
</tr>
<tr class="odd">
<td><p><em>Template</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>指示生成新证书时使用的证书模板；例如：-Template &quot;WebServer&quot;。所请求的模板必须已安装在 CA 上。请注意，输入的值必须是模板名称而不是模板显示名称。</p></td>
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

无。**Request-CsCertificate** cmdlet 不接受通过管道传递的输入。

## 返回类型

无。但 **Request-CsCertificate** cmdlet 会帮助管理 Microsoft.Rtc.Management.Deployment.CertificateReference 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCertificate](get-cscertificate.md)  
[Import-CsCertificate](import-cscertificate.md)  
[Remove-CsCertificate](remove-cscertificate.md)  
[Set-CsCertificate](set-cscertificate.md)

