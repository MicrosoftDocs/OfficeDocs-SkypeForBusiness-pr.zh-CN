---
title: Lync Server 2013 硬件负载平衡器要求
TOCTitle: 硬件负载平衡器要求
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49888364
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的硬件负载平衡器要求

 

_**上一次修改主题：** 2016-12-08_

对于起初使用 Lync Server 与其他组织建立联盟的新部署， Lync Server 2013 扩展的合并边缘拓扑已经为实现 DNS 负载平衡进行了优化。如果下列任何方案要求高可用性，则必须在 边缘服务器池上对以下内容使用硬件负载平衡器：

  - 使用 Office Communications Server 2007 R2 或 Office Communications Server 2007 与组织建立联盟

  - Exchange UM，针对在使用 Exchange 2010 SP1 之前使用 Exchange UM 的远程用户

  - 与公共 IM 用户的连接

> [!IMPORTANT]
> 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。


> [!NOTE]  
> 如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。



> [!NOTE]  
> Lync Server 2013 不支持直接服务器返回 (DSR) NAT。



要确定您的硬件负载平衡器是否支持 Lync Server 2013 必需的功能，请参阅“Lync Server 2010 负载平衡器合作伙伴”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)。

## 运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求

下面是运行 A/V 边缘服务的 边缘服务器的硬件负载平衡器要求：

  - 对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。

  - 对端口范围为 50,000 – 59,999 的外部端口关闭 TCP nagling。

  - 请不要对内部或外部防火墙使用 NAT。

  - 边缘内部接口与 边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。

  - 运行 A/V 边缘服务的 边缘服务器的外部接口必须使用公开的可路由 IP 地址，且不对任何边缘外部 IP 地址进行 NAT 或端口转换。

## 硬件负载平衡器要求

Lync Server 2013 中大大减少了有关 Web 服务的基于 Cookie 的相关性要求。如果要部署 Lync Server 2013 并且将不保留任何 Lync Server 2010前端服务器或 前端池，则无需基于 Cookie 的持久性。不过，如果您将临时或永久保留任何 Lync Server 2010前端服务器或 前端池，则仍需使用基于 Cookie 的持久性，因为已为 Lync Server 2010 部署并配置了它。

> [!NOTE]  
> <strong>如果您决定使用基于 Cookie 的相关性，但您的部署不需要它</strong>，如此做没有任何负面影响。



对于 **不使用**基于 Cookie 的相关性的部署：

  - 在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。

对于 **将使用**基于 Cookie 的相关性的部署：

  - 在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。

  - 不得将硬件负载平衡器 Cookie 标记为 httpOnly

  - 硬件负载平衡器 Cookie 不得具有过期时间

  - 硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）

  - 必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化

> [!NOTE]  
> 典型硬件负载平衡器配置使用源地址相关性和 20 分钟的 TCP 会话生存期，这对 Lync Server 和 Lync 2013 客户端同样适用，因为在整个客户端使用和/或应用程序交互期间都会维持会话状态。



如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。

> [!WARNING]  
> F5 硬件负载平衡器具有一个名为 OneConnect 的功能，这可确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的硬件负载平衡器供应商支持这一相同功能。最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。F5 提供专门针对这一要求的设置。<br />
> 有关第三方硬件负载平衡器的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</a>


以下是控制器和前端池 Web 服务的硬件负载平衡器要求：

  - 对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source\_addr 持久性（内部端口 80 和 443）。对于 Lync Server 2013，Source\_addr 持久性意味着始终向一台服务器发送来自单个 IP 地址的多个连接，以维持会话状态。

  - 使用 TCP 空闲超时 1800 秒。

  - 在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一条支持端口 4443 上从反向代理到硬件负载平衡器的 HTTPS 流量的规则。必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。

## 硬件负载平衡器关联要求的摘要


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
<td><p>Lync Web App（内部和外部用户）</p>
<p>移动设备（内部和外部用户）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App（仅外部用户）</p>
<p>移动设备（内部和外部用户）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App（仅内部用户）</p>
<p>移动设备（未部署）</p></td>
<td><p>无相关性</p></td>
<td><p>源地址相关性</p></td>
</tr>
</tbody>
</table>


## 硬件负载平衡器的端口监控

在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。例如，如果 前端服务器服务 (RTCSRV) 因 前端服务器或 前端池出现故障而停止，则 HLB 监控也应停止接收 Web 服务上的流量。可在 HLB 上实施端口监控来监控以下各项：

### 前端服务器用户池 – HLB 内部接口

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>源</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>源</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### 前端服务器用户池 – HLB 外部接口

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>无</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>无</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>

