---
title: 设置电话系统语音邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: f5dcf6012dc9ac6659d35c29a31ee6a5ff40eec2
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "22135527"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="e769c-103">设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="e769c-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="e769c-104">本文适用于[Office 365 管理员](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业中设置的每个人的电话系统的语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="e769c-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e769c-105">电话系统的语音邮件 Exchange 邮箱中仅支持放入的语音邮件消息，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="e769c-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="e769c-106">作为一回退机制，电话系统的语音邮件可以重新发送邮件使用 SMTP，这意味着与第三方电子邮件系统上的邮箱的用户将收到与不保证的服务正常运行时间或其他语音邮件功能，如更改其语音邮件消息其问候语和其他设置。</span><span class="sxs-lookup"><span data-stu-id="e769c-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="e769c-107">仅限云环境： 设置电话系统的语音邮件</span><span class="sxs-lookup"><span data-stu-id="e769c-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="e769c-108">对于业务联机和调用计划用户 Skype，电话系统的语音邮件是自动设置，然后分配给他们的**电话系统**许可证和电话号码后，为用户设置。</span><span class="sxs-lookup"><span data-stu-id="e769c-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e769c-109">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="e769c-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e769c-110">您可能还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="e769c-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e769c-111">请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e769c-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e769c-112">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[业务和 Microsoft 团队许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="e769c-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e769c-113">分配完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="e769c-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e769c-114">对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="e769c-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e769c-115">通过使用 Windows PowerShell 并执行以下步骤，您可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="e769c-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="e769c-116">内部部署环境与电话系统</span><span class="sxs-lookup"><span data-stu-id="e769c-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="e769c-117">有关配置电话系统语音邮件，以使用内部部署调用规划环境中的以下信息。</span><span class="sxs-lookup"><span data-stu-id="e769c-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="e769c-118">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="e769c-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e769c-119">您还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="e769c-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e769c-120">请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="e769c-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e769c-121">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[业务和 Microsoft 团队许可证分配 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="e769c-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e769c-122">按照[配置商务云连接器版指南的 Skype](https://technet.microsoft.com/en-us/library/mt605228.aspx)**为用户启用电话系统语音和语音邮件服务**部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="e769c-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="e769c-123">对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="e769c-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e769c-124">通过使用 Windows PowerShell 并执行以下步骤，您可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="e769c-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="e769c-125">您还可以参见[Exchange server 支持的 Azure PBX 语音邮件](https://support.microsoft.com/en-us/kb/3195158)以了解如何配置的电话系统的用户具有内部部署邮箱中的 Azure 语音邮件的传递。</span><span class="sxs-lookup"><span data-stu-id="e769c-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e769c-126">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="e769c-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="e769c-127">默认情况下启用语音邮件转录和转录亵渎隐蔽的所有组织和用户; 默认情况下禁用但是，您可以控制其使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)和[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e769c-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e769c-128">无法创建新策略实例转录和转录亵渎屏蔽使用**新建 CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e769c-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e769c-129">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="e769c-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e769c-130">若要查看所有可用的语音邮件策略实例，可以使用[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e769c-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="e769c-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e769c-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e769c-133">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="e769c-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="e769c-134">由于转录的默认设置是在您的组织，可能要使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)禁用它。</span><span class="sxs-lookup"><span data-stu-id="e769c-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="e769c-135">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="e769c-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e769c-136">打开您的组织转录亵渎蒙</span><span class="sxs-lookup"><span data-stu-id="e769c-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e769c-137">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="e769c-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e769c-138">如果没有启用它的业务要求，您可以使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)屏蔽转录亵渎。</span><span class="sxs-lookup"><span data-stu-id="e769c-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="e769c-139">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="e769c-139">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e769c-140">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="e769c-140">Turning off transcription for a user</span></span>

<span data-ttu-id="e769c-141">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="e769c-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e769c-142">例如，如果为所有用户都启用语音邮件转录，您可以分配一个策略来禁用特定用户的转录使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e769c-142">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="e769c-143">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="e769c-143">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e769c-144">开启转录亵渎隐蔽的用户</span><span class="sxs-lookup"><span data-stu-id="e769c-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e769c-145">若要启用转录亵渎屏蔽为某个特定用户，您可以分配一个策略来启用转录亵渎屏蔽为某个特定用户使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e769c-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="e769c-146">若要启用转录亵渎屏蔽单个用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="e769c-146">To enable transcription profanity masking for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e769c-p111">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="e769c-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e769c-149">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="e769c-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e769c-150">我们有培训信息和文章可帮助您成功与 Skype 的业务语音邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="e769c-150">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="e769c-151">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="e769c-151">Point them to the following articles:</span></span>
  
- <span data-ttu-id="e769c-152">[检查业务语音邮件和选项的 Skype](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章介绍如何收听语音邮件中的业务的 Skype、 更改语音邮件问候语，更改您的语音邮件设置和收听语音邮件以不同速度。</span><span class="sxs-lookup"><span data-stu-id="e769c-152">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="e769c-153">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="e769c-153">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="e769c-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="e769c-154">Related topics</span></span>
[<span data-ttu-id="e769c-155">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e769c-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="e769c-156">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="e769c-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 