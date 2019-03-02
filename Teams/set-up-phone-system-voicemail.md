---
title: 设置电话系统语音邮件
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 48617a9bb40257dffda993a171b42c4e63ba5d1d
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353327"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="d9b55-103">设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="d9b55-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="d9b55-104">本文适用于[Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业中设置的每个人的电话系统的语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="d9b55-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="d9b55-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span><span class="sxs-lookup"><span data-stu-id="d9b55-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="d9b55-107">仅限云环境： 设置电话系统的语音邮件</span><span class="sxs-lookup"><span data-stu-id="d9b55-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="d9b55-108">对于业务联机和调用计划用户 Skype，电话系统的语音邮件是自动设置，然后分配给他们的**电话系统**许可证和电话号码后，为用户设置。</span><span class="sxs-lookup"><span data-stu-id="d9b55-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="d9b55-109">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="d9b55-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="d9b55-110">您可能还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="d9b55-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="d9b55-111">请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d9b55-111">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="d9b55-112">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="d9b55-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="d9b55-113">分配完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="d9b55-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="d9b55-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="d9b55-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="d9b55-116">本地环境的电话系统</span><span class="sxs-lookup"><span data-stu-id="d9b55-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="d9b55-117">下面是有关配置电话系统语音邮件以用于本地通话套餐环境的信息。</span><span class="sxs-lookup"><span data-stu-id="d9b55-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="d9b55-118">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="d9b55-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="d9b55-119">您还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="d9b55-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="d9b55-120">请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d9b55-120">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="d9b55-121">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="d9b55-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="d9b55-122">按照[配置商务云连接器版指南的 Skype](https://technet.microsoft.com/library/mt605228.aspx)**为用户启用电话系统语音和语音邮件服务**部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="d9b55-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="d9b55-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="d9b55-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="d9b55-125">你还可以参阅 [Exchange Server 的 azure PBX 的语音邮件支持](https://support.microsoft.com/kb/3195158)，了解如何为拥有本地邮箱的电话系统用户配置 Azure 语音邮件消息的传递方式。</span><span class="sxs-lookup"><span data-stu-id="d9b55-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="d9b55-126">请还阅读并遵循以下文档中所述的步骤：[混合配置向导](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="d9b55-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="d9b55-127">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="d9b55-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="d9b55-128">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="d9b55-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9b55-129">无法创建新策略实例转录和转录亵渎屏蔽使用**新建 CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d9b55-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="d9b55-130">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="d9b55-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="d9b55-131">若要查看所有可用的语音邮件策略实例，可以使用[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9b55-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="d9b55-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="d9b55-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="d9b55-134">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="d9b55-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="d9b55-135">由于转录的默认设置是在您的组织，可能要使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)禁用它。</span><span class="sxs-lookup"><span data-stu-id="d9b55-135">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="d9b55-136">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="d9b55-136">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="d9b55-137">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="d9b55-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="d9b55-138">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="d9b55-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="d9b55-139">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="d9b55-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="d9b55-140">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="d9b55-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="d9b55-141">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="d9b55-141">Turning off transcription for a user</span></span>

<span data-ttu-id="d9b55-142">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="d9b55-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="d9b55-143">例如，如果为所有用户都启用语音邮件转录，您可以分配一个策略来禁用特定用户的转录使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9b55-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="d9b55-144">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="d9b55-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="d9b55-145">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="d9b55-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="d9b55-146">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="d9b55-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="d9b55-147">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="d9b55-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="d9b55-p111">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="d9b55-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="d9b55-150">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="d9b55-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="d9b55-151">我们有培训信息和文章可帮助您成功与 Skype 的业务语音邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="d9b55-151">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="d9b55-152">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="d9b55-152">Point them to the following articles:</span></span>

- <span data-ttu-id="d9b55-153">[检查业务语音邮件和选项的 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章介绍如何收听语音邮件中的业务的 Skype、 更改语音邮件问候语，更改您的语音邮件设置和收听语音邮件以不同速度。</span><span class="sxs-lookup"><span data-stu-id="d9b55-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="d9b55-154">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="d9b55-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="d9b55-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9b55-155">Related topics</span></span>
[<span data-ttu-id="d9b55-156">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d9b55-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="d9b55-157">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="d9b55-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


