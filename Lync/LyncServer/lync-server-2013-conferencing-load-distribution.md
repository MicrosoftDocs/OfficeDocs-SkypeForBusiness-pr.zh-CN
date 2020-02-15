---
title: Lync Server 2013 会议负载分发
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dad04b445421e27e68cf49900d4bb925918bd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 中的会议负载分发

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

与其他一些专用会议解决方案不同，Lync Server 体系结构是共享硬件模型。 这意味着很多软件组件共享了相同的硬件，这些组件中的每一个都支持不同的实时通信。 每种类型的实时通信都为服务器带来了特定的负载。 例如，前端服务器可以运行会话初始协议（SIP）路由组件、web 应用程序（如通讯簿搜索）、Web 会议服务、A/V 会议服务、企业语音应用程序（例如，会议助理应用程序和响应组应用程序）和中介服务器。 前端服务器上的一组数据库还提供了用于用户、联系人、状态、会议和语音路由数据的存储和处理。 由于存在此硬件共享，组件、服务和进程将争用 CPU 和内存资源，因此非会议工作负荷对服务器缩放有直接影响。

与其他基于硬件端口的会议解决方案相比，Lync Server 会议体系结构是一个无保留模型。 当用户安排会议时，Lync Server 在会议数据库中创建一条记录，该记录存储会议数据，但不事先为计划会议预留任何硬件资源。 相反，Lync Server 具有内置负载平衡逻辑，以在前端服务器上动态分配会议资源，从而在池中的所有前端服务器上平均分布负载。 这样做可以有效地设置和利用硬件资源，但可能难以支持特大型会议（尤其是在没有制定合适的计划时）。 例如，当 Lync Server 2013 池的运行接近其顶级容量时，每台前端服务器可能会主持大约125平均大小的会议。 添加另一个小会议并不是一个问题，但为1000用户添加会议是一个问题，因为前端服务器可能无法同时支持其他125会议的大型会议。

</div>

<span> </span>

</div>

</div>

</div>

