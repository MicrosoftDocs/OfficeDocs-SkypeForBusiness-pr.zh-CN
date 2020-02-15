---
title: Lync Server 2013：管理响应组队列
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group queues
ms:assetid: 1e91720c-ab67-4dfb-b30c-0ef2a8012310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520960(v=OCS.15)
ms:contentKeyID: 48183576
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e1c9a55c72522604168fec235f1b9d716cd5cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-queues-in-lync-server-2013"></a><span data-ttu-id="d760d-102">在 Lync Server 2013 中管理响应组队列</span><span class="sxs-lookup"><span data-stu-id="d760d-102">Managing Response Group queues in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d760d-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d760d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d760d-104">队列将保留对响应组的呼叫，直到代理应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="d760d-104">Queues hold calls to a response group until an agent answers the call.</span></span> <span data-ttu-id="d760d-105">管理队列时，需向队列分配一个或多个代理组并指定队列设置，如执行溢出操作前队列可以保留的呼叫数，以及执行超时操作前呼叫等待代理应答的时间长度。</span><span class="sxs-lookup"><span data-stu-id="d760d-105">When you manage a queue, you assign one or more agent groups to the queue and specify queue settings, such as the number of calls that the queue can hold before performing an overflow action and the length of time that a call waits for an agent before performing a time-out action.</span></span> <span data-ttu-id="d760d-106">当响应组应用程序搜索可用的代理时，它将按列出的顺序搜索代理组。</span><span class="sxs-lookup"><span data-stu-id="d760d-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d760d-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d760d-107">In This Section</span></span>

  - [<span data-ttu-id="d760d-108">在 Lync Server 2013 中创建或修改队列</span><span class="sxs-lookup"><span data-stu-id="d760d-108">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)

  - [<span data-ttu-id="d760d-109">在 Lync Server 2013 中删除响应组队列</span><span class="sxs-lookup"><span data-stu-id="d760d-109">Delete a Response Group queue in Lync Server 2013</span></span>](lync-server-2013-delete-a-response-group-queue.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

