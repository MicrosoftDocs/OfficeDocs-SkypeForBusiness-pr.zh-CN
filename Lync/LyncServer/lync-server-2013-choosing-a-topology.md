---
title: Lync Server 2013：选择拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中选择拓扑

</div>

<div id="mainSection">

<div id="mainBody">

_**主题上次修改时间：** 2013-02-21_

选择拓扑时，可以使用以下受支持的拓扑选项之一：

<div>


> [!NOTE]
> 除非另有说明，否则，如果你有 Microsoft Lync Server 2010 的体验，你将在此处发现指南，这主要是未更改的。



</div>

  - [Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 中使用公用 IP 地址的单一合并边缘](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。



</div>

下表总结了支持的 Microsoft Lync Server 2013 拓扑的可用功能。 列标题指示给定的边缘配置选项可用的功能。 使用缩放的边缘（DNS 负载平衡）选项作为示例，你可以看到它支持高可用性，可以使用无法路由的专用 IP 地址（带有 NAT），也可以使用分配给 Edge 外部接口的可路由的公共 IP 地址，从而降低成本，因为不需要硬件负载平衡器。

DNS 负载平衡支持的边缘故障切换方案是 Lync 到 Lync 的点到点会话、Lync 会议会话、Lync 到 PSTN 会话和 Office 365。 对于远程用户 Exchange 统一消息（UM）（在 Exchange 2010 SP1 之前）、公共即时消息（IM）连接和与运行 Office 通信的服务器之间的联盟，不能受益的边缘故障切换方案服务.

### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

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
<th>拓扑</th>
<th>高可用性</th>
<th>边缘池中的外部边缘服务器所需的其他 DNS 记录</th>
<th>Lync 至 Lync 会话的边缘故障转移</th>
<th>Lync to Lync EUM/PIC/OCS 联合身份验证会话的边缘故障转移</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用 NAT 的单个边缘</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>使用公共 IP 的单边</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>使用 NAT 进行缩放的边缘（DNS 负载平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>使用公共 IP 进行缩放的边缘（DNS 负载平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>缩放的边缘硬件负载平衡</p></td>
<td><p>是</p></td>
<td><p>不支持（每个 VIP 一个 DNS A 记录）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


**\*** 用于公共即时消息（IM）连接和与运行 Office 通信服务器的服务器的联盟的故障转移无法通过 DNS 负载平衡提供。 Exchange UM （远程用户）使用 DNS 负载平衡的故障转移要求使用 Exchange Server 2010 SP1 或更高版本。



> [!NOTE]
> 单个边缘和缩放的边缘（DNS 负载平衡）拓扑可以使用：
> <ul><li><p>可路由的公共 IP 地址</p></li>
> <li><p>如果使用对称网络地址转换（NAT），则无法路由的专用 IP 地址</p></li>
>
> <ul><li> 如果你将公共 IP 地址或专用 IP 地址与 NAT 配合使用，你仍将根据拓扑生成器中的配置选择使用相同数量的 IP 地址。 你可以将边缘服务器配置为对每个服务使用具有不同端口的单个 IP 地址，或对每个服务使用不同的 IP 地址，但使用同一端口（默认情况下为 TCP 443）。</li></ul>>
> 如果您决定将不可路由的专用 IP 地址与 NAT 配合使用，请执行以下操作：
> <ul><li><p>必须在所有三个外部接口上使用可路由的专用 IP 地址</p></li>
> <li><p>必须为传入和传出流量配置对称 NAT</p></li></ul>>
> 缩放边缘（硬件负载平衡）拓扑必须使用公共 IP 地址。



Lync Server 2013 支持将 Access、Web 会议和 A/V 边缘外部接口放置在对单个和缩放的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。

对所有 Edge 外部接口使用 NAT 需要使用 DNS 负载平衡。 与使用硬件负载平衡器相比，使用硬件负载平衡器时，如果使用不带 NAT 的 DNS 负载平衡，则可以按下表中所述，减少边缘池中的每边缘服务器的公共 IP 地址数：

  - Lync Server 2013 缩放的合并边缘（DNS 负载平衡）需要一个 Edge 池中每个边缘服务器的三个公共 IP 地址。

  - Lync Server 2013 缩放后的合并边缘（硬件负载平衡）需要三个公共 IP 地址用于负载平衡器虚拟 IP 地址（一次要求在将更多边缘服务器添加到池中时不增加）加上每个 IP 地址的三个公共 IP 地址在池中的边缘服务器。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>缩放后的合并边缘的 IP 地址要求（每个角色的 IP 地址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数</th>
<th>Lync Server 2013 的必需 IP 地址数（DNS 负载平衡）</th>
<th>Lync Server 2013 的必需 IP 地址数（硬件负载平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ppls-2</p></td>
<td><p>6</p></td>
<td><p>3（每个 VIP 1 个）6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>db-9</p></td>
<td><p>3（每个 VIP 1 个）9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>至</p></td>
<td><p>3（每个 VIP 1 个）12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>岁</p></td>
<td><p>3（每个 VIP 1 个） + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>缩放后的合并边缘的 IP 地址要求（针对所有角色的单个 IP 地址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数</th>
<th>Lync Server 2013 的必需 IP 地址数（DNS 负载平衡）</th>
<th>Lync Server 2013 的必需 IP 地址数（硬件负载平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>ppls-2</p></td>
<td><p>1（每个 VIP 1 个）2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1（每个 VIP 1 个）3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1（每个 VIP 1 个）4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1（每个 VIP 1 个）5</p></td>
</tr>
</tbody>
</table>


拓扑选择的主要决策点有高可用性和负载平衡。 高可用性的要求可能会影响负载平衡决策。

  - **高可用性**  如果需要高可用性，请在池中至少部署两台边缘服务器。 单个边缘池最多支持十二台边缘服务器。 如果需要更多容量，可以部署多个边缘池。 一般规则是给定用户群的10% 需要外部访问。
    
    <div>
    

    > [!IMPORTANT]
    > 拓扑生成器将允许你在一个 Edge 池中最多配置二十台边缘服务器。 在池中经过测试和支持的最大边缘服务器数为12，如果拓扑生成器允许大于12的数字，则不应将单个 Edge 池中的12台以上服务器的暗示支持视为暗示支持。

    
    </div>

  - **硬件负载平衡**  在对 Edge 外部接口使用公共可路由的 IP 地址时，使用硬件负载平衡支持 Lync Server 2013 Edge 服务器的负载平衡。 例如，在以下情况下，你可以使用此方法：对以下任何应用程序进行故障切换：
    
      - 公共 IM 连接
    
      - 与运行 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 的公司的联盟
    
      - 对 Exchange 2007 统一消息（UM）或 Exchange 2010 UM 的外部访问
        
        <div>
        

        > [!IMPORTANT]
        > Exchange UM 支持 Exchange 2010 SP1 和更高版本的 DNS 负载平衡。

        
        </div>
    
    这三个应用程序将继续运行，但它们不是 DNS 负载平衡感知，并且将仅连接到池中的第一个边缘服务器。 如果该服务器不可用，连接将失败。 例如，如果在池中部署了多个边缘服务器以处理联盟流量负载，则只有一个访问代理服务器在其他闲置时才会实际接收流量。

<div>


> [!IMPORTANT]
> 如果您使用 Lync Server 2010 和 Microsoft Office 365 联盟公司，则建议使用 DNS 负载平衡。 请注意，如果大多数联盟伙伴使用的是 Office 通信服务器2007或 Office 通信服务器 2007 R2，则会对性能产生重大影响。



</div>

</div>

<span> </span>

</div>

</div>

</div>

