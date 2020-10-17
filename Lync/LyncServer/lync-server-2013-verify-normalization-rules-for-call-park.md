---
title: Lync Server 2013：验证呼叫寄存的规范化规则
description: Lync Server 2013：验证呼叫寄存的规范化规则。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ac4c15091141e3069e7b77533d0e4148459f570
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547058"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="57dea-103">在 Lync Server 2013 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="57dea-103">Verify normalization rules for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57dea-104">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="57dea-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="57dea-105">呼叫寄存轨道式不得进行规范化。</span><span class="sxs-lookup"><span data-stu-id="57dea-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="57dea-106">检查您的拨号计划，以确保您的轨道编号不规范。</span><span class="sxs-lookup"><span data-stu-id="57dea-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="57dea-107">如果您必须创建一个额外的规范化规则来阻止对您的轨道式进行规范化，请按照在 [Lync Server 2013 中创建拨号计划中](lync-server-2013-create-a-dial-plan.md) 的过程来定义新的规范化规则，以便 **匹配的模式** 标识和 **转换模式** 为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="57dea-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="57dea-108">例如，如果您的呼叫寄存通道范围是7000–7999，则 **要匹配的模式** 为 **^ (7 \\ d {3}) $** and **转换模式** 为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="57dea-108">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57dea-109">请确保您的拨号计划中的默认规范化规则不包含 <STRONG>^ ( \d \* ) </STRONG>。</span><span class="sxs-lookup"><span data-stu-id="57dea-109">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="57dea-110">否则，您的呼叫寄存规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="57dea-110">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57dea-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57dea-111">See Also</span></span>


[<span data-ttu-id="57dea-112">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="57dea-112">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

