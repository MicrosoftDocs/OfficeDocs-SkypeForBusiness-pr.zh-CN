---
title: Lync Server 2013：视频会议的互操作性注意事项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的视频会议的互操作性注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

本部分介绍了当旧客户端与 Lync Server 2013 池或 Lync Server 2013 客户端和旧版池之间存在互操作时，迁移的共存阶段中的用户体验。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 池

当在 Lync Server 2013 池中使用旧客户端时，用户将遇到以下行为：

  - 对于两方呼叫，视频分辨率与旧版池中的相同。

  - 对于多方会议，视频分辨率和视频会议功能与旧版池中的功能相同。 库视图和高分辨率不可用。

</div>

<div>

## <a name="legacy-pools"></a>旧版池

当在旧版池中使用 Lync Server 2013 客户端时，用户将遇到以下行为：

  - 对于两方呼叫，Lync Server 2013 客户端可以使用以下新功能：
    
      - 如果两个参与者都在使用 Lync Server 2013 客户端，则可以使用 h-p。
    
      - Lync Server 2013 客户端对 TotalReceiveVideoBitRateKb 使用默认值，因为旧服务器不会使用带内设置发送此信息。

  - 对于多方会议，视频分辨率和视频会议功能与旧版池中的旧客户体验相同。

<div>


> [!NOTE]  
> 当旧式服务器托管 Lync Server 2013 客户端时，可以配置视频会议带宽，以便该池中的所有用户仅收到低分辨率视频，但发送高分辨率视频。 例如，在媒体配置中将 MaxVideoRateAllowed 设置为 CIF-250K 时，在会议策略中将 VideoBitRateKb 设置为 2000 kbps。 这种情况下的网络效果是不可能对池中的用户进行高分辨率。<BR>由于 MaxVideoRateAllowed 不再用于 Lync Server 2013 客户端，因此它无法阻止 Lync Server 2013 客户端请求高分辨率视频。 请改为将池中的所有用户的会议策略中的 VideoBitRateKb 设置为与 MaxVideoRateAllowed 相同的值（即，CIF 设置为 250 kbps，或将 VGA 设置为 600 kbps，或将 HD 设置为 1500 kbps）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

