---
title: Lync Server 2013 中的 DNS 摘要 - 自动发现
TOCTitle: Lync Server 2013 中的 DNS 摘要 - 自动发现
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945644(v=OCS.15)
ms:contentKeyID: 52061099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 摘要 - 自动发现

 

_**上一次修改主题：** 2015-03-09_

自动发现是一项灵活的服务，因为该服务允许通过 HTTP 或 HTTPS 进行通信。要实现此目的，必须正确配置承载自动发现服务的服务器所使用的域名系统 (DNS) 和证书。[证书摘要 - 自动发现](lync-server-2013-certificate-summary-autodiscover.md)中介绍了相关证书要求。

> [!IMPORTANT]
> Lync Server 客户端的 DNS 查找逻辑遵循特定的解析顺序。您应该始终在您的 DNS 中包括 lyncdiscoverinternal.&lt;域&gt; 和 lyncdiscover.&lt;域&gt;。排除 lyncdiscoverinternal.&lt;域&gt; 记录将导致内部客户端无法连接到所需服务或接受错误的自动发现响应。


### 内部 DNS 记录

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.<em>&lt;内部域名&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有控制器）的内部 Web 服务 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>A（主机，如果是 IPv6，则为 AAAA）</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;内部域名&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有控制器）的内部 Web 服务 IP 地址（如果您使用负载平衡器，则为虚拟 IP (VIP) 地址）。</p></td>
</tr>
</tbody>
</table>


您需要创建下列外部 DNS 记录之一：

### 外部 DNS 记录

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;sip 域&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有 控制器）的外部 Web 服务 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>A（主机，如果是 IPv6，则为 AAAA）</p></td>
<td><p>lyncdiscover. <em>&lt;sip 域&gt;</em></p></td>
<td><p>反向代理的外部或公用 IP 地址。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 外部流量将通过反向代理。



> [!NOTE]  
> 移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。因此，不支持通过 HTTPS 对其他域进行 CNAME 重定向。例如，不支持通过 HTTPS 将 lyncdiscover.contoso.com 的 DNS CNAME 记录重定向到 director.contoso.net 地址。在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便通过 HTTP 解析 CNAME 重定向。之后，后续请求会使用 HTTPS。若要支持此方案，您需要使用针对端口 80 (HTTP) 的 Web 发布规则配置反向代理。有关详细信息，请参阅<a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a>中的“创建针对端口 80 的 Web 发布规则”。支持通过 HTTPS 对同一域进行 CNAME 重定向。在这种情况下，目标域的证书涵盖了原始域。



## 另请参阅

#### 任务

[在 Lync Server 2013 中配置反向代理以实现移动功能](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### 概念

[证书摘要 - 自动发现](lync-server-2013-certificate-summary-autodiscover.md)

