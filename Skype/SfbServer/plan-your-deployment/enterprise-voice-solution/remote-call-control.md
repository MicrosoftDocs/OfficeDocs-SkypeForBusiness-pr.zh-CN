---
title: Plan for Business 的 Skype 中的远程呼叫控制
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。 在业务服务器 Skype，此功能已取代与通过单位电话呼叫。 中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。
ms.openlocfilehash: 31ee089e5f4142a0db728878d2bd35d86b628804
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879043"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="b635a-105">Plan for Business 的 Skype 中的远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="b635a-106">远程呼叫控制时在早期版本的 Lync Server 启用用户控制其 PBX 电话与 Lync Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="b635a-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="b635a-107">在业务服务器 Skype，此功能已取代与通过单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="b635a-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="b635a-108">*中的客户端版本的 Skype 业务服务器 2015年和转转接、 远程呼叫控件不再是可用于配置在客户端，并使用已删除。*</span><span class="sxs-lookup"><span data-stu-id="b635a-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="b635a-109">远程呼叫控制组织中的用户驻留在前端服务器运行 Lync Server 上可以继续使用远程呼叫控制，即使它们使用 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="b635a-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="b635a-110">但是，业务服务器位于 Skype 上的任何用户，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="b635a-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="b635a-111">有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b635a-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="b635a-112">**业务客户端与 Skype UI 启用的 Skype**</span><span class="sxs-lookup"><span data-stu-id="b635a-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="b635a-113">**业务客户端与 Lync UI 启用的 Skype**</span><span class="sxs-lookup"><span data-stu-id="b635a-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="b635a-114">**Skype 业务 2016年客户端**</span><span class="sxs-lookup"><span data-stu-id="b635a-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="b635a-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="b635a-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="b635a-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="b635a-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b635a-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b635a-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="b635a-118">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="b635a-118">Call via Work</span></span>  <br/> |<span data-ttu-id="b635a-119">1</span><span class="sxs-lookup"><span data-stu-id="b635a-119">1</span></span> <br/> |<span data-ttu-id="b635a-120">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="b635a-120">Call via Work</span></span>  <br/> |<span data-ttu-id="b635a-121">1</span><span class="sxs-lookup"><span data-stu-id="b635a-121">1</span></span> <br/> |<span data-ttu-id="b635a-122">1</span><span class="sxs-lookup"><span data-stu-id="b635a-122">1</span></span> <br/> |
| <span data-ttu-id="b635a-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b635a-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="b635a-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-126">1</span><span class="sxs-lookup"><span data-stu-id="b635a-126">1</span></span> <br/> |<span data-ttu-id="b635a-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="b635a-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b635a-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="b635a-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-132">1</span><span class="sxs-lookup"><span data-stu-id="b635a-132">1</span></span> <br/> |<span data-ttu-id="b635a-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b635a-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="b635a-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="b635a-135">支持既功能。</span><span class="sxs-lookup"><span data-stu-id="b635a-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="b635a-136">有关详细信息，请参阅 Lync Server 2013 文档中的[远程呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。</span><span class="sxs-lookup"><span data-stu-id="b635a-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b635a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b635a-137">See also</span></span>

[<span data-ttu-id="b635a-138">规划用单位电话的 Skype 业务服务器的呼叫</span><span class="sxs-lookup"><span data-stu-id="b635a-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="b635a-139">Skype for Business 的桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="b635a-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="b635a-140">使业务呼叫 Skype，但使用 PBX 桌面电话音频</span><span class="sxs-lookup"><span data-stu-id="b635a-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

