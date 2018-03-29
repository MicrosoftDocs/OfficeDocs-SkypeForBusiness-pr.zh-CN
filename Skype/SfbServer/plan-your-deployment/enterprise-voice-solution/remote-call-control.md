---
title: 在 Skype for Business 2015 中规划远程呼叫控制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制已启用用户控制手机 PBX Lync Server Lync 服务器的早期版本中的功能。 在 Skype 业务服务器，此功能已被调用通过工作。 在 Skype 业务服务器 2015年和不断向前的远程调用的客户端版本控制不再可用于在客户端配置和使用已删除。
ms.openlocfilehash: 2db859ad33a697d5bca632ca9b6677a3a67bd103
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="47f78-105">在 Skype for Business 2015 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="47f78-106">远程呼叫控制已启用用户控制手机 PBX Lync Server Lync 服务器的早期版本中的功能。</span><span class="sxs-lookup"><span data-stu-id="47f78-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="47f78-107">在 Skype 业务服务器，此功能已被调用通过工作。</span><span class="sxs-lookup"><span data-stu-id="47f78-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="47f78-108">*在 Skype 业务服务器 2015年和不断向前的远程调用的客户端版本控制不再可用于在客户端配置和使用已删除。*</span><span class="sxs-lookup"><span data-stu-id="47f78-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="47f78-109">驻留在前端服务器运行 Lync 服务器的远程调用控制用户在您的组织可以继续使用远程呼叫控制，即使他们的业务客户端使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="47f78-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="47f78-110">但是，对于任何用户驻留在 Skype 上的业务服务器，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="47f78-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="47f78-111">有关服务器/客户端组合以及它们是否可以支持远程呼叫控制或通过工号拨号，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="47f78-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="47f78-112">**Skype 业务 2015年客户端 With Skype ui 启用**</span><span class="sxs-lookup"><span data-stu-id="47f78-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="47f78-113">**Skype 业务 2015年客户端 With Lync ui 启用**</span><span class="sxs-lookup"><span data-stu-id="47f78-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="47f78-114">**Skype 业务 2016年客户端**</span><span class="sxs-lookup"><span data-stu-id="47f78-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="47f78-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="47f78-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="47f78-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="47f78-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="47f78-117">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="47f78-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="47f78-118">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="47f78-118">Call via Work</span></span>  <br/> |<span data-ttu-id="47f78-119">1</span><span class="sxs-lookup"><span data-stu-id="47f78-119">1</span></span> <br/> |<span data-ttu-id="47f78-120">通过工号拨号</span><span class="sxs-lookup"><span data-stu-id="47f78-120">Call via Work</span></span>  <br/> |<span data-ttu-id="47f78-121">1</span><span class="sxs-lookup"><span data-stu-id="47f78-121">1</span></span> <br/> |<span data-ttu-id="47f78-122">1</span><span class="sxs-lookup"><span data-stu-id="47f78-122">1</span></span> <br/> |
| <span data-ttu-id="47f78-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47f78-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="47f78-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-126">1</span><span class="sxs-lookup"><span data-stu-id="47f78-126">1</span></span> <br/> |<span data-ttu-id="47f78-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="47f78-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="47f78-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="47f78-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-132">1</span><span class="sxs-lookup"><span data-stu-id="47f78-132">1</span></span> <br/> |<span data-ttu-id="47f78-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="47f78-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="47f78-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="47f78-135">支持两种功能。</span><span class="sxs-lookup"><span data-stu-id="47f78-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="47f78-136">有关详细信息，请参阅 Lync Server 2013 文档中的[远程调用控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。</span><span class="sxs-lookup"><span data-stu-id="47f78-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47f78-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47f78-137">See also</span></span>

#### 

[<span data-ttu-id="47f78-138">规划工作在 Skype 业务服务器 2015年通过调用</span><span class="sxs-lookup"><span data-stu-id="47f78-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="47f78-139">Skype 业务为桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="47f78-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="47f78-140">使业务呼叫 Skype 但使用 PBX 的桌面电话的录音</span><span class="sxs-lookup"><span data-stu-id="47f78-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

