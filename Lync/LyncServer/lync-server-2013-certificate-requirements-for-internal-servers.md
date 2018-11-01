---
title: Lync Server 2013：内部服务器的证书要求
TOCTitle: 内部服务器的证书要求
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398094(v=OCS.15)
ms:contentKeyID: 49311849
ms.date: 02/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中内部服务器的证书要求

 

_**上一次修改主题：** 2017-02-17_

运行 Lync Server 并且需要证书的内部服务器包括 Standard Edition 服务器、Enterprise Edition 前端服务器、中介服务器和控制器。下表显示了这些服务器的证书要求。可以使用 Lync Server 证书向导请求这些证书。

> [!TIP]
> 与前端池、前端服务器或控制器上简单 URL 关联的使用者替代名称支持通配符证书。有关通配符证书支持的详细信息，请参阅<a href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配符证书支持</a>。


虽然我们建议对内部服务器选择内部企业证书颁发机构 (CA)，但您也可以选择公共 CA。有关符合以下条件的公共 CA 的列表：提供符合统一通信 (UC) 证书特定要求的证书以及与 Microsoft 一起合作处理 Lync Server 证书向导，请参阅 Microsoft 知识库文章 929395“Exchange Server 和 Communications Server 的统一通信证书合作伙伴”，网址为 [http://go.microsoft.com/fwlink/?linkid=202834\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=202834%26clcid=0x804)。

与其他应用程序和服务器（如 Exchange 2013）通信需要使用其他应用程序和产品支持的证书。对于 2013 版本，Lync Server 2013 和其他 Microsoft 服务器产品（包括 Exchange 2013 和 SharePoint Server）都支持使用开放式授权 (OAuth) 协议进行服务器到服务器的身份验证和授权。有关详细信息，请参阅部署文档或操作文档中的[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

对于运行 Windows 7 操作系统、Windows Server 2008 操作系统、Windows Server 2008 R2 操作系统、Windows Vista 操作系统和 Microsoft Lync Phone Edition 的客户端发出的连接，Lync Server 2013 支持（但不要求）使用 SHA-256 加密哈希算法签署的证书。为了支持使用 SHA-256 进行外部访问，公共 CA 需要使用 SHA-256 颁发外部证书。

下表按服务器角色显示了前端池和 Standard Edition Server 的证书要求。所有这些证书都是标准的 Web 服务器证书，具有私钥且不可导出。

请注意，使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。

> [!NOTE]  
> 每个证书友好名称在计算机存储中必须是唯一的。



> [!NOTE]  
> 如果您已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，您需要将它们添加到证书的“使用者可选名称”中。



### Standard Edition 服务器的证书

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
<th>使用者名称/ 公用名</th>
<th>使用者可选名称</th>
<th>示例</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>池的完全限定的域名 (FQDN)</p></td>
<td><p>池的 FQDN 和服务器的 FQDN</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
<td><p>对于 Standard Edition Server，服务器 FQDN 与池 FQDN 相同。</p>
<p>证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</p>
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
<li><p>管理简单 URL</p>
<p></p></li>
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul>
<p></p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>您无法在拓扑生成器中覆盖内部 Web FQDN。</p>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### 前端池中前端服务器的证书

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
<th>使用者名称/ 公用名</th>
<th>使用者可选名称</th>
<th>示例</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN 和服务器的 FQDN。</p>
<p>如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</p>
<p>如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul>
<p></p></td>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>使用通配符证书：</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>如果您有多个会议简单 URL，则必须将它们作为使用者可选名称全部添加。</p>
<p>简单 URL 条目支持通配符条目。</p></td>
</tr>
</tbody>
</table>


### 控制器的证书

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
<th>使用者名称/ 公用名</th>
<th>使用者可选名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>控制器池的 FQDN</p></td>
<td><p>控制器的 FQDN 和控制器池的 FQDN</p>
<p>如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</p></td>
<td><p>SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</p>
<p>如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</p></td>
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
</ul>
<p></p></td>
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
<li><p>或者，简单 URL 的通配符条目</p></li>
</ul></td>
<td><p>控制器外部 Web FQDN 必须不同于前端池或前端服务器。</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


如果具有独立中介服务器池，则其中的每个中介服务器需要使用下表中所列出的证书。如果将中介服务器与前端服务器并置，则使用本主题前面“前端池中前端服务器的证书”表所列的证书就足够了。

### 独立中介服务器的证书

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
<th>使用者名称/ 公用名</th>
<th>使用者可选名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN</p>
<p>池成员服务器的 FQDN</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### Survivable Branch Appliance 的证书

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
<th>使用者名称/ 公用名</th>
<th>使用者可选名称</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>设备的 FQDN</p></td>
<td><p>SIP.&lt;sipdomain&gt;（每个 SIP 域需要一个条目）</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)

