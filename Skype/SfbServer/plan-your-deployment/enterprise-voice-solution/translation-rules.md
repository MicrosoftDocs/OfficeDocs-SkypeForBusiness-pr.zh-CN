---
title: Skype for Business Server 中的转换规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解 Skype for Business Server 服务中的转换规则和拨号企业语音。
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802682"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="9add4-103">Skype for Business Server 中的转换规则</span><span class="sxs-lookup"><span data-stu-id="9add4-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="9add4-104">了解 Skype for Business Server 服务中的转换规则和拨号企业语音。</span><span class="sxs-lookup"><span data-stu-id="9add4-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="9add4-105">企业语音要求所有拨号字符串规范化为 E.164 格式，以便执行 RNL (反向) 。</span><span class="sxs-lookup"><span data-stu-id="9add4-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="9add4-106">被叫号码和呼叫号码均支持转换规则。</span><span class="sxs-lookup"><span data-stu-id="9add4-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="9add4-107">中继 (（即关联网关、专用交换机 (PBX) 或 SIP 中继) ）可能要求号码采用本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="9add4-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="9add4-108">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="9add4-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="9add4-109">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="9add4-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="9add4-110">通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="9add4-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="9add4-111">在规划要与特定中介服务器群集关联的网关和网关数时，将具有类似本地拨号要求的中继对等方分组可能很有用。</span><span class="sxs-lookup"><span data-stu-id="9add4-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="9add4-112">这可减少所需的转换规则数和编写转换规则所需的时间。</span><span class="sxs-lookup"><span data-stu-id="9add4-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9add4-113">将一个或多个转换规则与企业语音中继配置相关联，作为在中继对等方上配置转换规则的替代方法。</span><span class="sxs-lookup"><span data-stu-id="9add4-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="9add4-114">如果在中继对等方上配置了转换企业语音，请不要将转换规则与中继配置关联，因为这两个规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="9add4-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="9add4-115">示例转换规则</span><span class="sxs-lookup"><span data-stu-id="9add4-115">Example Translation Rules</span></span>

<span data-ttu-id="9add4-116">以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。</span><span class="sxs-lookup"><span data-stu-id="9add4-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="9add4-117">有关如何实施转换规则的详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9add4-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="9add4-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="9add4-118">**Description**</span></span>|<span data-ttu-id="9add4-119">**起始数字**</span><span class="sxs-lookup"><span data-stu-id="9add4-119">**Starting Digits**</span></span>|<span data-ttu-id="9add4-120">**Length**</span><span class="sxs-lookup"><span data-stu-id="9add4-120">**Length**</span></span>|<span data-ttu-id="9add4-121">**要删除的数字**</span><span class="sxs-lookup"><span data-stu-id="9add4-121">**Digits to Remove**</span></span>|<span data-ttu-id="9add4-122">**要添加的数字**</span><span class="sxs-lookup"><span data-stu-id="9add4-122">**Digits to Add**</span></span>|<span data-ttu-id="9add4-123">**匹配模式**</span><span class="sxs-lookup"><span data-stu-id="9add4-123">**Matching Pattern**</span></span>|<span data-ttu-id="9add4-124">**翻译**</span><span class="sxs-lookup"><span data-stu-id="9add4-124">**Translation**</span></span>|<span data-ttu-id="9add4-125">**示例**</span><span class="sxs-lookup"><span data-stu-id="9add4-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9add4-126">美国常规长途拨号</span><span class="sxs-lookup"><span data-stu-id="9add4-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="9add4-127"> (去除"+") </span><span class="sxs-lookup"><span data-stu-id="9add4-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="9add4-128">+1</span><span class="sxs-lookup"><span data-stu-id="9add4-128">+1</span></span>  <br/> |<span data-ttu-id="9add4-129">正好 12 位</span><span class="sxs-lookup"><span data-stu-id="9add4-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="9add4-130">1 </span><span class="sxs-lookup"><span data-stu-id="9add4-130">1</span></span>  <br/> |<span data-ttu-id="9add4-131">0</span><span class="sxs-lookup"><span data-stu-id="9add4-131">0</span></span>  <br/> |<span data-ttu-id="9add4-132">^\+ (1\d {10}) $</span><span class="sxs-lookup"><span data-stu-id="9add4-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="9add4-133">$1</span><span class="sxs-lookup"><span data-stu-id="9add4-133">$1</span></span>  <br/> |<span data-ttu-id="9add4-134">+14255551010 变为 14255551010</span><span class="sxs-lookup"><span data-stu-id="9add4-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="9add4-135">美国国际长途拨号</span><span class="sxs-lookup"><span data-stu-id="9add4-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="9add4-136"> (去除"+"并添加 011) </span><span class="sxs-lookup"><span data-stu-id="9add4-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="9add4-137">至少 11 位</span><span class="sxs-lookup"><span data-stu-id="9add4-137">At least 11</span></span>  <br/> |<span data-ttu-id="9add4-138">1 </span><span class="sxs-lookup"><span data-stu-id="9add4-138">1</span></span>  <br/> |<span data-ttu-id="9add4-139">011</span><span class="sxs-lookup"><span data-stu-id="9add4-139">011</span></span>  <br/> |<span data-ttu-id="9add4-140">^\+ (\d {9} \d+) $</span><span class="sxs-lookup"><span data-stu-id="9add4-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="9add4-141">011$1</span><span class="sxs-lookup"><span data-stu-id="9add4-141">011$1</span></span>  <br/> |<span data-ttu-id="9add4-142">+441235551010 变为 011441235551010</span><span class="sxs-lookup"><span data-stu-id="9add4-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


