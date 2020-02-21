---
title: Lync Server 2013：规划媒体旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de3d5132d7307f48de905f5bb6d28e53cbec14a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中规划媒体旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

媒体旁路功能是指在可能的情况下，从信号遍历中介服务器的呼叫的媒体路径中删除中介服务器。

媒体旁路功能可通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高语音质量。 由于绕过的呼叫无需媒体处理操作，这可减少中介服务器上的负载，从而提高可伸缩性。 这种负载降低补充了中介服务器控制多个网关的能力。

如果没有中介服务器的分支站点通过受限制带宽的一个或多个 WAN 链路连接到中央站点，则媒体旁路降低了带宽需求，因为允许来自分支站点的客户端的媒体直接流向本地网关，而不首先必须跨 WAN 链路传递到位于中央站点的中介服务器和背面。

通过从媒体处理中免除中介服务器，媒体旁路也可能会减少企业语音基础结构所需的中介服务器的数量。

下图显示了具有和没有媒体旁路功能的拓扑中的基本媒体和信号路径。

**具有和没有媒体旁路功能的媒体和信号路径**

![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")

一般而言，应尽可能启用媒体旁路。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的媒体旁路概述](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 中的媒体旁路模式](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 中的媒体旁路和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 中媒体旁路的技术要求](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>相关部分

[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置具有媒体旁路功能的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013 中的全局媒体旁路选项](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

