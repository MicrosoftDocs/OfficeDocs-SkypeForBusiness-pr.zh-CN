---
title: Lync Server 2013：呼叫允许控制的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中呼叫允许控制的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-22_

为了提高性能以及方便部署，在部署呼叫允许控制时，请应用以下最佳做法：

  - 确保已为当前媒体流量和预期媒体流量提供了充足的 WAN。
    
    <div>
    

    > [!NOTE]  
    > 建议在设置带宽限制时预留一定的缓冲区。有些方案（如争用情况）会影响使用的带宽总量，可能导致出现超出带宽限制的情况。例如，当媒体流量接近带宽限制时，如果两个呼叫都尝试启动，则其中一个呼叫可能会因为另一个设法首先启动而被拒绝。

    
    </div>

  - 监控网络使用情况以及呼叫详细信息记录，这样便可以根据网络使用情况的变化来选择最佳 CAC 设置并更新 CAC 设置。

  - 使用 CAC 带宽策略补充 QoS 设置。

  - 如果要将已阻止的呼叫重新路由到 PSTN，请验证 PSTN 功能和容量。 有关详细信息，请参阅[在 Lync Server 2013 中规划出站语音路由](lync-server-2013-planning-outbound-voice-routing.md)。
    
    <div>
    

    > [!NOTE]  
    > 容量指为支持潜在 PSTN 重新路由而需要打开的端口数量。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

