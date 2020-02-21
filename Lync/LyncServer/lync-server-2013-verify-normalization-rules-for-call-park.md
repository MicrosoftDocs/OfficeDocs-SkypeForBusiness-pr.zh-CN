---
title: Lync Server 2013：验证呼叫寄存的规范化规则
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
ms.openlocfilehash: 1fcde0adac292b8773a81c759c72765f832ce745
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="ca57c-102">在 Lync Server 2013 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="ca57c-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca57c-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ca57c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ca57c-104">呼叫寄存轨道式不得进行规范化。</span><span class="sxs-lookup"><span data-stu-id="ca57c-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="ca57c-105">检查您的拨号计划，以确保您的轨道编号不规范。</span><span class="sxs-lookup"><span data-stu-id="ca57c-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="ca57c-106">如果您必须创建一个额外的规范化规则来阻止对您的轨道式进行规范化，请按照在[Lync Server 2013 中创建拨号计划中](lync-server-2013-create-a-dial-plan.md)的过程来定义新的规范化规则，以便**匹配的模式**标识和**转换模式**为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="ca57c-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="ca57c-107">例如，如果您的呼叫寄存通道范围是7000–7999，则**要匹配的模式**为 **^ （\\7{3}d） $** and**转换模式**为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="ca57c-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca57c-108">请确保您的拨号计划中的默认规范化规则不包含<STRONG>^ （\d \*）</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ca57c-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="ca57c-109">否则，您的呼叫寄存规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="ca57c-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca57c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca57c-110">See Also</span></span>


[<span data-ttu-id="ca57c-111">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="ca57c-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

