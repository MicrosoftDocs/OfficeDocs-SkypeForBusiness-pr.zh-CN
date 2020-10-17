---
title: Lync Server 2013：转换规则
description: Lync Server 2013：转换规则。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549038"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="c8d11-103">Lync Server 2013 中的转换规则</span><span class="sxs-lookup"><span data-stu-id="c8d11-103">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8d11-104">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c8d11-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c8d11-105">Lync Server 2013 企业语音要求将所有拨号字符串正常化为 e.164 格式，以执行反向号码查找 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="c8d11-105">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c8d11-106">在 Microsoft Lync Server 2010 中，仅对被呼叫的号码支持转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8d11-106">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="c8d11-107">新增在 Microsoft Lync Server 2013 中，呼叫号码也支持转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8d11-107">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="c8d11-108">“中继对等方”\*\*（即，关联网关、专用交换机 (PBX) 或 SIP 中继）可能要求号码采用本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="c8d11-108">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="c8d11-109">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="c8d11-109">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="c8d11-110">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="c8d11-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="c8d11-111">通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="c8d11-111">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="c8d11-112">在规划与特定中介服务器群集相关联的网关和多个网关时，使用类似的本地拨号要求对中继对等方进行分组可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="c8d11-112">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="c8d11-113">这可减少所需的转换规则数和编写转换规则所需的时间。</span><span class="sxs-lookup"><span data-stu-id="c8d11-113">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8d11-114">将一个或多个转换规则与企业语音中继配置关联应用作在中继对等方上配置转换规则的替代方法。</span><span class="sxs-lookup"><span data-stu-id="c8d11-114">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c8d11-115">如果已在中继对等方上配置转换规则，则不要将转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="c8d11-115">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="c8d11-116">示例转换规则</span><span class="sxs-lookup"><span data-stu-id="c8d11-116">Example Translation Rules</span></span>

<span data-ttu-id="c8d11-117">以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。</span><span class="sxs-lookup"><span data-stu-id="c8d11-117">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="c8d11-118">有关如何实施转换规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="c8d11-118">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d11-119">说明</span><span class="sxs-lookup"><span data-stu-id="c8d11-119">Description</span></span></th>
<th><span data-ttu-id="c8d11-120">起始数字</span><span class="sxs-lookup"><span data-stu-id="c8d11-120">Starting Digits</span></span></th>
<th><span data-ttu-id="c8d11-121">Length</span><span class="sxs-lookup"><span data-stu-id="c8d11-121">Length</span></span></th>
<th><span data-ttu-id="c8d11-122">要删除的数字</span><span class="sxs-lookup"><span data-stu-id="c8d11-122">Digits to Remove</span></span></th>
<th><span data-ttu-id="c8d11-123">要添加的数字</span><span class="sxs-lookup"><span data-stu-id="c8d11-123">Digits to Add</span></span></th>
<th><span data-ttu-id="c8d11-124">匹配模式</span><span class="sxs-lookup"><span data-stu-id="c8d11-124">Matching Pattern</span></span></th>
<th><span data-ttu-id="c8d11-125">Translation</span><span class="sxs-lookup"><span data-stu-id="c8d11-125">Translation</span></span></th>
<th><span data-ttu-id="c8d11-126">示例</span><span class="sxs-lookup"><span data-stu-id="c8d11-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d11-127">美国常规长途拨号</span><span class="sxs-lookup"><span data-stu-id="c8d11-127">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="c8d11-128">（去掉“+”）</span><span class="sxs-lookup"><span data-stu-id="c8d11-128">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="c8d11-129">+ 1</span><span class="sxs-lookup"><span data-stu-id="c8d11-129">+1</span></span></p></td>
<td><p><span data-ttu-id="c8d11-130">正好 12 位</span><span class="sxs-lookup"><span data-stu-id="c8d11-130">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="c8d11-131">1</span><span class="sxs-lookup"><span data-stu-id="c8d11-131">1</span></span></p></td>
<td><p><span data-ttu-id="c8d11-132">0</span><span class="sxs-lookup"><span data-stu-id="c8d11-132">0</span></span></p></td>
<td><p><span data-ttu-id="c8d11-133">^\+ (1 \ d {10}) $</span><span class="sxs-lookup"><span data-stu-id="c8d11-133">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="c8d11-134">$1</span><span class="sxs-lookup"><span data-stu-id="c8d11-134">$1</span></span></p></td>
<td><p><span data-ttu-id="c8d11-135">+14255551010 变为 14255551010</span><span class="sxs-lookup"><span data-stu-id="c8d11-135">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d11-136">美国国际长途拨号</span><span class="sxs-lookup"><span data-stu-id="c8d11-136">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="c8d11-137">（去掉“+”并添加 011）</span><span class="sxs-lookup"><span data-stu-id="c8d11-137">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="c8d11-138">至少 11 位</span><span class="sxs-lookup"><span data-stu-id="c8d11-138">At least 11</span></span></p></td>
<td><p><span data-ttu-id="c8d11-139">1</span><span class="sxs-lookup"><span data-stu-id="c8d11-139">1</span></span></p></td>
<td><p><span data-ttu-id="c8d11-140">011</span><span class="sxs-lookup"><span data-stu-id="c8d11-140">011</span></span></p></td>
<td><p><span data-ttu-id="c8d11-141">^\+ ( \d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="c8d11-141">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="c8d11-142">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="c8d11-142">011$1</span></span></p></td>
<td><p><span data-ttu-id="c8d11-143">+441235551010 变为 011441235551010</span><span class="sxs-lookup"><span data-stu-id="c8d11-143">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

