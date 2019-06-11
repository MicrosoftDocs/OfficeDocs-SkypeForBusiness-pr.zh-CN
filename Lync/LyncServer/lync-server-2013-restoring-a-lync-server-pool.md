---
title: 'Lync Server 2013: 还原 Lync Server 池'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4035ddb27b77e165d612be9e35cbb02970892c8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="cab91-102">在 Lync Server 2013 中还原 Lync 服务器池</span><span class="sxs-lookup"><span data-stu-id="cab91-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cab91-103">_**主题上次修改时间:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="cab91-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="cab91-104">Lync Server 部署可能包含以下任何类型的池:</span><span class="sxs-lookup"><span data-stu-id="cab91-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="cab91-105">前端服务器</span><span class="sxs-lookup"><span data-stu-id="cab91-105">Front End Server</span></span>

  - <span data-ttu-id="cab91-106">中介服务器</span><span class="sxs-lookup"><span data-stu-id="cab91-106">Mediation Server</span></span>

  - <span data-ttu-id="cab91-107">持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="cab91-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="cab91-108">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="cab91-108">Edge Server</span></span>

<span data-ttu-id="cab91-109">如果整个池遇到中断, 请针对池中的每个成员服务器执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="cab91-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="cab91-110">对于前端池, 先还原后端服务器, 然后还原每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="cab91-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="cab91-111">有关详细信息, 请参阅[在 Lync server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)和[在 lync Server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cab91-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="cab91-112">对于所有其他类型的池, 请还原每个成员服务器。</span><span class="sxs-lookup"><span data-stu-id="cab91-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="cab91-113">有关详细信息, 请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cab91-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

