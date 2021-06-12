---
title: 管理语音邮件策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理用户的语音邮件策略。
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910054"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="04eb1-103">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="04eb1-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="04eb1-104">对于Skype for Business，通过语音信箱呼叫Microsoft Teams禁用语音邮件可能也会为你的Skype for Business禁用语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="04eb1-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="04eb1-105">所有用户的语音邮件组织默认设置</span><span class="sxs-lookup"><span data-stu-id="04eb1-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="04eb1-106">已启用语音邮件听录。</span><span class="sxs-lookup"><span data-stu-id="04eb1-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="04eb1-107">已禁用语音邮件听录亵渎内容屏蔽。</span><span class="sxs-lookup"><span data-stu-id="04eb1-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="04eb1-108">最大录制持续时间设置为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="04eb1-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="04eb1-109">可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 和 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet 控制这些默认值。</span><span class="sxs-lookup"><span data-stu-id="04eb1-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="04eb1-110">您的组织中的用户收到的语音邮件转录在托管您的组织或Microsoft 365 Office 365区域。</span><span class="sxs-lookup"><span data-stu-id="04eb1-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="04eb1-111">托管租户的区域可能与接收语音邮件的用户所在的区域不同。</span><span class="sxs-lookup"><span data-stu-id="04eb1-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="04eb1-112">若要查看托管租户的区域，请转到"组织配置文件"页，然后单击"[](https://go.microsoft.com/fwlink/p/?linkid=2067339)数据位置"旁边的"查看 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="04eb1-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04eb1-113">不能使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为听录和听录亵渎内容屏蔽创建新的策略实例，并且不能使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="04eb1-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="04eb1-114">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="04eb1-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="04eb1-115">若要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04eb1-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="04eb1-116">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="04eb1-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="04eb1-117">由于组织的听录默认设置为"开"，因此可能需要使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)禁用它。</span><span class="sxs-lookup"><span data-stu-id="04eb1-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="04eb1-118">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="04eb1-119">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="04eb1-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="04eb1-120">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="04eb1-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="04eb1-121">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="04eb1-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="04eb1-122">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="04eb1-123">更改组织的录制持续时间</span><span class="sxs-lookup"><span data-stu-id="04eb1-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="04eb1-124">默认情况下，组织的最大录制时长设置为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="04eb1-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="04eb1-125">如果需要增加或减少最大录制长度，可以使用 [Set-CsOnlineVoicemailPolicy 完成此操作](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。</span><span class="sxs-lookup"><span data-stu-id="04eb1-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="04eb1-126">例如，若要将最大录制时间设置为 60 秒，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="04eb1-127">针对组织的双语言系统提示</span><span class="sxs-lookup"><span data-stu-id="04eb1-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="04eb1-128">默认情况下，语音邮件系统提示以用户设置语音邮件时选择的语言向呼叫者显示。</span><span class="sxs-lookup"><span data-stu-id="04eb1-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="04eb1-129">如果需要以两种语言提供语音邮件系统提示，可以使用 [Set-CsOnlineVoicemailPolicy 完成此操作](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)。</span><span class="sxs-lookup"><span data-stu-id="04eb1-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="04eb1-130">主语言和辅助语言必须设置，不能相同。</span><span class="sxs-lookup"><span data-stu-id="04eb1-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="04eb1-131">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="04eb1-132">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="04eb1-132">Turning off transcription for a user</span></span>

<span data-ttu-id="04eb1-133">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="04eb1-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="04eb1-134">例如，如果为所有用户启用了语音邮件转录，则可以通过 [使用 Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 为特定用户分配禁用转录的策略。</span><span class="sxs-lookup"><span data-stu-id="04eb1-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="04eb1-135">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="04eb1-136">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="04eb1-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="04eb1-137">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="04eb1-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="04eb1-138">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="04eb1-139">更改用户的录制持续时间</span><span class="sxs-lookup"><span data-stu-id="04eb1-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="04eb1-140">必须先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet 创建自定义语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="04eb1-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="04eb1-141">以下显示的命令创建按用户联机语音邮件策略 OneMinuteVoicemailPolicy，MaximumRecordingLength 设置为 60 秒，其他字段设置为租户级全局值。</span><span class="sxs-lookup"><span data-stu-id="04eb1-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="04eb1-142">若要将此自定义策略分配给用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="04eb1-143">针对用户的双语言系统提示</span><span class="sxs-lookup"><span data-stu-id="04eb1-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="04eb1-144">必须先使用 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet 创建自定义语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="04eb1-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="04eb1-145">以下显示的命令创建按用户联机语音邮件策略 enUS-esSP-VoicemailPolicy，PrimarySystemPromptLanguage 设置为 en-US (英语 - 美国) ，SecondarySystemPromptLanguage 设置为 es-SP (西班牙语 - 西班牙) 。</span><span class="sxs-lookup"><span data-stu-id="04eb1-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="04eb1-146">若要将此自定义策略分配给用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="04eb1-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="04eb1-147">Get-CsOnlineVoicemailPolicy cmdlet 当前未返回 PrimarySystemPromptLanguage 和 SecondarySystemPromptLanguage 的值。</span><span class="sxs-lookup"><span data-stu-id="04eb1-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="04eb1-148">若要查看这些值，请修改命令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04eb1-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="04eb1-149">将 **PolicyName** 替换为策略的名称。</span><span class="sxs-lookup"><span data-stu-id="04eb1-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="04eb1-150">语音信箱和语音Microsoft 365 Office 365缓存语音邮件策略，并每隔 6 小时更新一次缓存。</span><span class="sxs-lookup"><span data-stu-id="04eb1-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="04eb1-151">因此，你所做的更改最多可能需要 6 小时才能应用。</span><span class="sxs-lookup"><span data-stu-id="04eb1-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
