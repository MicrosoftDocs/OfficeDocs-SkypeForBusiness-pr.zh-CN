---
title: Lync Server 2013：呼叫允许控制和中介服务器
TOCTitle: 呼叫允许控制和中介服务器
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398585(v=OCS.15)
ms:contentKeyID: 49313292
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫允许控制和中介服务器

 

_**上一次修改主题：** 2012-09-21_

呼叫允许控制 (CAC) 最初是在 Lync Server 2010 中引入的，此控制可根据可用带宽管理实时会话建立，以帮助改善拥堵网络中的用户体验质量 (QoE)。为支持此功能，中介服务器在 企业语音基础结构与网关或 SIP 中继提供商之间提供信号和媒体转换，并负责管理其在 Lync Server 端和网关端上两次交互的带宽。在呼叫允许控制中，呼叫的端接实体处理带宽预留。 中介服务器在网关端进行交互的对等网关（PSTN 网关、IP-PBX 和 SBC）不支持 Lync Server 2013 呼叫允许控制。因此， 中介服务器必须代表其对等网关处理带宽交互。如果可能的话， 中介服务器将提前预留带宽。如果不可能（例如，如果网关端的最终媒体终结点位置对于发往对等网关的传出呼叫是未知的），则会在发出呼叫时预留带宽。此行为可能导致带宽订阅过度，但这是防止错误响铃的唯一方法。

媒体旁路和带宽预留相互排斥。如果对呼叫使用媒体旁路功能，则不会对该呼叫执行呼叫允许控制。此处假定前提是此次呼叫不涉及具有限定带宽的链接。如果呼叫允许控制用于涉及 中介服务器的特定呼叫，则该呼叫无法采用媒体旁路。

有关媒体旁路或呼叫允许控制的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)或 [在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)。

