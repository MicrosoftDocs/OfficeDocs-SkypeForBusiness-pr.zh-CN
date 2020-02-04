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
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="11385-102">在 Lync Server 2013 中验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="11385-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11385-103">_**主题上次修改时间：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="11385-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="11385-104">调用寄存轨道式不得正常化。</span><span class="sxs-lookup"><span data-stu-id="11385-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="11385-105">检查拨号计划以确保未对通道号码进行规范化。</span><span class="sxs-lookup"><span data-stu-id="11385-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="11385-106">如果必须创建另一个规范化规则来防止你的轨道式被正常化，请按照在[Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)中的过程定义新的规范化规则，以便**匹配**"轨道范围" 和 "翻译 **$1\*\*\*\*模式**"。</span><span class="sxs-lookup"><span data-stu-id="11385-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="11385-107">例如，如果您的呼叫公园轨道范围为 7000-7999，则**要匹配的模式**为 **^ （\\7{3}d） $** 和**转换模式**为 **$1**。</span><span class="sxs-lookup"><span data-stu-id="11385-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11385-108">请确保拨号计划中的默认规范化规则不包含 <STRONG>^(\d\*)</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="11385-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="11385-109">否则，您的通话寄存规范化规则将永远不会运行。</span><span class="sxs-lookup"><span data-stu-id="11385-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11385-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11385-110">See Also</span></span>


[<span data-ttu-id="11385-111">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="11385-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

