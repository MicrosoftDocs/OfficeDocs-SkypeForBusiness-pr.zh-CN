---
title: Microsoft 团队中的 Cortana 语音帮助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何对团队使用 Cortana 语音帮助
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785386"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="e04e1-103">团队中的 Cortana 语音帮助</span><span class="sxs-lookup"><span data-stu-id="e04e1-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="e04e1-104">Microsoft 团队 iOS 和 Android 移动应用中支持 Cortana 语音帮助，并且仅针对美国用户显示了 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="e04e1-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="e04e1-105">目前尚不支持 GCC、GCC-高、DoD、教育机构租户。</span><span class="sxs-lookup"><span data-stu-id="e04e1-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="e04e1-106">其他语言和区域的扩展将在将来的版本中发生。</span><span class="sxs-lookup"><span data-stu-id="e04e1-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="e04e1-107">在团队移动应用和 Microsoft 团队显示设备上的 Cortana 语音帮助使 Microsoft 365 企业用户能够使用语音自然语言优化通信、协作和会议相关任务。</span><span class="sxs-lookup"><span data-stu-id="e04e1-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="e04e1-108">用户可以通过选择位于团队移动应用右上角的麦克风按钮来对 Cortana 讲话，或者说 Microsoft 团队显示 &#8220;Cortana&#8221;。</span><span class="sxs-lookup"><span data-stu-id="e04e1-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="e04e1-109">若要快速随时随地与团队成员联系，用户可以说出诸如 &#8220;呼叫 Megan 之类的查询&#8221; 或 &#8220;向我的下一个会议&#8221; 发送消息。</span><span class="sxs-lookup"><span data-stu-id="e04e1-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="e04e1-110">用户还可以通过说 &#8220;加入我的下一个会议&#8221; 并使用 "语音帮助" 共享文件、检查其日历等，从而加入会议。</span><span class="sxs-lookup"><span data-stu-id="e04e1-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="e04e1-111">这些语音帮助体验是使用 [Cortana 企业级服务](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供的，这些服务完全遵守 Office 365 的隐私、安全性和合规性承诺反映在 [在线服务条款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。</span><span class="sxs-lookup"><span data-stu-id="e04e1-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="e04e1-112">图像显示在移动设备上使用 Cortana 发送聊天。</span><span class="sxs-lookup"><span data-stu-id="e04e1-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![图像显示一系列显示 Cortana 聊天会话的移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="e04e1-114">管理员控制和限制</span><span class="sxs-lookup"><span data-stu-id="e04e1-114">Admin control and limitations</span></span>

<span data-ttu-id="e04e1-115">团队中的 Cortana 语音帮助已使用完全遵守 Office 365 企业级隐私、安全性和合规性的服务提供，这些服务反映在在线服务条款 (OST) 中。</span><span class="sxs-lookup"><span data-stu-id="e04e1-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="e04e1-116">默认情况下，将为租户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="e04e1-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="e04e1-117">租户管理员可以控制租户中的哪些人可以使用策略 (TeamsCortanaPolicy) 在团队中使用 Cortana 语音协助。</span><span class="sxs-lookup"><span data-stu-id="e04e1-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="e04e1-118">可以在用户帐户级别或租户级别设置此策略。</span><span class="sxs-lookup"><span data-stu-id="e04e1-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="e04e1-119">管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是否已禁用、是否仅使用压入按钮调用，或者是否与支持它的设备（如 Microsoft 团队显示) ） (一起启用。</span><span class="sxs-lookup"><span data-stu-id="e04e1-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="e04e1-120">管理员可以使用以下 PowerShell cmdlet 管理此策略 (该策略当前在 Microsoft 团队管理中心) 中不可用。</span><span class="sxs-lookup"><span data-stu-id="e04e1-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="e04e1-121">新-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e04e1-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e04e1-122">CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e04e1-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e04e1-123">授权-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e04e1-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e04e1-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e04e1-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="e04e1-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="e04e1-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="e04e1-126">例如，下面的命令将创建一个名为 &#8220;EmployeeCortanaPolicy&#8221; 的新策略，其中 Microsoft 团队中的 Cortana 语音帮助已禁用。</span><span class="sxs-lookup"><span data-stu-id="e04e1-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="e04e1-127">此示例显示了使用名称 &#8220;EmployeeCortanaPolicy&#8221; 更新现有策略，并仅使用 push 按钮调用在 Microsoft 团队中启用 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="e04e1-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="e04e1-128">用户将能够通过选择团队中的 Cortana 麦克风按钮来调用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="e04e1-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="e04e1-129">唤醒 word ( # B0&#8221; 或 &#8220;Cortana&#8221;) 调用将被禁用。</span><span class="sxs-lookup"><span data-stu-id="e04e1-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="e04e1-130">此示例演示了如何更新策略并启用了带压按钮和唤醒单词调用的 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="e04e1-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="e04e1-131">在 Microsoft 365 企业用户首次发布英语版时，团队移动应用将不支持唤醒 word 激活，但将来会受到支持。</span><span class="sxs-lookup"><span data-stu-id="e04e1-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="e04e1-132">唤醒 word 激活功能将在最初版本的 Microsoft 团队显示设备上运行。</span><span class="sxs-lookup"><span data-stu-id="e04e1-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="e04e1-133">用户控件</span><span class="sxs-lookup"><span data-stu-id="e04e1-133">User control</span></span>

<span data-ttu-id="e04e1-134">通过选择 "麦克风" 按钮，单个用户可以在 "团队移动应用" 中试用 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="e04e1-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="e04e1-135">他们可以通过简单地说 &#8220;Cortana，在 Microsoft 团队显示设备上试用 Cortana 语音帮助。 &#8221; 他们还可以控制是否使用团队移动应用或 Microsoft 团队显示中的设置为其设备启用团体中的 Cortana。</span><span class="sxs-lookup"><span data-stu-id="e04e1-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="e04e1-136">打开 "团队移动应用"，或转到 Microsoft 团队显示的 "环境 (主页) 屏幕。</span><span class="sxs-lookup"><span data-stu-id="e04e1-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="e04e1-137">在 "团队移动应用" 中，转到 " **设置** "。</span><span class="sxs-lookup"><span data-stu-id="e04e1-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="e04e1-138">在 "Microsoft 团队显示" 中，选择 "用户头像"，然后选择 "设置"。</span><span class="sxs-lookup"><span data-stu-id="e04e1-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="e04e1-139">如果启用了 Cortana，则 &#8220;Cortana，请转到 "设置"。 &#8221;</span><span class="sxs-lookup"><span data-stu-id="e04e1-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="e04e1-140">选择 " **Cortana** "。</span><span class="sxs-lookup"><span data-stu-id="e04e1-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="e04e1-141">将开关移动到 **"打开** " 或 " **关闭** "，具体取决于你是否希望在设备上进行 Cortana 语音协助。</span><span class="sxs-lookup"><span data-stu-id="e04e1-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
