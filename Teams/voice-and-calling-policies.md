---
title: 管理语音和呼叫策略Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解Teams和呼叫策略。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460582"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="231a6-103">管理语音和呼叫策略Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="231a6-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="231a6-104">语音和呼叫策略用于控制语音和Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="231a6-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="231a6-105">紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="231a6-105">Emergency calling policies</span></span>

<span data-ttu-id="231a6-106">使用 [紧急呼叫策略](manage-emergency-calling-policies.md) 来配置当贵组织的用户进行紧急呼叫时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="231a6-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="231a6-107">这些策略在管理中心Teams管理，或者使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="231a6-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![紧急呼叫策略的屏幕截图。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="231a6-109">紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="231a6-109">Emergency call routing policies</span></span>

<span data-ttu-id="231a6-110">如果组织已部署 **电话系统** 路由，可以使用紧急呼叫路由策略来确定紧急呼叫 [](manage-emergency-call-routing-policies.md)的路由位置、是否启用了增强型紧急服务，以及用于紧急服务的电话号码。</span><span class="sxs-lookup"><span data-stu-id="231a6-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="231a6-111">这些策略使用 PowerShell 或管理中心Microsoft Teams管理。</span><span class="sxs-lookup"><span data-stu-id="231a6-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![紧急呼叫路由策略的屏幕截图。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="231a6-113">调用方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="231a6-113">Caller ID policies</span></span>

<span data-ttu-id="231a6-114">[来电显示](caller-id-policies.md) 策略用于更改或阻止来电显示。</span><span class="sxs-lookup"><span data-stu-id="231a6-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![调用方 ID 策略的屏幕截图。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="231a6-116">语音路由策略</span><span class="sxs-lookup"><span data-stu-id="231a6-116">Voice routing policies</span></span>

<span data-ttu-id="231a6-117">语音 [路由策略](manage-voice-routing-policies.md) 是 PSTN 公用电话交换网 (PSTN) 容器。</span><span class="sxs-lookup"><span data-stu-id="231a6-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="231a6-118">如果组织已部署直接路由 **，电话系统策略**。</span><span class="sxs-lookup"><span data-stu-id="231a6-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="231a6-119">语音路由策略可以使用 PowerShell 或 Teams管理中心进行管理。</span><span class="sxs-lookup"><span data-stu-id="231a6-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![语音路由策略的屏幕截图。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="231a6-121">通话策略</span><span class="sxs-lookup"><span data-stu-id="231a6-121">Calling policies</span></span>

<span data-ttu-id="231a6-122">[呼叫策略](teams-calling-policy.md) 控制哪些呼叫和呼叫转发功能可供用户使用，包括用户是否可以进行私人呼叫、向呼叫组发送呼叫以及将呼叫路由到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="231a6-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![调用策略的屏幕截图。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="231a6-124">呼叫停放和检索策略</span><span class="sxs-lookup"><span data-stu-id="231a6-124">Call park and retrieve policies</span></span>

<span data-ttu-id="231a6-125">[呼叫暂停和检索](call-park-and-retrieve.md) 允许用户将其他用户置于保持状态，使同一用户或其他人能够继续呼叫。</span><span class="sxs-lookup"><span data-stu-id="231a6-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![呼叫停放和检索策略的屏幕截图。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="231a6-127">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="231a6-127">Create and manage dial plans</span></span>

<span data-ttu-id="231a6-128">[拨号计划](create-and-manage-dial-plans.md) 转换拨入的电话号码进行呼叫授权和路由。</span><span class="sxs-lookup"><span data-stu-id="231a6-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="231a6-129">可以通过 PowerShell 或管理中心创建和管理Microsoft Teams套餐。</span><span class="sxs-lookup"><span data-stu-id="231a6-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![拨号计划的屏幕截图。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="231a6-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="231a6-131">Related topics</span></span>

* [<span data-ttu-id="231a6-132">管理紧急呼叫策略Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="231a6-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="231a6-133">管理紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="231a6-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="231a6-134">在 Microsoft Teams 中管理呼叫方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="231a6-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="231a6-135">管理语音路由策略</span><span class="sxs-lookup"><span data-stu-id="231a6-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="231a6-136">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="231a6-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="231a6-137">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="231a6-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="231a6-138">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="231a6-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="231a6-139">使用Teams管理策略</span><span class="sxs-lookup"><span data-stu-id="231a6-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
