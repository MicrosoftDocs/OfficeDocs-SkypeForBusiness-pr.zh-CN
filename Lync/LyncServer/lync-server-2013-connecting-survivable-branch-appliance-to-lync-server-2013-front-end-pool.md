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
ms.openlocfilehash: 051f4c0837b654f389841dc94275577a51f5b904
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="c0e38-102">将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池</span><span class="sxs-lookup"><span data-stu-id="c0e38-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0e38-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c0e38-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c0e38-104">每个 Survivable 分支设备（SBA）都与一个前端池相关联，后者充当 SBA 的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="c0e38-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="c0e38-105">将前端池升级到 Lync Server 2013 时，在升级前端池时，SBA 必须与前端池解除关联。</span><span class="sxs-lookup"><span data-stu-id="c0e38-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="c0e38-106">在升级前端池之后，可以使用前端池 reassociated SBA。</span><span class="sxs-lookup"><span data-stu-id="c0e38-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="c0e38-107">这涉及到使用拓扑生成器删除拓扑中的 SBA，然后将 SBA 重新添加到拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="c0e38-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="c0e38-108">在从拓扑中删除 SBA 之前，必须将驻留在 SBA 上的用户移至另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="c0e38-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="c0e38-109">将 SBA 添加回拓扑后，可将这些用户移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="c0e38-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="c0e38-110">这些步骤概括如下：</span><span class="sxs-lookup"><span data-stu-id="c0e38-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="c0e38-111">将驻留在 SBA 上的分支用户移动到另一个前端池。</span><span class="sxs-lookup"><span data-stu-id="c0e38-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="c0e38-112">从拓扑中删除 SBA，以将现有的前端池与备份注册器解除关联。</span><span class="sxs-lookup"><span data-stu-id="c0e38-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="c0e38-113">将前端池升级到 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c0e38-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="c0e38-114">将 SBA 添加回拓扑。</span><span class="sxs-lookup"><span data-stu-id="c0e38-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="c0e38-115">将新的前端池与 SBA 作为备份注册器相关联。</span><span class="sxs-lookup"><span data-stu-id="c0e38-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="c0e38-116">将分支用户移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="c0e38-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c0e38-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c0e38-117">In This Section</span></span>

  - [<span data-ttu-id="c0e38-118">将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="c0e38-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="c0e38-119">将 Lync Server 2010 Survivable 分支装置分支站点添加到您的拓扑</span><span class="sxs-lookup"><span data-stu-id="c0e38-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

