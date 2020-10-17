---
title: Lync Server 2013：外部用户访问的方案
description: Lync Server 2013：外部用户访问的方案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b212d371d5a87470fc3d849f185bb5c8659ce05
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547638"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

为 Lync Server 2013 提供外部用户访问需要在您的外围网络中部署至少一个边缘服务器和一个反向代理。 （可选）您可以在内部网络中部署控制器或控制器池。

如果需要比单个边缘服务器更大的容量，或者如果您的边缘服务器部署需要高可用性，则可以在负载平衡池中配置负载平衡和部署多台边缘服务器。 如果您的组织具有多个数据中心，则可以在多个位置进行边缘服务器或边缘池部署。 但是，只有一台边缘服务器部署可以指定为联合路由。

本部分定义了边缘服务器部署的方案，并将规划部分映射到可能的方案。 例如，如果您的部署需要高可用性、具有可扩展邮件功能的联盟和状态 (XMPP) 联系人和 Lync 移动性，您可以在下表中选择满足这些要求的匹配条目，并使用引用的规划部分来定义您的部署，如下面的流程图所示。

**边缘服务器部署方案选择流程**

![示例部署流程图](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "示例部署流程图")

通过使用此过程，可以规划和记录您打算为用户部署的所有潜在功能的配置。 但是，您可以在部署边缘服务器后添加联盟和移动服务，并在添加其他功能之前确认了正确的操作。 将功能添加到现有边缘服务器部署的过程将在 "部署" 部分介绍。 有关部署的详细信息，请参阅在初始规划过程中，通过 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md) ，可以为添加的功能准备 dns、防火墙和证书要求，从而使您能够提前获取证书并配置 dns 和端口/协议要求。

<div>


> [!TIP]  
> 如果您计划安装边缘服务器和反向代理，然后在稍后添加功能 (例如，联盟和移动) ，请确定部署后所有服务所需的证书。 预先部署和获取所有功能的证书，并在最初部署的情况下，使您不必订购新证书来满足联合 (的要求，即在边缘服务器上) 或反向代理 (（即移动服务) ）。



</div>

<div>


> [!NOTE]  
> 所有边缘服务在每台边缘服务器上运行。 无法在两台不同的边缘服务器之间拆分服务。 如果部署边缘池以实现可伸缩性，则会在池中的每台边缘服务器上部署所有边缘服务。 XMPP 联合身份验证、Office 通信服务器和 Lync Server 联盟，公用 IM 连接和客户移动性是部署第一台边缘服务器或边缘池后可部署的其他服务。 移动服务是一项使用反向代理的功能。 移动服务的安装不会将功能添加到边缘服务器，但会要求重新配置反向代理。 在安装和配置边缘服务器时，列出这些功能的 " <STRONG>安装目标</STRONG> " 列在 " <STRONG>边缘服务器规划" 部分</STRONG> 下的 "相关列" 中提供了规划指南，以用于同时规划要部署的这些功能。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>确定和映射部署目标


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
<p>如果要在您的外围部署单个边缘服务器，请使用此规划部分。 将使用分配给边缘服务器的专用 IP 地址部署边缘服务器，并将使用 NAT 为 Internet 上的外部用户提供公共 IP 地址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中具有专用 IP 地址和 NAT 的单一合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>您决定仅为体系结构中的边缘服务提供一台服务器，还打算使用边缘服务器外部接口的公用 IP 地址连接到 Internet。</p>
<p>如果要在您的外围部署单个边缘服务器，请使用此规划部分。 将使用分配给边缘服务器的公共 IP 地址部署边缘服务器。 此方案使用路由，而不是 NAT。 边缘服务器的实际公用 IP 地址可用于外部用户连接。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中具有公用 IP 地址的单一合并边缘</a></p></td>
</tr>
<tr class="odd">
<td><p>您决定边缘服务的高可用性对您的用户很重要，并且您将在该池中部署两台或更多台边缘服务器。您还打算使用边缘服务器外部接口的专用 IP 地址通过 NAT 连接到 Internet。</p>
<p>如果要在您的外围部署一池边缘服务器，请使用此 "规划" 部分。 将使用分配给边缘服务器的专用 IP 地址部署边缘服务器，并使用 DNS 负载平衡跨池分布通信。 将使用 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="even">
<td><p>您决定边缘服务的高可用性对您的用户很重要，并且您将在该池中部署两台或更多台边缘服务器。 此外，您还打算将公用 IP 地址用于将边缘服务器外部接口连接到 Internet。</p>
<p>如果要在您的外围部署一池边缘服务器，请使用此 "规划" 部分。 将使用分配给边缘服务器的公用 IP 地址部署边缘服务器，并使用 DNS 负载平衡跨池分布通信。 将使用路由而不是 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">在 Lync Server 2013 中，扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</a></p></td>
</tr>
<tr class="odd">
<td><p>你已决定边缘服务的高可用性对你的用户很重要，你将使用硬件负载平衡器在此池中部署两台或多台边缘服务器。</p>
<p>如果要在您的外围部署一池边缘服务器，请使用此 "规划" 部分。 将使用硬件负载平衡器在池之间分布通信，将边缘服务器部署到分配给边缘服务器的公用 IP 地址。 将使用路由而不是 NAT 为 Internet 上的外部用户提供公用 IP 地址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘</a></p></td>
</tr>
<tr class="even">
<td><p>这些联盟方案允许您规划将扩展您的用户能与其通信的合作伙伴类型的功能。</p>
<ul>
<li><p>Lync Server 联合</p></li>
<li><p>Office 通信服务器联合</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
</ul></td>
<td><p>规划联盟方案</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">规划 Lync Server 2013 和 Office 通信服务器联盟</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">在 Lync Server 2013 中规划公共即时消息连接</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>移动服务通过反向代理提供。 为外部用户启用移动能力的服务部署在前端服务器或前端池上。 您可以在反向代理上创建发布规则或修改现有发布规则，以便为外部用户提供移动服务。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动性</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 下面的方案章节包含参考体系结构、DNS 示例、端口/协议定义和证书要求。 另外还包含表明您的 DNS、端口/协议定义和证书需求的图表。 这些图表提供一个模板供您填写并会将其分发给其他团队（例如，贵组织的网络团队、公钥基础结构团队和服务器部署团队）。 图的目标是增强通信，并确保在将所需的边缘服务器配置元素与将执行实际配置工作的人员进行通信时能够成功。 建议使用这些图表和相关参考体系结构来规划部署。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

