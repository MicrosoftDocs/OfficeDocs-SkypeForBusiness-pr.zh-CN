---
title: Lync Server 2013：更改与前端池关联的边缘池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ad6ee6e40edb76d4ef5d7d53524f89e44a2aee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="ab152-102">在 Lync Server 2013 中更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="ab152-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab152-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ab152-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ab152-104">如果边缘池出现故障，但同一站点中的前端池仍在运行，您将需要将前端池设置为使用其他站点中的边缘池，直到故障池恢复。</span><span class="sxs-lookup"><span data-stu-id="ab152-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="ab152-105">更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="ab152-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="ab152-106">在拓扑生成器中，导航到需要更改的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="ab152-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="ab152-107">右键单击该池，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab152-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ab152-108">在“关联”\*\*\*\* 部分的“关联边缘池(用于媒体组件)”\*\*\*\* 下，使用下拉框选择要与此前端池关联的边缘池。</span><span class="sxs-lookup"><span data-stu-id="ab152-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="ab152-109">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab152-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab152-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab152-110">See Also</span></span>


[<span data-ttu-id="ab152-111">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ab152-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

