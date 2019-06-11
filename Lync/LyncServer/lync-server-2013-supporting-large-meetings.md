---
title: 'Lync Server 2013: 支持大型会议'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>使用 Lync Server 2013 支持大型会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-03_

大型会议不遵循上一节中所述的测试模型, 因为它们具有以下特征:

  - 会议形式为一对多的演示。

  - 一个或一些用户为演示者，并且所有人只能作为出席者参与。

  - PowerPoint 演示文稿共享是主要数据协作活动。

  - 需要音频，还可能使用视频。

  - 一个专用人员, 通常是会议组织者或组织者的助理提前设置会议。

  - 专门人员（不是演示者）运行会议，包括根据需要连接到联机会议、验证音频、视频和幻灯片共享工作、管理会议厅和用户角色、将参与者静音和取消静音、提问和管理记录。

支持最多1000个用户的大型会议需要解决与共享硬件模型和非保留模型相关的问题。

为了给多达 1000 个用户的会议提供充足的 CPU 和会议资源，宿主前端服务器不应承载任何其他即时消息 (IM) 和状态或企业语音工作负荷。 无论其他会议的大小如何, 它也不会托管任何其他会议。 这意味着托管会议最多为1000个用户需要设置单独的 Lync 服务器池, 专用于托管最多1000用户的大型会议。

专用于托管大型会议的 Lync Server 池应同时托管一个会议和最多1000个用户, 因此需要通过带外计划流程提前保留会议时间, 以确保从前端 Serv 的专用支持。ers. 若要同时支持多个大型会议, 我们建议设置多个专用大型会议池。

我们建议专门的人员运行和监控大型会议的联机部分。 此人可能是组织者、组织者或演示者的代理人, 或者是专门的大型会议支持团队的成员, 具体取决于组织的首选项。

在以下部分中, 我们将介绍如何为大型会议实施专用池, 包括使用 Lync Server 2013 支持大型会议方案的最佳做法。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中设置对大型会议的支持](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [在 Lync Server 2013 中管理大型会议](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

