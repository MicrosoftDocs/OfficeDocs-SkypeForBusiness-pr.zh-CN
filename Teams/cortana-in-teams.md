---
title: Cortana语音帮助Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何通过语音Cortana语音Teams
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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428208"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="02ce0-103">Cortana语音帮助Teams</span><span class="sxs-lookup"><span data-stu-id="02ce0-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="02ce0-104">Cortana iOS 和 Android 的 Microsoft Teams 移动应用以及适用于美国、英国、加拿大、印度和澳大利亚的用户的 Microsoft Teams 移动应用中支持语音协助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="02ce0-105">Microsoft Teams 会议室Windows仅美国用户支持登录。</span><span class="sxs-lookup"><span data-stu-id="02ce0-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="02ce0-106">Cortana EDU 租户目前GCC GCC、DoD 和非 US EDU 租户提供语音协助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="02ce0-107">Cortana EDU 客户Teams移动应用中的语音帮助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="02ce0-108">在将来的版本中，将扩展到其他语言和地区。</span><span class="sxs-lookup"><span data-stu-id="02ce0-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="02ce0-109">Cortana预览下Microsoft Teams 会议室语音帮助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="02ce0-110">在其预览版中，Cortana在连接了 Rally 麦克风的设备上仅支持语言 EN-US 的语言。</span><span class="sxs-lookup"><span data-stu-id="02ce0-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="02ce0-111">Cortana Teams 移动应用、Windows 上的 Microsoft Teams 会议室 和 Microsoft Teams 显示设备上提供语音帮助，Microsoft 365 企业版 用户可以使用口语自然语言简化通信、协作和会议相关任务。</span><span class="sxs-lookup"><span data-stu-id="02ce0-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="02ce0-112">用户可以通过Cortana Teams 移动应用右上角的麦克风按钮，或者通过在 Microsoft Teams 会议室中说出 &#8220;Cortana&#8221; 或者使用 Microsoft Teams 显示器来与 Microsoft Teams 讲话。</span><span class="sxs-lookup"><span data-stu-id="02ce0-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="02ce0-113">要免费与团队快速联系，用户可以说查询，例如 &#8220;呼叫 Megan&#8221; 或 &#8220;将消息发送到我的下一个会议&#8221;。</span><span class="sxs-lookup"><span data-stu-id="02ce0-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="02ce0-114">用户还可以加入会议，&#8220;加入下一&#8221;会议，并使用语音协助共享文件、查看其日历等。</span><span class="sxs-lookup"><span data-stu-id="02ce0-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="02ce0-115">这些语音协助体验[是使用 Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企业级服务提供的，这些服务完全符合 Office 365 的隐私、安全性和合规性承诺，如在线服务条款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 所反映。</span><span class="sxs-lookup"><span data-stu-id="02ce0-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="02ce0-116">管理员控制和限制</span><span class="sxs-lookup"><span data-stu-id="02ce0-116">Admin control and limitations</span></span>

<span data-ttu-id="02ce0-117">Cortana中Teams语音帮助是使用完全符合 Office 365 企业级隐私、安全性和合规性承诺的服务提供的，如在线服务条款 (OST) 所反映。</span><span class="sxs-lookup"><span data-stu-id="02ce0-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="02ce0-118">默认情况下，将为租户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="02ce0-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="02ce0-119">租户管理员可以使用 TeamsCortanaPolicy Cortana策略控制Teams租户中的 (语音) 。</span><span class="sxs-lookup"><span data-stu-id="02ce0-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="02ce0-120">此策略在用户帐户级别或租户级别设置。</span><span class="sxs-lookup"><span data-stu-id="02ce0-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="02ce0-121">管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定是禁用了 Cortana，还是启用了按钮调用，或者启用了唤醒词调用， (也适用于支持它的设备，如 Microsoft Teams 显示) 。</span><span class="sxs-lookup"><span data-stu-id="02ce0-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="02ce0-122">管理员可以使用以下 PowerShell cmdlet 来管理此策略 (该策略目前Microsoft Teams管理中心) 。</span><span class="sxs-lookup"><span data-stu-id="02ce0-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="02ce0-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="02ce0-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="02ce0-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="02ce0-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="02ce0-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="02ce0-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="02ce0-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="02ce0-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="02ce0-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="02ce0-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="02ce0-128">例如，以下命令创建一个名称为 employeeCortanaPolicy &#8220;的策略，&#8221;禁用Cortana语音Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="02ce0-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="02ce0-129">此示例演示了使用 EmployeeCortanaPolicy &#8220;更新现有策略&#8221;并仅在Cortana按钮调用Microsoft Teams启用语音帮助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="02ce0-130">用户将能够通过在 Cortana 中选择"Cortana麦克风"按钮来调用Teams。</span><span class="sxs-lookup"><span data-stu-id="02ce0-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="02ce0-131">唤醒 (&#8220;"Cortana&#8221;或&#8220;Cortana&#8221;) 调用将被禁用。</span><span class="sxs-lookup"><span data-stu-id="02ce0-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="02ce0-132">此示例演示了通过推送按钮和唤醒Cortana更新策略并启用语音帮助。</span><span class="sxs-lookup"><span data-stu-id="02ce0-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="02ce0-133">在首次发布时，Microsoft 365 企业版美国用户使用英语，以下是可用的函数：</span><span class="sxs-lookup"><span data-stu-id="02ce0-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="02ce0-134">Teams移动应用不支持唤醒词激活，但将来会支持。</span><span class="sxs-lookup"><span data-stu-id="02ce0-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="02ce0-135">Microsoft Teams 会议室和Windows Microsoft Teams将支持唤醒词激活。</span><span class="sxs-lookup"><span data-stu-id="02ce0-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="02ce0-136">用户控件</span><span class="sxs-lookup"><span data-stu-id="02ce0-136">User control</span></span>

<span data-ttu-id="02ce0-137">单个用户可以尝试Cortana设备提供语音帮助：</span><span class="sxs-lookup"><span data-stu-id="02ce0-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="02ce0-138">选择移动应用中的麦克风Teams按钮。</span><span class="sxs-lookup"><span data-stu-id="02ce0-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="02ce0-139">选择麦克风按钮或在麦克风Cortana说"Microsoft Teams 会议室"。</span><span class="sxs-lookup"><span data-stu-id="02ce0-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="02ce0-140">在Cortana显示设备Microsoft Teams说"Microsoft Teams"。</span><span class="sxs-lookup"><span data-stu-id="02ce0-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="02ce0-141">通过使用设备中的Cortana Teams，可以控制设备是否已启用设备内设置。</span><span class="sxs-lookup"><span data-stu-id="02ce0-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="02ce0-142">Microsoft Teams 会议室上Windows</span><span class="sxs-lookup"><span data-stu-id="02ce0-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="02ce0-143">如果在租户级别启用了 Cortana，则可在设备级别进行更改。</span><span class="sxs-lookup"><span data-stu-id="02ce0-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="02ce0-144">Cortana将默认释放"关"。</span><span class="sxs-lookup"><span data-stu-id="02ce0-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="02ce0-145">若要Cortana级别启用配置，必须在 SkypeSettings XML 文件中添加以下 XML 属性：</span><span class="sxs-lookup"><span data-stu-id="02ce0-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="02ce0-146">如果在设备级别启用了Cortana，可在会议级别进行更改。</span><span class="sxs-lookup"><span data-stu-id="02ce0-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="02ce0-147">若要在Cortana启用语音协助，请移动开关"**开"或**"**关"。**</span><span class="sxs-lookup"><span data-stu-id="02ce0-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="02ce0-148">会议结束后，Cortana设备级别设置集。</span><span class="sxs-lookup"><span data-stu-id="02ce0-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
