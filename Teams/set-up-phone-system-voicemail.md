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
description: '了解如何为你的用户设置云语音邮件。 '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031068"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="c9c0b-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="c9c0b-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="c9c0b-104">本文介绍 Microsoft 365 或 Office 365 管理员，如 [关于管理员角色，这些管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 希望为企业中的每个人设置云语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="c9c0b-105">云语音邮件支持仅在 Exchange 邮箱中发送语音邮件消息，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="c9c0b-106">当代理人代表委托人进行通话应答呼叫时，通知在云语音邮件中不可用。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="c9c0b-107">用户可以接收有关未接来电的通知。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="c9c0b-108">仅限云的环境：为联机电话系统用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="c9c0b-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="c9c0b-109">对于联机电话系统用户，向用户分配 **电话系统** 许可证后，将自动为用户设置和设置云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="c9c0b-110">对于使用本地提供的电话号码的联机 Skype for Business 电话系统用户，您可能需要启用 [move-csuser-HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)的托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="c9c0b-111">为 Exchange Server 邮箱用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="c9c0b-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="c9c0b-112">以下信息介绍了如何配置云语音邮件，以便与联机电话系统的用户进行协作，但其邮箱位于 Exchange 服务器上。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="c9c0b-113">语音邮件通过 Exchange Online Protection 通过 SMTP 路由发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="c9c0b-114">若要支持成功传递这些邮件，请确保 exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置; [使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="c9c0b-115">若要在 Skype for Business 客户端中启用语音邮件功能（如自定义问候语和视觉语音邮件），需要通过 Exchange Web 服务将来自 Microsoft 365 或 Office 365 的连接到 Exchange server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="c9c0b-116">若要启用此连接，必须配置 [exchange 与 Exchange Online 组织之间的 "配置 Oauth 身份验证](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)" 中描述的新 Exchange Oauth 身份验证协议，或者从 EXCHANGE 2013 CU5 或更高版本运行 Exchange 混合向导。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="c9c0b-117">此外，你必须在 Skype for business [online 和 Exchange server 之间配置集成和 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中介绍的 Skype For business Online 和 exchange server 之间配置集成和 oauth。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="c9c0b-118">为 Skype for business Server 用户设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="c9c0b-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="c9c0b-119">若要为云语音邮件配置 Skype for Business 服务器用户，请参阅为 [本地用户规划云语音邮件服务](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="c9c0b-120">在你的组织中启用受保护的语音邮件</span><span class="sxs-lookup"><span data-stu-id="c9c0b-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="c9c0b-121">当某人为您的组织中的用户留下语音邮件时，语音邮件将作为电子邮件附件发送到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="c9c0b-122">使用邮件流规则应用邮件加密，可以防止将这些语音邮件转发给其他收件人。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="c9c0b-123">当您启用受保护的语音邮件时，用户可以通过呼叫其语音邮件邮箱或打开 outlook、Outlook 网页版或适用于 Android 或 iOS 中的邮件来收听受保护的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="c9c0b-124">不能在 Skype for Business 中打开受保护的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="c9c0b-125">有关邮件加密的详细信息，请参阅 [电子邮件加密](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="c9c0b-126">若要设置受保护的语音邮件，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="c9c0b-127">转到 https://admin.microsoft.com 使用具有全局管理员权限的帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="c9c0b-128">选择 " **全部显示** "，然后转到 " **管理中心**  >  **Exchange** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="c9c0b-129">在 Exchange 管理中心中，选择 " **邮件流**  >  **规则** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="c9c0b-130">选择 **+** " **添加** "，然后选择 "向 **邮件应用 Office 365 邮件加密和权限保护** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-130">Select **+** **Add** , and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="c9c0b-131">为新邮件流规则提供一个名称，然后在 " **应用此规则条件** " 下，选择 **邮件属性**  >  **包括 "**  >  **语音邮件** " 这一邮件类型。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-131">Provide a name for the new mail flow rule and then under **Apply this rule if** , select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="c9c0b-132">选择 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-132">Select **OK**.</span></span>
6. <span data-ttu-id="c9c0b-133">在 " **执行以下操作** " 下，选择 **"向邮件应用 Office 365 邮件加密和权限保护"** ，然后选择 " **选择一个** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-133">Under **Do the following** , select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="c9c0b-134">在 " **RMS 模板** " 下，选择 " **不转发** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-134">Under **RMS template** , select **Do not forward**.</span></span> <span data-ttu-id="c9c0b-135">选择 **"确定"** ，然后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="c9c0b-136">如果 **RMS 模板** 列表为空，则需要设置邮件加密。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="c9c0b-137">有关设置邮件加密的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="c9c0b-138">设置新的邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="c9c0b-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="c9c0b-139">配置和管理 Azure 信息保护模板</span><span class="sxs-lookup"><span data-stu-id="c9c0b-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="c9c0b-140">电子邮件的 "不转发" 选项</span><span class="sxs-lookup"><span data-stu-id="c9c0b-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="c9c0b-141">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="c9c0b-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="c9c0b-142">对于 Skype for Business 客户，通过 Microsoft 团队呼叫策略禁用语音邮件可能还会禁用 Skype for business 用户的语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="c9c0b-143">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="c9c0b-144">您的组织中的用户收到的语音邮件在托管 Microsoft 365 或 Office 365 组织的区域中 transcribed。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="c9c0b-145">租户的托管区域可能与接收语音邮件消息的用户所在的区域不同。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="c9c0b-146">若要查看租户的托管区域，请转到 " [组织配置文件](https://go.microsoft.com/fwlink/p/?linkid=2067339)" 页面，然后单击 " **数据位置** " 旁边的 " **查看详细信息** "。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9c0b-147">您不能使用 **且** cmdlet 创建用于脚本的新策略实例并使用脚本猥亵屏蔽，并且不能使用 **且** cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="c9c0b-148">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="c9c0b-149">若要查看所有可用的语音邮件策略实例，可以使用 [且](https://technet.microsoft.com/library/mt798311.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="c9c0b-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="c9c0b-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="c9c0b-152">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="c9c0b-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="c9c0b-153">由于脚本的默认设置适用于你的组织，你可能希望通过使用 [且将](https://technet.microsoft.com/library/mt798310.aspx)其禁用。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-153">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="c9c0b-154">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="c9c0b-155">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="c9c0b-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="c9c0b-156">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="c9c0b-157">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="c9c0b-158">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="c9c0b-159">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="c9c0b-159">Turning off transcription for a user</span></span>

<span data-ttu-id="c9c0b-160">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="c9c0b-161">例如，如果为所有用户启用语音邮件脚本，则可以使用 [且](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配策略以禁用特定用户的脚本。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c9c0b-162">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="c9c0b-163">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="c9c0b-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="c9c0b-164">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c9c0b-165">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="c9c0b-166">Microsoft 365 和 Office 365 中的语音邮件服务缓存语音邮件策略，每隔4小时更新缓存。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="c9c0b-167">因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="c9c0b-168">帮助用户了解团队语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="c9c0b-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="c9c0b-169">我们为你的用户提供了以下信息，用于管理其语音邮件设置以及团队中的其他呼叫功能：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="c9c0b-170">[管理团队的通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="c9c0b-171">本文介绍如何管理所有最终用户团队通话功能。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="c9c0b-172">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="c9c0b-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="c9c0b-173">我们有培训信息和文章，可帮助用户成功使用 Skype for Business 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-173">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="c9c0b-174">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="c9c0b-174">Point them to the following articles:</span></span>

- <span data-ttu-id="c9c0b-175">[检查 skype for business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置，以及以不同的速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c9c0b-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="c9c0b-176">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="c9c0b-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="c9c0b-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="c9c0b-177">Related topics</span></span>
[<span data-ttu-id="c9c0b-178">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c9c0b-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="c9c0b-179">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="c9c0b-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c9c0b-180">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="c9c0b-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
