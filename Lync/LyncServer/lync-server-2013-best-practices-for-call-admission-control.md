---
title: Lync Server 2013：呼叫允许控制的最佳做法
description: Lync Server 2013：呼叫允许控制的最佳实践。
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
ms.openlocfilehash: 17c32af904dc7fb48a1a5d1903bd6ed1f81f4cb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552128"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的呼叫允许控制最佳实践

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

若要提高性能和促进部署，请在部署呼叫允许控制时应用以下最佳做法：

  - 确保已为当前和预期的媒体流量充分设置了 Wan。
    
    <div>
    

    > [!NOTE]  
    > 我们建议您将缓冲区中的带宽限制考虑在内。 有些方案（如争用条件）会影响使用的总带宽，并且可能会导致超出带宽限制的情况。 例如，如果在媒体流量接近带宽限制的情况下，两个呼叫尝试启动，则其中一个会被拒绝，因为另一个托管的会先启动。

    
    </div>

  - 监视网络使用情况和呼叫详细信息记录，以便您可以选择最佳 CAC 设置并在网络使用变化时更新 CAC 设置。

  - 使用 CAC 带宽策略来补充 QoS 设置。

  - 如果要将阻止的呼叫重新路由到 PSTN，请验证 PSTN 功能和容量。 有关详细信息，请参阅 [在 Lync Server 2013 中规划出站语音路由](lync-server-2013-planning-outbound-voice-routing.md)。
    
    <div>
    

    > [!NOTE]  
    > 容量是指需要打开以支持可能的 PSTN 重新路由的端口数。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

