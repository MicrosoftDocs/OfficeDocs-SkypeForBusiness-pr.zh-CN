---
title: Lync Server 2013：外部用户访问的部署清单
TOCTitle: 外部用户访问的部署清单
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425910(v=OCS.15)
ms:contentKeyID: 49312606
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中外部用户访问的部署清单

 

_**上一次修改主题：** 2015-03-09_

在部署外围网络并实现外部用户支持之前，必须已部署 Microsoft Lync Server 2013 内部服务器，包括 前端池或 Standard Edition Server。如果您计划在内部网络中部署可选 控制器，您同样应该在部署 边缘服务器之前部署它们。有关 控制器部署过程的详细信息，请参阅规划文档中的 [Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)。

Microsoft Lync Server 2013 所含工具可同时简化内部服务器和边缘服务器的规划和部署。在完成拓扑后，可将生成的拓扑定义发布到您的生产环境。为此，您必须具有 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员身份。

  - **规划工具**    Office Communications Server 2007 R2 包括规划工具和边缘规划工具，可用于帮助指导拓扑设计。在 Lync Server 2010 中，这两个工具已组合为一个 规划工具，该工具可提供收集规划的用户计数、语音要求、外部用户访问类型和联盟选项等附加功能。另外，您还可以规划基础结构的网络参数，例如 IP 地址、负载平衡器类型和其他外围网络注意事项。

  - **拓扑生成器**    Lync Server 2013  拓扑生成器可帮助您定义拓扑和组件。 拓扑生成器对于部署运行 Lync Server 2013 的服务器至关重要。 拓扑生成器将结果发布到用于配置贵组织中运行 Lync Server 2013 的所有服务器的 中央管理存储。您无法在不使用 拓扑生成器的情况下在服务器上安装 Lync Server 2013。

如果在规划过程中设计了边缘拓扑（包括运行 拓扑生成器以定义边缘拓扑），则可以使用这些结果开始部署边缘服务器。如果您之前没有完成边缘拓扑构建，或想要更改之前指定的信息，则必须在继续执行其他部署步骤前运行 拓扑生成器。有关如何构建拓扑的详细信息，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

有关规划工具和拓扑生成器的详细信息，请参阅规划文档中的 [开始 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。

下表概述了边缘服务器部署过程。要审核在部署外部用户访问之前必须做出的规划决策，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

> [!WARNING]
> 下表中的信息主要涉及新的部署。如果已在 Lync Server 2010、Office Communications Server 2007 R2 或 Office Communications Server 2007 环境中部署了边缘服务器，请参阅<a href="migration.md">迁移</a>以了解有关迁移到 Lync Server 2013 的详细信息。Office Communications Server 2007 R2 之前的所有版本（包括 Office Communications Server 2007、Live Communications Server 2005 和 Live Communications Server 2003）均不支持迁移。


为了提高边缘服务器的性能和安全性，同时为了方便部署，在部署外围网络和边缘服务器时，请应用以下最佳做法：

  - 仅在已测试和验证 Lync Server 2013 在贵组织中的运行后才部署边缘服务器。

  - 我们建议您将边缘服务器部署到工作组中，而不是域中。这样做可以简化安装，并将 Active Directory 域服务 (AD DS) 置于外围网络外面。将 AD DS 置于外围网络中可能会造成严重的安全风险。

  - 支持将边缘服务器加入完全位于外围网络中的域，但不建议这样做。将边缘服务器作为内部域的一部分将影响受信任的网络边界，在此类环境中，Internet 是最不受信任的，外围网络比 Internet 的受信任程度略高，而内部网络是最受信任的。边缘服务器作为域成员将自动成为最受信任网络的一部分，但它却位于受信任程序较低的网络中（外围）。

## 边缘服务器的部署过程


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
<td><p>创建相应的边缘拓扑并确定相应的组件。</p></td>
<td><ul>
<li><p>运行 拓扑生成器配置边缘服务器设置并创建和发布拓扑，然后使用 Lync Server 命令行管理程序导出拓扑配置文件。</p></li>
</ul>
<p></p></td>
<td><p><strong>Domain Admins</strong> 组和 <strong>RTCUniversalServerAdmins</strong> 或 <strong>CsAdmins</strong> 组</p>
<div>

> [!NOTE]  
> 可以使用本地 Users 组成员的帐户定义拓扑，但发布拓扑需要使用 <strong>Domain Admins</strong> 组和 <strong>RTCUniversalServerAdmins</strong> 组成员的帐户。


</div></td>
<td><p>部署文档中的 <a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中构建边缘和控制器拓扑</a></p></td>
</tr>
<tr class="even">
<td><p>准备安装。</p></td>
<td><ol>
<li><p>确保满足系统先决条件。</p></li>
<li><p>配置每台边缘服务器上面向内部网络接口和面向公共网络接口的 IP 地址（如果使用，则为 IPv4 和 IPv6）。</p></li>
<li><p>配置内部和外部 DNS 记录（IPv4 和 IPv6 的主机 A 和 AAAA），包括配置要部署为边缘服务器的计算机上的 DNS 后缀。</p></li>
<li><p>（可选）创建并安装公共证书。获取证书所需的时间取决于颁发证书的证书颁发机构 (CA)。如果此时不执行该步骤，则必须在安装边缘服务器期间执行。在获取并安装证书之前，无法启动边缘服务器服务。</p></li>
<li><p>如果部署支持与 Windows Live、AOL 或 Yahoo! 用户通信，则设置对公共 IM 连接的支持。</p>

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>

</li>
<li><p>如果您的部署将使用以下内容，请配置 XMPP 支持以及 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 合作伙伴的联盟支持</p></li>
<li><p>配置防火墙。</p></li>
</ol></td>
<td><p>根据组织需要</p></td>
<td><p>部署文档中的<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">准备针对 Lync Server 2013 在外围网络中安装服务器</a></p></td>
</tr>
<tr class="odd">
<td><p>安装反向代理。</p></td>
<td><ul>
<li><p>在外围网络中安装反向代理（例如，面向 Microsoft Forefront Threat Management Gateway 2010 或 Microsoft Internet Security and Acceleration (ISA) 服务器 Service Pack 1）、获取所需公共证书并在反向代理服务器上配置 Web 发布规则。</p>
<p>如果您制定了移动计划并且要在前端池或 Standard Edition Server 上部署移动服务，请准备反向代理以提供移动服务。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 组或反向代理管理员</p></td>
<td><p></p>
<p>部署文档中的<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">为 Lync Server 2013 设置反向代理服务器</a></p></td>
</tr>
<tr class="even">
<td><p>安装控制器（可选）。</p></td>
<td><ul>
<li><p>（可选）在内部网络中安装并配置一个或多个控制器。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 组</p></td>
<td><p>部署文档中的<a href="lync-server-2013-setting-up-the-director.md">在 Lync Server 2013 中设置控制器</a></p></td>
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
<td><p>部署文档中的<a href="lync-server-2013-setting-up-edge-servers.md">在 Lync Server 2013 中设置边缘服务器</a></p></td>
</tr>
<tr class="even">
<td><p>配置外部用户访问部署。</p></td>
<td><ol>
<li><p>使用 Lync Server 控制面板配置对以下各项内容的支持（如果适用）：</p>
<ul>
<li><p>媒体中继</p></li>
<li><p>联盟路由</p></li>
<li><p>远程用户访问</p></li>
<li><p>与 Lync Server、 Office Communications Server 和 Live Communications Server 联盟</p></li>
<li><p>公共 IM 连接</p></li>
<li><p>XMPP 联盟</p></li>
<li><p>匿名用户</p></li>
</ul></li>
<li><p>为实现远程用户访问、联盟、公共 IM 连接、XMPP 和匿名用户支持配置用户帐户（如果适用）</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</p>
<p></p></td>
<td><p>部署文档中的<a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a></p></td>
</tr>
<tr class="odd">
<td><p>验证边缘服务器配置。</p></td>
<td><ol>
<li><p>验证服务器连接和从内部服务器复制的配置数据。</p></li>
<li><p>根据您的部署，验证外部用户（包括远程用户、联盟域中的用户、公共 IM 用户和匿名用户）能否进行连接。</p></li>
<li><p>使用 Lync Server 远程连接分析器 <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a> 验证配置和通信</p></li>
<li><p>解决配置和通信难题</p></li>
</ol></td>
<td><p>对于复制验证， <strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</p>
<p>对于用户连接验证，支持的各种类型的外部用户访问的用户</p>
<p>远程用户</p></td>
<td><p>部署文档中的<a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中验证边缘部署</a></p></td>
</tr>
</tbody>
</table>

