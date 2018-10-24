---
title: Lync Server 2013：外部用户访问概述
TOCTitle: 外部用户访问概述
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398775(v=OCS.15)
ms:contentKeyID: 49313675
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的外部用户访问概述

 

_**上一次修改主题：** 2016-12-08_

在本文档中，我们使用术语“外部用户”来定义从防火墙外部与 Lync Server 2013 和 Lync 2013 用户进行通信的一个很大的用户类别。可授权使用 Lync Server 2013 与内部用户（即，从防火墙内部登录 Lync Server 的用户）进行通信的外部用户包括：

  - **远程用户**   您所在组织内从防火墙外部登录到 Lync Server 的用户。

  - **联盟用户**   具有受信任客户或合作伙伴组织的帐户的用户，如 Lync Server 2010、Lync Server 2013 或 Office Communications Server 2007 R2。联盟用户也可以是通过边缘服务器上的 XMPP 代理和前端服务器或池上的 XMPP 网关使用可扩展消息传递和状态协议 (XMPP) 的已定义合作伙伴组织的成员。定义的受信任关系（称为“联盟”）与 Active Directory 域服务 信任关系无关或者无需依赖它。
    
    > [!NOTE]  
	> AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅<a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。
    


  - **公共即时消息连接用户**   您的用户通过公共即时消息连接服务（Windows Live、Yahoo\! 和 AOL）建立的联系人。

  - **移动用户**   使用运行 Lync Mobile 客户端的智能电话或平板电脑登录到您的内部部署并且能够与其他类别的用户进行通信的组织成员用户。移动用户使用通过反向代理发布的 Mobility Service 访问内部部署。有关可供 Lync Mobile 使用的功能的详细信息，请参阅移动客户端比较表，网址为 [http://go.microsoft.com/fwlink/?linkid=234777\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=234777%26clcid=0x804)。

  - **匿名用户**   匿名用户在组织的 Active Directory 域服务 中或受支持的联盟域中没有用户帐户，但可以受邀远程参加内部会议。

边缘部署可针对以下类型的通信提供外部访问：

  - **IM 和状态**   授权的外部用户可以参加 IM 对话和会议，并可获取相互之间的状态信息。公共 IM 服务提供商的用户可与组织中的单个 Lync Server 用户进行 IM 对话，且可以访问状态信息，但他们无法使用 Lync Server 参加 IM 多方会议。此 IM 对话在严格意义上属于对等通信。公共 IM 服务提供商的用户无法进行文件传输， Windows Messenger 2011 用户可进行音频/视频对等通信，但公共 IM 服务提供商的其他用户不可以。
    
    同时支持 SIP 和 XMPP 协议。若要提供针对 XMPP 的服务，请参阅 [规划 SIP、XMPP 联盟和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。

  - **Web 会议**   授权的外部用户可以参加 Lync Server 部署承载的会议。远程用户、联盟用户和匿名用户可以参加 Web 会议，而公共 IM 用户不能参加会议。根据您选择的选项，启用 Web 会议的用户可以参加桌面共享和应用程序共享，并且可以充当会议组织者或演示者。

  - **A/V 会议**   授权的外部用户可参加您的 Lync Server 部署承载的音频和视频会议。 Windows Messenger 2011 用户可进行音频/视频对等通信，但公共 IM 服务提供商的其他用户不可以。

为了控制通信，可以配置一个或多个策略以定义组织内外的用户如何相互通信。还可以为各个内部用户或特定类型的外部用户配置设置并应用策略，以控制与外部用户的通信。

Lync Server 2013 角色，用于提供外部访问：

**边缘服务器**    边缘服务器是运行允许外部访问 IM 和状态、会议、音频/视频和其他媒体（例如，文件传输）服务的服务的服务器或服务器池。可以选择将 边缘服务器配置为与其他 Lync Server 或 Office Communications Server 2007 R2 部署和其他 XMPP 部署进行联盟。可选的公共 IM 连接功能可通过 边缘服务器进行启用和配置。

**控制器**    控制器是运行 Lync Server 2013  控制器角色的可选服务器或服务器池，它将预先对用户请求进行身份验证并将请求路由至用户的主 前端服务器或 前端池，但不会承载任何用户帐户。

**反向代理**   反向代理是对在内部网络上发布可用资源并从已发布资源中检索客户端信息的专用服务器的泛称。 Lync Server 2013 使用反向代理发布大量功能，例如会议、会议加入位置、通讯簿、通讯组列表扩展、下载会议内容、设备更新、Mobility Service 等等。可使用可满足发布必需资源位置的要求的任何反向代理。为了演示必需的发布规则，使用了 Microsoft Forefront Threat Management Gateway (TMG) 2010 作为一个示例，但 Forefront TMG 2010 不是必需的。

> [!IMPORTANT]
> Lync Server 2013 同时支持 IPv4 和 IPv6。Windows Server 2008 R2、Windows Server 2012 和 Windows Server 2012 R2 使用可同时使用 IPv4 和 IPv6 的双协议栈。由于从 IPv4 到 IPv6 的部署的过渡特征，因此这一点非常重要。部署的某些方面可支持 IPv4，其他方面可使用 IPv6。这对于需要考虑 Internet 部署和内部部署的情况尤其重要。外部客户端必须通过反向代理进行通信以使用移动、会议、通讯簿下载等服务。当前，无论将 Forefront Threat Management Gateway 2010 和 Internet Security and Acceleration Server 2006 部署到的操作系统版本如何，二者都不支持 IPv6 寻址。由于 IPv6 和 IPv4 与外部客户端相关，因此您必须根据您对二者的使用来进行相应的规划。

