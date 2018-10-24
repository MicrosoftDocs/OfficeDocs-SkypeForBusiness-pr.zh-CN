---
title: Lync Server 2013：委派
TOCTitle: 委派
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994045(v=OCS.15)
ms:contentKeyID: 52061069
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的委派

 

_**上一次修改主题：** 2013-03-09_

Lync 中的委派功能通过以下方式受基于位置的路由影响：

  - 当启用了基于位置的路由的代理人代表经理发出呼叫时，代理人的语音策略将用于对呼叫进行授权，而代理人的站点语音路由策略将用于路由呼叫

  - 对于打给经理的传入 PSTN 经理，适用于呼叫转接或同时响铃的相同规则将按照呼叫转接和同时响铃主题所述进行应用。

  - 当代理人将 PSTN 终结点设置为同时响铃目标时，对于打给经理的传入呼叫，与传入 Tunk 相关联的站点的语音路由策略将用于将呼叫路由到代理人的 PSTN 终结点。

  - 对于委派，建议经理及其关联的代理人通常位于相同网络站点中。

## 另请参阅

#### 其他资源

[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)

