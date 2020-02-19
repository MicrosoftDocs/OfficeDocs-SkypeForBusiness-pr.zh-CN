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
ms.openlocfilehash: 5010608f05f99d1d1830874a80b6f9f44fd25b38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-04_

在部署外围网络并实现对外部用户的支持之前，必须已部署 Microsoft Lync Server 2013 内部服务器，包括前端池或 Standard Edition 服务器。 如果计划在内部网络中部署可选控制器，还应在部署边缘服务器之前部署它们。 有关控制器部署过程的详细信息，请参阅规划文档中的[Lync Server 2013 中的 Director 应用场景](lync-server-2013-scenarios-for-the-director.md)。

Microsoft Lync Server 2013 包括便于规划和部署内部服务器和边缘服务器的工具。 在完成拓扑后，可将生成的拓扑定义发布到您的生产环境。 为此，您必须具有 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员身份。

  - **规划工具**   Office 通信服务器 2007 R2 包含一个规划工具和一个边缘规划工具，可用于帮助引导拓扑设计。 在 Lync Server 2010 中，这两个工具组合在一起，后者具有其他特性和功能，例如，收集计划的用户计数、语音要求、外部用户访问类型和联合身份验证选项。 另外，您还可以规划基础结构的网络参数，例如 IP 地址、负载平衡器类型和其他外围网络注意事项。

  - **拓扑生成器**   Lync Server 2013 拓扑生成器可帮助你定义拓扑和组件。 拓扑生成器是部署运行 Lync Server 2013 的服务器所必需的。 拓扑生成器将结果发布到一个中央管理存储区，该存储用于配置组织中运行 Lync Server 2013 的所有服务器。 在不使用拓扑生成器的情况下无法在服务器上安装 Lync Server 2013。

如果您在规划过程中设计了边缘拓扑，包括运行拓扑生成器以定义边缘拓扑，则可以使用这些结果来启动边缘服务器部署。 如果您之前未完成建立边缘拓扑或要更改以前指定的信息，则必须先完成运行拓扑生成器，然后再继续执行其他部署步骤。 有关如何构建拓扑的详细信息，请参阅[Lync Server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)。

有关规划工具和拓扑生成器的详细信息，请参阅规划文档中的[开始规划 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。

下表概述了边缘服务器部署过程。 若要查看在部署外部用户访问之前必须做出的规划决策，请参阅[Lync Server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)。

<div>


> [!WARNING]  
> 下表中的信息主要涉及新的部署。 如果已在 Lync Server 2010、Office 通信服务器 2007 R2 或 Office 通信服务器2007环境中部署了边缘服务器，请参阅<A href="migration.md">迁移</A>以了解有关迁移到 Lync Server 2013 的详细信息。 Office 通信服务器 2007 R2 之前的任何版本都不支持迁移，包括 Office 通信服务器2007、Live 通信服务器2005和 Live 通信服务器2003。



</div>

为了提高边缘服务器的性能和安全性，同时为了方便部署，在部署外围网络和边缘服务器时，请应用以下最佳做法：

  - 只有在组织内部的 Lync Server 2013 经过测试和验证后，才部署边缘服务器。

  - 我们建议您将边缘服务器部署到工作组中，而不是域中。这样做可以简化安装，并将 Active Directory 域服务 (AD DS) 置于外围网络外面。将 AD DS 置于外围网络中可能会造成严重的安全风险。

  - 支持将边缘服务器加入完全位于外围网络中的域，但不建议这样做。将边缘服务器作为内部域的一部分将影响受信任的网络边界，在此类环境中，Internet 是最不受信任的，外围网络比 Internet 的受信任程度略高，而内部网络是最受信任的。边缘服务器作为域成员将自动成为最受信任网络的一部分，但它却位于受信任程序较低的网络中（外围）。

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
<th>Permissions</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>创建相应的边缘拓扑并确定相应的组件。</p></td>
<td><ul>
<li><p>运行拓扑生成器以配置边缘服务器设置，并创建和发布拓扑，然后使用 Lync Server 命令行管理程序导出拓扑配置文件。</p></li>
</ul></td>
<td><p><strong>Domain Admins</strong>组和<strong>RTCUniversalServerAdmins</strong>或<strong>CsAdmins</strong>组</p>
<div>

> [!NOTE]  
> 可以使用本地 Users 组成员的帐户定义拓扑，但发布拓扑需要使用 <STRONG>Domain Admins</STRONG> 组和 <STRONG>RTCUniversalServerAdmins</STRONG> 组成员的帐户。


</div></td>
<td><p>在部署文档的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中构建边缘和控制器拓扑</a></p></td>
</tr>
<tr class="even">
<td><p>准备安装。</p></td>
<td><ol>
<li><p>确保满足系统先决条件。</p></li>
<li><p>配置每台边缘服务器上面向内部网络接口和面向公共网络接口的 IP 地址（如果使用，则为 IPv4 和 IPv6）。</p></li>
<li><p>配置内部和外部 DNS 记录（IPv4 和 IPv6 的主机 A 和 AAAA），包括配置要部署为边缘服务器的计算机上的 DNS 后缀。</p></li>
<li><p>（可选）创建并安装公共证书。获取证书所需的时间取决于颁发证书的证书颁发机构 (CA)。如果此时不执行该步骤，则必须在安装边缘服务器期间执行。在获取并安装证书之前，无法启动边缘服务器服务。</p></li>
<li><p>如果部署支持与 Windows Live、AOL 或 Yahoo! 用户通信，则设置对公共 IM 连接的支持。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>


</div></li>
<li><p>如果您的部署将使用这些服务，则对 Office 通信服务器2007、Office 通信服务器 2007 R2 和 Lync Server 2010 合作伙伴的 XMPP 和联合支持的预配支持</p></li>
<li><p>配置防火墙。</p></li>
</ol></td>
<td><p>根据组织需要</p></td>
<td><p>准备在部署文档中为<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 在外围网络中安装服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>安装反向代理。</p></td>
<td><ul>
<li><p>在外围网络中设置反向代理（例如，对于 Microsoft Forefront 威胁管理网关2010或 Microsoft Internet Security and 加速（ISA） Server，使用 Service Pack 1），获取必要的公共证书，并配置反向代理服务器上的 web 发布规则。</p>
<p>如果您制定了移动计划并且要在前端池或 Standard Edition Server 上部署移动服务，请准备反向代理以提供移动服务。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 组或反向代理管理员</p></td>
<td><p>在部署文档中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">为 Lync Server 2013 设置反向代理服务器</a></p></td>
</tr>
<tr class="even">
<td><p>安装控制器（可选）。</p></td>
<td><ul>
<li><p>（可选）在内部网络中安装并配置一个或多个控制器。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 组</p></td>
<td><p>在部署文档的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 中设置控制器</a></p></td>
</tr>
<tr class="odd">
<td><p>安装边缘服务器。</p></td>
<td><ol>
<li><p>安装系统必备软件。</p></li>
<li><p>将导出的拓扑配置文件传输到每台边缘服务器。</p></li>
<li><p>在每台边缘服务器上安装 Lync Server 2013 软件。</p></li>
<li><p>配置边缘服务器。</p></li>
<li><p>为每台边缘服务器请求并安装证书。</p></li>
<li><p>启动边缘服务器服务。</p></li>
</ol></td>
<td><p><strong>Administrators</strong> 组</p></td>
<td><p>在部署文档中<a href="lync-server-2013-setting-up-edge-servers.md">设置 Lync Server 2013 中的边缘服务器</a></p></td>
</tr>
<tr class="even">
<td><p>配置外部用户访问部署。</p></td>
<td><ol>
<li><p>使用 Lync Server 控制面板配置对以下各项（如果适用）的支持：</p>
<ul>
<li><p>媒体中继</p></li>
<li><p>联盟路由</p></li>
<li><p>远程用户访问</p></li>
<li><p>与 Lync Server、Office 通信服务器和实时通信服务器的联盟</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
<li><p>匿名用户</p></li>
</ul></li>
<li><p>为实现远程用户访问、联盟、公共 IM 连接、XMPP 和匿名用户支持配置用户帐户（如果适用）</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</p></td>
<td><p>在部署文档中<a href="lync-server-2013-configuring-support-for-external-user-access.md">配置对 Lync Server 2013 中的外部用户访问的支持</a></p></td>
</tr>
<tr class="odd">
<td><p>验证边缘服务器配置。</p></td>
<td><ol>
<li><p>验证服务器连接和从内部服务器复制的配置数据。</p></li>
<li><p>根据您的部署，验证外部用户（包括远程用户、联盟域中的用户、公共 IM 用户和匿名用户）能否进行连接。</p></li>
<li><p>使用 Lync Server 远程连接分析器验证配置和通信<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>解决配置和通信难题</p></li>
</ol></td>
<td><p>对于复制验证，<strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</p>
<p>对于用户连接验证，支持的各种类型的外部用户访问的用户</p>
<p>远程用户</p></td>
<td><p>在部署文档中<a href="lync-server-2013-verifying-your-edge-deployment.md">验证 Lync Server 2013 中的边缘部署</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

