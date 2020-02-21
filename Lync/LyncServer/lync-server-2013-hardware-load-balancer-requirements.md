---
title: Lync Server 2013 硬件负载平衡器要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb8c3ff97930411cb8d679054015ffc18ab3ce2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013 的硬件负载平衡器要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-05-11_

Lync Server 2013 扩展的合并边缘拓扑经过优化，用于新部署的 DNS 负载平衡主要与使用 Lync Server 的其他组织联盟。 如果下列任何方案要求高可用性，则必须在边缘服务器池上对以下内容使用硬件负载平衡器：

  - 与使用 Office 通信服务器 2007 R2 或 Office 通信服务器2007的组织进行联盟

  - Exchange 2010 之前使用 Exchange UM 的远程用户的 exchange UM （SP1）

  - 与公共 IM 用户的连接

<div>


> [!IMPORTANT]  
> 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。



</div>

<div>


> [!NOTE]  
> 如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支持直接服务器返回（DSR） NAT。



</div>

若要确定您的硬件负载平衡器是否支持 Lync Server 2013 所需的必要功能，请参阅 at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)中的 "Lync Server 2010 负载平衡器合作伙伴"。

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求

以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：

  - 对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。

  - 对端口范围为 50,000 – 59,999 的外部端口关闭 TCP nagling。

  - 请不要对内部或外部防火墙使用 NAT。

  - 边缘内部接口与边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。

  - 运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且没有任何边缘外部 IP 地址上的 NAT 或端口转换。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬件负载平衡器要求

Lync Server 2013 for Web 服务中的基于 Cookie 的相关性要求大大减少。 如果要部署 Lync Server 2013，并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。 但是，如果您将临时或永久保留任何 Lync Server 2010 前端服务器或前端池，您仍将使用基于 cookie 的持久性，因为它是为 Lync Server 2010 部署和配置的。

<div>


> [!NOTE]  
> <STRONG>如果您决定使用基于 Cookie 的相关性，但您的部署不需要它</STRONG>，如此做没有任何负面影响。



</div>

对于**不使用**基于 Cookie 的相关性的部署：

  - 在端口 4443 的反向代理发布规则上，将“转发主机头”**** 设置为 True。 这可确保转发原始 URL。

对于**将使用**基于 Cookie 的相关性的部署：

  - 在端口 4443 的反向代理发布规则上，将“转发主机头”**** 设置为 True。这可确保转发原始 URL。

  - 不得将硬件负载平衡器 Cookie 标记为 httpOnly

  - 硬件负载平衡器 Cookie 不得具有过期时间

  - 硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）

  - 必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化

<div>


> [!NOTE]  
> 典型的硬件负载平衡器配置使用源地址关联和20分钟的 TCP 会话生存期，这对 Lync Server 和 Lync 2013 客户端来说是很好的，因为会话状态是通过客户端使用情况和/或应用程序交互来维护的。



</div>

如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。

<div>


> [!WARNING]  
> F5 硬件负载平衡器具有一个名为 OneConnect 的功能，这可确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的硬件负载平衡器供应商支持这一相同功能。最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。F5 提供专门针对这一要求的设置。<BR>有关第三方硬件负载平衡器的详细信息，请参阅<A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

以下是控制器和前端池 Web 服务的硬件负载平衡器要求：

  - 对于内部 Web 服务 Vip，请设置\_硬件负载平衡器上的源地址暂留（内部端口80，443）。 对于 Lync Server 2013，源\_地址暂留意味着来自单个 IP 地址的多个连接将始终发送到一台服务器，以维护会话状态。

  - 使用 TCP 空闲超时 1800 秒。

  - 在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一条支持端口 4443 上从反向代理到硬件负载平衡器的 HTTPS 流量的规则。必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。

<div>


> [!IMPORTANT]  
> 有关硬件负载平衡器配置的进一步阅读，请<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">在 Lync Server 2013 中查看带硬件负载平衡器的端口摘要-扩展的合并边缘</A>。



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬件负载平衡器关联要求的摘要


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端/用户位置</th>
<th>外部 Web 服务 FQDN 关联要求</th>
<th>内部 Web 服务 FQDN 关联要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App （内部和外部用户）</p>
<p>移动设备（内部和外部用户）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App （仅限外部用户）</p>
<p>移动设备（内部和外部用户）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App （仅限内部用户）</p>
<p>移动设备（未部署）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>硬件负载平衡器的端口监控

在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。 例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务上的流量。 可在 HLB 上实施端口监控来监控以下各项：

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>前端服务器用户池– HLB 内部接口

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
<th>虚拟 IP/端口</th>
<th>节点端口</th>
<th>节点计算机/监视器</th>
<th>持久性配置文件</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;池&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;池&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>前端服务器用户池– HLB 外部接口

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
<th>虚拟 IP/端口</th>
<th>节点端口</th>
<th>节点计算机/监视器</th>
<th>持久性配置文件</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;池&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>无</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;池&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>无</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

