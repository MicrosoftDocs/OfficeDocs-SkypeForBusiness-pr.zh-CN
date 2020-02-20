---
title: Lync Server 2013：定义转换规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4082e5ff206a25269e54062add6fcd49c8d22108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="4e8f5-102">在 Lync Server 2013 中定义转换规则</span><span class="sxs-lookup"><span data-stu-id="4e8f5-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e8f5-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4e8f5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4e8f5-104">Lync Server 2013 企业语音路由根据规范化为 e.164 格式的电话号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="4e8f5-105">这意味着，所有拨打的字符串都必须规范化为 e.164 格式，以执行反向号码查找（RNL），以便可以将它们转换为匹配的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="4e8f5-106">Lync Server 2013 提供了操作被叫 ID 和呼叫者 ID 演示的功能。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="4e8f5-107">本节讨论如何操作被叫 ID 和呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e8f5-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4e8f5-108">In This Section</span></span>

  - [<span data-ttu-id="4e8f5-109">Lync Server 2013 中的呼叫者 ID 演示</span><span class="sxs-lookup"><span data-stu-id="4e8f5-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="4e8f5-110">Lync Server 2013 中名为 ID 的演示文稿</span><span class="sxs-lookup"><span data-stu-id="4e8f5-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e8f5-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8f5-111">See Also</span></span>


[<span data-ttu-id="4e8f5-112">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="4e8f5-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

