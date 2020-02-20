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
ms.openlocfilehash: 31381edc58240d990096b47498b5c98845af5b2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部用户访问所需的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-29_

大多数边缘组件都部署在外围网络中。 以下组件组成了外围网络的边缘拓扑。 除非另有说明，组件是[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)的一部分，并且位于外围网络中。 边缘组件包括下列各项：

  - 边缘服务器

  - 反向代理

  - 道

  - 控制器（可选，并在内部网络中逻辑上）

  - 扩展的边缘拓扑的负载平衡（DNS 负载平衡或硬件负载平衡器）
    
    <div>
    

    > [!IMPORTANT]  
    > 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。

    
    </div>

<div>

## <a name="edge-servers"></a>边缘服务器

边缘服务器发送和接收外部用户由内部部署提供的服务的网络流量。 边缘服务器运行下列服务：

  - **访问边缘服务**   ： access edge 服务为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。

  - **Web 会议边缘服务**   web 会议边缘服务使外部用户能够加入托管在内部 Lync Server 2013 部署上的会议。

  - **A/v 边缘服务**   a/v 边缘服务使音频、视频、应用程序共享和文件传输可供外部用户使用。 您的用户可以向包含外部参与者的会议添加音频和视频，并且可以在点对点会话中使用音频和/或视频直接与外部用户进行通信。 A/V 边缘服务还提供对桌面共享和文件传输的支持。

  - **XMPP 代理服务**   XMPP 代理服务接受并发送可扩展消息和状态协议（XMPP）消息，并发送到已配置的 XMPP 联盟伙伴。

授权的外部用户可以访问边缘服务器，以便连接到内部 Lync Server 2013 部署，但边缘服务器不提供对内部网络的任何其他访问的方法。

<div>


> [!NOTE]  
> 部署边缘服务器以提供启用的 Lync 客户端和其他 Microsoft Edge 服务器（如在联合方案中）的连接。 它们的设计不允许来自其他端点客户端或服务器类型的连接。 可以部署 XMPP 网关服务器以允许与配置的 XMPP 合作伙伴之间的连接。 边缘服务器和 XMPP 网关仅支持来自这些客户端和联盟类型的端点连接。



</div>

</div>

<div>

## <a name="reverse-proxy"></a>反向代理

反向代理是实现以下功能所必需的：

  - 允许用户使用简单 URL 连接到会议或电话拨入式会议

  - 允许外部用户下载会议内容

  - 允许外部用户扩展通讯组

  - 允许用户获取基于用户的证书以便进行基于客户端证书的身份验证

  - 允许远程用户从通讯簿服务器下载文件，或者向通讯簿 Web 查询服务提交查询

  - 允许远程用户获取客户端和设备软件的更新

  - 允许移动设备自动发现提供 Mobility Service 的前端服务器

  - 允许通过 Office 365 或 Apple 推送通知服务向移动设备发送推送通知

有关与反向代理和反向代理必须满足的要求相关的其他信息，请参阅[Lync Server 2013 中反向代理的配置要求](lync-server-2013-configuration-requirements-for-reverse-proxy.md)中的详细信息。

<div>


> [!NOTE]  
> 外部用户不需要与您的组织的虚拟专用网络（VPN）连接即可参与使用 Lync Server 2013 的通信。 如果您在组织中实施了 VPN 技术，并且您的用户使用的是 Lync 的 VPN，媒体流量（如视频会议）可能会受到负面影响。 应考虑为媒体通信提供直接连接到 AV 边缘服务的方法，并绕过 VPN。 有关详细信息，请参阅 NextHop 博客文章 "启用 Lync Media 绕过 VPN 隧道" <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>。



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

可以在仅有外部防火墙的情况下部署边缘拓扑，也可以在外部防火墙和内部防火墙兼有的情况下部署边缘拓扑。 方案体系结构包括两个防火墙。 建议的方法是使用两道防火墙，因为这样可确保从一个网络边缘严格路由到另一网络边缘，并使内部部署享有两层防火墙的保护。

</div>

<div>

## <a name="director"></a>控制器

Director 是 Lync Server 2013 中的一个单独的可选服务器角色，它不会家庭用户帐户，也不提供状态或会议服务。 它充当内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。 Director 对入站请求，并将其重定向到用户的主池或服务器。 通过在 Director 的 preauthenticating，您可以从用户帐户中删除部署无法识别的请求。

控制器可帮助将 Enterprise Edition 前端池中的 Standard Edition 服务器和前端服务器与恶意流量（如拒绝服务（DoS）攻击）隔离。 如果网络在此类攻击中遇到无效的外部通信，则流量将在 Director 处结束。 有关使用控制器的详细信息，请参阅[Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)。

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

