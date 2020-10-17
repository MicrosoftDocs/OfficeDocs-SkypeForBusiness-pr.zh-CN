---
title: Lync Server 2013：支持大型会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523919"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>使用 Lync Server 2013 支持大型会议

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

大型会议不会遵循前面的部分中介绍的测试模型，因为它们具有以下特征：

  - 会议形式为一对多的演示。

  - 一个或一些用户为演示者，并且所有人只能作为出席者参与。

  - PowerPoint 演示文稿共享是主要数据协作活动。

  - 需要音频，还可能使用视频。

  - 主持人（一般是会议组织者或组织者的助手）提前设置好会议。

  - 专门人员（不是演示者）运行会议，包括根据需要连接到联机会议、验证音频、视频和幻灯片共享工作、管理会议厅和用户角色、将参与者静音或取消静音、提问和管理记录。

支持多达 1000 个用户的大型会议需要解决与共享硬件模型和无预约模型相关的问题。

为了使最高为1000个用户的会议具有充足的 CPU 和内存资源，托管前端服务器不应承载任何其他即时消息 (IM) 和状态或企业语音工作负载。 此外，它不应承载任何其他会议，无论其他会议的规模如何。 这意味着主持最多为1000个用户的会议需要设置一个单独的 Lync Server 池，专门用于承载最多为1000个用户的大型会议。

专用于主持大型会议的 Lync Server 池应同时托管一个会议，且最多只能为1000个用户提供一个会议，因此需要通过带外计划过程提前保留会议时间，以确保从前端服务器进行的专用支持。 若要同时支持多个大型会议，建议设置多个专用大型会议池。

建议让专门人员安排和监控大型会议的联机部分。此人可能是组织者、组织者或演示者的代理或专业大型会议支持团队的成员，这取决于组织者的首选项。

在以下各节中，我们将介绍如何为大型会议实施专用池，包括使用 Lync Server 2013 支持大型会议方案的最佳实践。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中设置对大型会议的支持](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [在 Lync Server 2013 中管理大型会议](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

