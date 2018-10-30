---
title: Lync Server 2013：基于位置的路由不支持的功能
TOCTitle: 基于位置的路由不支持的功能
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994071(v=OCS.15)
ms:contentKeyID: 52061115
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中基于位置的路由不支持的功能

 

_**上一次修改主题：** 2014-03-12_

基于位置的路由不适用于以下类型的交互。当 Lync 终结点与 PSTN 终结点使用这些功能进行交互时，不强制应用基于位置的路由。

  - PSTN 电话拨入式会议

  - 通过响应组的传入和传出 PSTN 呼叫

  - 通过呼叫寄存对 PSTN 呼叫进行呼叫寄存或检索

  - 到公告服务的传入 PSTN 呼叫

  - 通过组内呼叫应答检索的传入 PSTN 呼叫

要对以下列表中的交互类型强制应用基于位置的路由规则，必须为会议启用基于位置的路由：

  - PSTN 电话拨出式会议

  - 从点对点音频对话升级到涉及 PSTN 终结点的音频会议

  - 涉及 PSTN 终结点的咨询转接

要为会议启用基于位置的路由，请参阅[基于位置的路由会议](lync-server-2013-location-based-routing-for-conferencing.md)。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)

