---
title: Lync Server 2013：基于位置的路由的技术注意事项
TOCTitle: 基于位置的路由的技术注意事项
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994027(v=OCS.15)
ms:contentKeyID: 52060993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中基于位置的路由的技术注意事项

 

_**上一次修改主题：** 2013-03-09_

当规划基于位置的路由时，您应该考虑对以下情形的影响。

## 灾难恢复

在从主池故障转移到备份池期间以及还原主池的正常操作时，灾难恢复过程中应始终强制实施基于位置的路由。

## Survivable Branch Appliance

配置基于位置的路由会影响您在其中部署与 Survivable Branch Appliance 相关联的网关的位置的规划。与您的 SBA 相关联的网关必须位于与您的 Survivable Branch Appliance 相同的网络站点中；否则，如果配置了基于位置的路由，驻留在 Survivable Branch Appliance 上的用户不允许发出出站呼叫。当 Survivable Branch Appliance 和中央站点之间的 WAN 连接关闭时，基于位置的路由仍将强制实施。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)

