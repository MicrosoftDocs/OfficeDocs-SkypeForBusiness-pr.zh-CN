---
title: Lync Server 2013：规划 Lync Server 混合部署
TOCTitle: 规划 Lync Server 混合部署
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205403(v=OCS.15)
ms:contentKeyID: 49314795
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划 Lync Server 2013 混合部署

 

_**上一次修改主题：** 2016-12-08_

规划混合部署时应考虑用户和您的网络基础结构的以下要求。

## 基础结构要求

您必须在您的环境中具有以下内容才能实现和配置 Lync Server 2013 混合环境。

  - 启用了 Lync Online 的 Office 365 租户。

  - 本地或使用 Microsoft Azure 的 Active Directory 联合身份验证服务 (AD FS) 服务器。有关 AD FS 的详细信息，请参阅 [Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=393795) 或 [为 Windows Azure Pack 配置 Active Directory 联合身份验证服务](http://go.microsoft.com/fwlink/p/?linkid=522475)。

  - 应用了 Lync Server 2010 2013 年 3 月的累积更新的 Lync Server 2013 或 Lync Server 2010 的本地部署。

  - Lync Server 2013 管理工具。

  - 目录同步。有关目录同步的详细信息，请参阅[混合身份管理](http://go.microsoft.com/fwlink/p/?linkid=231010)。

## Lync 客户端支持

Lync 客户端中支持的功能以及本地和联机环境中可用的功能存在一些差异。在您确定要驻留组织中的用户的位置之前，您可以查看 Lync Server 不同配置的客户端支持。在 Lync 混合部署中，对 Skype for Business Online 支持以下客户端：

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

## 拓扑要求

若要使用 Skype for Business Online 配置您的 Lync Server 2013 混合部署，您需要具有以下支持的拓扑之一：

  - 本地具有 Lync Server 2013 的 Microsoft Office Communications Server 2007 R2。 Lync Server 2013 联盟 边缘服务器和联盟 边缘服务器中的下一个跃点服务器必须运行 Lync Server 2013，且必须已部署中央管理存储。 边缘服务器和池必须在本地部署。
    
    > [!IMPORTANT]
    > 尽管此拓扑受支持，但是某些功能可能会受限制。例如，Microsoft Lync Online 用户和本地 Office Communications Server 2007 R2 用户之间的状态信息无法按预期工作。


  - 应用了 Lync Server 2010 2013 年 3 月累积更新（或最新更新）的 Microsoft Lync Server 2010 和本地安装的 Lync Server 2013 管理工具。联盟 边缘服务器和来自联盟 边缘服务器的下一个跃点服务器必须运行应用了 2013 年 3 月（或最新）累积更新的 Microsoft Lync Server 2010。
    
    > [!IMPORTANT]
    > Lync Server 2013 管理工具应安装在有访问权限连接到现有 Lync Server 2010 部署的独立服务器上。可将用户从您的内部部署移动到 Lync Online 的 Move-CsUser cmdlet 必须从连接到您的内部部署的 Lync Server 2013 管理工具运行。


  - 所有服务器都运行 Lync Server 2013 的 Lync Server 2013 部署。

有关支持的拓扑的详细信息，请参阅[Lync Server 2013 中支持的拓扑](lync-server-2013-supported-topologies.md)和[用于企业混合部署的 Lync Server 2013 参考拓扑](http://go.microsoft.com/fwlink/p/?linkid=398709)。

有关混合部署和将 PowerShell 连接到 Lync Online 的故障排除信息，请参阅 [Lync Online：Lync PowerShell 和混合故障排除](http://go.microsoft.com/fwlink/p/?linkid=306718)。

## 联盟允许/阻止列表的要求

允许域列表包括已配置合作伙伴“边缘”完全限定域名 (FQDN) 的域。这些域有时也称*允许的合作伙伴服务器* 或*直接联盟合作伙伴*。您应熟悉开放联盟和封闭联盟（在本地部署中分别称为*合作伙伴发现* 和*允许的合作伙伴域列表*）之间的差异。

必须满足以下要求才能成功配置混合部署：

  - 为您的本地部署和您的 Office 365 租户配置的域匹配必须相同。如果在本地部署中启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。如果未启用合作伙伴发现，则必须为您的联机租户配置封闭联盟。

  - 本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。

  - 本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。

  - 必须启用联盟以实现联机租户的外部通信，这可通过使用 Lync Online 控制面板来配置。

## DNS 设置

为混合部署创建 DNS SRV 记录时，记录 \_sipfederationtls.\_tcp.\<域\> 和\_sip.\_tls.\<域\> 应指向本地访问代理。

## 防火墙注意事项

您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。

根据您的 Microsoft Online Services 数据中心的位置，您还必须配置网络防火墙设备以接受基于通配符域名（例如，来自 \*.outlook.com 的所有流量）的连接，如果贵组织的防火墙不支持通配符名称配置，您必须手动确定您要允许的 IP 地址范围以及指定端口。

请参阅帮助主题 [Office 365 URL 和 IP 地址范围](http://go.microsoft.com/fwlink/?linkid=252942)。

## 端口和协议要求

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
<td><p>对入站方向开放</p>
<ul>
<li><p>Active Directory 联合身份验证服务（联合服务器角色）</p>
<p>有关详细信息，请参阅了解 <a href="http://go.microsoft.com/fwlink/?linkid=281899">AD FS 角色服务</a>。</p></li>
<li><p>Active Directory 联合身份验证服务（代理服务器角色）</p></li>
<li><p>Microsoft Online Services 门户</p></li>
<li><p>我的公司门户</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 客户端（从本地 Lync Server 与 Lync Online 进行通信）</p></li>
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
<td><p>在 边缘服务器上打开入站/出站</p></td>
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
<tr class="even">
<td><p>TCP 443</p></td>
<td><p>对入站方向开放</p>
<ul>
<li><p>Active Directory 联合身份验证服务（联合服务器角色）</p>
<p>有关详细信息，请参阅了解 <a href="http://go.microsoft.com/fwlink/?linkid=281899">AD FS 角色服务</a>。</p></li>
<li><p>Active Directory 联合身份验证服务（代理服务器角色）</p></li>
<li><p>Microsoft Online Services 门户</p></li>
<li><p>我的公司门户</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 客户端（从本地 Lync Server 与 Lync Online 进行通信）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 80 和 443</p></td>
<td><p>对入站方向开放</p>
<ul>
<li><p>Microsoft Online Services 目录同步工具</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 5061</p></td>
<td><p>在 边缘服务器上打开入站/出站</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/TLS 443</p></td>
<td><p>为数据共享会话打开入站/出站</p></td>
</tr>
<tr class="even">
<td><p>STUN/TCP 443</p></td>
<td><p>为音频、视频、应用程序共享会话打开入站/出站</p></td>
</tr>
<tr class="odd">
<td><p>STUN/UDP 3478</p></td>
<td><p>为音频和视频会话打开入站/出站</p></td>
</tr>
<tr class="even">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>为音频和视频会话打开出站</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 如果需要与运行 Office Communications Server 2007 的合作伙伴联盟，您将需要打开入站/出站 RTP/UDP 和 RTP/TCP 端口 50000-59999。有关 A/V 防火墙要求的详细信息，请参阅 <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</a>。有关端口和协议的详细信息，请参阅 <a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘</a>。



## 用户帐户和数据

在 Lync Server 2013 混合部署中，必须首先在本地部署中创建任何您要驻留在 Lync Online 中的用户，以便在 Active Directory 域服务中创建用户帐户。然后，您可以将用户移动到 Skype for Business Online，这将移动用户的联系人列表。

当您使用 AD FS 和 Dirsync 在 Lync 本地和 Lync Online 部署之间同步用户帐户时，您需要在您的本地和联机 Lync 部署之间为贵组织中的所有 Lync 帐户同步 AD 帐户，即使用户未移动到 Lync Online 也是如此。如果未同步所有用户，则您的组织中的本地和联机用户之间的通信可能无法按预期工作。

> [!IMPORTANT]
> 如果用户是使用 Office 365 的联机门户创建的，则用户帐户将不会与本地 Active Directory 同步，且该用户不会存在于本地 Active Directory 中。如果您已在 Lync Online 中创建用户，并且希望配置与本地 Lync Server 的混合，请参阅本地部署中启用，请参阅<a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">在 Lync Server 2013 中将 Lync Online 用户迁移至本地 Lync</a>。


规划混合部署时还应考虑以下用户相关的问题。

  - **用户联系人**   Lync Online 用户联系人限制为 250 人。当帐户移动到 Lync Online 时，将从用户联系人列表中删除超过此数目的所有联系人。

  - **即时消息和状态**   用户联系人列表、组和访问控制列表 (ACL) 将与用户帐户一起迁移。

  - **会议数据、会议内容和安排的会议**   此内容将不会与用户帐户一起迁移。用户必须在其帐户迁移到 Lync Online 之后重新安排会议。

## 用户策略和功能

  - 在 Lync Server 2013 混合环境中，可为本地或联机用户（但不是同时）启用即时消息、语音和会议。

  - **Lync 客户端**   部分用户可能在移至 Lync Online 时需要新的客户端版本。对于 Office Communications Server 2007 R2，用户必须先移至 Lync Server 2013 池，然后才能迁移到 Lync Online。
    
    有关客户端支持的详细信息，请参阅 [Lync Online 客户端](http://go.microsoft.com/fwlink/?linkid=281902)和[支持的 Lync 客户端和网络端口配置](http://go.microsoft.com/fwlink/?linkid=281901)。

  - **内部策略和配置（非用户）**   联机和本地策略需要单独的配置。无法设置适用于二者的全局策略。

