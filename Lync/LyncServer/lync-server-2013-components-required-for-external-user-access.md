---
title: Lync Server 2013：外部用户访问所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部用户访问所需的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-05-29_

大多数边缘组件都部署在外围网络中。 以下组件构成了外围网络的边缘拓扑。 除非另有说明，组件属于[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)的一部分，并且位于外围网络中。 边缘组件包括下列各项：

  - Edge Servers

  - Reverse proxies

  - Firewalls

  - 控制器（可选，并且逻辑上位于内部网络中）

  - 扩展的边缘拓扑的负载平衡（DNS 负载平衡或硬件负载平衡器）
    
    <div>
    

    > [!IMPORTANT]  
    > 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。

    
    </div>

<div>

## <a name="edge-servers"></a>边缘服务器

边缘服务器针对由外部用户内部部署提供的服务发送和接收网络流量。 边缘服务器运行以下服务：

  - **Access edge 服务**   access edge 服务为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。

  - **网络会议边缘服务**   web 会议 edge 服务允许外部用户加入托管在内部 Lync Server 2013 部署上的会议。

  - **A/v 边缘**   服务 a/v 边缘服务使音频、视频、应用程序共享和文件传输可供外部用户使用。 用户可以向包括外部参与者的会议添加音频和视频，并且他们可以直接使用音频和/或视频与点对点会话中的外部用户进行通信。 A/V 边缘服务还提供对桌面共享和文件传输的支持。

  - **XMPP 代理服务**   XMPP 代理服务接受并向已配置 XMPP 联盟合作伙伴发送可扩展消息和状态协议（XMPP）消息。

授权外部用户可以访问 Edge 服务器，以便连接到您的内部 Lync Server 2013 部署，但 Edge 服务器不提供对内部网络的任何其他访问的方法。

<div>


> [!NOTE]  
> 部署边缘服务器以提供适用于已启用的 Lync 客户端和其他 Microsoft Edge 服务器（如在联盟方案中）的连接。 它们的设计目的不是允许来自其他终结点客户端或服务器类型的连接。 可部署 XMPP 网关服务器以允许与已配置的 XMPP 合作伙伴的连接。 Edge 服务器和 XMPP 网关只能支持来自这些客户端和联合类型的终结点连接。



</div>

</div>

<div>

## <a name="reverse-proxy"></a>反向代理

以下情况需要反向代理：

  - 允许用户使用简单 Url 连接到会议或拨入式会议

  - 允许外部用户下载会议内容

  - 使外部用户能够展开通讯组

  - 允许用户为基于客户端证书的身份验证获取基于用户的证书

  - 允许远程用户从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务

  - 使远程用户能够获取客户端和设备软件的更新

  - 使移动设备能够自动发现前端服务器，提供移动服务

  - 从 Office 365 或 Apple 推送通知服务启用移动设备的推送通知

有关与反向代理和反向代理必须满足的要求相关的其他信息，请参阅[Lync Server 2013 中反向代理的配置要求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)中的详细信息。

<div>


> [!NOTE]  
> 外部用户不需要与你的组织的虚拟专用网络（VPN）连接，即可使用 Lync Server 2013 参与通信。 如果你已在组织中实现 VPN 技术，并且你的用户使用的是 Lync 的 VPN，则媒体流量（如视频会议）可能会受到不利影响。 你应该考虑为媒体流量提供一种方法来直接连接到 AV 边缘服务并绕过 VPN。 有关详细信息，请参阅 NextHop 博客文章 "启用 Lync 媒体绕过 VPN 隧道" <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>。



</div>

</div>

<div>

## <a name="firewall"></a>防火墙

你可以仅使用外部防火墙或外部防火墙和内部防火墙部署 edge 拓扑。 方案体系结构包括两个防火墙。 使用两个防火墙是推荐的方法，因为它确保严格地从一个网络边缘路由到另一个网络边缘，并通过两个级别的防火墙保护内部部署。

</div>

<div>

## <a name="director"></a>控制器

Director 是 Lync Server 2013 中的一个独立的可选服务器角色，它不会家庭用户帐户，也不能提供状态或会议服务。 它充当一个内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。 Director preauthenticates 入站请求并将其重定向到用户的主池或服务器。 通过在 Director 上 preauthenticating，你可以丢弃对部署未知的用户帐户请求。

控制器可帮助将企业版前端池中的标准版服务器和前端服务器与恶意流量（如拒绝服务（DoS）攻击）隔离。 如果网络被此类攻击中的无效外部通信所淹没，则流量将在 Director 处结束。 有关使用控制器的详细信息，请参阅[Lync Server 2013 中的 Director 的方案](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 的硬件负载平衡器要求](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

