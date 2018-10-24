---
title: Lync Server 2013：新的中继功能
TOCTitle: 新的中继功能
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49888530
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的中继功能

 

_**上一次修改主题：** 2012-09-21_

在 Microsoft Lync Server 2013 中，可以在一个 中介服务器和一个网关之间定义多个中继。 Microsoft Lync Server 2010 仅允许在一个 中介服务器和一个 PSTN 网关之间定义一个中继。此功能使您能够灵活地定义额外的中继。中继是 中介服务器 FQDN 和侦听端口以及 PSTN 网关 FQDN 和侦听端口之间的逻辑关联。利用此新功能，可以轻松为以下各项定义中继：恢复能力（其中，可使用多个中介服务器将呼叫路由到相同的 PSTN 网关）、PBX 互操作性（其中，可在 IP-PBX 和 中介服务器之间使用具有不同的关联策略的多个中继）以及 SIP 中继配置（其中，不同站点上的 中介服务器具有针对同一运营商 FQDN 引用的运营商的 SIP 中继）。

## 另请参阅

#### 概念

[Lync Server 2013 中新的企业语音功能](lync-server-2013-new-enterprise-voice-features.md)

