---
title: Lync Server 2013：基于位置的路由概述
TOCTitle: 基于位置的路由概述
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994032(v=OCS.15)
ms:contentKeyID: 52061015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的基于位置的路由概述

 

_**上一次修改主题：** 2013-02-21_

基于位置的路由引入了一组新规则，它们可修改国内和国际 PSTN 呼叫的路由以防止收费绕路情形。使用基于位置的路由可灵活地将这些规则限定为仅特定区域、特定网关或特定用户集。

以下方案说明基于位置的路由可以强制实施的主要限制类型：

  - 发出呼叫 – 基于位置的路由可以强制传出呼叫从位于与呼叫者相同区域的 PSTN 网关发出，从而防止 PSTN 收费绕路情形，这样可防止呼叫从位于与呼叫者不同区域的 PSTN 网关发出。

  - 呼叫进入 – 如果路由传入呼叫的 PSTN 网关不位于与被叫 Lync 用户相同的区域中，则基于位置的路由可以防止传入 PSTN 呼叫拨打 Lync 终结点。

  - 未知区域 – 基于位置的路由限制发往和来自位于不确定区域的用户（例如，从 Internet 连接或者位于未知区域的用户）的传入和传入 PSTN 呼叫。

  - 国际区域 – 如果无法找到用户所在位置的本地网关，则基于位置的路由会通过国际 PSTN 网关强制实施传出呼叫的路由。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)

