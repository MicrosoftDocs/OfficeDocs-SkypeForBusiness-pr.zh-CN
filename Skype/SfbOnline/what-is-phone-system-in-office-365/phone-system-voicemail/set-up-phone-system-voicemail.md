---
title: "设置电话系统语音邮件"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: c0ea32a7e5792f00380c41c50cc69a2521a3eb37
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="62ff2-103">设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="62ff2-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="62ff2-104">本文是针对[Office 365 管理](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)者想要在业务的每个人设置了电话系统的语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="62ff2-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62ff2-105">电话系统语音邮件支持仅在 Exchange 邮箱中放入的语音邮件消息，并不支持所有第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="62ff2-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="62ff2-106">作为一种回退机制，电话系统语音邮件可以重新发送邮件使用 SMTP，这意味着有一个第三方电子邮件系统上的邮箱的用户将收到与无保证的服务的正常运行时间或其他语音邮件功能，例如更改其语音邮件消息他们问候和其他设置。</span><span class="sxs-lookup"><span data-stu-id="62ff2-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="62ff2-107">仅云环境： 设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="62ff2-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="62ff2-108">为业务联机并调用计划用户的 Skype，电话系统语音邮件自动设置和分配给他们的**电话系统**许可证及电话号码后为用户提供。</span><span class="sxs-lookup"><span data-stu-id="62ff2-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="62ff2-109">如果电话系统功能不包含在您的计划，可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="62ff2-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="62ff2-110">您可能还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="62ff2-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="62ff2-111">请参阅[附加业务和 Microsoft 小组授权的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="62ff2-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="62ff2-112">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[业务和 Microsoft 小组许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证给在您的业务的人。</span><span class="sxs-lookup"><span data-stu-id="62ff2-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="62ff2-113">分配完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="62ff2-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="62ff2-114">语音邮件抄写的支持已添加 3 月 2017 年和所有组织和用户的默认启用的。</span><span class="sxs-lookup"><span data-stu-id="62ff2-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="62ff2-115">通过使用 Windows PowerShell 并执行以下步骤，您可以为您的组织中禁用抄写。</span><span class="sxs-lookup"><span data-stu-id="62ff2-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="62ff2-116">电话系统与内部部署环境</span><span class="sxs-lookup"><span data-stu-id="62ff2-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="62ff2-117">以下信息是关于配置电话系统语音邮件使用内部调用计划环境。</span><span class="sxs-lookup"><span data-stu-id="62ff2-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="62ff2-118">如果电话系统功能不包含在您的计划，可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="62ff2-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="62ff2-119">您还需要购买一个 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="62ff2-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="62ff2-120">请参阅[附加业务和 Microsoft 小组授权的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="62ff2-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="62ff2-121">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[业务和 Microsoft 小组许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)和 Exchange Online 许可证给在您的业务的人。</span><span class="sxs-lookup"><span data-stu-id="62ff2-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="62ff2-122">按照[商务云连接器版指南配置 Skype](https://technet.microsoft.com/en-us/library/mt605228.aspx)的**用户语音电话系统和语音邮件服务启用**部分中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="62ff2-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="62ff2-123">语音邮件抄写的支持已添加 3 月 2017 年和所有组织和用户的默认启用的。</span><span class="sxs-lookup"><span data-stu-id="62ff2-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="62ff2-124">通过使用 Windows PowerShell 并执行以下步骤，您可以为您的组织中禁用抄写。</span><span class="sxs-lookup"><span data-stu-id="62ff2-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="62ff2-125">您还可以查看[Azure PBX 语音邮件的 Exchange Server 支持](https://support.microsoft.com/en-us/kb/3195158)以了解如何配置电话系统用户拥有本地邮箱的 Azure 的语音邮件消息的传递。</span><span class="sxs-lookup"><span data-stu-id="62ff2-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="62ff2-126">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="62ff2-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="62ff2-127">默认情况下启用语音邮件抄写并抄写亵渎屏蔽默认禁用的所有组织和用户;但是，您可以通过[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)和[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet 控制它们。</span><span class="sxs-lookup"><span data-stu-id="62ff2-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62ff2-128">不能创建新策略实例的抄写，并抄写亵渎掩蔽使用**New CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="62ff2-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="62ff2-129">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="62ff2-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="62ff2-130">若要查看所有可用的语音邮件策略实例，您可以使用[Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62ff2-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="62ff2-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="62ff2-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="62ff2-133">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="62ff2-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="62ff2-134">由于抄写的默认设置是在为您的组织，您可以通过[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)禁用它。</span><span class="sxs-lookup"><span data-stu-id="62ff2-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="62ff2-135">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="62ff2-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="62ff2-136">打开组织的抄写亵渎蒙</span><span class="sxs-lookup"><span data-stu-id="62ff2-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="62ff2-137">抄写亵渎屏蔽默认为您的组织。</span><span class="sxs-lookup"><span data-stu-id="62ff2-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="62ff2-138">如果有业务需求，以便启用它，则可以通过[设置 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)屏蔽抄写亵渎。</span><span class="sxs-lookup"><span data-stu-id="62ff2-138">If there is a business requirements to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="62ff2-139">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="62ff2-139">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="62ff2-140">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="62ff2-140">Turning off transcription for a user</span></span>

<span data-ttu-id="62ff2-141">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="62ff2-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="62ff2-142">例如，如果为所有用户都启用了语音邮件抄写，可以分配一个策略以禁用对特定用户使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 的抄写。</span><span class="sxs-lookup"><span data-stu-id="62ff2-142">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="62ff2-143">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="62ff2-143">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="62ff2-144">打开用户的抄写亵渎蒙</span><span class="sxs-lookup"><span data-stu-id="62ff2-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="62ff2-145">若要启用某一特定用户的抄写亵渎蒙，您可以分配一个策略，以使特定用户使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet 的抄写亵渎蒙。</span><span class="sxs-lookup"><span data-stu-id="62ff2-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="62ff2-146">若要启用抄写不敬为单个用户屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="62ff2-146">To enable transcription profanity masking for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="62ff2-p111">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="62ff2-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="62ff2-149">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="62ff2-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="62ff2-150">我们必须培训信息和文章，以帮助用户能成功与 Skype 业务语音邮件。</span><span class="sxs-lookup"><span data-stu-id="62ff2-150">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="62ff2-151">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="62ff2-151">Point them to the following articles:</span></span>
  
- <span data-ttu-id="62ff2-152">[检查业务语音邮件和选项的 Skype](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章解释了如何收听语音邮件中业务的 Skype、 更改您的语音邮件问候语、 更改您的语音邮件设置和收听语音邮件以不同的速度。</span><span class="sxs-lookup"><span data-stu-id="62ff2-152">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="62ff2-153">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="62ff2-153">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="62ff2-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="62ff2-154">Related topics</span></span>
[<span data-ttu-id="62ff2-155">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="62ff2-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="62ff2-156">下面是 Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="62ff2-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

## <a name="feedback"></a><span data-ttu-id="62ff2-157">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="62ff2-157">Feedback?</span></span>
<span data-ttu-id="62ff2-158">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="62ff2-158">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>