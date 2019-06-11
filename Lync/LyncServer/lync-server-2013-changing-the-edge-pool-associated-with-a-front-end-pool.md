---
title: Lync Server 2013：更改与前端池关联的边缘池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="fa0e2-102">在 Lync Server 2013 中更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="fa0e2-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa0e2-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fa0e2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fa0e2-104">如果边缘池已关闭, 但同一网站上的前端池仍在运行, 则需要将前端池设置为在其他网站上使用边缘池, 直到还原失败的边缘池。</span><span class="sxs-lookup"><span data-stu-id="fa0e2-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="fa0e2-105">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="fa0e2-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="fa0e2-106">在拓扑生成器中, 导航到需要更改的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="fa0e2-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="fa0e2-107">右键单击该池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="fa0e2-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="fa0e2-108">在 "**关联**" 部分中的 "**关联 Edge 池 (对于媒体组件)**" 下, 使用下拉框选择要与之关联的 "前端" 池的边缘池。</span><span class="sxs-lookup"><span data-stu-id="fa0e2-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="fa0e2-109">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fa0e2-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa0e2-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0e2-110">See Also</span></span>


[<span data-ttu-id="fa0e2-111">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="fa0e2-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

