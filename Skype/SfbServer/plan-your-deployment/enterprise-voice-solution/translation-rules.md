---
title: Skype 业务服务器中的转换规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解转换规则，并拨号字符串规范化 Skype 中的业务 Server 企业语音。
ms.openlocfilehash: 4ef5f92b8c5ef91abeb5ce2b6ea1e4c0eebe7580
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973184"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="a423a-103">Skype 业务服务器中的转换规则</span><span class="sxs-lookup"><span data-stu-id="a423a-103">Translation rules in Skype for Business Server</span></span>
 
<span data-ttu-id="a423a-104">了解转换规则，并拨号字符串规范化 Skype 中的业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="a423a-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>
  
 <span data-ttu-id="a423a-105">企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。</span><span class="sxs-lookup"><span data-stu-id="a423a-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a423a-106">支持呼叫的号码以及呼叫的号码转换规则。</span><span class="sxs-lookup"><span data-stu-id="a423a-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="a423a-107">Thetrunk 对等方 （即，关联的网关、 专用交换机 (PBX) 或 SIP 中继） 可能要求号码都本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="a423a-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="a423a-108">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="a423a-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="a423a-109">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="a423a-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
<span data-ttu-id="a423a-110">通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="a423a-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="a423a-111">规划的网关和多少网关与特定的中介服务器群集，相关联时可能有用组中继对等方具有类似本地拨号要求。</span><span class="sxs-lookup"><span data-stu-id="a423a-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="a423a-112">这可减少所需的转换规则数和编写转换规则所需的时间。</span><span class="sxs-lookup"><span data-stu-id="a423a-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a423a-113">将一个或多个转换规则与企业语音中继配置相关联应用作中继对等方上配置转换规则的替代项。</span><span class="sxs-lookup"><span data-stu-id="a423a-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="a423a-114">不关联转换规则与企业语音中继配置如果中继对等方上, 配置了转换规则因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="a423a-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span> 
  
## <a name="example-translation-rules"></a><span data-ttu-id="a423a-115">示例转换规则</span><span class="sxs-lookup"><span data-stu-id="a423a-115">Example Translation Rules</span></span>

<span data-ttu-id="a423a-116">以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。</span><span class="sxs-lookup"><span data-stu-id="a423a-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>
  
<span data-ttu-id="a423a-117">有关如何实施转换规则的详细信息，请参阅部署文档中的[Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="a423a-117">For details about how to implement translation rules, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
  
|<span data-ttu-id="a423a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="a423a-118">**Description**</span></span>|<span data-ttu-id="a423a-119">**起始数字**</span><span class="sxs-lookup"><span data-stu-id="a423a-119">**Starting Digits**</span></span>|<span data-ttu-id="a423a-120">**长度**</span><span class="sxs-lookup"><span data-stu-id="a423a-120">**Length**</span></span>|<span data-ttu-id="a423a-121">**要删除的数字**</span><span class="sxs-lookup"><span data-stu-id="a423a-121">**Digits to Remove**</span></span>|<span data-ttu-id="a423a-122">**要添加的数字**</span><span class="sxs-lookup"><span data-stu-id="a423a-122">**Digits to Add**</span></span>|<span data-ttu-id="a423a-123">**匹配模式**</span><span class="sxs-lookup"><span data-stu-id="a423a-123">**Matching Pattern**</span></span>|<span data-ttu-id="a423a-124">**转换**</span><span class="sxs-lookup"><span data-stu-id="a423a-124">**Translation**</span></span>|<span data-ttu-id="a423a-125">**示例**</span><span class="sxs-lookup"><span data-stu-id="a423a-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a423a-126">美国常规长途拨号</span><span class="sxs-lookup"><span data-stu-id="a423a-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="a423a-127">(去掉 +)</span><span class="sxs-lookup"><span data-stu-id="a423a-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="a423a-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="a423a-128">+1</span></span>  <br/> |<span data-ttu-id="a423a-129">正好 12 位</span><span class="sxs-lookup"><span data-stu-id="a423a-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="a423a-130">1</span><span class="sxs-lookup"><span data-stu-id="a423a-130">1</span></span>  <br/> |<span data-ttu-id="a423a-131">0</span><span class="sxs-lookup"><span data-stu-id="a423a-131">0</span></span>  <br/> |<span data-ttu-id="a423a-132">^\+(1\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a423a-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="a423a-133">$1</span><span class="sxs-lookup"><span data-stu-id="a423a-133">$1</span></span>  <br/> |<span data-ttu-id="a423a-134">+14255551010 变为 14255551010</span><span class="sxs-lookup"><span data-stu-id="a423a-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="a423a-135">美国国际长途拨号</span><span class="sxs-lookup"><span data-stu-id="a423a-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="a423a-136">(去掉 + 并添加 011)</span><span class="sxs-lookup"><span data-stu-id="a423a-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="a423a-137">至少 11 位</span><span class="sxs-lookup"><span data-stu-id="a423a-137">At least 11</span></span>  <br/> |<span data-ttu-id="a423a-138">1</span><span class="sxs-lookup"><span data-stu-id="a423a-138">1</span></span>  <br/> |<span data-ttu-id="a423a-139">011</span><span class="sxs-lookup"><span data-stu-id="a423a-139">011</span></span>  <br/> |<span data-ttu-id="a423a-140">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="a423a-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="a423a-141">011$1</span><span class="sxs-lookup"><span data-stu-id="a423a-141">011$1</span></span>  <br/> |<span data-ttu-id="a423a-142">+441235551010 变为 011441235551010</span><span class="sxs-lookup"><span data-stu-id="a423a-142">+441235551010 becomes 011441235551010</span></span>  <br/> |
   

