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
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662207"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="66c97-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="66c97-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="66c97-104">本文适用于 Microsoft 365 或 Office 365 管理员，如" [关于](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 想要为企业中的每个人设置云语音邮件功能管理员角色"中所述。</span><span class="sxs-lookup"><span data-stu-id="66c97-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="66c97-105">云语音邮件仅支持将语音邮件置于 Exchange 邮箱中，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="66c97-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="66c97-106">当代理人代表代理人应答呼叫时，通知在云语音邮件中不可用。</span><span class="sxs-lookup"><span data-stu-id="66c97-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="66c97-107">用户可以接收未接来电的通知。</span><span class="sxs-lookup"><span data-stu-id="66c97-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="66c97-108">仅云环境：为在线电话系统用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="66c97-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="66c97-109">对于在线电话系统用户，在向用户分配电话系统许可证后，将自动为用户设置和预配云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="66c97-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="66c97-110">对于具有本地提供的电话号码的在线 Skype for Business Phone 系统用户，您可能需要使用 [Set-CsUser -HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)$True。</span><span class="sxs-lookup"><span data-stu-id="66c97-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="66c97-111">为邮箱用户Exchange Server语音邮件</span><span class="sxs-lookup"><span data-stu-id="66c97-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="66c97-112">以下信息有关将云语音邮件配置为与使用电话系统在线但其邮箱位于Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="66c97-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="66c97-113">语音邮件通过 SMTP 通过 Exchange Online Protection 路由传送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="66c97-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="66c97-114">若要成功传递这些邮件，请确保 Exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置; [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="66c97-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="66c97-115">若要启用语音邮件功能，例如自定义 Skype for Business 客户端中的问候语和可视语音邮件，需要通过 Exchange Web Services 从 Microsoft 365 或 Office 365 连接到 Exchange 服务器邮箱。</span><span class="sxs-lookup"><span data-stu-id="66c97-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="66c97-116">若要启用此连接，必须配置 Exchange 和 Exchange Online 组织之间配置 [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。</span><span class="sxs-lookup"><span data-stu-id="66c97-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="66c97-117">此外，你必须在 Skype for Business Online 和 Exchange 服务器之间配置集成和 Oauth，如在 Skype for Business Online 和 Exchange Server 之间配置集成 [和 OAuth 中所述](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="66c97-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="66c97-118">为 Skype for Business Server 用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="66c97-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="66c97-119">若要为云语音邮件配置 Skype for Business 服务器用户，请参阅"为本地用户规划云[语音邮件服务"。](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="66c97-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="66c97-120">在组织中启用受保护的语音邮件</span><span class="sxs-lookup"><span data-stu-id="66c97-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="66c97-121">当某人为贵组织的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="66c97-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="66c97-122">使用邮件流规则应用邮件加密，可以阻止这些语音邮件转发给其他收件人。</span><span class="sxs-lookup"><span data-stu-id="66c97-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="66c97-123">启用受保护的语音邮件后，用户可以通过呼叫进入其语音邮件邮箱或在 Outlook、Outlook 网页版或 Outlook for Android 或 iOS 中打开邮件来收听受保护的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="66c97-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="66c97-124">受保护的语音邮件消息在 Skype for Business 或 Microsoft Teams 中无法打开。</span><span class="sxs-lookup"><span data-stu-id="66c97-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="66c97-125">有关邮件加密详细信息，请参阅"[电子邮件加密"。](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="66c97-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="66c97-126">若要设置受保护的语音邮件，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="66c97-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="66c97-127">转到 https://admin.microsoft.com 具有全局管理员权限的帐户并登录。</span><span class="sxs-lookup"><span data-stu-id="66c97-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="66c97-128">选择 **"全部显示**"，然后转到 **管理中心**  >  **Exchange。**</span><span class="sxs-lookup"><span data-stu-id="66c97-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="66c97-129">在 Exchange 管理中心中，选择 **"邮件流**  >  **规则"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="66c97-130">选择 **+** **"添加**"，然后选择"对 **邮件应用 Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="66c97-131">提供新邮件流规则的名称，然后在"应用 **此** 规则"下选择"邮件 **属性**  >  **包括语音邮件"类型**  >  。</span><span class="sxs-lookup"><span data-stu-id="66c97-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="66c97-132">选择 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-132">Select **OK**.</span></span>
6. <span data-ttu-id="66c97-133">在 **"执行下列操作"下**，选择"对邮件应用 **Office 365** 邮件加密和权限保护"，然后选择"选择 **一个"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="66c97-134">在 **RMS 模板下**，选择 **"不转发"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="66c97-135">选择 **"确定**"，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="66c97-136">如果 **RMS 模板** 列表为空，则需要设置消息加密。</span><span class="sxs-lookup"><span data-stu-id="66c97-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="66c97-137">有关设置消息加密的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="66c97-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="66c97-138">设置新的消息加密功能</span><span class="sxs-lookup"><span data-stu-id="66c97-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="66c97-139">配置和管理 Azure 信息保护的模板</span><span class="sxs-lookup"><span data-stu-id="66c97-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="66c97-140">电子邮件的"不转发"选项</span><span class="sxs-lookup"><span data-stu-id="66c97-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="66c97-141">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="66c97-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="66c97-142">对于 Skype for Business 客户，通过 Microsoft Teams 呼叫策略禁用语音邮件也可能禁用 Skype for Business 用户的语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="66c97-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="66c97-143">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="66c97-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="66c97-144">组织中用户收到的语音邮件在托管 Microsoft 365 或 Office 365 组织的区域进行转录。</span><span class="sxs-lookup"><span data-stu-id="66c97-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="66c97-145">托管租户的区域可能与接收语音邮件的用户所在的区域不同。</span><span class="sxs-lookup"><span data-stu-id="66c97-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="66c97-146">若要查看托管租户的区域，请转到"组织配置文件"页，然后单击"[](https://go.microsoft.com/fwlink/p/?linkid=2067339)数据位置"旁边的"查看 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="66c97-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66c97-147">不能使用 **New-CsOnlineVoiceMailPolicy** cmdlet 为听录和听录不性屏蔽创建新的策略实例，并且不能使用 **Remove-CsOnlineVoiceMailPolicy** cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="66c97-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="66c97-148">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="66c97-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="66c97-149">若要查看所有可用的语音邮件策略实例，可以使用 [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66c97-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="66c97-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="66c97-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="66c97-152">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="66c97-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="66c97-153">由于组织的听录默认设置已打开，因此可能需要使用 [Set-CsOnlineVoicemailPolicy 禁用它](https://technet.microsoft.com/library/mt798310.aspx)。</span><span class="sxs-lookup"><span data-stu-id="66c97-153">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="66c97-154">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="66c97-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="66c97-155">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="66c97-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="66c97-156">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="66c97-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="66c97-157">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="66c97-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="66c97-158">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="66c97-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="66c97-159">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="66c97-159">Turning off transcription for a user</span></span>

<span data-ttu-id="66c97-160">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="66c97-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="66c97-161">例如，如果为所有用户启用了语音邮件转录，则可以通过 [使用 Grant-CsOnlineVoicemailPolidlet](https://technet.microsoft.com/library/mt798309.aspx) 为特定用户分配禁用转录的策略。</span><span class="sxs-lookup"><span data-stu-id="66c97-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="66c97-162">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="66c97-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="66c97-163">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="66c97-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="66c97-164">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="66c97-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="66c97-165">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="66c97-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="66c97-166">Microsoft 365 和 Office 365 中的语音邮件服务每 4 小时缓存一次语音邮件策略并更新缓存。</span><span class="sxs-lookup"><span data-stu-id="66c97-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="66c97-167">因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="66c97-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="66c97-168">帮助用户了解 Teams 语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="66c97-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="66c97-169">我们为用户提供了以下信息，以便管理其语音邮件设置以及 Teams 中的其他呼叫功能：</span><span class="sxs-lookup"><span data-stu-id="66c97-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="66c97-170">[在 Teams 中管理通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="66c97-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="66c97-171">本文介绍如何管理所有最终用户 Teams 通话功能。</span><span class="sxs-lookup"><span data-stu-id="66c97-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="66c97-172">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="66c97-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="66c97-173">我们提供培训信息和文章来帮助用户成功使用 Skype for Business 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="66c97-173">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="66c97-174">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="66c97-174">Point them to the following articles:</span></span>

- <span data-ttu-id="66c97-175">[检查 Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)语音邮件和选项：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置以及以不同速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="66c97-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="66c97-176">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="66c97-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="66c97-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="66c97-177">Related topics</span></span>
[<span data-ttu-id="66c97-178">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="66c97-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="66c97-179">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="66c97-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="66c97-180">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="66c97-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
