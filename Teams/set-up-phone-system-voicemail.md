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
description: '了解如何为用户云语音邮件帐户。 '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901900"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="43b72-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="43b72-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="43b72-104">本文适用于Microsoft 365或Office 365管理员，如想要为业务中的云语音邮件设置管理员角色中所述。 [](/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="43b72-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="43b72-105">云语音邮件仅支持将语音邮件Exchange邮箱中，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="43b72-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="43b72-106">当代理人代表代理人应答呼叫时，通知在云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="43b72-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="43b72-107">用户可以接收未接来电的通知。</span><span class="sxs-lookup"><span data-stu-id="43b72-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="43b72-108">仅云环境：为联机云语音邮件设置电话系统环境</span><span class="sxs-lookup"><span data-stu-id="43b72-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="43b72-109">对于 Online 电话系统用户，云语音邮件分配用户许可证后，系统会自动为用户 **电话系统设置和** 预配这些许可证。</span><span class="sxs-lookup"><span data-stu-id="43b72-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="43b72-110">对于Skype for Business 电话系统本地提供电话号码的 Online 用户，可能需要使用[Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True。</span><span class="sxs-lookup"><span data-stu-id="43b72-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="43b72-111">为云语音邮件用户Exchange Server邮箱用户</span><span class="sxs-lookup"><span data-stu-id="43b72-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="43b72-112">以下信息用于配置云语音邮件，以便与联机进行登录但邮箱位于电话系统的用户Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="43b72-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="43b72-113">语音邮件通过 SMTP 通过 Exchange 发送到用户的邮箱Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="43b72-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="43b72-114">若要成功传递这些消息，请确保在 Exchange 服务器和服务器之间正确Exchange连接器Exchange Online Protection;[使用连接器配置邮件Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="43b72-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="43b72-115">若要启用语音邮件功能，例如自定义 Skype for Business 客户端中的问候语和可视语音邮件，需要从 Microsoft 365 或 Office 365 通过 Exchange Web 服务连接到 Exchange 服务器邮箱。</span><span class="sxs-lookup"><span data-stu-id="43b72-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="43b72-116">若要启用此连接，必须配置在 Exchange 与 Exchange Online 组织之间配置[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)身份验证中所述的新 Exchange Oauth 身份验证协议，或者从 Exchange 2013 CU5 或更高版运行 Exchange 混合向导。</span><span class="sxs-lookup"><span data-stu-id="43b72-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="43b72-117">此外，必须在 Skype for Business Online 和 Exchange 服务器之间配置集成和 Oauth，如在 Skype for Business Online 和 Exchange Server 之间配置集成和[OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述。</span><span class="sxs-lookup"><span data-stu-id="43b72-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="43b72-118">为云语音邮件用户Skype for Business Server组</span><span class="sxs-lookup"><span data-stu-id="43b72-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="43b72-119">若要Skype for Business服务器用户云语音邮件，请参阅[为本地云语音邮件计划服务](/skypeforbusiness/hybrid/plan-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="43b72-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="43b72-120">在组织中启用受保护的语音邮件</span><span class="sxs-lookup"><span data-stu-id="43b72-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="43b72-121">当某人为您的组织中的用户留下语音邮件时，语音邮件作为电子邮件附件传送到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="43b72-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="43b72-122">使用邮件流规则应用邮件加密，可以防止这些语音邮件转发给其他收件人。</span><span class="sxs-lookup"><span data-stu-id="43b72-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="43b72-123">启用受保护的语音邮件后，用户可以通过呼叫进入其语音邮件邮箱或在 Outlook、Outlook 网页版或 Outlook for Android 或 iOS 中打开邮件来收听受保护的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="43b72-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="43b72-124">受保护的语音邮件无法通过语音信箱或Skype for Business Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="43b72-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="43b72-125">有关邮件加密的信息，请参阅 [电子邮件加密](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="43b72-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="43b72-126">若要设置受保护的语音邮件，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="43b72-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="43b72-127">转到 https://admin.microsoft.com ，使用具有全局管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="43b72-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="43b72-128">选择 **"全部显示**"，然后转到"管理 **中心**  >  **Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="43b72-129">在"Exchange管理中心"中，选择"**邮件流规则**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="43b72-130">选择 **+** **"添加**"，然后选择 **"Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="43b72-131">提供新邮件流规则的名称，然后在"如果应用此规则 **"** 下，选择"邮件 **属性**  >  **包括邮件类型**  >  **""语音邮件"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="43b72-132">选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-132">Select **OK**.</span></span>
6. <span data-ttu-id="43b72-133">在 **"执行下列操作"** 下，选择 **"Office 365 邮件加密邮件应用权限保护**"，然后选择"选择 **一个"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="43b72-134">在 **"RMS 模板"** 下，选择 **"不转发"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="43b72-135">选择 **"确定**"，然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="43b72-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="43b72-136">如果 **RMS 模板** 列表为空，则需要设置消息加密。</span><span class="sxs-lookup"><span data-stu-id="43b72-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="43b72-137">有关设置消息加密的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="43b72-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="43b72-138">设置新的消息加密功能</span><span class="sxs-lookup"><span data-stu-id="43b72-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="43b72-139">配置和管理 Azure 信息保护的模板</span><span class="sxs-lookup"><span data-stu-id="43b72-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="43b72-140">电子邮件的"不转发"选项</span><span class="sxs-lookup"><span data-stu-id="43b72-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="43b72-141">帮助用户了解Teams语音信箱功能</span><span class="sxs-lookup"><span data-stu-id="43b72-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="43b72-142">我们针对你的用户提供有关管理其语音邮件设置的信息以及其他呼叫功能，Teams：</span><span class="sxs-lookup"><span data-stu-id="43b72-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="43b72-143">[在 中管理Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="43b72-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="43b72-144">本文介绍如何管理所有最终用户和Teams功能。</span><span class="sxs-lookup"><span data-stu-id="43b72-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="43b72-145">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="43b72-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="43b72-146">我们提供培训信息和文章来帮助用户成功使用语音邮件Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="43b72-146">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="43b72-147">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="43b72-147">Point them to the following articles:</span></span>

- <span data-ttu-id="43b72-148">[检查Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)和选项：本文介绍如何在 Skype for Business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置以及以不同速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="43b72-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="43b72-149">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="43b72-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="43b72-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="43b72-150">Related topics</span></span>
[<span data-ttu-id="43b72-151">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="43b72-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="43b72-152">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="43b72-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="43b72-153">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="43b72-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
