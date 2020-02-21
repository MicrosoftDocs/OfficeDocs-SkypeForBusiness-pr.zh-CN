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
ms.openlocfilehash: dc30881da768d8dad9f952df37bdf1accdf091b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中选择拓扑

</div>

<div id="mainSection">

<div id="mainBody">

_**上次修改的主题：** 2013-02-21_

选择拓扑后，可以使用以下支持的拓扑选项之一：

<div>


> [!NOTE]
> 除非另有说明，否则，如果你有 Microsoft Lync Server 2010 的经验，你将在此处发现指南主要保持不变。



</div>

  - [Lync Server 2013 中具有专用 IP 地址和 NAT 的单一合并边缘](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 中具有公用 IP 地址的单一合并边缘](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [在 Lync Server 2013 中，扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。



</div>

下表汇总了支持的 Microsoft Lync Server 2013 拓扑结构中提供的功能。 列标题指明了给定的边缘配置选项可用的功能。 以“扩展边缘”（DNS 负载已平衡）选项为例，您可以了解到它支持高可用性、可以使用分配给边缘外部接口的不可路由专用 IP 地址（具有 NAT）或可路由的公用 IP 地址，并可降低成本（因为不需要硬件负载平衡器）。

DNS 负载平衡支持的边缘故障转移方案为 Lync 到 Lync 的点对点会话、Lync 会议会话、Lync 到 PSTN 会话和 Office 365。 无法从 DNS 负载平衡中受益的边缘故障转移方案是远程用户 Exchange 统一消息（UM）的故障转移（Exchange 2010 SP1 之前）、公共即时消息（IM）连接以及与运行 Office 通信的服务器的联盟服务器主板.

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
<th>边缘池中的外部边缘服务器是否需要其他 DNS A 记录</th>
<th>Lync 到 Lync 会话的边缘故障转移</th>
<th>Lync to Lync EUM/PIC/OCS 联合会话的边缘故障转移</th>
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
<td><p>使用公用 IP 的单个边缘</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>使用 NAT 的扩展边缘（DNS 负载已平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>使用公用 IP 的扩展边缘（DNS 负载已平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>扩展边缘（硬件负载已平衡）</p></td>
<td><p>是</p></td>
<td><p>不支持（每个 VIP 一个 DNS A 记录）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


**\*** 用于公共即时消息（IM）连接的故障转移以及与运行 Office 通信服务器的服务器的联盟在 DNS 负载平衡中不可用。 使用 DNS 负载平衡的 exchange UM （远程用户）故障转移需要 Exchange Server 2010 SP1 或更高版本。



> [!NOTE]
> 单个边缘和扩展边缘（DNS 负载已平衡）拓扑可以使用：
> <ul><li><p>可路由的公用 IP 地址</p></li>
> <li><p>如果使用对称网络地址转换（NAT），则不可路由的专用 IP 地址</p></li>
>
> <ul><li> 如果使用公用 IP 地址或使用 NAT 的专用 IP 地址，则仍将根据拓扑生成器中的配置选择使用相同数量的 IP 地址。 您可以将边缘服务器配置为对每个服务使用具有不同端口的单个 IP 地址，或对每个服务使用不同的 IP 地址，但使用相同的端口（默认情况下为 TCP 443）。</li></ul>>
> 如果您决定使用与 NAT 的不可路由的专用 IP 地址：
> <ul><li><p>您必须在所有三个外部接口上使用可路由的专用 IP 地址</p></li>
> <li><p>必须为传入和传出流量配置对称 NAT</p></li></ul>>
> 扩展边缘（硬件负载已平衡）拓扑必须使用公用 IP 地址。



Lync Server 2013 支持将访问、Web 会议和 A/V 边缘外部接口放置在为单一和扩展的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。

对所有边缘的外部接口使用 NAT 需要使用 DNS 负载平衡。与使用硬件负载平衡器相比，使用 DNS 负载平衡（不含 NAT）使您可以减少边缘池中每台边缘服务器的公用 IP 地址的数量，如以下列表所示：

  - Lync Server 2013 扩展的合并边缘（DNS 负载平衡）对边缘池中的每台边缘服务器都需要三个公共 IP 地址。

  - Lync Server 2013 扩展的合并边缘（硬件负载平衡）需要三个公共 IP 地址用于负载平衡器虚拟 IP 地址（一种时间要求，在将更多边缘服务器添加到池中时不增加）加上每个服务器的三个公用 IP 地址。池中的边缘服务器。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>扩展的合并边缘的 IP 地址要求（每个角色一个 IP 地址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数量</th>
<th>所需 IP 地址的数目 Lync Server 2013 （DNS 负载平衡）</th>
<th>所需 IP 地址的数目 Lync Server 2013 （硬件负载平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双面</p></td>
<td><p>6 </p></td>
<td><p>3（每个 VIP 1 个）+ 6</p></td>
</tr>
<tr class="even">
<td><p>第三章</p></td>
<td><p>9 </p></td>
<td><p>3（每个 VIP 1 个）+9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3（每个 VIP 1 个）+12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15 </p></td>
<td><p>3（每个 VIP 1 个）+15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>扩展的合并边缘的 IP 地址要求（单个 IP 地址用于所有角色）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数量</th>
<th>所需 IP 地址的数目 Lync Server 2013 （DNS 负载平衡）</th>
<th>所需 IP 地址的数目 Lync Server 2013 （硬件负载平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双面</p></td>
<td><p>双面</p></td>
<td><p>1（每个 VIP 1 个）2</p></td>
</tr>
<tr class="even">
<td><p>第三章</p></td>
<td><p>第三章</p></td>
<td><p>1（每个 VIP 1 个）+ 3</p></td>
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


拓扑选择的主要决策点是高可用性和负载平衡。高可用性的要求会影响负载平衡决策。

  - **高可用性**  如果需要高可用性，请在池中部署至少两台边缘服务器。 单个边缘池最长可支持12台边缘服务器。 如果需要更多的容量，可以部署多个边缘池。 一般规则是，如果给定用户群的10%，则需要外部访问。
    
    <div>
    

    > [!IMPORTANT]
    > 拓扑生成器将允许您在单个边缘池中配置最长20台边缘服务器。 池中经过测试且受支持的边缘服务器的最大数量为12，拓扑生成器允许大于12的值不应解释为单个边缘池中的12台边缘服务器的暗示支持。

    
    </div>

  - **硬件负载平衡**  在对边缘外部接口使用可公开路由的 IP 地址时，对 Lync Server 2013 边缘服务器的负载平衡支持硬件负载平衡。 例如，在以下任一应用程序需要故障转移的情况下，将使用此方法：
    
      - 公共 IM 连接
    
      - 与运行 Microsoft Office 通信服务器2007或 Microsoft Office 通信服务器 2007 R2 的公司的联盟
    
      - 外部访问 Exchange 2007 统一消息 (UM) 或 Exchange 2010 UM
        
        <div>
        

        > [!IMPORTANT]
        > Exchange UM 支持 Exchange 2010 SP1 和更高版本的 DNS 负载平衡。

        
        </div>
    
    这三个应用程序将继续运行，但不会进行 DNS 负载平衡，而且只会连接到池中的第一台边缘服务器。如果该服务器不可用，则连接将失败。例如，如果在池中部署多台边缘服务器以处理联盟流量负载，则实际上只有一个访问代理会收到流量，而其他设备处于空闲状态。

<div>


> [!IMPORTANT]
> 如果要与使用 Lync Server 2010 和 Microsoft Office 365 的公司进行联盟，则建议使用 DNS 负载平衡。 请注意，如果大多数联盟伙伴使用的是 Office 通信服务器2007或 Office 通信服务器 2007 R2，则会对性能产生重大影响。



</div>

</div>

<span> </span>

</div>

</div>

</div>

