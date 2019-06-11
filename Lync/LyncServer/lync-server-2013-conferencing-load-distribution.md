---
title: Lync Server 2013 会议加载分发
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 中的会议负载分配

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

与其他一些专用会议解决方案不同, Lync 服务器体系结构是共享硬件模型。 这意味着同一硬件由许多软件组件共享, 每个组件都支持不同的实时通信。 每种类型的实时通信都将在服务器上放置特定负载。 例如, 前端服务器可以运行会话初始协议 (SIP) 路由组件、web 应用程序 (如通讯簿搜索)、Web 会议服务、A/V 会议服务、企业语音应用程序 (例如, 会议助理应用程序和响应组应用程序) 和中介服务器。 前端服务器上的一组数据库还为用户、联系人、联机状态、会议和语音路由数据提供存储和处理。 通过这种硬件共享、组件、服务和进程来争用 CPU 和内存资源, 因此非会议工作负载对服务器缩放有直接影响。

与其他基于硬件的其他会议解决方案相比, Lync Server 会议体系结构是一个无保留模型。 当用户安排会议时, Lync Server 在会议数据库中创建记录, 该记录用于存储会议数据, 但不会提前为计划会议保留任何硬件资源。 因此, Lync Server 具有内置负载平衡逻辑, 可通过在池中的所有前端服务器上平均分配负载的方式在前端服务器上动态分配会议资源。 这将有效地预配和利用硬件资源, 但这使得支持超大型会议非常困难 (特别是不恰当的计划)。 例如, 当 Lync Server 2013 池的运行速度接近其最高容量时, 每台前端服务器可能会主持大约125平均大小的会议。 再添加一个小型会议不会有问题，但是添加一个 1000 用户的会议就会出现问题，因为前端服务器可能无法在已有其他 125 个会议的同时支持这样的大型会议。

</div>

<span> </span>

</div>

</div>

</div>

