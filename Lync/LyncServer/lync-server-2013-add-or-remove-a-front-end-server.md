---
title: Lync Server 2013：添加或删除前端服务器
description: Lync Server 2013：添加或删除前端服务器。
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
ms.openlocfilehash: 297bbf42dbba3d4f9926fd5ab9e0d7ed79349dc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571998"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="376b3-103">在 Lync Server 2013 中添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="376b3-103">Add or remove a Front End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376b3-104">_**上次修改的主题：** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="376b3-104">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="376b3-p101">将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。为了防止对用户的服务造成任何中断，在添加或删除前端服务器时，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="376b3-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="376b3-107">如果要将新服务器添加到池，请将新的池服务器更新为与池中现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="376b3-107">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="376b3-108">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="376b3-108">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="376b3-p102">如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="376b3-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="376b3-111">当所删除的服务器没有当前会话时，请停止这些服务器上的 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="376b3-111">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="376b3-112">打开拓扑生成器，然后添加或删除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="376b3-112">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="376b3-113">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="376b3-113">Publish the topology.</span></span>

5.  <span data-ttu-id="376b3-114">如果池已从两个前端服务器到两个以上，或者从两个以上的服务器到两个以上，则需要键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="376b3-114">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="376b3-115">如果池具有三个或更多的服务器，则在键入此 cmdlet 时，其中必须至少有三个服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="376b3-115">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="376b3-116">重新启动池中的所有前端服务器，一次一台。</span><span class="sxs-lookup"><span data-stu-id="376b3-116">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

