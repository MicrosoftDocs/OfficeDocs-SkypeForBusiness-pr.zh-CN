---
title: 证书摘要 - SIP、XMPP 联盟和公共即时消息
TOCTitle: 证书摘要 - SIP、XMPP 联盟和公共即时消息
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49313608
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 证书摘要 - SIP、XMPP 联盟和公共即时消息

 

_**上一次修改主题：** 2015-03-09_

与 Microsoft Lync Server 2013、Lync Server 2010 和 Office Communications Server 联盟所需的证书通常将由您配置、请求和分配到边缘服务器的证书满足。

用于启用并与可扩展消息传递和状态协议 (XMPP) 伙伴建立通信的证书要求需要为您的 XMPP 域添加条目。作为使用者替代名称 (SAN) 包含在证书上的记录将成为可以参与 XMPP 通信的域。如果要针对整个域启用 XMPP，则该域可以是根级别域（例如，contoso.com），或者要针对用户的子集启用 XMPP，该域也可以是选定的子域（例如，corp.contoso.com、finance.contoso.com）。

若要配置公共即时消息连接的证书，请注意，这与其他 SIP 联盟类型或标准边缘服务器证书没有区别，只是 America Online (AOL) 要求证书（对于边缘池）也包含客户端 EKU。客户端 EKU 是对证书的补充，并且是分配给您的边缘服务器的外部公共证书的一部分。

若要确认您已满足边缘服务器部署的正确证书要求，请查看标题为**另请参阅**的章节中所列的主题。



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/访问边缘</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>
<div>

> [!NOTE]  
> 支持 contoso.com XMPP 命名空间


</div>
<p>sip.fabrikam.com</p>
<div>

> [!NOTE]  
> 支持 fabrikam.com SIP 命名空间


</div>
<p>fabrikam.com</p>
<div>

> [!NOTE]  
> 支持 fabrikam.com XMPP 命名空间


</div></td>
<td><p>如果要部署与 AOL 的公共 IM 连接，则证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU。该证书分配给以下各项的外部 边缘服务器接口：</p>
<ul>
<li><p>访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>
<div>

> [!NOTE]  
> 从技术上来说，证书不分配给 A/V 边缘。安全通信和身份验证通过媒体中继身份验证服务 (MRAS) 进行管理。MRAS 使用分配给边缘服务器内部接口的证书。


</div>
<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[Lync Server 2013 中的示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 概念

[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 中的证书摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Lync Server 2013 中的证书摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Lync Server 2013 中的证书摘要 - 使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

