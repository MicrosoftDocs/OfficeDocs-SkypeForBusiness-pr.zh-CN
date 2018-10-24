---
title: Lync Server 2013：媒体绕过和中介服务器
TOCTitle: 媒体绕过和中介服务器
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398719(v=OCS.15)
ms:contentKeyID: 49313564
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的媒体绕过和中介服务器

 

_**上一次修改主题：** 2012-09-21_

媒体旁路是一种 Lync Server 功能，使管理员可以将呼叫路由配置为直接在用户终结点和公用电话交换网 (PSTN) 网关之间流动，而无需遍历 中介服务器。媒体旁路功能通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高呼叫质量。当没有 中介服务器的远程站点通过一个或多个具有限定带宽的 WAN 链路连接到中央站点时，媒体旁路功能允许来自远程站点上的客户端的媒体直接流到其本地网关，而无需首先通过 WAN 链路流到中央站点上的 中介服务器再流回，从而降低了带宽要求。由于无需媒体处理操作，因此也补充了 中介服务器控制多个网关的能力。

媒体旁路功能和呼叫允许控制 (CAC) 相互排斥。如果某次呼叫使用媒体旁路功能，则不会为此次呼叫执行 CAC。假定前提是此次呼叫不涉及具有限定带宽的链接。

## 另请参阅

#### 概念

[Lync Server 2013 中的呼叫允许控制和中介服务器](lync-server-2013-call-admission-control-and-mediation-server.md)  

#### 其他资源

[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

