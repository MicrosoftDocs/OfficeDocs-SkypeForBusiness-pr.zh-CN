---
title: Lync Server 2013：外部用户访问概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3d85b7e3eae8839e3e65e02dde5955c8145c64
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

在本文档中，我们使用术语 "*外部用户*" 定义与您的 lync Server 2013 和 lync 2013 用户在防火墙外部进行通信的大型用户类别。 您可以授权的外部用户将 Lync Server 2013 与内部用户（即从防火墙内登录到 Lync Server 的用户）进行通信）可能包括以下内容：

  - ****   从防火墙外登录 Lync Server 的组织的远程用户用户。

  - **联合用户**   拥有具有受信任的客户或合作伙伴组织的帐户的用户，例如 lync server 2010、lync server 2013 或 Office 通信服务器 2007 R2。 联合用户也可以是使用可扩展消息传递和状态协议（XMPP）的已定义合作伙伴组织的成员，方法是在前端服务器上的 XMPP 代理和前端服务器或池上的 XMPP 网关上使用 "代理"。 已定义的信任关系称为联合，与 Active Directory 域服务信任关系无关或依赖于 Active Directory 域服务信任关系。
    
    <div>
    

    > [!NOTE]  
    > AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。

    
    </div>

  - **公共即时消息连接用户**   通过公共即时消息连接服务（Windows Live、Yahoo）建立的用户联系人\! 和 AOL）。

  - **移动用户**   是指组织中使用智能手机或平板电脑的成员登录到内部部署，并且能够与其他用户类别进行通信的用户。 移动用户使用通过反向代理发布的移动服务来访问内部部署。 有关 Lync Mobile 可用的特性和功能的详细信息，请参阅中[https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)的移动客户端比较表。

  - **匿名用户**   在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户，但在本地会议中收到远程参与邀请的用户。

您的边缘部署为以下类型的通信提供了外部访问：

  - **Im 和状态**   授权外部用户可以参与 im 对话和会议，并可以获取有关其他人状态的信息。 公共 IM 服务提供商的用户可以参与与组织中各个 Lync Server 用户的 IM 对话并访问状态信息，但不能使用 Lync Server 参与 IM 多方会议。 它是严格的对等通信。 公共 IM 服务提供商的用户不支持文件传输，对等通信中的音频/视频支持 Windows Messenger 2011 用户，但不支持公共 IM 服务提供商的其他用户。
    
    支持 SIP 和 XMPP 协议。 若要为 XMPP 提供服务，请参阅[Lync Server 2013 中的规划 SIP、XMPP 联盟和公用即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。

  - **Web 会议**   授权的外部用户可以参与在 Lync Server 部署上托管的会议。 可以为远程用户、联合用户和匿名用户启用 web 会议，但公共 IM 用户不能参与会议。 根据您选择的选项，启用了 web 会议的用户可以参与桌面和应用程序共享，并可充当会议组织者或演示者。

  - **A/V 会议**   授权的外部用户可以参与 Lync Server 部署托管的音频和视频会议。 对等通信中的音频/视频支持 Windows Messenger 2011 用户，但不适用于公共 IM 服务提供商的其他用户。

为了控制通信，可以配置一个或多个策略，用于定义组织内部和外部的用户如何相互通信。 您还可以为单个内部用户或特定类型的外部用户配置设置和应用策略，以控制与外部用户的通信。

Lync Server 2013 用于提供外部访问权限的角色：

**边缘服务器**   ：边缘服务器是运行服务的服务器或服务器池，这些服务允许外部访问 IM 和状态、会议、音频/视频和其他媒体（例如，文件传输）服务。 （可选）可以将边缘服务器配置为与其他 Lync Server 或 Office 通信服务器 2007 R2 部署以及其他 XMPP 部署进行联盟。 可选的公共 IM 连接功能已通过边缘服务器启用和配置。

**Director**   director 控制器是运行 Lync server 2013 控制器角色的可选服务器或服务器池，它预身份验证用户请求并将请求路由到用户的主前端服务器或前端池，但不在家任何用户帐户。

**反向代理**   反向代理是专用服务器的常规术语，用于发布内部网络上可用的资源，并从已发布的资源检索客户端的信息。 Lync Server 2013 使用反向代理来发布许多功能，如会议会议、会议加入位置、通讯簿、通讯组列表展开、下载会议内容、设备更新、移动服务等。 可以使用任何能够满足发布必需资源位置的要求的反向代理。 Microsoft Forefront 威胁管理网关（TMG）2010用作演示必要的发布规则的示例，但不需要 Forefront TMG 2010。

<div>


> [!IMPORTANT]  
> Lync Server 2013 同时支持 IPv4 和 IPv6。 Windows Server&nbsp;2008&nbsp;r2、Windows Server 2012 和 Windows server 2012 R2 使用可以同时使用 IPv4 和 IPv6 的双重堆栈。 这一点很重要，因为部署从 IPv4 迁移到 IPv6 的过渡性质。 在某些方面可以支持 IPv4，在其他区域的部署中，可以使用 IPv6。 这一点在 Internet 和内部部署相关时尤其重要。 外部客户端必须通过反向代理进行通信，才能使用移动、会议、通讯簿下载等服务。 目前，Forefront 威胁管理网关2010和 Internet 安全性和加速服务器2006不支持 IPv6 寻址，而不管它们是在什么操作系统版本上部署的。 您必须根据 IPv6 和 IPv4 的使用情况进行相应的规划，因为它们与外部客户端相关。



</div>

</div>

<span> </span>

</div>

</div>

</div>

