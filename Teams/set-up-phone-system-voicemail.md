---
title: 设置云语音邮件
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
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为用户设置云语音邮件。 '
ms.openlocfilehash: 26594c9d955cb21dc5751491e1857525660bdcae
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041931"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="25362-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="25362-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="25362-104">本文适用于[Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)想要在企业中设置的所有人云语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="25362-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="25362-105">云语音邮件 Exchange 邮箱中仅支持放入的语音邮件和不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="25362-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="25362-106">仅限云环境： 将云语音邮件设置</span><span class="sxs-lookup"><span data-stu-id="25362-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="25362-107">对于业务联机和调用计划用户 Skype，云语音邮件是自动设置，然后分配给他们的**电话系统**许可证和电话号码后，为用户设置。</span><span class="sxs-lookup"><span data-stu-id="25362-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="25362-108">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="25362-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="25362-109">您可能还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="25362-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="25362-110">请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="25362-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="25362-111">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="25362-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="25362-112">分配完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="25362-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="25362-113">对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="25362-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="25362-114">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="25362-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="25362-115">本地环境的电话系统</span><span class="sxs-lookup"><span data-stu-id="25362-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="25362-116">有关配置云语音邮件，以使用内部部署调用规划环境中的以下信息。</span><span class="sxs-lookup"><span data-stu-id="25362-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="25362-117">如果电话系统功能不包括在您的计划，您可能需要购买附加许可证**电话系统**。</span><span class="sxs-lookup"><span data-stu-id="25362-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="25362-118">您还需要购买 Exchange Online 的许可证。</span><span class="sxs-lookup"><span data-stu-id="25362-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="25362-119">请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="25362-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="25362-120">[分配或删除业务的 Office 365 的许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，[分配的 Microsoft 团队许可证](assign-teams-licenses.md)，以及您企业中的人员的 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="25362-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="25362-121">按照说明匹配本地 PSTN 呼叫的用户部署的解决方案。</span><span class="sxs-lookup"><span data-stu-id="25362-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="25362-122">对于云连接器 Edition，请按照[商务云连接器版指南配置 Skype](https://technet.microsoft.com/library/mt605228.aspx)的**启用用户电话系统的语音和语音邮件服务**部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="25362-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="25362-123">对于与 Skype 的业务服务器呼叫 PSTN，按照[为本地的企业语音用户启用](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="25362-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="25362-124">团队直接路由，请按照[配置直接](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)路由**配置的电话号码并启用企业语音和语音邮件**部分。</span><span class="sxs-lookup"><span data-stu-id="25362-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="25362-125">对语音邮件转录已添加从年 3 月 2017年和支持的所有组织和用户的默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="25362-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="25362-126">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="25362-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="25362-127">语音邮件消息传送到通过 SMTP 通过 Exchange Online Protection 路由的用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="25362-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="25362-128">若要启用这些邮件成功传递，请确保您的 Exchange 服务器和 Exchange Online Protection 之间正确配置了 Exchange Connectors。</span><span class="sxs-lookup"><span data-stu-id="25362-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="25362-129">[使用连接器配置邮件流](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="25362-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="25362-130">若要启用语音邮件功能，如自定义问候语，电话拨入式访问和 visual 语音邮件，不需要从 Office 365 连接到 Exchange 服务器邮箱通过 Exchange Web 服务。</span><span class="sxs-lookup"><span data-stu-id="25362-130">To enable Voicemail features such as customizing greeting, dial in access and visual voicemail, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="25362-131">若要启用此连接必须配置新的 Exchange Oauth 身份验证协议介绍在[Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="25362-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="25362-132">Exchange 混合向导运行从 Exchange 2013 CU5 或更高版本将自动处理步骤 5 和 6 中的要求。</span><span class="sxs-lookup"><span data-stu-id="25362-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="25362-133">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="25362-133">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="25362-134">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="25362-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25362-135">无法创建新策略实例转录和转录亵渎屏蔽使用**新建 CsOnlineVoiceMailPolicy** cmdlet，并且您不能删除现有策略实例使用**删除 CsOnlineVoiceMailPolicy** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25362-135">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="25362-136">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="25362-136">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="25362-137">若要查看所有可用的语音邮件策略实例，可以使用[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25362-137">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="25362-138">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="25362-138">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="25362-140">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="25362-140">Turning off transcription for your organization</span></span>

<span data-ttu-id="25362-141">由于转录的默认设置是在您的组织，可能要使用[集 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)禁用它。</span><span class="sxs-lookup"><span data-stu-id="25362-141">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="25362-142">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="25362-142">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="25362-143">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="25362-143">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="25362-144">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="25362-144">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="25362-145">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="25362-145">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="25362-146">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="25362-146">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="25362-147">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="25362-147">Turning off transcription for a user</span></span>

<span data-ttu-id="25362-148">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="25362-148">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="25362-149">例如，如果为所有用户都启用语音邮件转录，您可以分配一个策略来禁用特定用户的转录使用[授予 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25362-149">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="25362-150">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="25362-150">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="25362-151">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="25362-151">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="25362-152">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="25362-152">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="25362-153">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="25362-153">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="25362-p113">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="25362-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="25362-156">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="25362-156">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="25362-157">我们有培训信息和文章可帮助您成功与 Skype 的业务语音邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="25362-157">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="25362-158">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="25362-158">Point them to the following articles:</span></span>

- <span data-ttu-id="25362-159">[检查业务语音邮件和选项的 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)： 这篇文章介绍如何收听语音邮件中的业务的 Skype、 更改语音邮件问候语，更改您的语音邮件设置和收听语音邮件以不同速度。</span><span class="sxs-lookup"><span data-stu-id="25362-159">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="25362-160">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="25362-160">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="25362-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="25362-161">Related topics</span></span>
[<span data-ttu-id="25362-162">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="25362-162">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="25362-163">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="25362-163">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


