---
title: Lync Server 2013：媒体旁路的技术要求
TOCTitle: 媒体旁路的技术要求
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398435(v=OCS.15)
ms:contentKeyID: 49313026
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中媒体旁路的技术要求

 

_**上一次修改主题：** 2012-09-21_

对于每个对 PSTN 的呼叫， 中介服务器会确定是否能直接将来自源 Lync 终结点的媒体发送给 中介服务器对等方，而无需遍历 中介服务器。对等方可以是与其中路由呼叫的中介服务器之间的中继关联的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。

当满足以下要求时，可采用媒体旁路功能：

  - 中介服务器对等方必须支持媒体旁路的必需功能，最重要的是处理多震响应（称为“早期对话”）的功能。与网关、PBX 制造商或 ITSP 联系，以获取网关、PBX 或 SBC 可接受的最大早期对话数的值。

  - 中介服务器对等方必须接受直接来自 Lync 终结点的媒体流量。许多 ITSP 仅允许其 SBC 接收来自 中介服务器的流量。与您的 ITSP 联系，以确定其 SBC 是否接受直接来自 Lync 终结点的媒体流量。

  - Lync 客户端与 中介服务器对等方必须连接正常，这意味着它们位于同一网络区域，或位于通过不具有带宽限制的 WAN 链路连接到该区域的网络站点上。

## 另请参阅

#### 概念

[Lync Server 2013 中的媒体绕过模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒体绕过和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)

