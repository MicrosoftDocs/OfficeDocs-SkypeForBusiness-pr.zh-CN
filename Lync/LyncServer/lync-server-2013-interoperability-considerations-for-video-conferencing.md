---
title: Lync Server 2013：视频会议的互操作性注意事项
description: Lync Server 2013：视频会议的互操作性注意事项。
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
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543928"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 中视频会议的互操作性注意事项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

本部分介绍了在迁移的共存阶段，在旧客户端与 Lync Server 2013 池或 Lync Server 2013 客户端和旧版池之间存在互操作性时的用户体验。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 池

当在 Lync Server 2013 池中使用旧版客户端时，用户将遇到以下行为：

  - 对于双方呼叫，视频分辨率与在旧池中时相同。

  - 对于多方会议，视频分辨率和视频会议功能与在旧池中时相同。库视图和高分辨率不可用。

</div>

<div>

## <a name="legacy-pools"></a>旧池

当在旧版池中使用 Lync Server 2013 客户端时，用户将遇到以下行为：

  - 对于两方呼叫，Lync Server 2013 客户端可以使用以下新功能：
    
      - 如果两个参与者都使用 Lync Server 2013 客户端，则可以使用 h-p。
    
      - Lync Server 2013 客户端使用 TotalReceiveVideoBitRateKb 的默认值，因为旧版服务器不会通过带内设置发送此信息。

  - 对于多方会议，视频分辨率和视频会议功能与旧池中的旧客户端的体验相同。

<div>


> [!NOTE]  
> 当旧版服务器承载 Lync Server 2013 客户端时，可以配置视频会议带宽，以便池上的所有用户仅收到低分辨率视频，但发送高分辨率视频。 例如，在媒体配置中将 MaxVideoRateAllowed 设置为 CIF-250K，并在会议策略中将 VideoBitRateKb 设置为 2000 kbps。 此情形下的实际结果是池中的用户无法使用高分辨率。<BR>因为 MaxVideoRateAllowed 不再用于 Lync Server 2013 客户端，所以它无法阻止 Lync Server 2013 客户端请求高分辨率视频。 在池中的所有用户的会议策略中将 VideoBitRateKb 设置为与 MaxVideoRateAllowed 相同的值（即，将 CIF 设置为 250 kbps，或将 VGA 设置为 600 kbps，将 HD 设置为 1500 kbps）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

