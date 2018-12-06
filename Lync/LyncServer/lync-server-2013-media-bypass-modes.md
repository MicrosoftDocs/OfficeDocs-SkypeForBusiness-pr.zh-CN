---
title: Lync Server 2013：媒体绕过模式
TOCTitle: 媒体绕过模式
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425862(v=OCS.15)
ms:contentKeyID: 49312505
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的媒体绕过模式

 

_**上一次修改主题：** 2012-10-05_

必须配置全局和每个单个 PSTN 中继的媒体旁路。在全局范围内启用媒体旁路时，有两种选择：“始终绕过”和“使用站点和区域信息”。

顾名思义，“始终绕过”表示将试图绕过所有 PSTN 呼叫。“始终绕过”用于既不需要启用呼叫允许控制也不需要指定与何时尝试媒体旁路相关的详细配置信息的部署。此外，在客户端和 PSTN 网关之间有完全连接时需使用“始终绕过”。在此配置中，所有子网将映射至唯一的绕过 ID，该 ID 由系统计算得出。

通过“使用站点和区域信息”，与站点和区域配置关联的绕过 ID 将用于做出绕过决定。此配置可使您灵活地配置大部分常用拓扑的绕过，因为除了支持与呼叫允许控制 (CAC) 的交互之外，它还可以使您对何时发生绕过进行精确控制。系统会尝试通过自动分配绕过 ID 简化任务，如下所示。

  - 系统会自动为每个区域分配单个唯一的绕过 ID。

  - 任何通过 WAN 链路连接到区域的没有带宽限制的站点将继承与该区域相同的绕过 ID。

  - 将为通过 WAN 链路与区域关联的具有带宽限制的站点分配与该区域不同的绕过 ID。

  - 与每个站点关联的子网将继承该站点的绕过 ID。

## 另请参阅

#### 概念

[Lync Server 2013 中的媒体旁路概述](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 中的媒体绕过和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒体旁路的技术要求](lync-server-2013-technical-requirements-for-media-bypass.md)

