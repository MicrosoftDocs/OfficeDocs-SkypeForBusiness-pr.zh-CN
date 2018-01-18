---
title: Set up Phone System voicemail
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 7d4ad9fa310ee8b90b813bfe949401c602c6a2f2
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="c1478-103">Set up Phone System voicemail</span><span class="sxs-lookup"><span data-stu-id="c1478-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="c1478-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span><span class="sxs-lookup"><span data-stu-id="c1478-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1478-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span><span class="sxs-lookup"><span data-stu-id="c1478-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="c1478-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span><span class="sxs-lookup"><span data-stu-id="c1478-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="c1478-107">Cloud-only environments: Set up Phone System voicemail</span><span class="sxs-lookup"><span data-stu-id="c1478-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="c1478-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span><span class="sxs-lookup"><span data-stu-id="c1478-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="c1478-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span><span class="sxs-lookup"><span data-stu-id="c1478-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c1478-110">You may also need to purchase an Exchange Online license.</span><span class="sxs-lookup"><span data-stu-id="c1478-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c1478-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c1478-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c1478-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span><span class="sxs-lookup"><span data-stu-id="c1478-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="c1478-113">After you do that, they will be able to receive voicemail messages!</span><span class="sxs-lookup"><span data-stu-id="c1478-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="c1478-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span><span class="sxs-lookup"><span data-stu-id="c1478-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="c1478-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="c1478-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="c1478-116">Phone System with on-premises environments</span><span class="sxs-lookup"><span data-stu-id="c1478-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="c1478-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span><span class="sxs-lookup"><span data-stu-id="c1478-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="c1478-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span><span class="sxs-lookup"><span data-stu-id="c1478-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c1478-119">You also need to purchase an Exchange Online license.</span><span class="sxs-lookup"><span data-stu-id="c1478-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c1478-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c1478-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c1478-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span><span class="sxs-lookup"><span data-stu-id="c1478-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="c1478-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1478-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="c1478-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span><span class="sxs-lookup"><span data-stu-id="c1478-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="c1478-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="c1478-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="c1478-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span><span class="sxs-lookup"><span data-stu-id="c1478-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="c1478-126">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="c1478-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="c1478-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c1478-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c1478-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1478-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c1478-129">You can manage the transcription settings for your users using voicemail policies.</span><span class="sxs-lookup"><span data-stu-id="c1478-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="c1478-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1478-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="c1478-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="c1478-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="c1478-133">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="c1478-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="c1478-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1478-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="c1478-135">To do this, run:</span><span class="sxs-lookup"><span data-stu-id="c1478-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="c1478-136">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="c1478-136">Turning off transcription for a user</span></span>

<span data-ttu-id="c1478-137">User policies are evaluated before the organizational default settings.</span><span class="sxs-lookup"><span data-stu-id="c1478-137">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="c1478-138">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1478-138">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="c1478-139">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="c1478-139">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="c1478-p110">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="c1478-p110">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="c1478-142">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="c1478-142">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="c1478-143">We have training information and articles to help your users be successful with Skype for Business voicemail.</span><span class="sxs-lookup"><span data-stu-id="c1478-143">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="c1478-144">Point them to the following articles:</span><span class="sxs-lookup"><span data-stu-id="c1478-144">Point them to the following articles:</span></span>
  
- <span data-ttu-id="c1478-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span><span class="sxs-lookup"><span data-stu-id="c1478-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="c1478-146">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="c1478-146">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="c1478-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1478-147">Related topics</span></span>
[<span data-ttu-id="c1478-148">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1478-148">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="c1478-149">Here's what you get with Phone System in Office 365</span><span class="sxs-lookup"><span data-stu-id="c1478-149">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
