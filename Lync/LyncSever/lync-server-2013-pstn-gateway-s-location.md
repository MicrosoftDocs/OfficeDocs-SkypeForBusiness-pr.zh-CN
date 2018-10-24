---
title: Lync Server 2013：PSTN 网关的位置
TOCTitle: PSTN 网关的位置
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994031(v=OCS.15)
ms:contentKeyID: 52061014
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 PSTN 网关的位置

 

_**上一次修改主题：** 2013-03-09_

通过 PSTN 网关和 PBX 的呼叫可能需要基于位置的路由限制，具体取决于此类系统的位置。可以为每个 Trunk 按粒度级别启用基于位置的路由。

在 Trunk 上启用时，基于位置的路由将引入以下一组规则：

  - 当为每个 Trunk 启用基于位置的路由时，该 Trunk 上定义的规则仅适用于通过该 Trunk 路由的呼叫。

  - 为防止 PSTN 收费绕路情形（呼叫来源于一个网络站点，该网络站点不同于 PSTN 网关所在的网络站点），基于位置的路由引入了网络站点与给定 Trunk 的关联。这定义允许呼叫路由到给定 Trunk 的网络站点。

可通过两种方式为 Trunk 启用基于位置的路由：

  - 为 Trunk 定义将呼叫发出到 PSTN 的 PSTN 网关。此类型的 Trunk 路由的传入呼叫只能路由到位于与 Trunk 相同的站点中的终结点。

  - 为 Trunk 定义不会将呼叫发出到 PSTN 而为在静态位置具有传统电话（如 PBX 电话）的用户提供服务的中介服务器对等端。对于此特殊配置，此类型的 Trunk 路由的传入呼叫将视为来自与 Trunk 相同的网络站点。来自 PBX 用户的呼叫与位于 Trunk 所在相同网络站点的 Lync 用户具有相同的基于位置的路由强制实施。如果位于独立网络站点的两个 PBX 系统通过 Lync Server 连接，则基于位置的路由将允许从一个网站站点中的 PBX 终结点路由到另一个网络站点中的终结点。此情形不会被基于位置的路由阻止。除了此情形之外，按照与相同位置的 Lync 用户相同的方式，连接到采用此配置的中介服务器对等端的终结点能够从其他中介服务器对等端发出或接收呼叫，不管与中介服务器对等端相关联的网络站点如何，呼叫都不会路由到 PSTN（例如连接到其他 PBX 的终结点）。所有涉及 PSTN 终结点的入站呼叫、出站呼叫和呼叫转接受基于位置的路由约束，只能使用定义为此类中介服务器对等端本地网关的 PSTN 网关。

## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由指南](lync-server-2013-guidance-for-location-based-routing.md)

