---
title: 设置云语音邮件
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
description: '了解如何为用户设置云语音邮件。 '
ms.openlocfilehash: fa30184d38822141d0f30404fb55b79eefd5d33d
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997420"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="97126-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="97126-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="97126-104">本文适用于 Microsoft 365 或 Office 365 管理员[](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)，如关于想要为企业中的每个人设置云语音邮件功能管理员角色中所述。</span><span class="sxs-lookup"><span data-stu-id="97126-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="97126-105">云语音邮件仅支持将语音邮件置于 Exchange 邮箱中，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="97126-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="97126-106">当代理人代表代理人应答呼叫时，通知在云语音邮件中不可用。</span><span class="sxs-lookup"><span data-stu-id="97126-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="97126-107">用户可以接收未接来电的通知。</span><span class="sxs-lookup"><span data-stu-id="97126-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="97126-108">仅云环境：为联机电话系统用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="97126-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="97126-109">对于在线电话系统用户，向用户分配电话系统许可证后，将自动为用户 **设置和预配** 云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="97126-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="97126-110">对于使用本地提供的电话号码的在线 Skype for Business Phone 系统用户，可能需要使用 [Set-CsUser -HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)$True。</span><span class="sxs-lookup"><span data-stu-id="97126-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="97126-111">为邮箱用户Exchange Server云语音邮件</span><span class="sxs-lookup"><span data-stu-id="97126-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="97126-112">以下信息将有关配置云语音邮件以与在线使用电话系统但其邮箱位于 Exchange Server 的用户一Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="97126-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="97126-113">语音邮件通过 SMTP 通过 Exchange Online Protection 路由传送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="97126-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="97126-114">若要成功传递这些邮件，请确保 Exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置; [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="97126-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="97126-115">若要启用语音邮件功能，例如自定义 Skype for Business 客户端中的问候语和可视语音邮件，需要通过 Exchange Web Services 从 Microsoft 365 或 Office 365 连接到 Exchange 服务器邮箱。</span><span class="sxs-lookup"><span data-stu-id="97126-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="97126-116">若要启用此连接，必须配置在 Exchange 和 Exchange Online 组织之间配置 [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。</span><span class="sxs-lookup"><span data-stu-id="97126-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="97126-117">此外，你必须在 Skype for Business Online 和 Exchange Server 之间配置集成和 Oauth，如在 Skype for Business Online 和 Exchange Server 之间配置 [集成和 OAuth 中所述](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="97126-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="97126-118">为 Skype for Business Server 用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="97126-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="97126-119">若要为云语音邮件配置 Skype for Business 服务器用户，请参阅为本地用户规划 [云语音邮件服务](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="97126-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="97126-120">在组织中启用受保护的语音邮件</span><span class="sxs-lookup"><span data-stu-id="97126-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="97126-121">当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="97126-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="97126-122">使用邮件流规则应用邮件加密，可以防止这些语音邮件转发给其他收件人。</span><span class="sxs-lookup"><span data-stu-id="97126-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="97126-123">启用受保护的语音邮件后，用户可以通过呼叫进入语音邮件邮箱或在 Outlook、Outlook 网页版或 Outlook for Android 或 iOS 中打开邮件来收听受保护的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="97126-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="97126-124">在 Skype for Business 或 Microsoft Teams 中无法打开受保护的语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="97126-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="97126-125">有关邮件加密的信息，请参阅 [电子邮件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="97126-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="97126-126">若要设置受保护的语音邮件，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="97126-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="97126-127">转到 https://admin.microsoft.com ，使用具有全局管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="97126-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="97126-128">选择 **"全部显示**"，然后转到管理 **中心**  >  **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="97126-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="97126-129">在 Exchange 管理中心中，选择"**邮件流**  >  **规则"。**</span><span class="sxs-lookup"><span data-stu-id="97126-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="97126-130">选择 **+** **"添加**"，然后选择 **"对邮件应用 Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="97126-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="97126-131">提供新邮件流规则的名称，然后在"如果应用此规则 **"** 下，选择"邮件 **属性**  >  **包括邮件类型**  >  **""语音邮件"。**</span><span class="sxs-lookup"><span data-stu-id="97126-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="97126-132">选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="97126-132">Select **OK**.</span></span>
6. <span data-ttu-id="97126-133">在 **"执行下列操作"** 下，选择"对邮件应用 **Office 365** 邮件加密和权限保护"，然后选择"选择 **一个"。**</span><span class="sxs-lookup"><span data-stu-id="97126-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="97126-134">在 **"RMS 模板"** 下，选择 **"不转发"。**</span><span class="sxs-lookup"><span data-stu-id="97126-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="97126-135">选择 **"确定**"，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="97126-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="97126-136">如果 **RMS 模板** 列表为空，则需要设置消息加密。</span><span class="sxs-lookup"><span data-stu-id="97126-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="97126-137">有关设置消息加密的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="97126-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="97126-138">设置新的消息加密功能</span><span class="sxs-lookup"><span data-stu-id="97126-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="97126-139">配置和管理 Azure 信息保护的模板</span><span class="sxs-lookup"><span data-stu-id="97126-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="97126-140">电子邮件的"不转发"选项</span><span class="sxs-lookup"><span data-stu-id="97126-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="97126-141">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="97126-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="97126-142">对于 Skype for Business 客户，通过 Microsoft Teams 呼叫策略禁用语音邮件也可能禁用 Skype for Business 用户的语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="97126-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="97126-143">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="97126-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="97126-144">您的组织中的用户收到的语音邮件在托管 Microsoft 365 或 Office 365 组织的区域进行转录。</span><span class="sxs-lookup"><span data-stu-id="97126-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="97126-145">托管租户的区域可能与接收语音邮件的用户所在的区域不同。</span><span class="sxs-lookup"><span data-stu-id="97126-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="97126-146">若要查看托管租户的区域，请转到"组织配置文件"页，然后单击"[](https://go.microsoft.com/fwlink/p/?linkid=2067339)数据位置"旁边的"查看 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="97126-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97126-147">不能使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为听录和听录亵渎内容屏蔽创建新的策略实例，并且不能使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="97126-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="97126-148">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="97126-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="97126-149">若要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="97126-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

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
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="97126-150">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="97126-150">Turning off transcription for your organization</span></span>

<span data-ttu-id="97126-151">由于组织的听录默认设置为"开"，因此可能需要使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)禁用它。</span><span class="sxs-lookup"><span data-stu-id="97126-151">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="97126-152">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="97126-152">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="97126-153">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="97126-153">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="97126-154">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="97126-154">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="97126-155">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="97126-155">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="97126-156">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="97126-156">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="97126-157">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="97126-157">Turning off transcription for a user</span></span>

<span data-ttu-id="97126-158">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="97126-158">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="97126-159">例如，如果为所有用户启用了语音邮件转录，则可以通过 [使用 Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 为特定用户分配禁用转录的策略。</span><span class="sxs-lookup"><span data-stu-id="97126-159">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="97126-160">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="97126-160">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="97126-161">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="97126-161">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="97126-162">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="97126-162">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="97126-163">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="97126-163">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="97126-164">Microsoft 365 和 Office 365 中的语音邮件服务每 4 小时缓存一次语音邮件策略并更新缓存。</span><span class="sxs-lookup"><span data-stu-id="97126-164">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="97126-165">因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="97126-165">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="97126-166">帮助用户了解 Teams 语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="97126-166">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="97126-167">我们在 Teams 中为用户提供有关管理语音邮件设置和其他呼叫功能的以下信息：</span><span class="sxs-lookup"><span data-stu-id="97126-167">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="97126-168">[在 Teams 中管理通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="97126-168">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="97126-169">本文介绍如何管理所有最终用户 Teams 呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="97126-169">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="97126-170">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="97126-170">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="97126-171">我们提供培训信息和文章来帮助你的用户成功使用 Skype for Business 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="97126-171">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="97126-172">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="97126-172">Point them to the following articles:</span></span>

- <span data-ttu-id="97126-173">[检查 Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)语音邮件和选项：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置以及以不同速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="97126-173">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="97126-174">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="97126-174">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="97126-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="97126-175">Related topics</span></span>
[<span data-ttu-id="97126-176">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="97126-176">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="97126-177">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="97126-177">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="97126-178">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="97126-178">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
