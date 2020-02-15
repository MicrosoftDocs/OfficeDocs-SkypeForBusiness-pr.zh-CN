---
title: 在 Skype for Business 中规划远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync Server 控制其 PBX 电话。 在 Skype for Business Server 中，此功能已由通过工作的呼叫取代。 在 Skype for business Server 2015 的客户端版本中，远程呼叫控制不再可在客户端中进行配置，已将其删除以供使用。
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982797"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="6126c-105">在 Skype for Business 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="6126c-106">远程呼叫控制是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync Server 控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="6126c-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="6126c-107">在 Skype for Business Server 中，此功能已由通过工作的呼叫取代。</span><span class="sxs-lookup"><span data-stu-id="6126c-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="6126c-108">*在 Skype for business Server 2015 的客户端版本中，远程呼叫控制不再可在客户端中进行配置，已将其删除以供使用。*</span><span class="sxs-lookup"><span data-stu-id="6126c-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="6126c-109">远程呼叫控制组织中驻留在运行 Lync Server 的前端服务器上的用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端也是如此。</span><span class="sxs-lookup"><span data-stu-id="6126c-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="6126c-110">但是，对于驻留在 Skype for Business 服务器上的任何用户，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="6126c-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="6126c-111">请参阅下表了解服务器/客户端组合，以及它们是否可以支持远程呼叫控制或通过工作进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="6126c-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="6126c-112">**启用了 Skype UI 的 skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="6126c-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="6126c-113">**启用了 Lync UI 的 Skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="6126c-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="6126c-114">**Skype for Business 2016 客户端**</span><span class="sxs-lookup"><span data-stu-id="6126c-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="6126c-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="6126c-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="6126c-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="6126c-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6126c-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6126c-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="6126c-118">通过工作进行呼叫</span><span class="sxs-lookup"><span data-stu-id="6126c-118">Call via Work</span></span>  <br/> |<span data-ttu-id="6126c-119">1 </span><span class="sxs-lookup"><span data-stu-id="6126c-119">1</span></span> <br/> |<span data-ttu-id="6126c-120">通过工作进行呼叫</span><span class="sxs-lookup"><span data-stu-id="6126c-120">Call via Work</span></span>  <br/> |<span data-ttu-id="6126c-121">1 </span><span class="sxs-lookup"><span data-stu-id="6126c-121">1</span></span> <br/> |<span data-ttu-id="6126c-122">1 </span><span class="sxs-lookup"><span data-stu-id="6126c-122">1</span></span> <br/> |
| <span data-ttu-id="6126c-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6126c-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="6126c-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-126">1 </span><span class="sxs-lookup"><span data-stu-id="6126c-126">1</span></span> <br/> |<span data-ttu-id="6126c-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="6126c-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6126c-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="6126c-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-132">1 </span><span class="sxs-lookup"><span data-stu-id="6126c-132">1</span></span> <br/> |<span data-ttu-id="6126c-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="6126c-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="6126c-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="6126c-135">这两种功能都不受支持。</span><span class="sxs-lookup"><span data-stu-id="6126c-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="6126c-136">有关详细信息，请参阅 Lync Server 2013 文档中的[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。</span><span class="sxs-lookup"><span data-stu-id="6126c-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6126c-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6126c-137">See also</span></span>

[<span data-ttu-id="6126c-138">通过 Skype for Business Server 中的工作规划呼叫计划</span><span class="sxs-lookup"><span data-stu-id="6126c-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="6126c-139">Skype for business 的桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="6126c-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="6126c-140">发出 Skype for Business 呼叫，但使用你的 PBX 桌面电话进行音频</span><span class="sxs-lookup"><span data-stu-id="6126c-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

