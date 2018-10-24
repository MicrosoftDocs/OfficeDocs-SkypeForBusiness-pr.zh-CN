---
title: Lync Server 2013：新的外部用户访问功能
TOCTitle: 新的外部用户访问功能
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398794(v=OCS.15)
ms:contentKeyID: 49313695
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的外部用户访问功能

 

_**上一次修改主题：** 2012-10-17_

Lync Server 2013 引入了扩展用户的功能和通信方式的新功能。而且， Lync Server 2013 引入了对现有服务的更改，以便更好地集成和扩展可供组织使用的服务。下面是可能会影响 Lync Server 2013  边缘服务器服务的规划和部署的更改的摘要。

  - **对 IPv6 寻址的支持 -** Lync Server 2013 支持所有 边缘服务器服务的 IPv6 寻址。如果您已通过 Windows Server 中的配置为接口提供了 IPv6 地址，则可在通过 拓扑生成器的 IP 地址配置的 边缘服务器配置中使用 IPv6 地址。
    
    > [!IMPORTANT]
    > 在 Lync Server 2013 中使用 IPv6 地址取决于组织部署的路由器和防火墙中是否支持 IPv6，以及 Internet 服务提供商提供的支持。


  - **可扩展消息传递和状态协议 (XMPP)** Lync Server 2013 引入了完全集成的 XMPP 代理（部署在 边缘服务器上）和部署在 前端服务器上的 XMPP 网关。可将 XMPP 联盟作为可选组件来部署。添加并配置 XMPP 代理和 XMPP 网关将允许 Microsoft Lync 2013 用户针对即时消息 (IM) 和状态添加基于 XMPP 的合作伙伴中的联系人。
    
    > [!NOTE]  
    > 目前， Lync Server 2013 中的 XMPP 服务仅在 Lync 客户端和基于 XMPP 的联系人之间提供了即时消息和状态。
    


  - **移动客户端的 Mobility Service** Lync Server 2010 的客户更新中引入的， Lync Server 2013 中的 Mobility Service 允许使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备的移动电话和平板电脑设备上的 Microsoft Lync Mobile 客户端执行发送和接收即时消息、查看联系人和查看状态等活动。此外，移动设备支持某些企业语音功能，如单击以加入会议、通过工号拨号、一号通、语音邮件和未接电话通知。
    
    > [!NOTE]  
    > Mobility Service 使用 前端服务器上部署的反向代理和已发布服务。 边缘服务器无需任何更改。
    


  - **控制器是可选角色** 未更改 Lync Server 2013 拓扑中的 控制器服务器的角色。该角色仍然承载 Web 服务、预先验证传入用户请求的身份并将外部用户定向至其主池。将 控制器从建议的角色更改为可选角色不会减小 控制器的值，但着重减少服务器计数和其他硬件要求（例如， 控制器的硬件负载平衡器要求），但不危害功能。因为 前端服务器可执行与 控制器相同的工作，而不影响提供的服务，因此您也可部署 控制器（如果您选择）。在确信 前端服务器将代替 控制器提供相同的服务的情况下，您可安全排除后者。

## 另请参阅

#### 概念

[在 Lync Server 2013 中规划和配置 IPv6](lync-server-2013-planning-for-and-configuring-ipv6.md)  

#### 其他资源

[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)

