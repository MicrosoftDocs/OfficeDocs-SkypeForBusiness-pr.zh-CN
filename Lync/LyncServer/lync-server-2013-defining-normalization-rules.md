---
title: Lync Server 2013：定义规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a09f5075ffe8ff267f31333d3dba0f4fffbc41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="94d29-102">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="94d29-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94d29-103">_**上次修改的主题：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="94d29-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="94d29-104">Lync Server 2013 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为. 164 格式;换言之，规范化规则采用用户拨打的电话号码，并将该号码转换为 Lync Server 在内部使用的格式。</span><span class="sxs-lookup"><span data-stu-id="94d29-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="94d29-105">必须将每个拨号计划分配给一个或多个规范化规则。</span><span class="sxs-lookup"><span data-stu-id="94d29-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="94d29-106">有关规范化规则的详细信息，请参阅规划文档中的[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="94d29-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="94d29-107">有关如何编写正则表达式的详细信息，请参阅中[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)的 ".Net Framework 正则表达式"。</span><span class="sxs-lookup"><span data-stu-id="94d29-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="94d29-108">可以使用以下任一方法定义或编辑规范化规则：</span><span class="sxs-lookup"><span data-stu-id="94d29-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="94d29-109">使用 "**生成规范化规则**" 工具指定要删除的起始数字、长度、要删除的数字和要添加的数字的值，然后让 Lync Server 控制面板为您生成相应的匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="94d29-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="94d29-110">手动编写正则表达式以定义匹配模式和转换规则。</span><span class="sxs-lookup"><span data-stu-id="94d29-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94d29-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="94d29-111">In This Section</span></span>

  - [<span data-ttu-id="94d29-112">在 Lync Server 2013 中使用 Build a 规范化规则创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="94d29-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="94d29-113">在 Lync Server 2013 中手动创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="94d29-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94d29-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94d29-114">See Also</span></span>


[<span data-ttu-id="94d29-115">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="94d29-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="94d29-116">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="94d29-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

