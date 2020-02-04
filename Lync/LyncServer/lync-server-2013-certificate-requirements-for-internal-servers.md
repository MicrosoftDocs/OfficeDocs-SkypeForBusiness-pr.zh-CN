---
title: Lync Server 2013：内部服务器的证书要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 中内部服务器的证书要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2017-02-17_

运行 Lync Server 且需要证书的内部服务器包括标准版 Server、企业版前端服务器、中介服务器和 Director。 下表显示了这些服务器的证书要求。 您可以使用 Lync Server 证书向导请求这些证书。

<div>


> [!TIP]  
> 对于与前端池、前端服务器或控制器上的简单 Url 相关联的主题备用名称，支持通配符证书。 有关通配符证书支持的详细信息，请参阅<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配证书支持</A>。



</div>

虽然建议内部服务器使用内部企业证书颁发机构（CA），但您也可以使用公共 CA。 对于提供符合统一通信（UC）证书特定要求的证书的公共 Ca 的列表，并与 Microsoft 进行合作以确保它们使用 Lync Server 证书向导，请参阅 Microsoft 知识库929395： "Exchange Server 的统一通信证书合作伙伴和通信服务器" 一[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)文。

与其他应用程序和服务器（如 Exchange 2013）通信需要其他应用程序和产品支持的证书。 对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。 有关详细信息，请参阅在部署文档或操作文档中[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

对于运行 Windows 7 操作系统、Windows Server 2008 操作系统、Windows Server 2008 R2 操作系统、Windows Vista 操作系统和 Microsoft Lync Phone Edition 的客户端的连接，Lync Server 2013 包括支持（但不必需）使用 SHA-256 加密哈希函数对证书进行签名。 若要支持使用 SHA-256 的外部访问，外部证书由使用 SHA-256 的公共 CA 颁发。

下表显示了前端池和标准版服务器的服务器角色的证书要求。 所有这些都是标准 web 服务器证书、私钥、不可导出的。

请注意，使用证书向导申请证书时，系统会自动配置服务器增强型密钥用法（EKU）。

<div>


> [!NOTE]  
> 每个证书友好名称在计算机存储中必须是唯一的。



</div>

<div>


> [!NOTE]  
> 如果您已在 DNS 中配置了 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要在证书的 "主题备用名称" 中添加它们。



</div>

### <a name="certificates-for-standard-edition-server"></a>标准版服务器的证书

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>证书</th>
<th>使用者名称/常用名称</th>
<th>使用者替代名称</th>
<th>示例</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>池的完全限定的域名（FQDN）</p></td>
<td><p>池的 FQDN 和服务器的 FQDN</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
<td><p>在标准版服务器上，服务器 FQDN 与池 FQDN 相同。</p>
<p>证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。</p>
<p>也可将此证书用于服务器到服务器身份验证。</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>内部 Web FQDN（与服务器的 FQDN 相同）</p></li>
<li><p>会议简单 URL</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>不能在拓扑生成器中替代内部 web FQDN。</p>
<p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>每个 SIP 域的会议简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>前端服务器在前端池中的证书

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>证书</th>
<th>使用者名称/常用名称</th>
<th>使用者替代名称</th>
<th>示例</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>池的 FQDN</p></td>
<td><p>服务器的池和 FQDN 的 FQDN。</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，并且在组策略中需要严格的 DNS 匹配，你还需要 sipdomain （对于你拥有的每个 SIP 域）的条目。</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
<td><p>证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者可选名称中。</p>
<p>也可将此证书用于服务器到服务器身份验证。</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>池的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>内部 Web FQDN（与服务器的 FQDN 不同）</p></li>
<li><p>服务器 FQDN</p></li>
<li><p>Lync 池 FQDN</p></li>
<li><p>会议简单 URL</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>池的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Director 的证书

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>证书</th>
<th>使用者名称/常用名称</th>
<th>使用者替代名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>控制器池的 FQDN</p></td>
<td><p>Director 的 FQDN、控制器池的 FQDN</p>
<p>如果此池是客户端的自动登录服务器，并且在组策略中需要严格的 DNS 匹配，你还需要 sipdomain （对于你拥有的每个 SIP 域）的条目。</p></td>
<td><p>SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</p>
<p>如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>内部 Web FQDN（与服务器的 FQDN 相同）</p></li>
<li><p>服务器 FQDN</p></li>
<li><p>Lync 池 FQDN</p></li>
<li><p>会议简单 URL</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者是简单 Url 的通配符条目</p></li>
</ul></td>
<td><p>控制器外部 Web FQDN 必须不同于前端池或前端服务器。</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


如果你有独立的中介服务器池，则其中的中介服务器需要下表中列出的证书。 如果你 collocate 前端服务器的中介服务器，本主题前面的 "前端服务器的前端服务器证书" 表中列出的证书已足够。

### <a name="certificates-for-stand-alone-mediation-server"></a>独立中介服务器的证书

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>证书</th>
<th>使用者名称/常用名称</th>
<th>使用者替代名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN</p>
<p>池成员服务器的 FQDN</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable 分支装置的证书

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>证书</th>
<th>使用者名称/常用名称</th>
<th>使用者替代名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>设备的 FQDN</p></td>
<td><p>SIP.&lt;sipdomain&gt; （每个 SIP 域需要一个条目）</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

