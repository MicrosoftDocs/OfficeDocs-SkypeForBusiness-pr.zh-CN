---
title: Lync Server 2013：呼叫允许控制的最佳做法
TOCTitle: 呼叫允许控制的最佳做法
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398770(v=OCS.15)
ms:contentKeyID: 49313665
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中呼叫允许控制的最佳做法

 

_**上一次修改主题：** 2012-09-22_

为了提高性能以及方便部署，在部署呼叫允许控制时，请应用以下最佳做法：

  - 确保已为当前媒体流量和预期媒体流量提供了充足的 WAN。
    
    > [!NOTE]  
    > 建议在设置带宽限制时预留一定的缓冲区。有些方案（如争用情况）会影响使用的带宽总量，可能导致出现超出带宽限制的情况。例如，当媒体流量接近带宽限制时，如果两个呼叫都尝试启动，则其中一个呼叫可能会因为另一个设法首先启动而被拒绝。
    


  - 监控网络使用情况以及呼叫详细信息记录，这样便可以根据网络使用情况的变化来选择最佳 CAC 设置并更新 CAC 设置。

  - 使用 CAC 带宽策略补充 QoS 设置。

  - 如果要将已阻止的呼叫重新路由到 PSTN，请验证 PSTN 功能和容量。有关详细信息，请参阅 [在 Lync Server 2013 中规划出站语音路由](lync-server-2013-planning-outbound-voice-routing.md)。
    
    > [!NOTE]  
    > 容量指为支持潜在 PSTN 重新路由而需要打开的端口数量。
    

