---
title: 在 Teams 中管理语音和呼叫策略
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347980"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="5a149-102">在 Microsoft Teams 中管理语音和呼叫策略</span><span class="sxs-lookup"><span data-stu-id="5a149-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="5a149-103">语音和呼叫策略用于控制 Microsoft Teams 中的语音和呼叫。</span><span class="sxs-lookup"><span data-stu-id="5a149-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="5a149-104">紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="5a149-104">Emergency calling policies</span></span>

<span data-ttu-id="5a149-105">使用 [紧急呼叫策略](manage-emergency-calling-policies.md) 来配置当组织中用户进行紧急呼叫时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="5a149-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="5a149-106">这些策略在 Teams 管理中心内管理，或者使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a149-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![紧急呼叫策略的屏幕截图。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="5a149-108">紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="5a149-108">Emergency call routing policies</span></span>

<span data-ttu-id="5a149-109">如果组织已部署电话系统直接 **路由**，可以使用紧急呼叫路由策略 [](manage-emergency-call-routing-policies.md)来确定紧急呼叫的路由位置、是否启用了增强的紧急服务，以及用于紧急服务的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5a149-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="5a149-110">这些策略使用 PowerShell 或 Microsoft Teams 管理中心进行管理。</span><span class="sxs-lookup"><span data-stu-id="5a149-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![紧急呼叫路由策略的屏幕截图。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="5a149-112">调用方 ID 策略</span><span class="sxs-lookup"><span data-stu-id="5a149-112">Caller ID policies</span></span>

<span data-ttu-id="5a149-113">[调用方 ID](caller-id-policies.md) 策略用于更改或阻止来电显示。</span><span class="sxs-lookup"><span data-stu-id="5a149-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![调用方 ID 策略的屏幕截图。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="5a149-115">语音路由策略</span><span class="sxs-lookup"><span data-stu-id="5a149-115">Voice routing policies</span></span>

<span data-ttu-id="5a149-116">语音 [路由策略](manage-voice-routing-policies.md) 是一个容器，用于公用电话交换网络 (PSTN) 使用情况记录。</span><span class="sxs-lookup"><span data-stu-id="5a149-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="5a149-117">如果组织已部署电话系统直接路由，可以使用 **这些策略**。</span><span class="sxs-lookup"><span data-stu-id="5a149-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="5a149-118">可以使用 PowerShell 或 Teams 管理中心管理语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="5a149-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![语音路由策略的屏幕截图。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="5a149-120">通话策略</span><span class="sxs-lookup"><span data-stu-id="5a149-120">Calling policies</span></span>

<span data-ttu-id="5a149-121">[呼叫策略](teams-calling-policy.md) 控制哪些呼叫和呼叫转发功能可供用户使用，包括用户是否可以进行私人呼叫、将呼叫发送到呼叫组以及将呼叫路由到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="5a149-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![调用策略的屏幕截图。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="5a149-123">呼叫停放和检索策略</span><span class="sxs-lookup"><span data-stu-id="5a149-123">Call park and retrieve policies</span></span>

<span data-ttu-id="5a149-124">[呼叫暂停和检索](call-park-and-retrieve.md) 允许用户将其他用户置于保持状态，使同一用户或其他人能够继续呼叫。</span><span class="sxs-lookup"><span data-stu-id="5a149-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![呼叫停放和检索策略的屏幕截图。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="5a149-126">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="5a149-126">Create and manage dial plans</span></span>

<span data-ttu-id="5a149-127">[拨号计划](create-and-manage-dial-plans.md) 转换拨入的电话号码，进行呼叫授权和路由。</span><span class="sxs-lookup"><span data-stu-id="5a149-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="5a149-128">可以通过 PowerShell 或 Microsoft Teams 管理中心创建和管理拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5a149-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![拨号计划的屏幕截图。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="5a149-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a149-130">Related topics</span></span>

* [<span data-ttu-id="5a149-131">在 Microsoft Teams 中管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="5a149-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="5a149-132">管理紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="5a149-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="5a149-133">在 Microsoft Teams 中管理来电显示策略</span><span class="sxs-lookup"><span data-stu-id="5a149-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="5a149-134">管理语音路由策略</span><span class="sxs-lookup"><span data-stu-id="5a149-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="5a149-135">Microsoft Teams 中的呼叫策略</span><span class="sxs-lookup"><span data-stu-id="5a149-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="5a149-136">Microsoft Teams 中的呼叫寄存和取回</span><span class="sxs-lookup"><span data-stu-id="5a149-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="5a149-137">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="5a149-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="5a149-138">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="5a149-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
