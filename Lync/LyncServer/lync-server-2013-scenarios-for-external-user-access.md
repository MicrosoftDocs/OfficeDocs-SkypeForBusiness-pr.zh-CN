---
title: Lync Server 2013：外部用户访问方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

为 Lync Server 2013 提供外部用户访问需要在你的外围网络中至少部署一个 Edge 服务器和一个反向代理。 或者, 您可以在内部网络中部署 Director 或控制器池。

如果你需要比单个 Edge 服务器提供的容量更大的容量, 或者如果你的 Edge 服务器部署需要高可用性, 则可以在负载平衡的池中配置负载平衡和部署多台边缘服务器。 如果您的组织有多个数据中心, 则可以在多个位置拥有 Edge 服务器或边缘池部署。 但是, 只能将一个边缘服务器部署指定为联盟路由。

本部分定义了边缘服务器部署的方案, 并将计划分区映射到可能的方案。 例如, 如果你的部署需要高可用性、具有可扩展消息和状态 (XMPP) 联系人的联盟以及 Lync 移动性, 你可以选择下表中满足这些要求的匹配条目, 并使用引用的计划分区来定义你的部署, 如下流程图所示。

**边缘服务器部署方案选择过程**

![示例部署流程图](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "示例部署流程图")

通过使用此过程, 你可以为你希望为用户部署的所有潜在功能的配置进行规划和记录。 但是, 你可以在部署 Edge 服务器之后添加联盟和移动服务, 并在添加其他功能之前确认了正确的操作。 在 "部署" 部分中介绍了将功能添加到现有边缘服务器部署的过程。 有关部署的详细信息, 请参阅在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)通过在初始计划过程中包括规划这些功能, 你可以为添加的功能做好 DNS、防火墙和证书要求的准备。这使你能够提前获取证书和配置 DNS 和端口/协议要求。

<div>


> [!TIP]  
> 如果你打算安装 Edge 服务器和反向代理, 然后稍后添加功能 (例如, 联盟和移动), 请确定部署后所有服务所需的证书。 提前计划和获取所有功能的证书, 最初部署或不是, 您不必订购新的证书来满足联盟 (即在 Edge 服务器上) 或反向代理 (即移动性) 的要求。服务)。



</div>

<div>


> [!NOTE]  
> 所有 edge 服务都在每台边缘服务器上运行。 无法在两台不同的边缘服务器之间拆分服务。 如果为可伸缩性部署边缘池, 则会在池中的每台边缘服务器上部署所有 Edge 服务。 XMPP 联盟、Office 通信服务器和 Lync 服务器联盟、公共 IM 连接和客户移动性是部署第一台边缘服务器或边缘池后可以部署的其他服务。 移动服务是使用反向代理的功能。 安装移动服务不会将功能添加到 Edge 服务器, 但需要重新配置反向代理。 列出这些功能的 "<STRONG>安装目标</STRONG>" 列在 "<STRONG>边缘服务器规划" 部分</STRONG>下的 "相关列" 中提供规划指南, 或者在边缘服务器上同时规划要部署的这些功能的部分已安装和配置。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>标识和映射部署目标


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
<td><p>你已确定单个服务器已足够用于你的基础结构中的 Edge 服务。 你还打算将 Edge 服务器的专用 IP 地址用于带有 NAT 的外部接口到 Internet。</p>
<p>如果您在您的周边环境中部署单个边缘服务器, 请使用此规划部分。 你将部署分配给 Edge 服务器的专用 IP 地址的边缘服务器, 并将使用 NAT 为 Internet 上的外部用户提供公共 IP 地址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>你已确定单个服务器已足够用于你的基础结构中的 Edge 服务。 你还打算将边缘服务器外部接口的公共 IP 地址用于 Internet。</p>
<p>如果您在您的周边环境中部署单个边缘服务器, 请使用此规划部分。 你将部署分配给 Edge 服务器的公共 IP 地址的边缘服务器。 在此方案中, 您将使用路由, 而不是 NAT。 边缘服务器的实际公共 IP 地址可用于外部用户连接。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中使用公用 IP 地址的单一合并边缘</a></p></td>
</tr>
<tr class="odd">
<td><p>你已确定 Edge 服务的高可用性对你的用户很重要, 你将在此池中部署两台或多台 Edge 服务器。 你还打算将 Edge 服务器的专用 IP 地址用于带有 NAT 的外部接口到 Internet。</p>
<p>如果您在您的外围环境中部署了一个 Edge 服务器池, 请使用此规划部分。 你将使用分配给 Edge 服务器的专用 IP 地址部署边缘服务器, 使用 DNS 负载平衡在池中分布通信。 你将使用 NAT 为 Internet 上的外部用户提供公共 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="even">
<td><p>你已确定 Edge 服务的高可用性对你的用户很重要, 你将在此池中部署两台或多台 Edge 服务器。 你还打算将边缘服务器外部接口的公共 IP 地址用于 Internet。</p>
<p>如果您在您的外围环境中部署了一个 Edge 服务器池, 请使用此规划部分。 你将使用分配给 Edge 服务器的公共 IP 地址部署边缘服务器, 使用 DNS 负载平衡在池中分布通信。 您将使用路由来为 Internet 上的外部用户提供公共 IP 地址, 而不是 NAT。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="odd">
<td><p>你已确定 Edge 服务的高可用性对你的用户很重要, 你将使用硬件负载平衡器在此池中部署两台或多台 Edge 服务器。</p>
<p>如果您在您的外围环境中部署了一个 Edge 服务器池, 请使用此规划部分。 你将使用分配给 Edge 服务器的公共 IP 地址部署边缘服务器, 使用硬件负载平衡器在池中分布通信。 您将使用路由来为 Internet 上的外部用户提供公共 IP 地址, 而不是 NAT。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>联合身份验证方案允许你对将扩展你的用户可以与之通信的合作伙伴类型的功能进行规划。</p>
<ul>
<li><p>Lync Server 联合身份验证</p></li>
<li><p>Office 通信服务器联合</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
</ul></td>
<td><p>规划联盟方案</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">规划 Lync Server 2013 和 Office 通信服务器联合</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">在 Lync Server 2013 中规划公共即时消息连接</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联合</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>移动服务通过反向代理提供。 为外部用户启用移动能力的服务将部署在前端服务器或前端池。 在反向代理服务器上创建或修改现有发布规则, 以便为外部用户启用移动服务。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动功能</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 在以下方案部分中, 参考体系结构、示例 DNS、端口/协议定义和证书要求。 还包括用于你的 DNS、端口/协议定义和证书需求的图表。 图表将提供模板供你填写和分发到其他团队 (例如, 你的组织的网络团队、公共密钥基础结构团队和服务器部署团队)。 图表的目标是增强通信, 并确保在将所需的边缘服务器配置元素与将执行实际配置工作的人员进行通信时确保成功。 我们建议你使用图表和关联的参考体系结构来规划你的部署。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

