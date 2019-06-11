---
title: Lync Server 2013：前端池的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 中前端池的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-07_

若要成功完成此过程, 你应至少作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。

您需要先配置所需的域名系统 (DNS) 记录, 然后再在拓扑生成器中发布拓扑。 此外, Lync Server 2013 部署的配置中使用的一些完全限定的域名 (Fqdn) 是逻辑的, 而不是物理服务器 Fqdn, 因此在发布之前需要其他 DNS 配置。

<div>


> [!WARNING]  
> Lync Server 2013 不支持单标记的域。 例如, 支持一个名为 " <STRONG>contoso. local</STRONG> " 的根域的林, 但不支持名为<STRONG>local</STRONG>的根域。 有关详细信息, 请参阅 Microsoft 知识库文章 300684, "有关<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp为</A>具有单标签 DNS 名称的域配置 Windows 的信息", 请参阅 kbid = 300684。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名称必须与服务器上配置的计算机名相同。 默认情况下, 未加入域的计算机的计算机名是一个短名称, 而不是 FQDN。 拓扑生成器使用 FQDN，而不是短名称。 <STRONG>仅使用标准字符</STRONG>(包括 A – Z、A – z、0–9和连字符) 在分配运行 Lync Server、Edge 服务器和池的服务器的 Fqdn 时。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共证书颁发机构 (Ca) 通常不支持 FQDN 中的非标准字符 (当 FQDN 必须分配给证书中的 SN 时)。



</div>

在部署拓扑后运行拓扑之前, 请确保已创建以下 Active Directory 和 DNS 记录 (满足特定功能的需要):

  - 将在拓扑中存在的每个服务器角色将发布为 Active Directory 对象 (将计算机加入域将完成此操作)。

  - 每个服务器都存在 DNS A 记录。

  - 如果计划对\_sipinternaltls\_tcp 形式的客户端使用自动登录, 则每个 SIP 域都存在 DNS SRV 记录。\<SIP 域\>。 如果将手动配置用于客户端, 则不需要此记录。

  - 每个配置的简单 URL 的 DNS A 记录, 其中通常有四个: "满足"、"拨入"、"lwa" 和 "计划程序"。 此外, 还有一个用于访问 Lync Server 2013 控制面板的特殊 URL 的管理员简单 URL。

  - 运行 SQL Server 的服务器必须加入域, 并且拓扑生成器正在发布的计算机可以访问该服务器。

该表遵循 "规划" 部分中提供的参考体系结构。 有关详细信息, 请参阅规划文档中[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

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
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS 负载平衡)。 需要针对池中每个前端服务器的 IP 地址的 DNS A 记录, 映射到池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (硬件负载平衡器的虚拟 IP (VIP))。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 前端服务器 (节点 1)。</p>
<p>Pool01 前端服务器 (节点 2)。</p>
<p>Pool01 前端服务器 (节点 3)。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 前端服务器 (节点 2)。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>客户端到服务器 web 流量的 Pool01 (VIP)。</p></td>
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
<td><p>对于 Lync Phone Edition 是必需的, 或者自动登录未安装 DNS SRV 记录的客户端, 并且对于严格的域匹配。 在所有情况下均不需要。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>假定第二 SIP 域。 适用于 Lync Phone Edition、自动登录没有 DNS SRV 记录的客户端以及严格的域匹配。 在所有情况下均不需要。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>内部发布的电话拨入式会议的简单 URL-前端服务器 (如果已安装, 则为 Director) 响应简单的 URL 查询。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>在内部发布的会议的简单 URL-前端服务器 (如果已安装, 则为 Director) 响应简单的 URL 查询。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>iis</p></td>
<td><p>可选记录, Lync Server 2013 控制面板的简单 URL 发布在内部-前端服务器 (如果已安装, 则为 Director), 可响应简单的 URL 查询。 建议仅限主机名 (不使用域名)。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = 硬件负载平衡器的虚拟 IP 地址



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
<th>映射到/批注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>自动配置要在内部工作的 Lync 2013 客户端所需。</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _tcp</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>自动配置要在内部工作的 Lync 2013 客户端所需。</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _udp</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>运行 Lync Phone Edition 的设备所需的网络时间协议 (NTP) 源。 在内部, 这应该指向域控制器。 如果域控制器未定义, 它将尝试使用 NTP 服务器 time.windows.com。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

