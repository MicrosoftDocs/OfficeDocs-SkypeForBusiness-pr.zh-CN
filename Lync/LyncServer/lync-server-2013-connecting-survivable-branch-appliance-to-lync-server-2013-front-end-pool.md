---
title: 将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="25e18-102">将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池</span><span class="sxs-lookup"><span data-stu-id="25e18-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e18-103">_**主题上次修改时间：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="25e18-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="25e18-104">每个 Survivable 分支装置（SBA）都与一个前端池相关联，后者充当 SBA 的备份注册机构。</span><span class="sxs-lookup"><span data-stu-id="25e18-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="25e18-105">当前端池升级到 Lync Server 2013 时，在升级前端池时，SBA 必须与前端池解除关联。</span><span class="sxs-lookup"><span data-stu-id="25e18-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="25e18-106">升级前端池后，SBA 可以与前端池 reassociated。</span><span class="sxs-lookup"><span data-stu-id="25e18-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="25e18-107">这包括从拓扑生成器的拓扑中删除 SBA，然后再次将 SBA 添加到拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="25e18-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="25e18-108">在从拓扑结构中删除 SBA 之前，必须将驻留在 SBA 上的用户移动到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="25e18-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="25e18-109">将 SBA 添加回拓扑后，这些用户可以移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="25e18-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="25e18-110">下面总结了这些步骤：</span><span class="sxs-lookup"><span data-stu-id="25e18-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="25e18-111">将驻留在 SBA 上的分支用户移到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="25e18-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="25e18-112">从拓扑中删除 SBA，以将现有的前端池与备份注册机构解除关联。</span><span class="sxs-lookup"><span data-stu-id="25e18-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="25e18-113">将前端池升级到 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="25e18-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="25e18-114">将 SBA 添加回拓扑。</span><span class="sxs-lookup"><span data-stu-id="25e18-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="25e18-115">将新的前端池与 SBA 作为备份注册机构相关联。</span><span class="sxs-lookup"><span data-stu-id="25e18-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="25e18-116">将分支用户移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="25e18-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25e18-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="25e18-117">In This Section</span></span>

  - [<span data-ttu-id="25e18-118">将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="25e18-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="25e18-119">将 Lync Server 2010 Survivable Branch Appliance 分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="25e18-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

