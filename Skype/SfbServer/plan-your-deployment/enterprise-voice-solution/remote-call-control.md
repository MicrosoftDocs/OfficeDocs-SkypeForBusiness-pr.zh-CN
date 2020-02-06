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
description: "\"远程呼叫控制\" 是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync 服务器控制其 PBX 电话。 在 Skype for Business 服务器中，此功能已替换为 \"通过工作通话\"。 在 Skype for business Server 2015 的客户端版本和未来版本中，客户端中的远程呼叫控制不再可用，已被删除以供使用。"
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802502"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="e19ab-105">在 Skype for Business 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="e19ab-106">"远程呼叫控制" 是以前版本的 Lync Server 中的一项功能，允许用户使用 Lync 服务器控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="e19ab-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="e19ab-107">在 Skype for Business 服务器中，此功能已替换为 "通过工作通话"。</span><span class="sxs-lookup"><span data-stu-id="e19ab-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="e19ab-108">*在 Skype for business Server 2015 的客户端版本和未来版本中，客户端中的远程呼叫控制不再可用，已被删除以供使用。*</span><span class="sxs-lookup"><span data-stu-id="e19ab-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="e19ab-109">远程呼叫控制组织中托管的前端服务器上托管的用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端也是如此。</span><span class="sxs-lookup"><span data-stu-id="e19ab-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="e19ab-110">但是，对于驻留在 Skype for business 服务器上的任何用户，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="e19ab-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="e19ab-111">有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e19ab-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="e19ab-112">**启用 Skype UI 的 skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="e19ab-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="e19ab-113">**启用了 Lync UI 的 Skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="e19ab-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="e19ab-114">**Skype for Business 2016 客户端**</span><span class="sxs-lookup"><span data-stu-id="e19ab-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="e19ab-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="e19ab-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="e19ab-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="e19ab-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e19ab-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e19ab-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="e19ab-118">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="e19ab-118">Call via Work</span></span>  <br/> |<span data-ttu-id="e19ab-119">1</span><span class="sxs-lookup"><span data-stu-id="e19ab-119">1</span></span> <br/> |<span data-ttu-id="e19ab-120">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="e19ab-120">Call via Work</span></span>  <br/> |<span data-ttu-id="e19ab-121">1</span><span class="sxs-lookup"><span data-stu-id="e19ab-121">1</span></span> <br/> |<span data-ttu-id="e19ab-122">1</span><span class="sxs-lookup"><span data-stu-id="e19ab-122">1</span></span> <br/> |
| <span data-ttu-id="e19ab-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e19ab-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="e19ab-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-126">raid-1</span><span class="sxs-lookup"><span data-stu-id="e19ab-126">1</span></span> <br/> |<span data-ttu-id="e19ab-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="e19ab-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e19ab-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="e19ab-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-132">raid-1</span><span class="sxs-lookup"><span data-stu-id="e19ab-132">1</span></span> <br/> |<span data-ttu-id="e19ab-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="e19ab-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e19ab-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="e19ab-135">这两个功能都不受支持。</span><span class="sxs-lookup"><span data-stu-id="e19ab-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="e19ab-136">有关详细信息，请参阅 Lync Server 2013 文档中的 "[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)"。</span><span class="sxs-lookup"><span data-stu-id="e19ab-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e19ab-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e19ab-137">See also</span></span>

[<span data-ttu-id="e19ab-138">通过 Skype for Business Server 中的工作计划呼叫计划</span><span class="sxs-lookup"><span data-stu-id="e19ab-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="e19ab-139">Skype for business 的桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="e19ab-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="e19ab-140">进行 Skype for Business 呼叫，但使用 PBX 桌面电话进行音频</span><span class="sxs-lookup"><span data-stu-id="e19ab-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

