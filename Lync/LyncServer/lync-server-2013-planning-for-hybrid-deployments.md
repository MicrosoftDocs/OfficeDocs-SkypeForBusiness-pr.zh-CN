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
ms.openlocfilehash: c70002eb7be67c221997465b6cdd5d252df284db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>规划 Lync Server 2013 混合部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-05-25_

在规划混合部署时，应考虑对用户和网络基础结构的以下要求。

<div>

## <a name="infrastructure-requirements"></a>基础结构要求

您必须在您的环境中配置以下各项才能实现和部署混合部署。

  - 启用了 Skype for Business Online 的 Microsoft Office 365 租户。 请注意，您只能将一个租户用于与本地部署的混合配置。

  - 在受支持的拓扑中部署的 Skype for Business Server 或 Lync Server 的单一本地部署（基础架构）。 请参阅拓扑要求。
    
    有关为混合配置 Lync Server 2013 或 Lync Server 2010 部署的信息，请参阅[配置 Lync server 2013 混合部署](lync-server-2013-configuring-hybrid-deployments.md)。

  - Skype for Business Server 2015 管理工具。 如果您使用的是 Lync Server 2013 或 Lync Server 2010，则可以使用 Lync Server 2013 管理工具。

  - 若要支持 Office 365 单一登录，以便用户可以使用与在本地登录 Office 时相同的登录凭据来登录 Office，您可以使用 Azure Active Directory （AAD）连接的密码同步功能。 您还可以将 Active Directory 联合身份验证服务（AD FS）用于 Office 365 的单一登录。
    
    有关详细信息，请参阅[将您的本地标识与 Azure Active Directory 集成](https://go.microsoft.com/fwlink/p/?linkid=619754)。

  - 用于保持本地和联机 Active Directory 对象同步的单个目录同步解决方案。 有关目录同步的详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?linkid=530320)。

</div>

<div>

## <a name="lync-client-support"></a>Lync 客户端支持

Lync 客户端支持的功能以及本地和联机环境中提供的功能存在一些差异。 在决定要在组织中的哪些位置的位置之前，您可以查看不同的 Lync Server 配置的客户端支持。 Lync 混合部署中的 Skype for Business Online 支持以下客户端：

  - Lync 2010

  - Lync 2013

  - Lync Windows 应用商店应用

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync 会议室系统

  - Lync Basic 2013

有关客户端支持的详细信息，请参阅下列主题：

  - [Lync Online 客户端](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 的移动客户端比较表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>拓扑要求

若要配置与 Skype for Business Online 的混合部署，您需要具有以下受支持的拓扑之一：

  - 一个 Skype for business Server 2015 部署，其中包含运行 Skype for Business Server 2015 的所有服务器。

  - Lync Server 2013 部署，其中包含运行 Lync Server 2013 的所有服务器。

  - Lync Server 2010 部署，其中包含运行 Lync Server 2010 的所有服务器以及最新的累积更新。
    
      - 联合边缘服务器和联合边缘服务器中的下一个跃点服务器必须使用最新的累积更新运行 Lync Server 2010。
    
      - Skype for Business Server 2015 或 Lync Server 2013 管理工具必须至少安装在一台服务器或管理工作站上。

  - 混合 Lync Server 2013 和 Skype for Business Server 2015 部署，其中至少有一个运行 Skype for Business Server 2015 的站点中具有以下服务器角色：
    
      - 至少一个企业版池或 Standard Edition server
    
      - 与 SIP 联盟关联的控制器池（如果存在）
    
      - 与 SIP 联盟关联的边缘池

  - 混合 Lync Server 2010 和 Skype for Business Server 2015 部署，其中至少有一个运行 Skype for Business Server 2015 的站点中具有以下服务器角色：
    
      - 至少一个企业版池或 Standard Edition server
    
      - 与 SIP 联盟关联的控制器池（如果存在）
    
      - 与站点的 SIP 联盟关联的边缘池

  - 在至少一个运行 Lync Server 2013 的站点中具有以下服务器角色的混合 Lync Server 2010 和 Lync Server 2013 部署：
    
      - 站点中至少有一个企业版池或 Standard Edition server
    
      - 与 SIP 联盟关联的控制器池（如果它存在于网站中）
    
      - 与站点的 SIP 联盟关联的边缘池

<div>


> [!IMPORTANT]  
> 所有用户管理（包括用户在本地和 UNRESOLVED_TOKEN_VAL 之间移动（skypeforbusiness））都需要使用管理工具的最新安装版本来完成。 管理工具必须安装在具有对现有本地部署和 Internet 的连接访问权限的单独服务器上。 将用户从本地部署移动到 UNRESOLVED_TOKEN_VAL （skype16_online）的<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">get-csuser</A> cmdlet 必须从连接到本地部署的管理工具运行。



</div>

有关支持的拓扑的详细信息，请参阅[Lync server 2013 支持的拓扑](lync-server-2013-supported-topologies.md)和[适用于企业混合部署的 Lync Server 2013 参考拓扑](https://go.microsoft.com/fwlink/p/?linkid=398709)。

有关混合部署和将 PowerShell 连接到 Lync Online 的故障排除信息，请参阅[Lync Online： Lync PowerShell 和混合故障排除](https://go.microsoft.com/fwlink/p/?linkid=306718)。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>联合身份验证允许/阻止列表的要求

"允许的域" 列表包括已配置合作伙伴边缘完全限定域名（FQDN）的域。 这有时称为 "允许的*合作伙伴服务器*" 或 "*直接联盟伙伴*"。 您应熟悉开放联合身份验证和已关闭联盟之间的区别（分别称为 "*合作伙伴发现*" 和 "*允许的合作伙伴域列表*"），在本地部署中。

若要成功配置混合部署，必须满足以下要求：

  - 必须为您的本地部署和 Office 365 租户配置域匹配。 如果在本地部署上启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。 如果未启用合作伙伴发现，则必须为您的联机租户配置关闭的联合身份验证。

  - 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。

  - 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。

  - 必须为使用 Lync Online 控制面板配置的联机租户的外部通信启用联合。

</div>

<div>

## <a name="dns-settings"></a>DNS 设置

在为混合部署创建 DNS 记录时，所有 Lync 外部 DNS 记录都应指向内部部署基础结构。 有关所需 DNS 记录的详细信息，请参阅[Lync Server 2013 的域名系统（DNS）要求](lync-server-2013-domain-name-system-dns-requirements.md)。

此外，还需要确保下表中所述的 DNS 解析在本地部署中运行：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS 记录</p></td>
<td><p>可解析者</p></td>
<td><p>DNS 要求</p></td>
</tr>
<tr class="even">
<td><p>_Sipfederationtls _tcp 的 DNS SRV 记录。&lt;sipdomain.com&gt;用于所有受支持的 SIP 域解析为访问边缘外部 IP （s）</p></td>
<td><p>边缘服务器</p></td>
<td><p>在混合配置中启用联合通信。 边缘服务器需要知道为在本地和联机之间拆分的 SIP 域路由联盟流量的位置。</p></td>
</tr>
<tr class="odd">
<td><p>用于边缘 Web 会议服务 FQDN 的 DNS A 记录，例如，webcon.contoso.com 解析为 Web 会议边缘外部 IP （s）</p></td>
<td><p>连接到用户计算机的内部公司网络</p></td>
<td><p>使联机用户能够在本地托管会议中显示或查看内容。 内容包括 PowerPoint 文件、白板、投票和共享便笺。</p></td>
</tr>
</tbody>
</table>


根据组织中配置 DNS 的方式，您可能需要将这些记录添加到相应 SIP 域的内部托管 DNS 区域中，以提供对这些记录的内部 DNS 解析。

</div>

<div>

## <a name="firewall-considerations"></a>防火墙注意事项

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据 Microsoft Online Services 数据中心的位置，您还必须将网络防火墙设备配置为根据通配符域名（例如，所有来自\*outlook.com 的流量）接受连接。 如果组织的防火墙不支持通配符名称配置，则必须手动确定要允许和指定端口的 IP 地址范围。

请参阅帮助主题 " [Office 365 url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?linkid=252942)"。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>端口和协议要求

除了内部 Lync Server 2013 通信的端口要求之外，还必须配置以下端口。


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
<td><p>对入站方向开放</p>
<ul>
<li><p>Active Directory 联合身份验证服务（联合服务器角色）</p>
<p>有关详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=281899">了解 AD FS 角色服务</a>。</p></li>
<li><p>Active Directory 联合身份验证服务（代理服务器角色）</p></li>
<li><p>Microsoft Online Services 门户</p></li>
<li><p>我的公司门户</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 客户端（从内部部署 Lync Server 与 Lync Online 的通信）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 和 443</p></td>
<td><p>对入站方向开放</p>
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

在 Lync Server 2013 混合部署中，您要在家中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。 然后，您可以将用户移动到 Skype for Business Online，这将移动用户的联系人列表。

当您在 Lync 本地部署和使用 AD FS 的 Lync Online 部署之间同步用户帐户时，您需要在本地和联机 Lync 部署之间同步组织中的所有 Lync 用户的 AD 帐户，即使用户不会移动到 Lync Online。 如果不同步所有用户，组织中的内部部署用户和联机用户之间的通信可能无法按预期工作。

<div>


> [!IMPORTANT]  
> 如果用户是使用适用于 Office 365 的联机门户创建的，则该用户帐户将不会与本地 Active Directory 同步，并且该用户将不会存在于本地 Active Directory 中。 如果你已在 Lync Online 中创建用户，并且想要使用本地 Lync Server 配置混合，请参阅<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中的将用户从 Lync Online 移动到 lync 本地</A>。



</div>

在规划混合部署时，还应考虑以下与用户相关的问题。

  - **用户联系人**   Lync Online 用户的联系人限制为250。 当帐户移动到 Lync Online 时，该号码之外的所有联系人都将从用户的联系人列表中删除。

  - **即时消息和状态**   用户联系人列表、组和访问控制列表（acl）随用户帐户一起迁移。

  - **会议数据、会议内容和计划会议**   此内容不会随用户帐户一起迁移。 用户必须在其帐户迁移到 Lync Online 之后重新安排会议。

</div>

<div>

## <a name="user-policies-and-features"></a>用户策略和功能

  - 在 Lync Server 2013 混合环境中，可以对本地或联机的即时消息、语音和会议启用用户，但不能同时启用两者。

  - **Lync 客户端**   在移动到 Lync Online 时，某些用户可能需要新的客户端版本。 对于 Office 通信服务器 2007 R2，在迁移到 Lync Online 之前，必须将用户移动到 Lync Server 2013 池。
    
    有关客户端支持的详细信息，请参阅[适用于 Lync Online 的客户端](https://go.microsoft.com/fwlink/p/?linkid=281902)和[支持的 lync 客户端和网络端口配置](https://go.microsoft.com/fwlink/p/?linkid=281901)。

  - **本地策略和配置（非用户）**   联机和本地策略需要单独的配置。 无法设置同适用于二者的全局策略。

</div>

</div>

<span> </span>

</div>

</div>

</div>

