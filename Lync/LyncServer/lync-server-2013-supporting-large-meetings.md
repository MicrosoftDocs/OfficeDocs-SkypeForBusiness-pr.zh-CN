---
title: Lync Server 2013：支持大型会议
description: Lync Server 2013：支持大型会议。
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
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554778"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="c3297-103">使用 Lync Server 2013 支持大型会议</span><span class="sxs-lookup"><span data-stu-id="c3297-103">Supporting large meetings using Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3297-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c3297-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c3297-105">大型会议不会遵循前面的部分中介绍的测试模型，因为它们具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="c3297-105">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="c3297-106">会议形式为一对多的演示。</span><span class="sxs-lookup"><span data-stu-id="c3297-106">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="c3297-107">一个或一些用户为演示者，并且所有人只能作为出席者参与。</span><span class="sxs-lookup"><span data-stu-id="c3297-107">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="c3297-108">PowerPoint 演示文稿共享是主要数据协作活动。</span><span class="sxs-lookup"><span data-stu-id="c3297-108">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="c3297-109">需要音频，还可能使用视频。</span><span class="sxs-lookup"><span data-stu-id="c3297-109">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="c3297-110">主持人（一般是会议组织者或组织者的助手）提前设置好会议。</span><span class="sxs-lookup"><span data-stu-id="c3297-110">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="c3297-111">专门人员（不是演示者）运行会议，包括根据需要连接到联机会议、验证音频、视频和幻灯片共享工作、管理会议厅和用户角色、将参与者静音或取消静音、提问和管理记录。</span><span class="sxs-lookup"><span data-stu-id="c3297-111">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="c3297-112">支持多达 1000 个用户的大型会议需要解决与共享硬件模型和无预约模型相关的问题。</span><span class="sxs-lookup"><span data-stu-id="c3297-112">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="c3297-113">为了使最高为1000个用户的会议具有充足的 CPU 和内存资源，托管前端服务器不应承载任何其他即时消息 (IM) 和状态或企业语音工作负载。</span><span class="sxs-lookup"><span data-stu-id="c3297-113">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="c3297-114">此外，它不应承载任何其他会议，无论其他会议的规模如何。</span><span class="sxs-lookup"><span data-stu-id="c3297-114">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="c3297-115">这意味着主持最多为1000个用户的会议需要设置一个单独的 Lync Server 池，专门用于承载最多为1000个用户的大型会议。</span><span class="sxs-lookup"><span data-stu-id="c3297-115">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="c3297-116">专用于主持大型会议的 Lync Server 池应同时托管一个会议，且最多只能为1000个用户提供一个会议，因此需要通过带外计划过程提前保留会议时间，以确保从前端服务器进行的专用支持。</span><span class="sxs-lookup"><span data-stu-id="c3297-116">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="c3297-117">若要同时支持多个大型会议，建议设置多个专用大型会议池。</span><span class="sxs-lookup"><span data-stu-id="c3297-117">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="c3297-p103">建议让专门人员安排和监控大型会议的联机部分。此人可能是组织者、组织者或演示者的代理或专业大型会议支持团队的成员，这取决于组织者的首选项。</span><span class="sxs-lookup"><span data-stu-id="c3297-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="c3297-120">在以下各节中，我们将介绍如何为大型会议实施专用池，包括使用 Lync Server 2013 支持大型会议方案的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c3297-120">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3297-121">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c3297-121">In This Section</span></span>

  - [<span data-ttu-id="c3297-122">在 Lync Server 2013 中设置对大型会议的支持</span><span class="sxs-lookup"><span data-stu-id="c3297-122">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="c3297-123">在 Lync Server 2013 中管理大型会议</span><span class="sxs-lookup"><span data-stu-id="c3297-123">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

