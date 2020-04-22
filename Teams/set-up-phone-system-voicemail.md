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
ms.openlocfilehash: 4f85e8db6f50becb4ae2406e84621c08507e9737
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779728"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="8d498-103">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="8d498-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="8d498-104">本文适用于希望为企业中的每个人设置云语音邮件功能的[Office 365 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="8d498-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="8d498-105">云语音邮件支持仅在 Exchange 邮箱中发送语音邮件消息，并且不支持任何第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="8d498-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="8d498-106">仅限云的环境：设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="8d498-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="8d498-107">对于 Skype for Business Online 和通话计划用户，向用户分配**电话系统**许可证和电话号码后，将自动为用户设置和设置云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8d498-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="8d498-108">如果您的计划中未包含电话系统功能，您可能需要购买 "**电话系统**加载项" 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8d498-109">您可能还需要购买 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8d498-110">请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d498-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8d498-111">[分配或删除 Office 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，向企业中的人员[分配 Microsoft 团队许可证](assign-teams-licenses.md)和 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="8d498-112">分配完成后，他们将能够接收语音邮件消息！</span><span class="sxs-lookup"><span data-stu-id="8d498-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="8d498-113">对语音邮件脚本的支持已添加到2017年3月，并且默认情况下为所有组织和用户启用。</span><span class="sxs-lookup"><span data-stu-id="8d498-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="8d498-114">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="8d498-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="8d498-115">本地环境的电话系统</span><span class="sxs-lookup"><span data-stu-id="8d498-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="8d498-116">以下信息介绍如何配置云语音邮件以使用本地通话计划环境。</span><span class="sxs-lookup"><span data-stu-id="8d498-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="8d498-117">如果您的计划中未包含电话系统功能，您可能需要购买 "**电话系统**加载项" 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8d498-118">您还需要购买 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8d498-119">请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="8d498-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8d498-120">[分配或删除 Office 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)，向企业中的人员[分配 Microsoft 团队许可证](assign-teams-licenses.md)和 Exchange Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="8d498-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="8d498-121">按照为你的用户部署的本地 PSTN 呼叫解决方案匹配说明。</span><span class="sxs-lookup"><span data-stu-id="8d498-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="8d498-122">对于云连接器版本，请按照 "[配置 Skype for Business 云连接器](https://technet.microsoft.com/library/mt605228.aspx)的**用户电话语音和语音邮件服务**" 部分中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="8d498-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="8d498-123">对于使用 Skype for Business 服务器的 PSTN 呼叫，请遵循[启用企业内部部署企业语音的用户](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)。</span><span class="sxs-lookup"><span data-stu-id="8d498-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="8d498-124">对于团队直接路由，请按照配置电话号码和启用 "[配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)" 部分中的 "**启用企业语音和语音邮件**" 部分。</span><span class="sxs-lookup"><span data-stu-id="8d498-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="8d498-125">对语音邮件脚本的支持已添加到2017年3月，并且默认情况下为所有组织和用户启用。</span><span class="sxs-lookup"><span data-stu-id="8d498-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="8d498-126">通过使用 Windows PowerShell 并执行以下步骤，你可以为组织禁用转录。</span><span class="sxs-lookup"><span data-stu-id="8d498-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="8d498-127">语音邮件通过 Exchange Online Protection 通过 SMTP 路由发送到用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8d498-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="8d498-128">若要支持成功传递这些邮件，请确保 exchange 连接器在 Exchange 服务器和 Exchange Online Protection 之间正确配置;[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="8d498-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="8d498-129">若要启用语音邮件功能（如自定义问候语）和 Skype for business 客户端中的视觉语音邮件，需要通过 Exchange Web 服务将来自 Office 365 的连接到 Exchange server 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8d498-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="8d498-130">若要启用此连接，必须配置[exchange 和 Exchange Online 组织之间的 "配置 Oauth 身份验证](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)" 中介绍的新 Exchange Oauth 身份验证协议，或者从 EXCHANGE 2013 CU5 或更高版本运行 Exchange 混合向导。</span><span class="sxs-lookup"><span data-stu-id="8d498-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="8d498-131">此外，你必须在 Skype for business [online 和 Exchange server 之间配置集成和 oauth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中介绍的 Skype For business Online 和 exchange server 之间配置集成和 oauth。</span><span class="sxs-lookup"><span data-stu-id="8d498-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

> [!NOTE]
> <span data-ttu-id="8d498-132">当代理人代表委托人进行通话应答呼叫时，通知在云语音邮件中不可用。</span><span class="sxs-lookup"><span data-stu-id="8d498-132">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="8d498-133">用户可以接收有关未接来电的通知。</span><span class="sxs-lookup"><span data-stu-id="8d498-133">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="8d498-134">设置组织的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="8d498-134">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="8d498-135">对于 Skype for Business 客户，通过 Microsoft 团队呼叫策略禁用语音邮件可能还会禁用 Skype for business 用户的语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="8d498-135">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="8d498-136">默认情况下，为所有组织和用户启用语音邮件转录并禁用转录亵渎屏蔽；但是，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 和 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet 对其进行控制。</span><span class="sxs-lookup"><span data-stu-id="8d498-136">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="8d498-137">您的组织中的用户收到的语音邮件在托管 Office 365 组织的区域中 transcribed。</span><span class="sxs-lookup"><span data-stu-id="8d498-137">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 organization is hosted.</span></span> <span data-ttu-id="8d498-138">租户的托管区域可能与接收语音邮件消息的用户所在的区域不同。</span><span class="sxs-lookup"><span data-stu-id="8d498-138">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="8d498-139">若要查看租户的托管区域，请转到 "[组织配置文件](https://go.microsoft.com/fwlink/p/?linkid=2067339)" 页面，然后单击 "**数据位置**" 旁边的 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="8d498-139">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d498-140">您不能使用**且**cmdlet 创建用于脚本的新策略实例并使用脚本猥亵屏蔽，并且不能使用**且**cmdlet 删除现有策略实例。</span><span class="sxs-lookup"><span data-stu-id="8d498-140">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="8d498-141">可以使用语音邮件策略为用户管理转录设置。</span><span class="sxs-lookup"><span data-stu-id="8d498-141">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="8d498-142">若要查看所有可用的语音邮件策略实例，可以使用[且](https://technet.microsoft.com/library/mt798311.aspx)cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d498-142">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="8d498-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="8d498-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolic 结果窗口。](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="8d498-145">为组织禁用转录</span><span class="sxs-lookup"><span data-stu-id="8d498-145">Turning off transcription for your organization</span></span>

<span data-ttu-id="8d498-146">由于脚本的默认设置适用于你的组织，你可能希望通过使用[且将](https://technet.microsoft.com/library/mt798310.aspx)其禁用。</span><span class="sxs-lookup"><span data-stu-id="8d498-146">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="8d498-147">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="8d498-147">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="8d498-148">打开组织的转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="8d498-148">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="8d498-149">默认情况下，为组织禁用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="8d498-149">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="8d498-150">如果有启用它的业务要求，你可以使用 [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="8d498-150">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="8d498-151">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="8d498-151">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="8d498-152">为用户禁用转录</span><span class="sxs-lookup"><span data-stu-id="8d498-152">Turning off transcription for a user</span></span>

<span data-ttu-id="8d498-153">用户策略的优先级高于组织默认设置。</span><span class="sxs-lookup"><span data-stu-id="8d498-153">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="8d498-154">例如，如果为所有用户启用语音邮件脚本，则可以使用[且](https://technet.microsoft.com/library/mt798309.aspx)cmdlet 分配策略以禁用特定用户的脚本。</span><span class="sxs-lookup"><span data-stu-id="8d498-154">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="8d498-155">要为单个用户禁用转录，请运行：</span><span class="sxs-lookup"><span data-stu-id="8d498-155">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="8d498-156">为用户开启转录亵渎屏蔽</span><span class="sxs-lookup"><span data-stu-id="8d498-156">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="8d498-157">要为特定用户启用转录亵渎屏蔽，你可以使用 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet 分配一个策略，以便为特定用户启用转录亵渎屏蔽。</span><span class="sxs-lookup"><span data-stu-id="8d498-157">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="8d498-158">要为单个用户启用转录亵渎屏蔽，请运行：</span><span class="sxs-lookup"><span data-stu-id="8d498-158">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="8d498-p115">[!重要信息] Office 365 中的语音邮件服务缓存语音邮件策略，并每隔 4 小时更新一次缓存。因此，你所作的策略更改最长可能需要 4 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="8d498-p115">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="8d498-161">帮助用户了解团队语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="8d498-161">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="8d498-162">我们为你的用户提供了以下信息，用于管理其语音邮件设置以及团队中的其他呼叫功能：</span><span class="sxs-lookup"><span data-stu-id="8d498-162">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="8d498-163">[管理团队的通话设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="8d498-163">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="8d498-164">本文介绍如何管理所有最终用户团队通话功能。</span><span class="sxs-lookup"><span data-stu-id="8d498-164">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="8d498-165">帮助你的用户了解 Skype for Business 语音邮件的功能</span><span class="sxs-lookup"><span data-stu-id="8d498-165">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="8d498-166">我们有培训信息和文章，可帮助用户成功使用 Skype for Business 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8d498-166">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="8d498-167">指示他们访问以下文章：</span><span class="sxs-lookup"><span data-stu-id="8d498-167">Point them to the following articles:</span></span>

- <span data-ttu-id="8d498-168">[检查 skype for business 语音邮件和选项](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)：本文介绍如何在 Skype for business 中收听语音邮件、更改语音邮件问候语、更改语音邮件设置，以及以不同的速度收听语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8d498-168">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="8d498-169">Skype for Business 2016 培训</span><span class="sxs-lookup"><span data-stu-id="8d498-169">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="8d498-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d498-170">Related topics</span></span>
[<span data-ttu-id="8d498-171">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8d498-171">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="8d498-172">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="8d498-172">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8d498-173">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="8d498-173">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

