---
title: 用于视频会议的互操作性注意事项
TOCTitle: 用于视频会议的互操作性注意事项
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204790(v=OCS.15)
ms:contentKeyID: 49312426
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于视频会议的互操作性注意事项

 

_**上一次修改主题：** 2012-10-02_

本节介绍迁移的共存阶段的用户体验，此时在旧客户端与 Lync Server 2013 池或 Lync Server 2013 客户端与旧池之间存在互操作。

## Lync Server 2013 池

在 Lync Server 2013 池中使用旧客户端时，用户将体验以下行为：

  - 对于双方呼叫，视频分辨率与在旧池中时相同。

  - 对于多方会议，视频分辨率和视频会议功能与在旧池中时相同。库视图和高分辨率不可用。

## 旧池

在旧池中使用 Lync Server 2013 客户端时，用户将体验以下行为：

  - 对于双方呼叫，Lync Server 2013 客户端可以使用以下新功能：
    
      - 如果两个参与者都使用 Lync Server 2013 客户端，则 H.264 可用。
    
      - Lync Server 2013 客户端使用 TotalReceiveVideoBitRateKb 的默认值，因为旧服务器不使用带内设置发送此信息。

  - 对于多方会议，视频分辨率和视频会议功能与旧池中的旧客户端的体验相同。

> [!NOTE]  
> 当旧服务器托管 Lync Server 2013 客户端时，可以配置视频会议带宽，以便池中的所有用户都仅接收低分辨率视频，而发送高分辨率视频。例如，在媒体配置中将 MaxVideoRateAllowed 设置为 CIF-250K，并在会议策略中将 VideoBitRateKb 设置为 2000 kbps。此情形下的实际结果是池中的用户无法使用高分辨率。<br />
因为 MaxVideoRateAllowed 不再用于 Lync Server 2013 客户端，所以它无法阻止 Lync Server 2013 客户端请求高分辨率视频。在池中的所有用户的会议策略中将 VideoBitRateKb 设置为与 MaxVideoRateAllowed 相同的值（即，将 CIF 设置为 250 kbps，或将 VGA 设置为 600 kbps，将 HD 设置为 1500 kbps）。


