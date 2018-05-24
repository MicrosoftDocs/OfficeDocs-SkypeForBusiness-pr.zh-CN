---
title: 在 Skype for Business 2015 中规划远程呼叫控制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。 中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。
ms.openlocfilehash: e3a8031a79d547a279b377a45e1e8461cd47a2e7
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="f0a6d-105">在 Skype for Business 2015 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="f0a6d-106">远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="f0a6d-107">在业务服务器 Skype，此功能已取代与通过单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="f0a6d-108">*中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。*</span><span class="sxs-lookup"><span data-stu-id="f0a6d-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="f0a6d-109">远程呼叫控制组织中的用户驻留在前端服务器运行 Lync Server 上可以继续使用远程呼叫控制，即使它们使用 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="f0a6d-110">但是，业务服务器位于 Skype 上的任何用户，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="f0a6d-111">有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="f0a6d-112">**启用业务 2015年客户端 With Skype UI 的 Skype**</span><span class="sxs-lookup"><span data-stu-id="f0a6d-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="f0a6d-113">**启用业务 2015年客户端 With Lync UI 的 Skype**</span><span class="sxs-lookup"><span data-stu-id="f0a6d-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="f0a6d-114">**Skype 业务 2016年客户端**</span><span class="sxs-lookup"><span data-stu-id="f0a6d-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="f0a6d-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="f0a6d-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="f0a6d-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="f0a6d-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f0a6d-117">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f0a6d-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="f0a6d-118">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="f0a6d-118">Call via Work</span></span>  <br/> |<span data-ttu-id="f0a6d-119">1</span><span class="sxs-lookup"><span data-stu-id="f0a6d-119">1</span></span> <br/> |<span data-ttu-id="f0a6d-120">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="f0a6d-120">Call via Work</span></span>  <br/> |<span data-ttu-id="f0a6d-121">1</span><span class="sxs-lookup"><span data-stu-id="f0a6d-121">1</span></span> <br/> |<span data-ttu-id="f0a6d-122">1</span><span class="sxs-lookup"><span data-stu-id="f0a6d-122">1</span></span> <br/> |
| <span data-ttu-id="f0a6d-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a6d-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="f0a6d-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-126">1</span><span class="sxs-lookup"><span data-stu-id="f0a6d-126">1</span></span> <br/> |<span data-ttu-id="f0a6d-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="f0a6d-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0a6d-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="f0a6d-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-132">1</span><span class="sxs-lookup"><span data-stu-id="f0a6d-132">1</span></span> <br/> |<span data-ttu-id="f0a6d-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f0a6d-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="f0a6d-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="f0a6d-135">支持既功能。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="f0a6d-136">有关详细信息，请参阅 Lync Server 2013 文档中的[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。</span><span class="sxs-lookup"><span data-stu-id="f0a6d-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0a6d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a6d-137">See also</span></span>

#### 

[<span data-ttu-id="f0a6d-138">规划用单位电话的 Skype 业务服务器 2015年呼叫</span><span class="sxs-lookup"><span data-stu-id="f0a6d-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="f0a6d-139">Skype for Business 的桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="f0a6d-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="f0a6d-140">使业务呼叫 Skype，但使用 PBX 桌面电话音频</span><span class="sxs-lookup"><span data-stu-id="f0a6d-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

