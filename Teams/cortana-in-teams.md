---
title: Microsoft 团队中的 Cortana 语音助手
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何将 Cortana 语音助手与团队一起使用
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522310"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="23f00-103">团队中的 Cortana 语音帮助</span><span class="sxs-lookup"><span data-stu-id="23f00-103">Cortana voice assistance in Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> <span data-ttu-id="23f00-104">仅适用于美国用户的 Microsoft 团队 iOS 和 Android 移动应用支持 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="23f00-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="23f00-105">目前尚不支持 GCC、GCC-高、DoD、教育机构租户。</span><span class="sxs-lookup"><span data-stu-id="23f00-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="23f00-106">其他语言和区域的扩展将在将来的版本中发生。</span><span class="sxs-lookup"><span data-stu-id="23f00-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="23f00-107">团队移动应用中的 Cortana 语音帮助使 Microsoft 365 企业用户能够使用语音自然语言优化通信、协作和会议相关任务。</span><span class="sxs-lookup"><span data-stu-id="23f00-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="23f00-108">用户可以通过单击位于团队移动应用右上角的麦克风按钮来向 Cortana 讲话。</span><span class="sxs-lookup"><span data-stu-id="23f00-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="23f00-109">若要在旅途中快速联系他们的团队，用户可以说出诸如 "呼叫 Megan" 或 "向我的下一会议发送一条消息" 之类的查询。</span><span class="sxs-lookup"><span data-stu-id="23f00-109">To quickly connect with their team while on the go, users can say queries such as “call Megan” or “send a message to my next meeting.”</span></span> <span data-ttu-id="23f00-110">用户还可以通过说 "加入我的下一个会议" 来加入会议，并使用语音协助共享文件、检查其日历等。</span><span class="sxs-lookup"><span data-stu-id="23f00-110">Users can also join meetings by saying “join my next meeting” and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="23f00-111">这些语音帮助体验是使用[Cortana 企业级服务](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)提供的，这些服务完全遵守 Office 365 的隐私、安全性和合规性承诺，这些服务反映在[在线服务条款（OST）](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。</span><span class="sxs-lookup"><span data-stu-id="23f00-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="23f00-112">图像显示在移动设备上的 Cortana 中发送聊天。</span><span class="sxs-lookup"><span data-stu-id="23f00-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![图像显示一系列显示 Cortana 聊天会话的移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="23f00-114">管理员控制和限制</span><span class="sxs-lookup"><span data-stu-id="23f00-114">Admin control and Limitations</span></span>

<span data-ttu-id="23f00-115">团队中的 Cortana 语音帮助已使用完全遵守 Office 365 企业级隐私、安全性和合规性承诺的服务提供，并反映在在线服务条款（OST）中。</span><span class="sxs-lookup"><span data-stu-id="23f00-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="23f00-116">默认情况下，将为租户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="23f00-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="23f00-117">租户管理员可以控制租户中的哪些用户可以使用策略（TeamsCortanaPolicy）在团队中使用 Cortana 语音协助。</span><span class="sxs-lookup"><span data-stu-id="23f00-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="23f00-118">可以在用户帐户级别或租户级别设置此策略。</span><span class="sxs-lookup"><span data-stu-id="23f00-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="23f00-119">管理员可以使用此策略控制中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是否已禁用、是否仅使用压入按钮调用，或者是否同时使用唤醒字词调用（适用于支持它的设备）。</span><span class="sxs-lookup"><span data-stu-id="23f00-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="23f00-120">管理员可以使用以下 PowerShell cmdlet 管理此策略（该策略当前在 Microsoft 团队管理中心中不可用）。</span><span class="sxs-lookup"><span data-stu-id="23f00-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="23f00-121">新-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="23f00-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="23f00-122">CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="23f00-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="23f00-123">授权-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="23f00-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="23f00-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="23f00-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="23f00-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="23f00-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="23f00-126">例如，下面的命令将创建一个名为 "EmployeeCortanaPolicy" 的新策略，其中 Microsoft 团队中的 Cortana 语音助手处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="23f00-126">For example, the command below creates a new policy with name "EmployeeCortanaPolicy" where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="23f00-127">此示例显示了如何更新名称为 "EmployeeCortanaPolicy" 的现有策略，并仅使用 push 按钮调用在 Microsoft 团队中启用 Cortana 语音助手。</span><span class="sxs-lookup"><span data-stu-id="23f00-127">This example shows updating an existing policy with name "EmployeeCortanaPolicy" and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="23f00-128">用户将能够通过点击团队中的 Cortana 麦克风按钮来调用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="23f00-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="23f00-129">唤醒 word （"你好小娜"）调用将被禁用。</span><span class="sxs-lookup"><span data-stu-id="23f00-129">Wake word ("Hey Cortana”) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="23f00-130">此示例演示了如何更新策略以及如何同时启用 "压入" 按钮和唤醒单词调用的 Cortana 语音助手。</span><span class="sxs-lookup"><span data-stu-id="23f00-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="23f00-131">在 Microsoft 365 企业用户首次发布英语版时，团队移动应用将不支持唤醒 word 激活，但将来会受到支持。</span><span class="sxs-lookup"><span data-stu-id="23f00-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="23f00-132">用户控件</span><span class="sxs-lookup"><span data-stu-id="23f00-132">User control</span></span>

<span data-ttu-id="23f00-133">通过单击 "麦克风" 按钮，单个用户可以在 "团队移动应用" 中试用 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="23f00-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="23f00-134">他们还可以控制是否使用团队移动应用中的设置为其设备启用了团体中的 Cortana。</span><span class="sxs-lookup"><span data-stu-id="23f00-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="23f00-135">打开 "团队移动应用"。</span><span class="sxs-lookup"><span data-stu-id="23f00-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="23f00-136">转到 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="23f00-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="23f00-137">选择 " **Cortana**"。</span><span class="sxs-lookup"><span data-stu-id="23f00-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="23f00-138">将开关移动到 **"打开**" 或 "**关闭**"，具体取决于你是否希望在设备上进行 Cortana 语音协助。</span><span class="sxs-lookup"><span data-stu-id="23f00-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>