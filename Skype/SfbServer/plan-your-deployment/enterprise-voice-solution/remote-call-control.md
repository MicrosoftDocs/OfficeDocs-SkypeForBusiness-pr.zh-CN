---
title: 在 Skype for Business 中规划远程呼叫控制
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
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制其 PBX 电话。 在 Skype for Business Server 中，此功能已替换为通过工位呼叫功能。 在 Skype for Business Server 2015 的客户端版本中以及今后，远程呼叫控制不再可用于在客户端中配置，并且已删除供其使用。
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114608"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="63f1d-105">在 Skype for Business 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="63f1d-106">远程呼叫控制是 Lync Server 早期版本中的一项功能，它使用户能够使用 Lync Server 控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="63f1d-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="63f1d-107">在 Skype for Business Server 中，此功能已替换为通过工位呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="63f1d-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="63f1d-108">*在 Skype for Business Server 2015 的客户端版本中以及今后，远程呼叫控制不再可用于在客户端中配置，并且已删除供其使用。*</span><span class="sxs-lookup"><span data-stu-id="63f1d-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="63f1d-109">组织中位于运行 Lync Server 的前端服务器上远程呼叫控制用户可以继续使用远程呼叫控制，即使他们使用的是 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="63f1d-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="63f1d-110">但是，对于位于 Skype for Business Server 上的任何用户，不支持远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="63f1d-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="63f1d-111">有关服务器/客户端组合及其是否可以支持远程呼叫控制或通过工位呼叫的信息，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="63f1d-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="63f1d-112">**启用 Skype UI 的 Skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="63f1d-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="63f1d-113">**启用 Lync UI 的 Skype for Business 客户端**</span><span class="sxs-lookup"><span data-stu-id="63f1d-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="63f1d-114">**Skype for Business 2016 客户端**</span><span class="sxs-lookup"><span data-stu-id="63f1d-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="63f1d-115">**Lync 2013 客户端**</span><span class="sxs-lookup"><span data-stu-id="63f1d-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="63f1d-116">**Lync 2010 客户端**</span><span class="sxs-lookup"><span data-stu-id="63f1d-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="63f1d-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="63f1d-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="63f1d-118">通过工作电话呼叫</span><span class="sxs-lookup"><span data-stu-id="63f1d-118">Call via Work</span></span>  <br/> |<span data-ttu-id="63f1d-119">1</span><span class="sxs-lookup"><span data-stu-id="63f1d-119">1</span></span> <br/> |<span data-ttu-id="63f1d-120">通过工作电话呼叫</span><span class="sxs-lookup"><span data-stu-id="63f1d-120">Call via Work</span></span>  <br/> |<span data-ttu-id="63f1d-121">1</span><span class="sxs-lookup"><span data-stu-id="63f1d-121">1</span></span> <br/> |<span data-ttu-id="63f1d-122">1</span><span class="sxs-lookup"><span data-stu-id="63f1d-122">1</span></span> <br/> |
| <span data-ttu-id="63f1d-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63f1d-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="63f1d-124">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-125">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-126">1</span><span class="sxs-lookup"><span data-stu-id="63f1d-126">1</span></span> <br/> |<span data-ttu-id="63f1d-127">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-128">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="63f1d-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="63f1d-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="63f1d-130">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-131">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-132">1</span><span class="sxs-lookup"><span data-stu-id="63f1d-132">1</span></span> <br/> |<span data-ttu-id="63f1d-133">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="63f1d-134">远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="63f1d-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="63f1d-135">这两种功能都不受支持。</span><span class="sxs-lookup"><span data-stu-id="63f1d-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="63f1d-136">有关详细信息，请参阅 Lync Server 2013 文档中的 Remote [Call Control。](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control)</span><span class="sxs-lookup"><span data-stu-id="63f1d-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63f1d-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63f1d-137">See also</span></span>

[<span data-ttu-id="63f1d-138">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="63f1d-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="63f1d-139">Skype for Business 的桌面客户端功能比较</span><span class="sxs-lookup"><span data-stu-id="63f1d-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="63f1d-140">拨打 Skype for Business 电话，但将 PBX 桌面电话用于音频</span><span class="sxs-lookup"><span data-stu-id="63f1d-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)