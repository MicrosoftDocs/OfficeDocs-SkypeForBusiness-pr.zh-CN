---
title: Lync Server 2013：翻译规则
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
ms.openlocfilehash: d4ae330633acb04a35abe19356f4b00ff09ef41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="a651c-102">Lync Server 2013 中的翻译规则</span><span class="sxs-lookup"><span data-stu-id="a651c-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a651c-103">_**主题上次修改时间：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a651c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a651c-104">Lync Server 2013 企业版语音要求将所有拨号字符串正常化为格式，以便执行反向数字查找（RNL）。</span><span class="sxs-lookup"><span data-stu-id="a651c-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a651c-105">在 Microsoft Lync Server 2010 中，仅支持被呼叫号码的翻译规则。</span><span class="sxs-lookup"><span data-stu-id="a651c-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="a651c-106">Microsoft Lync Server 2013 中的新增，翻译规则也支持呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="a651c-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="a651c-107">*中继对等方*（即，关联网关、专用交换机 (PBX) 或 SIP 中继）可能要求号码采用本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="a651c-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="a651c-108">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="a651c-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="a651c-109">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="a651c-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="a651c-110">通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="a651c-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="a651c-111">在规划要与特定中介服务器群集关联的网关和多少个网关时，使用类似的本地拨号要求对干线对等进行分组可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="a651c-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="a651c-112">这可减少所需的转换规则数和编写转换规则所需的时间。</span><span class="sxs-lookup"><span data-stu-id="a651c-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a651c-113">将一个或多个翻译规则与企业语音中继配置相关联应用作在中继对等上配置翻译规则的替代方法。</span><span class="sxs-lookup"><span data-stu-id="a651c-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="a651c-114">如果你已在中继对等上配置了转换规则，请不要将翻译规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="a651c-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="a651c-115">示例转换规则</span><span class="sxs-lookup"><span data-stu-id="a651c-115">Example Translation Rules</span></span>

<span data-ttu-id="a651c-116">以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。</span><span class="sxs-lookup"><span data-stu-id="a651c-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="a651c-117">有关如何实现翻译规则的详细信息，请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="a651c-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="a651c-118">描述</span><span class="sxs-lookup"><span data-stu-id="a651c-118">Description</span></span></th>
<th><span data-ttu-id="a651c-119">起始数字</span><span class="sxs-lookup"><span data-stu-id="a651c-119">Starting Digits</span></span></th>
<th><span data-ttu-id="a651c-120">长度</span><span class="sxs-lookup"><span data-stu-id="a651c-120">Length</span></span></th>
<th><span data-ttu-id="a651c-121">要删除的数字</span><span class="sxs-lookup"><span data-stu-id="a651c-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="a651c-122">要添加的数字</span><span class="sxs-lookup"><span data-stu-id="a651c-122">Digits to Add</span></span></th>
<th><span data-ttu-id="a651c-123">匹配模式</span><span class="sxs-lookup"><span data-stu-id="a651c-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="a651c-124">转换</span><span class="sxs-lookup"><span data-stu-id="a651c-124">Translation</span></span></th>
<th><span data-ttu-id="a651c-125">示例</span><span class="sxs-lookup"><span data-stu-id="a651c-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a651c-126">美国常规长途拨号</span><span class="sxs-lookup"><span data-stu-id="a651c-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="a651c-127">（去掉“+”）</span><span class="sxs-lookup"><span data-stu-id="a651c-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="a651c-128">+1</span><span class="sxs-lookup"><span data-stu-id="a651c-128">+1</span></span></p></td>
<td><p><span data-ttu-id="a651c-129">正好 12 位</span><span class="sxs-lookup"><span data-stu-id="a651c-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="a651c-130">1</span><span class="sxs-lookup"><span data-stu-id="a651c-130">1</span></span></p></td>
<td><p><span data-ttu-id="a651c-131">0</span><span class="sxs-lookup"><span data-stu-id="a651c-131">0</span></span></p></td>
<td><p><span data-ttu-id="a651c-132">^\+（1 \ d{10}） $</span><span class="sxs-lookup"><span data-stu-id="a651c-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="a651c-133">$1</span><span class="sxs-lookup"><span data-stu-id="a651c-133">$1</span></span></p></td>
<td><p><span data-ttu-id="a651c-134">+14255551010 变为 14255551010</span><span class="sxs-lookup"><span data-stu-id="a651c-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a651c-135">美国国际长途拨号</span><span class="sxs-lookup"><span data-stu-id="a651c-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="a651c-136">（去掉“+”并添加 011）</span><span class="sxs-lookup"><span data-stu-id="a651c-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="a651c-137">至少 11 位</span><span class="sxs-lookup"><span data-stu-id="a651c-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="a651c-138">1</span><span class="sxs-lookup"><span data-stu-id="a651c-138">1</span></span></p></td>
<td><p><span data-ttu-id="a651c-139">011</span><span class="sxs-lookup"><span data-stu-id="a651c-139">011</span></span></p></td>
<td><p><span data-ttu-id="a651c-140">^\+（\d{9}\d +） $</span><span class="sxs-lookup"><span data-stu-id="a651c-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="a651c-141">011$1</span><span class="sxs-lookup"><span data-stu-id="a651c-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="a651c-142">+441235551010 变为 011441235551010</span><span class="sxs-lookup"><span data-stu-id="a651c-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

