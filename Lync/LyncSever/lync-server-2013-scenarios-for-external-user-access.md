---
title: Lync Server 2013：外部用户访问方案
TOCTitle: 外部用户访问方案
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425727(v=OCS.15)
ms:contentKeyID: 49312275
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的外部用户访问方案

 

_**上一次修改主题：** 2015-03-09_

为 Lync Server 2013 提供外部用户访问需要您在外围网络中至少部署一台 边缘服务器和一个反向代理。或者，您可以在内部网络中部署 控制器或 控制器池。

如果需要的容量高于单台 边缘服务器可提供的容量，或者您需要实现 边缘服务器部署的高可用性，则可配置负载平衡并在负载平衡池中部署多台 边缘服务器。如果您的组织有多个数据中心，则可在多个位置部署 边缘服务器或 边缘池。但是，只能将其中一个 边缘服务器部署指定为联盟路由。

本节定义 边缘服务器部署方案，并将规划章节映射至可能的方案。例如，如果您的部署要求高可用性，与可扩展消息传递和状态 (XMPP) 联系人联盟，以及 Lync 客户端移动性，您可以在下表中选择符合这些要求的条目，并使用引用的规划章节定义您的部署，如以下流程图所示。

**边缘服务器部署方案选择流程**

![示例部署流程图](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "示例部署流程图")

通过使用此过程，您可以规划和记录要为用户部署的所有潜在功能的配置。但是，您可以在已部署 边缘服务器且确认操作正确之后，并在添加其他功能之前，添加联合身份验证服务和移动服务。将在部署章节中介绍向现有 边缘服务器部署中添加功能的过程。有关部署的详细信息，请参阅 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。通过在初始规划过程中规划这些功能，您可以为已添加的功能准备好 DNS、防火墙和证书要求，以便提前购买证书并配置 DNS 和端口/协议要求。

> [!TIP]
> 如果您计划先安装 边缘服务器和反向代理，然后再添加功能（例如联盟和移动性），请确定在部署后您要为所有服务提供哪些证书。不管开始时有没有进行部署，提前为所有功能规划并购买证书将避免您为符合联盟（在 边缘服务器上）或反向代理（用于移动服务）要求而订购新的证书。


> [!NOTE]  
> 所有边缘服务都运行在各自的边缘服务器上。不能将服务拆分到两台不同的边缘服务器上。如果您部署边缘池以实现可伸缩性，那么所有边缘服务将部署在该池中各自的边缘服务器上。XMPP 联盟、Office Communications Server 和 Lync Server 联盟、公共 IM 连接和客户端移动性是可以在部署了第一台边缘服务器或第一个边缘池后部署的其他服务。移动服务是一项使用反向代理的功能。安装移动服务不会将功能添加到边缘服务器上，但需要重新配置您的反向代理。列出这些功能的“安装目标”列在“边缘服务器规划章节”下的相关列中提供了规划指南，以便同时规划要在安装和配置边缘服务器后部署的这些功能。



## 确定和映射部署目标


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安装目标</th>
<th>边缘服务器规划文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>您决定仅为体系结构中的边缘服务提供一台服务器，还打算使用边缘服务器外部接口的专用 IP 地址通过 NAT 连接到 Internet。</p>
<p>如果您要在外围部署一台 边缘服务器，请使用此规划章节。您要部署的 边缘服务器具有分配给该 边缘服务器的专用 IP 地址，并且您需要使用 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>您决定仅为体系结构中的边缘服务提供一台服务器，还打算使用边缘服务器外部接口的公用 IP 地址连接到 Internet。</p>
<p>如果您要在外围部署一台 边缘服务器，请使用此规划章节。您要部署的 边缘服务器具有分配给该 边缘服务器的公用 IP 地址。此方案使用路由，而不是 NAT。 边缘服务器的实际公用 IP 地址可用于外部用户连接。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中使用公用 IP 地址的单一合并边缘</a></p></td>
</tr>
<tr class="odd">
<td><p>您决定边缘服务的高可用性对您的用户很重要，并且您将在该池中部署两台或更多台边缘服务器。您还打算使用边缘服务器外部接口的专用 IP 地址通过 NAT 连接到 Internet。</p>
<p>如果您要在外围中部署 边缘服务器池，请使用此规划章节。您要部署的 边缘服务器具有分配给该 边缘服务器的专用 IP 地址，以便使用 DNS 负载平衡在整个池中分发通信。将使用 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="even">
<td><p>您已确定边缘服务的高可用性对您的用户很重要，并且您将在该池中部署两台或更多台 边缘服务器。您还打算使用 边缘服务器外部接口的公用 IP 地址连接到 Internet。</p>
<p>如果您要在外围部署 边缘服务器池，请使用此规划章节。您要部署的 边缘服务器具有分配给该 边缘服务器的公用 IP 地址，以便使用 DNS 负载平衡在整个池中分发通信。将使用路由而不是 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="odd">
<td><p>您已确定边缘服务的高可用性对您的用户很重要，并且您将使用硬件负载平衡器在该池中部署两台或更多台 边缘服务器。</p>
<p>如果您要在外围部署 边缘服务器池，请使用此规划章节。您要部署的 边缘服务器具有分配给该 边缘服务器的公用 IP 地址，以便使用硬件负载平衡器在整个池中分发通信。将使用路由而不是 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>这些联盟方案允许您规划将扩展您的用户能与其通信的合作伙伴类型的功能。</p>
<ul>
<li><p>Lync Server 联盟</p></li>
<li><p>Office Communications Server 联盟</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
</ul></td>
<td><p>规划联盟方案</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">规划 Lync Server 和 Office Communications Server 联盟</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">规划公共即时消息连接</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>移动服务通过反向代理提供。为外部用户提供移动支持的服务部署在 前端服务器或 前端池上。您可以在反向代理上创建发布规则或修改现有发布规则，以便为外部用户提供移动服务。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动功能</a></p></td>
</tr>
</tbody>
</table>


> [!TIP]
> 下面的方案章节包含参考体系结构、DNS 示例、端口/协议定义和证书要求。另外还包含表明您的 DNS、端口/协议定义和证书需求的图表。这些图表提供一个模板供您填写并会将其分发给其他团队（例如，贵组织的网络团队、公钥基础结构团队和服务器部署团队）。这些图表的用途是增强沟通能力，确保在与实际执行配置工作的人员沟通所需 边缘服务器配置元素时能够成功传达您的意图。建议使用这些图表和相关参考体系结构来规划部署。

