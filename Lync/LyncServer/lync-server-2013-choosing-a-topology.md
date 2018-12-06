---
title: Lync Server 2013：选择拓扑
TOCTitle: 选择拓扑
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425716(v=OCS.15)
ms:contentKeyID: 49312257
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中选择拓扑

 

_**上一次修改主题：** 2015-03-09_

选择拓扑后，可以使用以下支持的拓扑选项之一：

> [!NOTE]  
> 如果您使用过 Microsoft Lync Server 2010，那么除非另行说明，否则您会发现此处的指南基本没有变化。



  - [Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 中使用公用 IP 地址的单一合并边缘](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

> [!IMPORTANT]  
> 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。


下表汇总了支持的 Microsoft Lync Server 2013 拓扑提供的功能。列标题指明了给定的边缘配置选项可用的功能。以“扩展边缘”（DNS 负载已平衡）选项为例，您可以了解到它支持高可用性、可以使用分配给边缘外部接口的不可路由专用 IP 地址（具有 NAT）或可路由的公用 IP 地址，并可降低成本（因为不需要硬件负载平衡器）。

支持 DNS 负载平衡的边缘故障转移方案为 Lync 到 Lync 的点到点会话、 Lync 会议会话、 Lync 到 PSTN 会话和 Office 365。无法从 DNS 负载平衡中受益的边缘故障转移方案可针对远程用户 Exchange 统一消息 (UM)（ Exchange 2010 SP1 之前的版本）、公共即时消息 (IM) 连接以及与运行 Office Communications Server 的服务器的联盟，实现故障转移。

### 边缘服务器拓扑选项摘要

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
<th>用于 Lync 到 Lync 会话的边缘故障转移</th>
<th>用于 Lync 到 Lync EUM/PIC/OCS 联盟会话的边缘故障转移</th>
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


**\*** DNS 负载平衡不支持针对公共即时消息 (IM) 连接和与运行 Office Communications Server 的服务器的联盟实现故障转移。使用 DNS 负载平衡的 Exchange UM（远程用户）故障转移需要 Exchange Server 2010 SP1 或更高版本。

> [!NOTE]  
> 单个边缘和扩展边缘（DNS 负载已平衡）拓扑可以使用：
> 
> <ul><li><p>可路由的公用 IP 地址</p></li>
> <li><p>不可路由的专用 IP 地址，如果使用对称的网络地址转换 (NAT)</p></li></ul>
>
> 如果使用公用 IP 地址或具有 NAT 的专用 IP 地址，您将基于在 拓扑生成器中的配置选择，仍使用相同数量的 IP 地址。您可以将 边缘服务器配置为对每个服务使用单个 IP 地址和不同的端口，或者对每个服务使用不同的 IP 地址，但使用相同的端口（默认为 TCP 443）。
> 
> 如果您决定使用不可路由的带 NAT 的专用 IP 地址：
> 
> <ul><li><p>必须在所有三个外部接口上使用可路由的专用 IP 地址</p></li>
> <li><p>必须为传入和传出流量配置对称 NAT</p></li></ul>
> 
> 扩展边缘（硬件负载已平衡）拓扑必须使用公用 IP 地址。



Lync Server 2013 支持将访问、Web 会议和 A/V 边缘外部接口置于路由器或防火墙之后，以便对单个和扩展的合并边缘服务器拓扑执行网络地址转换 (NAT)。

对所有边缘的外部接口使用 NAT 需要使用 DNS 负载平衡。与使用硬件负载平衡器相比，使用 DNS 负载平衡（不含 NAT）使您可以减少边缘池中每台边缘服务器的公用 IP 地址的数量，如以下列表所示：

  - Lync Server 2013 扩展的合并边缘（DNS 负载已平衡）要求边缘池中的每台边缘服务器具有三个公用 IP 地址。

  - Lync Server 2013 扩展的合并边缘（硬件负载已平衡）需要三个公用 IP 地址作为负载平衡器虚拟 IP 地址（一次性要求，向池中添加更多边缘服务器时无需增加 IP 地址），此外，池中每台边缘服务器还需要三个公用 IP 地址。

### 扩展的合并边缘的 IP 地址要求（每个角色一个 IP 地址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数量</th>
<th>Lync Server 2013 所需的 IP 地址数量（DNS 负载已平衡）</th>
<th>Lync Server 2013 所需的 IP 地址数量（硬件负载已平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3（每个 VIP 1 个）6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3（每个 VIP 1 个）9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3（每个 VIP 1 个）12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3（每个 VIP 1 个）15</p></td>
</tr>
</tbody>
</table>


### 扩展的合并边缘的 IP 地址要求（单个 IP 地址用于所有角色）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每个池的边缘服务器数量</th>
<th>Lync Server 2013 所需的 IP 地址数量（DNS 负载已平衡）</th>
<th>Lync Server 2013 所需的 IP 地址数量（硬件负载已平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
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


拓扑选择的主要决策点是高可用性和负载平衡。高可用性的要求会影响负载平衡决策。

  - **高可用性** 如果需要高可用性，请在池中至少部署两台边缘服务器。单个边缘池将最多支持 12 台边缘服务器。如果需要更多容量，可以部署多个边缘池。一般而言，10% 的给定用户群将需要进行外部访问。
    
    > [!IMPORTANT]  
	> 拓扑生成器将允许您在单个 边缘池中最多配置 20 台 边缘服务器。池中经过测试并受支持的最大 边缘服务器数为 12，而 拓扑生成器允许大于 12 的数字不应解释为单个 边缘池中可隐性支持超过 12 台 边缘服务器。


  - **硬件负载平衡**   在使用边缘外部接口的公用可路由 IP 地址时，负载平衡 Lync Server 2013  边缘服务器支持硬件负载平衡。例如，在以下任一应用程序需要故障转移的情况下，将使用此方法：
    
      - 公共 IM 连接
    
      - 与运行 Microsoft Office Communications Server 2007 或 Microsoft Office Communications Server 2007 R2 的公司建立联盟
    
      - 外部访问 Exchange 2007 统一消息 (UM) 或 Exchange 2010 UM
        
        > [!IMPORTANT]  
		> Exchange UM 支持 Exchange 2010 SP1 和更高版本的 DNS 负载平衡。
    
    这三个应用程序将继续运行，但不会进行 DNS 负载平衡，而且只会连接到池中的第一台边缘服务器。如果该服务器不可用，则连接将失败。例如，如果在池中部署多台边缘服务器以处理联盟流量负载，则实际上只有一个访问代理会收到流量，而其他设备处于空闲状态。

> [!IMPORTANT]  
> 如果与使用 Lync Server 2010 和 Microsoft Office 365 的公司建立联盟，则建议使用 DNS 负载平衡。请注意，如果大多数联盟伙伴都使用 Office Communications Server 2007 或 Office Communications Server 2007 R2，则会对性能产生显著影响。

