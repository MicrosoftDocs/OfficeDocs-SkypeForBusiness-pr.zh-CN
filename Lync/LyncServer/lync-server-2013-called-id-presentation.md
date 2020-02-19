---
title: Lync Server 2013：称为 ID 演示文稿
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b4ad6f728f01f0cf9ef1aac6ed57ad22c7ff345
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="8995e-102">Lync Server 2013 中名为 ID 的演示文稿</span><span class="sxs-lookup"><span data-stu-id="8995e-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8995e-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8995e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8995e-104">在 Lync Server 2010 中，被叫方的电话号码（称为电话号码）可以从 e.164 格式转换为中继对等方（即，关联网关、专用交换机（PBX）或 SIP 中继）所需的本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="8995e-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="8995e-105">为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。</span><span class="sxs-lookup"><span data-stu-id="8995e-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8995e-p102">将一个或多个转换规则与企业语音中继配置进行关联的功能可用作在中继对等方上配置转换规则的<EM></EM>备选方法。如果已在中继对等方上配置转换规则，则不要将任何转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="8995e-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="8995e-108">可以使用以下任一方法创建或修改转换规则：</span><span class="sxs-lookup"><span data-stu-id="8995e-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="8995e-109">使用 "**生成转换规则**" 工具指定要删除的起始数字、长度、要删除的数字和要添加的数字的值，然后让 Lync Server 控制面板为您生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="8995e-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="8995e-110">手动编写正则表达式以定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="8995e-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8995e-111">有关如何编写正则表达式的信息，请参阅处<A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>的 ".Net Framework 正则表达式"。</span><span class="sxs-lookup"><span data-stu-id="8995e-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8995e-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="8995e-112">In This Section</span></span>

  - [<span data-ttu-id="8995e-113">使用 Lync Server 2013 中的 "构建转换规则" 工具创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="8995e-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="8995e-114">在 Lync Server 2013 中手动创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="8995e-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8995e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8995e-115">See Also</span></span>


[<span data-ttu-id="8995e-116">Lync Server 2013 中的呼叫者 ID 演示</span><span class="sxs-lookup"><span data-stu-id="8995e-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

