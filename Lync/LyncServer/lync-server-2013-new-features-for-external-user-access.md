---
title: Lync Server 2013：用于外部用户访问的新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中用于外部用户访问的新功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-17_

Lync Server 2013 引入了新功能，用于扩展用户的功能和通信方法。 另外，Lync Server 2013 引入了对现有服务所做的更改，以便更好地集成和扩展可供您的组织使用的服务。 以下是可能影响您规划和部署 Lync Server 2013 Edge Server 服务的更改的摘要。

  - **对 ipv6 寻址**   Lync Server 2013 的支持支持所有边缘服务器服务的 ipv6 寻址。 如果已通过 Windows Server 中的配置为接口提供了 IPv6 地址，则可以通过拓扑生成器中的 IP 地址配置来使用边缘服务器配置中的 IPv6 地址。
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中使用 IPv6 地址取决于您的组织部署的路由器和防火墙中的 IPv6 支持，以及通过 Internet 服务提供商的支持。

    
    </div>

  - **可扩展消息传递和状态协议（XMPP）**   Lync Server 2013 引入了一个完全集成的 XMPP 代理（部署在边缘服务器上）和部署在前端服务器上的 XMPP 网关。 可将 XMPP 联盟作为可选组件来部署。 添加和配置 XMPP 代理和 XMPP 网关将允许您的 Microsoft Lync 2013 用户添加来自基于 XMPP 的合作伙伴的联系人，以实现即时消息（IM）和状态。
    
    <div>
    

    > [!NOTE]  
    > 目前，Lync Server 2013 中的 XMPP 服务仅在 Lync 客户端和基于 XMPP 的联系人之间提供即时消息和状态。

    
    </div>

  - **适用**   于 lync server 2010 的客户更新中引入的移动客户端移动服务在 lync server 的客户更新中，lync server 2013 中的移动服务允许使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备的移动电话和平板电脑设备上的 Microsoft Lync 移动客户端执行类似发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备支持某些企业语音功能，例如，通过单击加入会议、通过工作、单号码到达、语音邮件和未接来电通知进行呼叫。
    
    <div>
    

    > [!NOTE]  
    > Mobility Service 使用反向代理和在前端服务器上部署的已发布服务。 无需对边缘服务器进行任何更改。

    
    </div>

  - **Director 是可选角色**   Lync server 2013 拓扑中的控制器服务器的角色未发生更改。 它仍承载 web 服务，对传入的用户请求进行预身份验证，并将外部用户定向到其主池。 将 Director 从推荐角色更改为可选角色不会降低 Director 的价值，但强调的是减少服务器数量和其他硬件要求（例如，控制器的硬件负载平衡器）要求，而不危害特性和功能。 由于前端服务器可以执行与提供的服务不受影响的控制器相同的作业，因此，如果选择，则可以选择部署控制器。 你可以放心地排除 Director，前端服务器将在其位置提供相同的服务。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划和配置 IPv6](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中规划可扩展消息和状态协议（XMPP）联盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

