---
title: Lync Server 2013：DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
TOCTitle: DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205319(v=OCS.15)
ms:contentKeyID: 49314455
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）

 

_**上一次修改主题：** 2017-03-09_

与证书和端口的 DNS 记录要求相比，远程访问 Lync Server 2013 的 DNS 记录要求非常简单。此外，许多记录是可选的，具体取决于如何配置运行 Lync 2013 的客户端以及是否启用联盟。

有关 Lync 2013 DNS 要求的详细信息，请参阅 [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

有关在未配置拆分式 DNS 的情况下配置 Lync 2013 客户端自动配置的详细信息，请参阅 [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)中的“在没有拆分式 DNS 的情况下自动配置”一节。

下表包含 DNS 记录的摘要，支持单一的合并边缘拓扑图中显示的单一合并边缘拓扑需要这些 DNS 记录。请注意，某些 DNS 记录仅适用于自动配置 Lync 2013 客户端。如果计划使用组策略对象 (GPO) 配置 Lync 客户端，则不需要关联的记录。

## 重要提示： 边缘服务器网络适配器要求

要避免出现路由问题，请确认您的 边缘服务器中至少存在两个网络适配器，并确认只在与外部接口关联的网络适配器上设置默认网关。例如，如[Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)中的“扩展的合并边缘方案”图所示，默认网关将指向外部防火墙。

您可以在每台边缘服务器中配置两个网络适配器，如下所示：

  - **网络适配器 1 - 节点 1（内部接口）**
    
    分配有 172.25.33.10 的内部接口。
    
    未定义默认网关。
    
    确保存在从包含边缘内部接口的网络到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络的路由（例如，从 172.25.33.0 到 192.168.10.0）。

  - **网络适配器 1 - 节点 2（内部接口）**
    
    分配有 172.25.33.11 的内部接口。
    
    未定义默认网关。
    
    确保存在从包含边缘内部接口的网络到包含运行 Lync Server 2013 或 Lync Server 2013 客户端的服务器的任何网络的路由（例如，从 172.25.33.0 到 192.168.10.0）。

  - **网络适配器 2 节点 1（外部接口）**
    
    3 个专用 IP 地址将分配给此网络适配器，例如为 访问边缘服务分配 131.107.155.10，为 Web 会议边缘服务分配 131.107.155.20，为 A/V 边缘服务分配 131.107.155.30。
    
    访问边缘服务公用 IP 地址是默认网关设置为公共路由器时的主要 IP 地址 (131.107.155.1)。
    
    Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中 **本地连接属性**的 **Internet 协议第四版 (TCP/IPv4)** 和 **Internet 协议版本 6 (TCP/IPv6)** 属性的 **高级**部分中的其他 IP 地址。
    
    > [!NOTE]  
    > 虽然可以对所有三个边缘服务接口使用一个 IP 地址，但不建议这样做。虽然这样能节省 IP 地址，但每个服务需要不同的端口号。默认端口号为 443/TCP，这将确保大多数远程防火墙允许通信。针对 访问边缘服务、 Web 会议边缘服务和 A/V 边缘服务分别将端口值更改为 5061/TCP、444/TCP 和 443/TCP（举例而言）可能导致远程用户遇到问题，即，他们所用的防火墙不允许通过 5061/TCP 和 444/TCP 进行通信。此外，使用三个不同的 IP 地址将使故障排除更加轻松，因为这样能筛选 IP 地址。
    


  - **网络适配器 2 节点 2（外部接口）**
    
    3 个专用 IP 地址将分配给此网络适配器，例如为 访问边缘服务分配 131.107.155.11，为 Web 会议边缘服务分配 131.107.155.21，为 A/V 边缘服务分配 131.107.155.31..
    
    访问边缘服务公用 IP 地址是默认网关设置为公共路由器时的主要 IP 地址 (131.107.155.1)。
    
    Web 会议边缘服务和 A/V 边缘服务专用 IP 地址是 Windows Server 中 **本地连接属性**的 **Internet 协议第四版 (TCP/IPv4)** 和 **Internet 协议版本 6 (TCP/IPv6)** 属性的 **高级**部分中的其他 IP 地址。

> [!TIP]
> 使用两个网络适配器配置 边缘服务器是两个选项之一。另一个选项是对 边缘服务器的内部端使用一个网络适配器，对该服务器的外部端使用三个网络适配器。此选项的主要优点是每个 边缘服务器服务具有不同的网络适配器，当需要进行故障排除时，这就可能实现更简明的数据收集


### 使用公用 IP 地址的扩展的合并边缘（DNS 负载平衡）所需的 DNS 记录（示例）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN/DNS 记录</th>
<th>IP 地址/FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 和 131.107.155.11</p></td>
<td><p>访问边缘服务外部接口 (Contoso)。根据需要对包含启用了 Lync 的用户的所有 SIP 域重复</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 和 131.107.155.21</p></td>
<td><p>Web 会议边缘服务外部接口</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 和 131.107.155.31</p></td>
<td><p>A/V 边缘服务外部接口</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口。 Lync 2013 和 Lync 2010 客户端的自动配置需要此接口才能在外部正常运行。根据需要对包含启用了 Lync 的用户的所有 SIP 域重复。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务外部接口。用于实现称为“允许的 SIP 域”的联盟伙伴（在之前的版本中称为“增强联盟”）的自动 DNS 发现。根据需要对包含启用了 Lync 的用户的所有 SIP 域重复</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 和 172.25.33.11</p></td>
<td><p>合并边缘内部接口</p></td>
</tr>
</tbody>
</table>


## 联盟所需的记录


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 访问边缘服务外部接口。用于实现称为“允许的 SIP 域”的联盟（在之前的版本中称为“增强联盟”）对其他潜在联盟伙伴的自动 DNS 发现。</p>
<div>

> [!IMPORTANT]
> 根据需要对包含启用了 Lync 的用户和使用 推送通知服务或 Apple 推送通知服务的 Microsoft Lync Mobile 客户端的所有 SIP 域重复

</div></td>
</tr>
</tbody>
</table>


## DNS 摘要 – 公共即时消息连接


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN/DNS 记录</th>
<th>IP 地址/FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务接口</p></td>
<td><p>访问边缘服务外部接口 (Contoso)。根据需要对包含启用了 Lync 的用户的所有 SIP 域重复</p></td>
</tr>
</tbody>
</table>


## 可扩展消息传递和状态协议的 DNS 摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或 边缘池上的 XMPP 代理外部接口。根据需要对包含启用了 Lync 的用户的所有内部 SIP 域重复，其中与 XMPP 联系人的联系通过配置外部访问策略来允许，这通过全局策略、用户所在的站点策略或应用于启用了 Lync 的用户的用户策略来实现。还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。请参阅 <strong>另请参阅</strong>中的主题了解详细信息</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com（例如）</p></td>
<td><p>承载 XMPP 代理的 边缘服务器或 边缘池上的 访问边缘服务的 IP 地址</p></td>
<td><p>指向 访问边缘服务或承载 XMPP 代理服务的 边缘池。通常，您创建的 SRV 记录将指向主机（A 或 AAAA）记录</p></td>
</tr>
</tbody>
</table>

