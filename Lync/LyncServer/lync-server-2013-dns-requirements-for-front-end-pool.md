---
title: Lync Server 2013：前端池的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078b8dc63e630487e13f1d187896bcf0617c0d15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 中的前端池的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-07_

若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

在拓扑生成器中发布拓扑之前，需要配置所需的域名系统（DNS）记录。 此外，Lync Server 2013 部署的配置中使用的某些完全限定域名（Fqdn）是逻辑的，而不是物理服务器 Fqdn，因此在发布之前需要其他 DNS 配置。

<div>


> [!WARNING]  
> Lync Server 2013 不支持单标签域。 例如，支持具有名为 <STRONG>contoso.local</STRONG> 的根域的林，但不支持名为 <STRONG>local</STRONG> 的根域。 有关详细信息，请参阅 Microsoft 知识库文章300684，"有关为带有单标签 DNS 名称的域配置 Windows 的信息" <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp，请参阅 http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 300684</A>。



</div>

<div>


> [!IMPORTANT]  
> 指定的名称必须与在服务器上配置的计算机名称相同。 默认情况下，未加入域的计算机的计算机名称是短名称，不是 FQDN。 拓扑生成器使用 FQDN，而不是短名称。 在分配运行 Lync Server、边缘服务器和池的服务器的 Fqdn 时，<STRONG>仅使用标准字符</STRONG>（包括 a – z、a – z、0–9和连字符）。 不要使用 Unicode 字符或下划线。 FQDN 中的非标准字符通常不受外部 DNS 和公共证书颁发机构 (CA) 的支持（如必须向证书中的 SN 分配 FQDN 时）。



</div>

在部署拓扑后再对其进行操作之前，请确保已创建以下 Active Directory 和 DNS 记录（如您对特定功能的需求）：

  - 将在拓扑中存在的每个服务器角色发布为 Active Directory 对象（将计算机加入域将实现此目的）。

  - 每台服务器都存在 DNS A 记录。

  - 如果计划对\_sipinternaltls\_tcp 形式的客户端使用自动登录，则每个 SIP 域都有一个 DNS SRV 记录。\<SIP 域\>。 如果使用客户端的手动配置，则不需要此记录。

  - 每个配置的简单 URL（通常有四种：会议、拨入、LWA 和计划程序）的 DNS A 记录。 此外，还提供了管理员简单的 URL，它是访问 Lync Server 2013 控制面板的特殊 URL。

  - 运行 SQL Server 的服务器必须加入域，并且拓扑生成器正在发布的计算机可以访问该服务器。

此表遵照规划部分中提供的参考体系结构。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>前端池所需的 DNS 记录

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>类型</th>
<th>FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01（DNS 负载平衡）。 要求池中的每台前端服务器的 IP 地址的 DNS A 记录，映射到池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01（硬件负载平衡器的虚拟 IP (VIP)）。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 前端服务器（节点1）。</p>
<p>Pool01 前端服务器（节点2）。</p>
<p>Pool01 前端服务器（节点3）。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 前端服务器（节点2）。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>客户端到服务器的 Web 通信的 Pool01 (VIP)。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>运行 SQL Server 2008 R2 的 Pool01 后端服务器。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>对于 Lync Phone Edition 是必需的，或者自动登录未安装 DNS SRV 记录的客户端，以及严格的域匹配。 并非在所有情况下都需要。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>假定存在第二个 SIP 域。 对于 Lync Phone Edition 是必需的，自动登录没有 DNS SRV 记录的客户端，以及严格的域匹配。 并非在所有情况下都需要。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部发布的电话拨入式会议的简单 URL –前端服务器（如果已安装，则为 Director）响应简单 URL 查询。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>在内部发布的会议的简单 URL –前端服务器（如果已安装，则为 Director）响应简单 URL 查询。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>可选记录，Lync Server 2013 控制面板的简单 URL 发布在内部-前端服务器（如果已安装，则为 Director）响应简单 URL 查询。 建议只使用主机名（无域名）。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP 表示硬件负载平衡器的虚拟 IP 地址



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>前端池的 DNS SRV 记录


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>类型</th>
<th>FQDN</th>
<th>目标 FQDN</th>
<th>端口</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp .com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>自动配置 Lync 2013 客户端以在内部工作的必需。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp .com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>自动配置 Lync 2013 客户端以在内部工作的必需。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _udp .com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>运行 Lync Phone Edition 的设备所需的网络时间协议（NTP）源。 在内部，它应指向域控制器。 如果未定义域控制器，则会尝试使用 NTP 服务器 time.windows.com。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

