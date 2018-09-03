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
description: '了解如何为 Skype for Business 用户设置电话系统（云 PBX）语音邮件。 '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252886"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="0ad4d-103">设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="0ad4d-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="0ad4d-104">本文适用于想要为企业中的每位用户设置电话系统语音邮件功能的 [Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-104">This article is for the [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up Skype for Business Cloud PBX voicemail for everyone in their business.</span></span>

> [!NOTE]
> <span data-ttu-id="0ad4d-105">电话系统语音邮件仅支持在 Exchange 邮箱中存储语音邮件消息，不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-105">Cloud PBX voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="0ad4d-106">作为一种回退机制，电话系统语音邮件可以使用 SMTP 重新发送消息，这意味着使用第三方电子邮件系统的邮箱的用户将收到其语音邮件消息，但服务运行时间和其他语音邮件功能（例如更改其问候语和其他设置）没有保证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-106">As a fallback mechanism, Cloud PBX Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings .</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="0ad4d-107">仅限云环境：设置电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="0ad4d-107">Set up Phone System voicemail</span></span>

<span data-ttu-id="0ad4d-108">对于 Skype for Business Online 和通话套餐用户，在你为其分配 **电话系统** 许可证和电话号码后，系统自动为他们设置和配置电话系统语音邮件。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-108">For Skype for Business Online and PSTN Calling users, Cloud PBX voicemail is automatically set up and provisioned for users after you assign a Skype for Business Cloud PBX license and a phone number to them.</span></span>

1. <span data-ttu-id="0ad4d-109">如果你的套餐不包含电话系统功能，你可能需要购买 **电话系统** 加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-109">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="0ad4d-110">你可能还需要购买 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-110">You may also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="0ad4d-111">请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-111">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="0ad4d-112">为企业员工[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)以及 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-112">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span> <span data-ttu-id="0ad4d-113">操作完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="0ad4d-113">After you do that, they will be able to receive voicemail messages!</span></span>

3. <span data-ttu-id="0ad4d-114">从 2017 年 3 月开始增加了对语音邮件转录的支持，默认情况下为所有组织和用户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-114">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="0ad4d-115">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="0ad4d-116">本地环境的电话系统</span><span class="sxs-lookup"><span data-stu-id="0ad4d-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="0ad4d-117">下面是有关配置电话系统语音邮件以用于本地通话套餐环境的信息。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>

1. <span data-ttu-id="0ad4d-118">如果你的套餐不包含电话系统功能，你可能需要购买 **电话系统** 加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-118">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="0ad4d-119">你可能还需要购买 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-119">You also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="0ad4d-120">请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-120">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="0ad4d-121">为企业员工[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)以及 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-121">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span>

3. <span data-ttu-id="0ad4d-122">按照 [配置商业云连接器 Edition 指南](https://technet.microsoft.com/en-us/library/mt605228.aspx) 的 **为用户启用电话系统语音和语音邮件服务** 部分的说明操作。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-122">Next, follow the instructions in the **Enable users for Cloud PBX voice and voice mail services** section of the[Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="0ad4d-123">从 2017 年 3 月开始增加了对语音邮件转录的支持，默认情况下为所有组织和用户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-123">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="0ad4d-124">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="0ad4d-125">你还可以参阅 [Exchange Server 的 azure PBX 的语音邮件支持](https://support.microsoft.com/en-us/kb/3195158)，了解如何为拥有本地邮箱的电话系统用户配置 Azure 语音邮件消息的传递方式。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="0ad4d-126">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="0ad4d-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="0ad4d-127">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ad4d-128">无法使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为转录和转录亵渎屏蔽创建新的策略实例，且无法使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="0ad4d-129">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="0ad4d-130">要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-130">To see the all available voicemail policy instances, you can use the[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="0ad4d-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="0ad4d-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>

![Get-CsOnlineVoiceMailPolic 结果窗口。](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="0ad4d-133">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="0ad4d-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="0ad4d-134">由于默认情况下为组织启用转录，你可能会希望通过使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 来禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-134">Because the default setting for transcription is on for your organization, you may want to disable it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="0ad4d-135">要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="0ad4d-135">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="0ad4d-136">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="0ad4d-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="0ad4d-137">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="0ad4d-138">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="0ad4d-139">要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="0ad4d-139">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="0ad4d-140">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="0ad4d-140">Turning off transcription for a user</span></span>

<span data-ttu-id="0ad4d-141">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="0ad4d-142">例如，如果为所有用户启用了语音邮件转录，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户禁用转录。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-142">For example, if voicemail transcription is enabled for all of your users you can assign a policy to disable transcription for a specific user using [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="0ad4d-143">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="0ad4d-143">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="0ad4d-144">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="0ad4d-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="0ad4d-145">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="0ad4d-146">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="0ad4d-146">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="0ad4d-p111">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="0ad4d-149">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="0ad4d-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="0ad4d-150">我们拥有培训信息和文章，可帮助你的用户成功使用 Skype for Business 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-150">We have a lot of training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="0ad4d-151">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="0ad4d-151">Point them to the following articles:</span></span>

- <span data-ttu-id="0ad4d-152">[检查 Skype for Business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置并以不同速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="0ad4d-152">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="0ad4d-153">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="0ad4d-153">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="0ad4d-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ad4d-154">Related topics</span></span>
[<span data-ttu-id="0ad4d-155">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0ad4d-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="0ad4d-156">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="0ad4d-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


