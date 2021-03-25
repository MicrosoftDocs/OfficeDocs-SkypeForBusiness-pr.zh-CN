---
title: Microsoft Teams 中的 Cortana 语音帮助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何在 Teams 中使用 Cortana 语音协助
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118471"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="94956-103">Teams 中的 Cortana 语音帮助</span><span class="sxs-lookup"><span data-stu-id="94956-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="94956-104">Microsoft Teams iOS 和 Android 移动应用、Windows 版 Microsoft Teams 会议室和 Microsoft Teams 显示器支持 Cortana 语音帮助，仅适用于美国用户。</span><span class="sxs-lookup"><span data-stu-id="94956-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="94956-105">它当前不适用于 GCC、GCC-High、DoD、EDU 租户。</span><span class="sxs-lookup"><span data-stu-id="94956-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="94956-106">在将来的版本中，将扩展到其他语言和地区。</span><span class="sxs-lookup"><span data-stu-id="94956-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="94956-107">Microsoft Teams 会议室中的 Cortana 语音帮助在预览版下发布。</span><span class="sxs-lookup"><span data-stu-id="94956-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="94956-108">在其预览版中，只有美国支持 Cortana，在连接了 Rally 麦克风的设备上支持语言 EN-US。</span><span class="sxs-lookup"><span data-stu-id="94956-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="94956-109">Teams 移动应用、Windows 版 Microsoft Teams 会议室和 Microsoft Teams 显示设备中的 Cortana 语音帮助使 Microsoft 365 企业版用户能够使用口语自然语言简化通信、协作和会议相关任务。</span><span class="sxs-lookup"><span data-stu-id="94956-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="94956-110">用户可以通过选择 Teams 移动应用右上角的麦克风按钮，或在 Microsoft Teams 会议室中说出 &#8220;Cortana&#8221; 或者使用 Microsoft Teams 显示器来与 Cortana 讲话。</span><span class="sxs-lookup"><span data-stu-id="94956-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="94956-111">要免费与团队快速联系，用户可以说查询，例如 &#8220;呼叫 Megan&#8221; 或 &#8220;将消息发送到我的下一个会议&#8221;。</span><span class="sxs-lookup"><span data-stu-id="94956-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="94956-112">用户还可以加入会议，&#8220;加入下一&#8221;会议，并使用语音协助共享文件、查看其日历等。</span><span class="sxs-lookup"><span data-stu-id="94956-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="94956-113">这些语音协助体验是使用 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 企业级服务提供的，这些服务完全符合 Office 365 的隐私、安全性和合规性承诺，如联机服务条款 [ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 一样。</span><span class="sxs-lookup"><span data-stu-id="94956-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="94956-114">该图像显示使用 Cortana 在移动设备上发送聊天。</span><span class="sxs-lookup"><span data-stu-id="94956-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![显示 Cortana 聊天会话的一系列移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="94956-116">管理员控制和限制</span><span class="sxs-lookup"><span data-stu-id="94956-116">Admin control and limitations</span></span>

<span data-ttu-id="94956-117">Teams 中的 Cortana 语音帮助是使用完全符合 Office 365 企业级隐私、安全性和合规性承诺的服务提供的，如在线服务条款 (OST) 。</span><span class="sxs-lookup"><span data-stu-id="94956-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="94956-118">默认情况下，将为租户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="94956-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="94956-119">租户管理员可以使用 TeamsCortanaPolicy (策略控制租户中的哪些人可以使用 Teams 中的 Cortana 语音) 。</span><span class="sxs-lookup"><span data-stu-id="94956-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="94956-120">可在用户帐户级别或租户级别设置此策略。</span><span class="sxs-lookup"><span data-stu-id="94956-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="94956-121">管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是禁用、仅通过推送按钮调用启用，还是通过唤醒词调用启用， (也适用于支持它的设备，如 Microsoft Teams 显示) 。</span><span class="sxs-lookup"><span data-stu-id="94956-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="94956-122">管理员可以使用以下 PowerShell cmdlet 管理此策略 (Microsoft Teams 管理中心中当前) 。</span><span class="sxs-lookup"><span data-stu-id="94956-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="94956-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="94956-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="94956-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="94956-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="94956-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="94956-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="94956-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="94956-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="94956-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="94956-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="94956-128">例如，以下命令创建一个名称为 EmployeeCortanaPolicy &#8220;策略，&#8221;禁用 Microsoft Teams 中的 Cortana 语音帮助。</span><span class="sxs-lookup"><span data-stu-id="94956-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="94956-129">此示例演示了使用 EmployeeCortanaPolicy &#8220;更新现有策略，&#8221;在 Microsoft Teams 中启用 Cortana 语音帮助（仅推送按钮调用）。</span><span class="sxs-lookup"><span data-stu-id="94956-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="94956-130">用户将能够通过在 Teams 中选择 Cortana 麦克风按钮来调用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="94956-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="94956-131">唤醒 (&#8220;你好小娜&#8221;或&#8220;Cortana&#8221;) 调用将被禁用。</span><span class="sxs-lookup"><span data-stu-id="94956-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="94956-132">此示例演示了通过推送按钮和唤醒词调用更新策略并启用 Cortana 语音协助。</span><span class="sxs-lookup"><span data-stu-id="94956-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="94956-133">美国 Microsoft 365 企业版用户最初使用英语版本时，可以使用以下函数：</span><span class="sxs-lookup"><span data-stu-id="94956-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="94956-134">Teams 移动应用不支持唤醒词激活，但将来会支持。</span><span class="sxs-lookup"><span data-stu-id="94956-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="94956-135">Windows 和 Microsoft Teams 显示设备的 Microsoft Teams 会议室将支持唤醒词激活。</span><span class="sxs-lookup"><span data-stu-id="94956-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="94956-136">用户控件</span><span class="sxs-lookup"><span data-stu-id="94956-136">User control</span></span>

<span data-ttu-id="94956-137">单个用户可以在不同的设备中试用 Cortana 语音帮助：</span><span class="sxs-lookup"><span data-stu-id="94956-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="94956-138">在 Teams 移动应用中选择麦克风按钮。</span><span class="sxs-lookup"><span data-stu-id="94956-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="94956-139">在 Microsoft Teams 会议室中选择麦克风按钮或说"Cortana"。</span><span class="sxs-lookup"><span data-stu-id="94956-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="94956-140">在 Microsoft Teams 显示设备上说"Cortana"。</span><span class="sxs-lookup"><span data-stu-id="94956-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="94956-141">通过使用设备中的设置，你可以控制 Teams 中的 Cortana 是否为设备启用。</span><span class="sxs-lookup"><span data-stu-id="94956-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="94956-142">Teams 移动应用或 Microsoft Teams 显示</span><span class="sxs-lookup"><span data-stu-id="94956-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="94956-143">打开 Teams 移动应用。</span><span class="sxs-lookup"><span data-stu-id="94956-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="94956-144">选择"**设置**  >  **""Cortana"。**</span><span class="sxs-lookup"><span data-stu-id="94956-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="94956-145">将开关移动到 **"开"或**"**关"。**</span><span class="sxs-lookup"><span data-stu-id="94956-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="94956-146">Microsoft Teams 显示</span><span class="sxs-lookup"><span data-stu-id="94956-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="94956-147">转到 Microsoft Teams () 环境环境。</span><span class="sxs-lookup"><span data-stu-id="94956-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="94956-148">选择用户头像，然后选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="94956-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="94956-149">如果 Cortana 已启用，则说"Cortana，转到"设置"。</span><span class="sxs-lookup"><span data-stu-id="94956-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="94956-150">将开关移动到 **"开"或**"**关"。**</span><span class="sxs-lookup"><span data-stu-id="94956-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="94956-151">Windows 上的 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="94956-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="94956-152">如果在租户级别启用了 Cortana，可在设备级别进行更改。</span><span class="sxs-lookup"><span data-stu-id="94956-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="94956-153">默认情况下，Cortana 将解除禁用。</span><span class="sxs-lookup"><span data-stu-id="94956-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="94956-154">若要在设备级别启用 Cortana，必须在 SkypeSettings XML 文件中添加这些 XML 属性：</span><span class="sxs-lookup"><span data-stu-id="94956-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="94956-155">如果在设备级别启用了 Cortana，则可在会议级别进行更改。</span><span class="sxs-lookup"><span data-stu-id="94956-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="94956-156">若要在会议期间启用 Cortana 语音协助，请移动开关"**打开"或**"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="94956-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="94956-157">会议结束后，Cortana 将返回到设备级别设置集。</span><span class="sxs-lookup"><span data-stu-id="94956-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>