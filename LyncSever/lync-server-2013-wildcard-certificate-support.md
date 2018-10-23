---
title: Lync Server 2013 通配符证书支持
TOCTitle: 通配符证书支持
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202161(v=OCS.15)
ms:contentKeyID: 49311968
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的通配符证书支持

 

_**上一次修改主题：** 2013-03-21_

Lync Server 2013 使用证书来提供通信加密和服务器身份信息验证。在某些情况下，如通过反向代理的 Web 发布，不需要使用与提供服务的服务器的完全限定域名 (FQDN) 匹配的强使用者替代名称 (SAN) 项。在这些情况下，可以使用具有通配符 SAN 项（通常称为“通配符证书”）的证书来减少从公共证书颁发机构请求证书的成本，并降低证书规划流程的复杂性。

> [!WARNING]
> 若要保留统一通信 (UC) 设备（例如，桌面电话）的功能，您应该小心测试已部署的证书，确保设备在实施通配符证书后可以正常运行。

不支持使用通配符项作为任何角色的主题名称（也称为公用名或 CN）。使用 SAN 中的通配符项时支持以下服务器角色：

   **反向代理。** 简单的 URL（会议和拨入）发布证书支持通配符 SAN 项。

   **反向代理。** 发布证书上 LyncDiscover 的 SAN 项支持通配符 SAN 项。

   **控制器。** 控制器 Web 组件中 LyncDiscover 和 LyncDiscoverInternal 的简单 URL（会议和拨入）和 SAN 项支持通配符 SAN 项。

   **前端服务器 (标准版) 和 前端池 (企业版)。** 前端 Web 组件中 LyncDiscover 和 LyncDiscoverInternal 的简单 URL（会议和拨入）和 SAN 项支持通配符 SAN 项。

   **Exchange 统一消息 (UM)。**  部署为独立的服务器时，服务器不使用 SAN 项。

   **Microsoft Exchange Server 客户端访问服务器。** 内部客户端和外部客户端支持 SAN 中的通配符项。

   相同服务器上的 **Exchange 统一消息 (UM) 和 Microsoft Exchange Server 客户端访问服务器。** 支持通配符 SAN 项。

该主题中未提到的服务器角色：

  - 内部服务器角色（包括但不限于 中介服务器、 存档和监控服务器、 Survivable Branch Appliance 或 Survivable Branch Server）

  - 外部 边缘服务器界面

  - 内部 边缘服务器
    
    > [!NOTE]
    > 对于内部 边缘服务器界面，可以将通配符项分配到 SAN，支持该操作。不会在内部 边缘服务器上查询 SAN，但通配符 SAN 项具有有限的值。
    

有关证书配置（包括在证书中使用通配符）的详细信息，请参阅以下主题：

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的证书摘要 - 单一控制器](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的证书摘要 - 反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [集成本地统一消息与 Lync Server 2013 的指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

有关为 Exchange 配置证书（包括使用通配符等）的详细信息，请参阅 Exchange 2013 产品文档。

