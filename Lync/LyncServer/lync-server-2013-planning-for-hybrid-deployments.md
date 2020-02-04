---
title: Lync Server 2013：规划混合部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>规划 Lync Server 2013 混合部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-05-25_

规划混合部署时，应考虑针对用户和网络基础结构的以下要求。

<div>

## <a name="infrastructure-requirements"></a>基础结构要求

你必须在你的环境中配置以下配置，才能实现和部署混合部署。

  - 已启用 Skype for Business Online 的 Microsoft Office 365 租户。 请注意，你只能将单个租户用于你的本地部署的混合配置。

  - 在受支持的拓扑中部署的 Skype for business 服务器或 Lync Server 的单个本地部署（基础架构）。 请参阅拓扑要求。
    
    有关为混合配置 Lync Server 2013 或 Lync Server 2010 部署的信息，请参阅[配置 Lync server 2013 混合部署](lync-server-2013-configuring-hybrid-deployments.md)。

  - Skype for Business Server 2015 管理工具。 如果您使用的是 Lync Server 2013 或 Lync Server 2010，则可以使用 Lync Server 2013 管理工具。

  - 若要支持使用 Office 365 的单一登录，以便用户可以使用相同的登录凭据登录到 Office，因为它们是在本地执行的，你可以使用 Azure Active Directory （AAD）连接的密码同步功能。 还可以使用 Active Directory 联合身份验证服务 (AD FS) 来进行 Office 365 单一登录。
    
    有关详细信息，请参阅[将本地标识与 Azure Active Directory 集成](http://go.microsoft.com/fwlink/p/?linkid=619754)。

  - 用于保持本地和联机 Active Directory 对象同步的单个目录同步解决方案。 有关目录同步的详细信息，请参阅[目录集成工具](http://go.microsoft.com/fwlink/p/?linkid=530320)。

</div>

<div>

## <a name="lync-client-support"></a>Lync 客户端支持

Lync 客户端支持的功能有一些差异，以及本地和联机环境中的可用功能。 在决定您想要在您的组织中的哪个位置开始用户，您可以查看 Lync Server 的各种配置的客户支持。 Lync 混合部署中的 Skype for Business Online 支持以下客户端：

  - Lync 2010

  - Lync 2013

  - Lync Windows 应用商店应用

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync Room System

  - Lync Basic 2013

有关客户端支持的详细信息，请参阅以下主题：

  - [Lync Online 客户端](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 的移动客户端比较表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>拓扑要求

若要配置与 Skype for Business Online 的混合部署，您需要具有以下支持的拓扑之一：

  - 使用运行 Skype for business Server 2015 的所有服务器的 Skype for business Server 2015 部署。

  - Lync Server 2013 部署，其中包含运行 Lync Server 2013 的所有服务器。

  - Lync Server 2010 部署，其中所有服务器都运行 Lync Server 2010 和最新的累积更新。
    
      - 联合边缘服务器中的联盟边缘服务器和下一个跃点服务器必须运行 Lync Server 2010 和最新的累积更新。
    
      - Skype for Business Server 2015 或 Lync Server 2013 管理工具必须至少安装在一台服务器或管理工作站上。

  - 混合 Lync Server 2013 和 Skype for business Server 2015 部署，其中至少一个运行 Skype for business Server 2015 的网站中具有以下服务器角色：
    
      - 至少一个企业版池或 Standard Edition 服务器 
    
      - 与 SIP 联盟关联的控制器池（如果存在）
    
      - 与 SIP 联盟关联的边缘池

  - 混合 Lync Server 2010 和 Skype for business Server 2015 部署，其中至少一个运行 Skype for business Server 2015 的网站中具有以下服务器角色：
    
      - 至少一个企业版池或 Standard Edition 服务器 
    
      - 与 SIP 联盟关联的控制器池（如果存在）
    
      - 与站点的 SIP 联盟关联的边缘池

  - 混合 Lync Server 2010 和 Lync Server 2013 部署，在至少一个运行 Lync Server 2013 的网站中具有以下服务器角色：
    
      - 站点中至少一个企业版池或 Standard Edition 服务器
    
      - 与 SIP 联盟关联的控制器池（如果站点中存在）
    
      - 与站点的 SIP 联盟关联的边缘池

<div>


> [!IMPORTANT]  
> 所有用户管理，包括用户在本地和 UNRESOLVED_TOKEN_VAL （skypeforbusiness）之间移动，需要使用最新安装版本的管理工具完成。 管理工具必须安装在一个单独的服务器上，该服务器具有对现有本地部署和 Internet 的连接访问权限。 将用户从本地部署移动到 UNRESOLVED_TOKEN_VAL （skype16_online）的<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-csuser</A> cmdlet 必须从连接到本地部署的管理工具运行。



</div>

有关支持的拓扑的详细信息，请参阅[Lync server 2013 中支持的拓扑](lync-server-2013-supported-topologies.md)和[适用于企业混合部署的 Lync Server 2013 参考拓扑](http://go.microsoft.com/fwlink/p/?linkid=398709)。

有关混合部署和将 PowerShell 连接到 Lync Online 的疑难解答信息，请参阅[Lync online： Lync PowerShell 和混合疑难解答](http://go.microsoft.com/fwlink/p/?linkid=306718)。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>联盟允许/阻止列表的要求

允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。这些域有时也称*允许的合作伙伴服务器* 或*直接联盟合作伙伴*。您应熟悉开放联盟和封闭联盟（在本地部署中分别称为*合作伙伴发现* 和*允许的合作伙伴域列表*）之间的差异。

必须满足以下要求才能成功配置混合部署：

  - 为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。

  - 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。

  - 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。

  - 必须为使用 Lync Online 控制面板配置的在线租户的外部通信启用联合身份验证。

</div>

<div>

## <a name="dns-settings"></a>DNS 设置

为混合部署创建 DNS 记录时，所有 Lync 外部 DNS 记录都应指向本地基础结构。 有关所需 DNS 记录的详细信息，请参阅[Lync Server 2013 的域名系统（DNS）要求](lync-server-2013-domain-name-system-dns-requirements.md)。

此外，您还需要确保下表中所述的 DNS 解析在您的本地部署中正常运行：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS 记录</p></td>
<td><p>解析者</p></td>
<td><p>DNS 要求</p></td>
</tr>
<tr class="even">
<td><p>_Sipfederationtls _tcp 的 DNS SRV 记录。&lt;用于&gt;所有支持的 SIP 域的 sipdomain.com，这些 SIP 域解析为访问边缘外部 IP</p></td>
<td><p>边缘服务器</p></td>
<td><p>在混合配置中启用联盟通信。边缘服务器需要知道在什么位置为 SIP 域路由分布在本地设备和在线设备上的联盟流量。</p></td>
</tr>
<tr class="odd">
<td><p>边缘 Web 会议服务 FQDN 的 DNS A 记录，例如解析为 Web 会议边缘外部 IP 的 webcon.contoso.com</p></td>
<td><p>已连接到用户计算机的内部公司网络</p></td>
<td><p>让在线用户能够在本地托管会议中演示或查看内容。内容包括 PowerPoint 文件、白板、轮询和共享笔记。</p></td>
</tr>
</tbody>
</table>


根据 DNS 在您的组织中如何配置，您可能需要将这些记录添加到内部托管 DNS 区域，以便相应的 SIP 域能够提供对这些记录的内部 DNS 解析。

</div>

<div>

## <a name="firewall-considerations"></a>防火墙注意事项

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据 Microsoft Online Services 数据中心的位置，你还必须配置你的网络防火墙设备以接受基于通配符域名的连接（例如，来自 outlook.com 的\*所有流量）。 如果你的组织的防火墙不支持通配符名称配置，你将必须手动确定你希望允许的 IP 地址范围和指定的端口。

请参阅帮助主题 " [Office 365 url 和 IP 地址范围](http://go.microsoft.com/fwlink/p/?linkid=252942)"。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>端口和协议要求

除了内部 Lync Server 2013 通信的端口要求，您还必须配置以下端口。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>协议/端口</th>
<th>应用程序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>打开入站</p>
<ul>
<li><p>Active Directory 联合身份验证服务（联合服务器角色）</p>
<p>有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=281899">了解 AD FS 角色服务</a>。</p></li>
<li><p>Active Directory 联合身份验证服务（代理服务器角色）</p></li>
<li><p>Microsoft Online Services 门户</p></li>
<li><p>我的公司门户</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 客户端（从本地 Lync Server 与 Lync Online 进行通信）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 和443</p></td>
<td><p>打开入站</p>
<ul>
<li><p>Microsoft Online Services 目录同步工具</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>在边缘服务器上打开入站/出站</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>为数据共享会话打开入站/出站</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>为音频、视频、应用程序共享会话打开入站/出站</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>为音频和视频会话打开入站/出站</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>为音频和视频会话打开出站</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>用户帐户和数据

在 Lync Server 2013 混合部署中，你希望在 Lync Online 中开始的任何用户都必须首先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。 然后，你可以将用户移动到 Skype for business Online，这将移动用户的联系人列表。

使用 AD FS 和 Dirsync 在 Lync 本地和 Lync Online 部署之间同步用户帐户时，你需要在本地和联机 Lync 部署之间同步组织中的所有 Lync 用户的广告帐户，即使用户不会移至 Lync Online。 如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。

<div>


> [!IMPORTANT]  
> 如果用户是使用 Office 365 的联机门户创建的，则用户帐户将不会与本地 Active Directory 同步，并且用户不会存在于本地 Active Directory 中。 如果你已在 Lync Online 中创建了用户，并且想要使用本地 Lync 服务器配置混合，请参阅<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">在 Lync server 2013 中将用户从 Lync Online 移动到本地 lync</A>。



</div>

规划混合部署时还应考虑以下用户相关的问题。

  - **用户联系人**   Lync Online 用户的联系人限制为250。 当帐户移动到 Lync Online 时，将从用户联系人列表中删除超过此数目的所有联系人。

  - **即时消息和状态**   用户联系人列表、组和访问控制列表（acl）使用用户帐户进行迁移。

  - **会议数据、会议内容和已安排的会议**   此内容不会与用户帐户一起迁移。 用户必须在其帐户迁移到 Lync Online 之后重新安排会议。

</div>

<div>

## <a name="user-policies-and-features"></a>用户策略和功能

  - 在 Lync Server 2013 混合环境中，可为本地或联机用户（但不是同时）启用即时消息、语音和会议。

  - **Lync 客户端**   在移动到 Lync Online 时，某些用户可能需要新的客户端版本。 对于 Office 通信服务器 2007 R2，在迁移到 Lync Online 之前，必须将用户移到 Lync Server 2013 池。
    
    有关客户端支持的详细信息，请参阅 Lync Online 和[支持的 lync 客户端和网络端口配置](http://go.microsoft.com/fwlink/p/?linkid=281901)[的客户端](http://go.microsoft.com/fwlink/p/?linkid=281902)。

  - **本地策略和配置（非用户）**   在线和本地策略需要单独配置。 无法设置适用于二者的全局策略。

</div>

</div>

<span> </span>

</div>

</div>

</div>

