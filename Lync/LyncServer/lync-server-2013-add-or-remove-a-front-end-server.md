---
title: Lync Server 2013：添加或删除前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="484cc-102">在 Lync Server 2013 中添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="484cc-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="484cc-103">_**上次修改的主题：** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="484cc-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="484cc-p101">将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。为了防止对用户的服务造成任何中断，在添加或删除前端服务器时，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="484cc-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="484cc-106">如果要将新服务器添加到池，请将新的池服务器更新为与池中现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="484cc-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="484cc-107">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="484cc-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="484cc-p102">如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="484cc-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="484cc-110">当所删除的服务器没有当前会话时，请停止这些服务器上的 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="484cc-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="484cc-111">打开拓扑生成器，然后添加或删除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="484cc-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="484cc-112">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="484cc-112">Publish the topology.</span></span>

5.  <span data-ttu-id="484cc-113">如果池已从两个前端服务器到两个以上，或者从两个以上的服务器到两个以上，则需要键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="484cc-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="484cc-114">如果池具有三个或更多的服务器，则在键入此 cmdlet 时，其中必须至少有三个服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="484cc-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="484cc-115">重新启动池中的所有前端服务器，一次一台。</span><span class="sxs-lookup"><span data-stu-id="484cc-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

