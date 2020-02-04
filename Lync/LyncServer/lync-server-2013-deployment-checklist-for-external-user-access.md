---
title: Lync Server 2013：外部用户访问的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部用户访问的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-04_

在部署你的外围网络并实现对外部用户的支持之前，你必须已部署 Microsoft Lync Server 2013 内部服务器，包括前端池或标准版服务器。 如果你计划在内部网络中部署可选控制器，还应在部署 Edge 服务器之前部署它们。 有关 Director 部署过程的详细信息，请参阅规划文档中[Lync Server 2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md)。

Microsoft Lync Server 2013 包括便于规划和部署内部服务器和边缘服务器的工具。 拓扑完成后，将生成的拓扑定义发布到生产环境。 若要执行此操作，您必须是 "**域管理员**" 组和 " **RTCUniversalServerAdmins** " 组的成员。

  - **规划工具**   Office 通信服务器 2007 R2 包括一个计划工具和一条边缘规划工具，可用于帮助指导拓扑设计。 在 Lync Server 2010 中，这两个工具合并到了一个计划工具中，该工具具有额外的功能，例如收集计划的用户计数、语音要求、外部用户访问类型和联盟选项。 此外，你可以规划基础结构的网络参数，例如 IP 地址、负载平衡器类型和其他外围网络注意事项。

  - **拓扑生成器**   Lync Server 2013 拓扑生成器可帮助你定义拓扑和组件。 拓扑生成器对于运行 Lync Server 2013 的服务器来说非常重要。 拓扑生成器将结果发布到用于配置组织中运行 Lync Server 2013 的所有服务器的中央管理存储。 无法在不使用拓扑生成器的情况下在服务器上安装 Lync Server 2013。

如果你在计划过程中设计了 edge 拓扑，包括运行拓扑生成器以定义边缘拓扑，则可以使用这些结果开始边缘服务器部署。 如果你之前未完成构建 edge 拓扑或想要更改以前指定的信息，则必须先完成拓扑生成器运行，然后再继续执行其他部署步骤。 有关如何构建拓扑的详细信息，请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

有关规划工具和拓扑生成器的详细信息，请参阅在规划文档中[开始 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。

下表提供了边缘服务器部署过程的概述。 若要查看在部署外部用户访问之前必须制定的规划决策，请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

<div>


> [!WARNING]  
> 下表中的信息重点介绍新的部署。 如果你已在 Lync Server 2010、Office 通信服务器 2007 R2 或 Office 通信服务器2007环境中部署了 Edge 服务器，请参阅<A href="migration.md">迁移</A>以了解有关迁移到 Lync Server 2013 的详细信息。 Office 通信服务器 2007 R2 之前的任何版本均不支持迁移，包括 Office 通信服务器2007、实时通信服务器2005和实时通信服务器2003。



</div>

若要提高边缘服务器性能和安全性以及便于部署，请在部署外围网络和边缘服务器时应用以下最佳做法：

  - 只有在组织内部对 Lync Server 2013 进行了测试和验证后，才部署 Edge 服务器。

  - 我们建议你在工作组而不是域中部署边缘服务器。 这样做可简化安装并将 Active Directory 域服务（AD DS）保留在外围网络之外。 在外围网络中查找 AD DS 可能会带来严重的安全风险。

  - 支持将 Edge 服务器联接到完全位于外围网络的域，但不建议这样做。 作为内部域的一部分的边缘服务器违反受信任网络边界，其中 Internet 最少受信任，外围网络比 Internet 更受信任，并且内部网络最受信任。 作为域成员的边缘服务器自动成为最受信任网络的一部分，但驻留在不太受信任的网络（周边）中。

<div>

## <a name="deployment-process-for-edge-servers"></a>边缘服务器的部署过程


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>权限</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>创建适当的边缘拓扑，并确定相应的组件。</p></td>
<td><ul>
<li><p>运行拓扑生成器以配置边缘服务器设置，并创建和发布拓扑，然后使用 Lync Server Management Shell 导出拓扑配置文件。</p></li>
</ul></td>
<td><p><strong>域管理员</strong>组和<strong>RTCUniversalServerAdmins</strong>或<strong>CsAdmins</strong>组</p>
<div>

> [!NOTE]  
> 你可以使用属于本地用户组的成员的帐户定义拓扑，但发布拓扑需要一个帐户，该帐户是<STRONG>域管理员</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组的成员。


</div></td>
<td><p>在部署文档的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中构建边缘和控制器拓扑</a></p></td>
</tr>
<tr class="even">
<td><p>准备设置。</p></td>
<td><ol>
<li><p>确保满足系统先决条件。</p></li>
<li><p>为每台边缘服务器上的内部和面向公众的网络接口配置 IP 地址（IPv4 和 IPv6，如果使用）。</p></li>
<li><p>配置内部和外部 DNS 记录（IPv4 和 IPv6 的主机 A 和 AAAA），包括在计算机上配置 DNS 后缀以将其部署为 Edge 服务器。</p></li>
<li><p>可选创建和安装公共证书。 获取证书所需的时间取决于证书颁发机构（CA）颁发的证书。 如果此时不执行此步骤，则必须在安装边缘服务器期间执行此操作。 无法启动 Edge 服务器服务，直到获得并安装证书。</p></li>
<li><p>如果你的部署支持与 Windows Live、AOL 或 Yahoo！的通信，则预配对公共 IM 连接的支持 那些.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>


</div></li>
<li><p>预配支持 Office 通信服务器2007、Office 通信服务器 2007 R2、Lync Server 2010 合作伙伴的 XMPP 和联合支持，如果你的部署将使用这些</p></li>
<li><p>配置防火墙。</p></li>
</ol></td>
<td><p>根据您的组织的需要</p></td>
<td><p>准备在部署文档中<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 的外围网络中安装服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>设置反向代理。</p></td>
<td><ul>
<li><p>在外围网络中设置反向代理（例如，对于 Microsoft Forefront 威胁管理网关2010或 Microsoft Internet 安全和加速（ISA） Server），获取必要的公共证书，并配置反向代理服务器上的 web 发布规则。</p>
<p>如果你计划移动服务并在前端池或标准版服务器上部署移动服务，请为移动服务准备反向代理。</p></li>
</ul></td>
<td><p><strong>管理员</strong>组或反向代理管理员</p></td>
<td><p>在部署文档中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">为 Lync Server 2013 设置反向代理服务器</a></p></td>
</tr>
<tr class="even">
<td><p>设置 Director （可选）。</p></td>
<td><ul>
<li><p>可选在内部网络中安装和配置一个或多个控制器。</p></li>
</ul></td>
<td><p><strong>管理员</strong>组</p></td>
<td><p>在部署文档的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 中设置 Director</a></p></td>
</tr>
<tr class="odd">
<td><p>设置边缘服务器。</p></td>
<td><ol>
<li><p>安装必备软件。</p></li>
<li><p>将导出的拓扑配置文件传输到每台边缘服务器。</p></li>
<li><p>在每台边缘服务器上安装 Lync Server 2013 软件。</p></li>
<li><p>配置边缘服务器。</p></li>
<li><p>为每个边缘服务器请求和安装证书。</p></li>
<li><p>启动边缘服务器服务。</p></li>
</ol></td>
<td><p><strong>管理员</strong>组</p></td>
<td><p>在部署文档的<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 中设置边缘服务器</a></p></td>
</tr>
<tr class="even">
<td><p>为外部用户访问配置部署。</p></td>
<td><ol>
<li><p>使用 Lync Server "控制面板" 配置对以下各项的支持（如果适用）：</p>
<ul>
<li><p>媒体中继</p></li>
<li><p>联盟路线</p></li>
<li><p>远程用户访问</p></li>
<li><p>与 Lync Server、Office 通信服务器和实时通信服务器的联盟</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
<li><p>匿名用户</p></li>
</ul></li>
<li><p>为远程用户访问、联盟、公共 IM 连接、XMPP 和匿名用户支持配置用户帐户（如果适用）</p></li>
</ol></td>
<td><p>分配给<strong>CSAdministrator</strong>角色的<strong>RTCUniversalServerAdmins</strong>组或用户帐户</p></td>
<td><p>在部署文档中<a href="lync-server-2013-configuring-support-for-external-user-access.md">配置 Lync Server 2013 中外部用户访问的支持</a></p></td>
</tr>
<tr class="odd">
<td><p>验证边缘服务器配置。</p></td>
<td><ol>
<li><p>验证服务器连接和来自内部服务器的配置数据的复制。</p></li>
<li><p>验证外部用户是否可以连接，包括远程用户、联盟域中的用户、公共 IM 用户以及匿名用户（根据你的部署情况）。</p></li>
<li><p>使用 Lync Server 远程连接分析器验证配置和通信<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>解决配置和通信问题</p></li>
</ol></td>
<td><p>有关复制的验证，请<strong>RTCUniversalServerAdmins</strong>组或分配给<strong>CSAdministrator</strong>角色的用户帐户</p>
<p>对于用户连接，您支持的每种类型的外部用户访问的用户</p>
<p>远程用户</p></td>
<td><p>在部署文档的<a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 中验证 edge 部署</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

