---
title: Skype for Business 服务器中的翻译规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解有关翻译规则和在 Skype for Business Server 企业语音中拨打字符串规范化的信息。
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297363"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="fcbeb-103">Skype for Business 服务器中的翻译规则</span><span class="sxs-lookup"><span data-stu-id="fcbeb-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="fcbeb-104">了解有关翻译规则和在 Skype for Business Server 企业语音中拨打字符串规范化的信息。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="fcbeb-105">对于执行反向数字查找 (RNL), 企业语音要求将所有拨号字符串正常化为 E-164 格式。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="fcbeb-106">同时支持被呼叫号码和通话号码的翻译规则。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="fcbeb-107">Thetrunk 对等 (即关联网关、专用分支交换 (PBX) 或 SIP 干线) 可能要求数字采用本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="fcbeb-108">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="fcbeb-109">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="fcbeb-110">通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="fcbeb-111">在规划要与特定中介服务器群集关联的网关和多少个网关时, 使用类似的本地拨号要求对干线对等进行分组可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="fcbeb-112">这可减少所需的转换规则数和编写转换规则所需的时间。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcbeb-113">将一个或多个翻译规则与企业语音中继配置相关联应用作在中继对等上配置翻译规则的替代方法。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="fcbeb-114">如果你已在中继对等上配置了转换规则, 请不要将翻译规则与企业语音中继配置相关联, 因为这两个规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="fcbeb-115">示例转换规则</span><span class="sxs-lookup"><span data-stu-id="fcbeb-115">Example Translation Rules</span></span>

<span data-ttu-id="fcbeb-116">以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="fcbeb-117">有关如何实施转换规则的详细信息，请参阅部署文档中的 [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fcbeb-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="fcbeb-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-118">**Description**</span></span>|<span data-ttu-id="fcbeb-119">**起始数字**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-119">**Starting Digits**</span></span>|<span data-ttu-id="fcbeb-120">**长度**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-120">**Length**</span></span>|<span data-ttu-id="fcbeb-121">**要删除的数字**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-121">**Digits to Remove**</span></span>|<span data-ttu-id="fcbeb-122">**要添加的数字**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-122">**Digits to Add**</span></span>|<span data-ttu-id="fcbeb-123">**匹配模式**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-123">**Matching Pattern**</span></span>|<span data-ttu-id="fcbeb-124">**转换**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-124">**Translation**</span></span>|<span data-ttu-id="fcbeb-125">**示例**</span><span class="sxs-lookup"><span data-stu-id="fcbeb-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fcbeb-126">美国常规长途拨号</span><span class="sxs-lookup"><span data-stu-id="fcbeb-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="fcbeb-127">(去掉 "+")</span><span class="sxs-lookup"><span data-stu-id="fcbeb-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="fcbeb-128">+1</span><span class="sxs-lookup"><span data-stu-id="fcbeb-128">+1</span></span>  <br/> |<span data-ttu-id="fcbeb-129">正好 12 位</span><span class="sxs-lookup"><span data-stu-id="fcbeb-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="fcbeb-130">1</span><span class="sxs-lookup"><span data-stu-id="fcbeb-130">1</span></span>  <br/> |<span data-ttu-id="fcbeb-131">0</span><span class="sxs-lookup"><span data-stu-id="fcbeb-131">0</span></span>  <br/> |<span data-ttu-id="fcbeb-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="fcbeb-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="fcbeb-133">$1</span><span class="sxs-lookup"><span data-stu-id="fcbeb-133">$1</span></span>  <br/> |<span data-ttu-id="fcbeb-134">+14255551010 变为 14255551010</span><span class="sxs-lookup"><span data-stu-id="fcbeb-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="fcbeb-135">美国国际长途拨号</span><span class="sxs-lookup"><span data-stu-id="fcbeb-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="fcbeb-136">(去掉 "+" 并添加 011)</span><span class="sxs-lookup"><span data-stu-id="fcbeb-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="fcbeb-137">至少 11 位</span><span class="sxs-lookup"><span data-stu-id="fcbeb-137">At least 11</span></span>  <br/> |<span data-ttu-id="fcbeb-138">1</span><span class="sxs-lookup"><span data-stu-id="fcbeb-138">1</span></span>  <br/> |<span data-ttu-id="fcbeb-139">011</span><span class="sxs-lookup"><span data-stu-id="fcbeb-139">011</span></span>  <br/> |<span data-ttu-id="fcbeb-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="fcbeb-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="fcbeb-141">011$1</span><span class="sxs-lookup"><span data-stu-id="fcbeb-141">011$1</span></span>  <br/> |<span data-ttu-id="fcbeb-142">+441235551010 变为 011441235551010</span><span class="sxs-lookup"><span data-stu-id="fcbeb-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


