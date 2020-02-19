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
ms.openlocfilehash: a3f9e8f029b4c621d15c17c5af5f7eac3207b832
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 中的内部服务器的证书要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-02-17_

运行 Lync Server 且要求证书的内部服务器包括 Standard Edition server、Enterprise Edition 前端服务器、中介服务器和控制器。 下表显示了这些服务器的证书要求。 您可以使用 Lync Server 证书向导来请求这些证书。

<div>


> [!TIP]  
> 对于与前端池、前端服务器或控制器上的简单 Url 相关联的使用者替代名称，支持通配符证书。 有关通配符证书支持的详细信息，请参阅<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配符证书支持</A>。



</div>

虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。 有关公用 Ca 的列表，这些 Ca 提供符合统一通信（UC）证书的特定要求的证书，并已与 Microsoft 合作以确保它们使用 Lync Server 证书向导，请参阅文章 Microsoft 知识库 929395 "Exchange Server 的统一通信证书合作伙伴和通信服务器"，网址为 at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。

与其他应用程序和服务器（如 Exchange 2013）的通信需要其他应用程序和产品支持的证书。 对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。 有关详细信息，请参阅部署文档或操作文档中的[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

对于运行 Windows 7 操作系统的客户端的连接、Windows Server 2008 操作系统、Windows Server 2008 R2 操作系统、Windows Vista 操作系统和 Microsoft Lync Phone Edition，Lync Server 2013 支持（但不要求）使用 SHA-256 加密哈希函数对证书进行签名。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。

下表按服务器角色显示了前端池和 Standard Edition Server 的证书要求。所有这些证书都是标准的 Web 服务器证书，具有私钥且不可导出。

请注意，使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。

<div>


> [!NOTE]  
> 每个证书友好名称在计算机存储中必须是唯一的。



</div>

<div>


> [!NOTE]  
> 如果您已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将其添加到证书的使用者备用名称中。



</div>

### <a name="certificates-for-standard-edition-server"></a>Standard Edition Server 的证书

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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>池的完全限定的域名 (FQDN)</p></td>
<td><p>池的 FQDN 和服务器的 FQDN</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN = se01;SAN = se01</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
<td><p>对于 Standard Edition Server，服务器 FQDN 与池 FQDN 相同。</p>
<p>证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</p>
<p>您还可以使用此证书进行服务器到服务器身份验证。</p></td>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN = se01;SAN = se01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</p>
<p>使用通配符证书：</p>
<p>SN = se01;SAN = se01;SAN = * .com</p></td>
<td><p>您不能在拓扑生成器中覆盖内部 web FQDN。</p>
<p>如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>满足每个 SIP 域的简单 Url</p></li>
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN = se01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</p>
<p>使用通配符证书：</p>
<p>SN = se01;SAN = webcon01;SAN = * .com</p></td>
<td><p>如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>前端池中前端服务器的证书

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
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN 和服务器的 FQDN。</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN = eepool;SAN = eepool;SAN = ee01</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
<td><p>证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</p>
<p>您还可以使用此证书进行服务器到服务器身份验证。</p></td>
</tr>
<tr class="even">
<td><p>Web 内部</p></td>
<td><p>池的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>内部 web FQDN （与服务器的 FQDN 不同）</p></li>
<li><p>服务器 FQDN</p></li>
<li><p>Lync 池 FQDN</p></li>
<li><p>会议简单 URL</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN = ee01;SAN = ee01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</p>
<p>使用通配符证书：</p>
<p>SN = ee01;SAN = ee01;SAN = * .com</p></td>
<td><p>如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</p>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN = ee01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</p>
<p>使用通配符证书：</p>
<p>SN = ee01;SAN = webcon01;SAN = * .com</p></td>
<td><p>如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>控制器的证书

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
<td><p>默认值</p></td>
<td><p>控制器池的 FQDN</p></td>
<td><p>控制器的 FQDN 和控制器池的 FQDN</p>
<p>如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</p>
<p>如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN = dir01;SAN = dir01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</p>
<p>SN = dir01;SAN = dir01 SAN = （contoso .com）</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>服务器的 FQDN</p></td>
<td><p>以下各项：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>拨入简单 URL</p></li>
<li><p>管理简单 URL</p></li>
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>控制器外部 web FQDN 必须不同于前端池或前端服务器。</p>
<p>SN = dir01;SAN = directorwebcon01 SAN = "contoso. .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</p>
<p>SN = dir01;SAN = directorwebcon01 SAN = （contoso .com）</p></td>
</tr>
</tbody>
</table>


如果具有独立中介服务器池，则其中的每个中介服务器需要使用下表中所列出的证书。如果将中介服务器与前端服务器并置，则使用本主题前面“前端池中前端服务器的证书”表所列的证书就足够了。

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
<td><p>默认值</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN</p>
<p>池成员服务器的 FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable Branch Appliance 的证书

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
<td><p>默认值</p></td>
<td><p>设备的 FQDN</p></td>
<td><p>SIP.&lt;sipdomain&gt; （每个 SIP 域需要一个条目）</p></td>
<td><p>SN = sba01;SAN = "contoso .com";SAN = sip. .com</p></td>
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

