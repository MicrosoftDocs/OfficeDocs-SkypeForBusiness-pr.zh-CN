---
title: 团队和 Skype 互操作性
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中的团队用户与 Skype (消费者) 用户之间的互操作性功能。
localization_priority: Normal
ms.openlocfilehash: 9bb38fa33e7ef3692f5946fef4769bb45f782f1a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030968"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="e96c3-103">团队和 Skype 互操作性</span><span class="sxs-lookup"><span data-stu-id="e96c3-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="e96c3-104">本文提供了 Microsoft 团队和 Skype (消费者) 之间的互操作性功能概述。</span><span class="sxs-lookup"><span data-stu-id="e96c3-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="e96c3-105">了解团队用户和 Skype 用户可以如何通过聊天和通话以及适用的管理控制进行通信。</span><span class="sxs-lookup"><span data-stu-id="e96c3-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="e96c3-106">你的组织中的团队用户可以使用其电子邮件地址与 Skype 用户聊天和呼叫 Skype 用户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e96c3-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="e96c3-107">团队用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话。</span><span class="sxs-lookup"><span data-stu-id="e96c3-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="e96c3-108">Skype 用户可以使用团队用户搜索和启动一对一的纯文本对话或音频/视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="e96c3-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="e96c3-109">这些功能在桌面版、web 版和移动版 (Android 和 iOS) 客户端和 Skype 均可使用。</span><span class="sxs-lookup"><span data-stu-id="e96c3-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="e96c3-110">为获得最佳体验，我们建议使用 Skype 版本8.58 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="e96c3-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="e96c3-111">本文中讨论的团队和 Skype 互操作功能在 GCC、GCC 高或 DOD 部署或私有云环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="e96c3-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="e96c3-112">聊天和通话体验</span><span class="sxs-lookup"><span data-stu-id="e96c3-112">Chat and calling experience</span></span>

<span data-ttu-id="e96c3-113">下面是聊天和通话体验的概述。</span><span class="sxs-lookup"><span data-stu-id="e96c3-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="e96c3-114">团队用户与 Skype 用户开始聊天或通话</span><span class="sxs-lookup"><span data-stu-id="e96c3-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="e96c3-115">团队用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="e96c3-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="e96c3-116">然后，团队用户可以在搜索结果中选择 Skype 用户，以便与他们开始聊天或通话。</span><span class="sxs-lookup"><span data-stu-id="e96c3-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="e96c3-117">Skype 用户可能选择不在搜索结果中显示。</span><span class="sxs-lookup"><span data-stu-id="e96c3-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="e96c3-118">在这种情况下，不会在团队和团队用户无法找到它们的搜索结果中显示它们。</span><span class="sxs-lookup"><span data-stu-id="e96c3-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="e96c3-119">Skype 用户与团队用户开始聊天或通话</span><span class="sxs-lookup"><span data-stu-id="e96c3-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="e96c3-120">Skype 用户可以使用其电子邮件地址搜索和开始与团队用户聊天。</span><span class="sxs-lookup"><span data-stu-id="e96c3-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="e96c3-121">将通知团队用户收到来自 Skype 用户的新邮件，并且必须首先接受邮件，然后他们才能回复。</span><span class="sxs-lookup"><span data-stu-id="e96c3-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="e96c3-122">如果团队用户选择 " **接受** "，则接受对话，并且这两个用户都可以互相聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="e96c3-122">If the Teams user selects **Accept** , the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="e96c3-123">如果团队用户选择 " **阻止** "，则对话会被阻止，并且将阻止来自该 Skype 用户的后续消息和呼叫。</span><span class="sxs-lookup"><span data-stu-id="e96c3-123">If the Teams user selects **Block** , the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="e96c3-124">如果团队用户选择 " **查看邮件** "，则邮件将显示在 "团队" 中，帮助用户决定是接受还是阻止对话。</span><span class="sxs-lookup"><span data-stu-id="e96c3-124">If the Teams user selects **View messages** , the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="e96c3-125">如果您从 Skype for Business 升级到团队，并且您的用户在 "仅限工作组" 模式下，则 Skype 用户与团队用户之间的聊天和通话将发送给团队。</span><span class="sxs-lookup"><span data-stu-id="e96c3-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="e96c3-126">如果你的用户处于 "孤岛" 模式，Skype 用户的聊天和呼叫将发送到 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="e96c3-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="e96c3-127">团队用户阻止或取消阻止 Skype 用户</span><span class="sxs-lookup"><span data-stu-id="e96c3-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="e96c3-128">在团队用户接受或阻止来自 Skype 用户的初始对话请求后，他们可以随时选择阻止或取消阻止该用户。</span><span class="sxs-lookup"><span data-stu-id="e96c3-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="e96c3-129">他们可以在对话中或在团队的隐私设置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e96c3-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="e96c3-130">Skype 用户不知道他们已被阻止。</span><span class="sxs-lookup"><span data-stu-id="e96c3-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="e96c3-131">被阻止的 Skype 用户以及其他人和公共交换电话网络)  (由团队用户阻止的用户阻止的联系人列表中列出的团队用户已阻止的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e96c3-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="e96c3-132">优缺点</span><span class="sxs-lookup"><span data-stu-id="e96c3-132">Limitations</span></span>

- <span data-ttu-id="e96c3-133">对话是纯文本的。</span><span class="sxs-lookup"><span data-stu-id="e96c3-133">Conversations are text-only.</span></span> <span data-ttu-id="e96c3-134">这意味着没有丰富的格式、@mentions、表情符号或其他任何其他聊天功能，这些功能在 [本机团队聊天体验](native-chat-for-external-users.md)中可用。</span><span class="sxs-lookup"><span data-stu-id="e96c3-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="e96c3-135">对话仅一对一。</span><span class="sxs-lookup"><span data-stu-id="e96c3-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="e96c3-136">不支持群组聊天。</span><span class="sxs-lookup"><span data-stu-id="e96c3-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="e96c3-137">团队用户和 Skype 用户看不到彼此的状态。</span><span class="sxs-lookup"><span data-stu-id="e96c3-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="e96c3-138">不支持使用 Skype ID 或电话号码搜索 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="e96c3-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="e96c3-139">Skype 用户无法呼叫设置呼叫转移至其他用户号码、代理人号码或公共交换电话网络的团队用户 (PSTN) 号码。</span><span class="sxs-lookup"><span data-stu-id="e96c3-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="e96c3-140">仅支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e96c3-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="e96c3-141">不支持互操作性提升、群组通话和会议。</span><span class="sxs-lookup"><span data-stu-id="e96c3-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="e96c3-142">代理不支持代表团队用户呼叫 Skype 用户的能力。</span><span class="sxs-lookup"><span data-stu-id="e96c3-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="e96c3-143">不支持与聊天的屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="e96c3-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="e96c3-144">设置团队用户是否可以与 Skype 用户进行通信</span><span class="sxs-lookup"><span data-stu-id="e96c3-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="e96c3-145">作为管理员，你可以使用 Microsoft 团队管理中心或 PowerShell 设置外部访问设置，以控制你的组织中的团队用户是否可以与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="e96c3-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="e96c3-146">默认情况下，对于新租户，此功能处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="e96c3-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="e96c3-147">但是，如果您的域尚未提供以下 DNS SRV 记录，则需要由 IT 管理员对其进行配置，例如 _sipfederationtls .com。</span><span class="sxs-lookup"><span data-stu-id="e96c3-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="e96c3-148">**服务** ： sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e96c3-148">**Service** : sipfederationtls</span></span><br/>
<span data-ttu-id="e96c3-149">**协议** ： TCP</span><span class="sxs-lookup"><span data-stu-id="e96c3-149">**Protocol** : TCP</span></span><br/>
<span data-ttu-id="e96c3-150">**优先级** ：100</span><span class="sxs-lookup"><span data-stu-id="e96c3-150">**Priority** : 100</span></span><br/>
<span data-ttu-id="e96c3-151">**重量** ：1</span><span class="sxs-lookup"><span data-stu-id="e96c3-151">**Weight** : 1</span></span><br/>
<span data-ttu-id="e96c3-152">**端口** ：5061</span><span class="sxs-lookup"><span data-stu-id="e96c3-152">**Port** : 5061</span></span><br/>
<span data-ttu-id="e96c3-153">**目标** ： sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e96c3-153">**Target** : sipfed.online.lync.com</span></span>

<span data-ttu-id="e96c3-154">如果您从 Skype for Business 升级到团队，您在 Skype for business 管理中心配置的外部通信设置将迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="e96c3-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e96c3-155">在 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="e96c3-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="e96c3-156">在 "Microsoft 团队管理中心" 中，转到 " **组织范围的设置**  >  **外部访问** "，然后打开 " **用户可以与 Skype 用户通信** "。</span><span class="sxs-lookup"><span data-stu-id="e96c3-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access** , and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="e96c3-157">有关如何配置此和其他外部访问设置的分步指导，请参阅 [管理团队中的外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)。</span><span class="sxs-lookup"><span data-stu-id="e96c3-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e96c3-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e96c3-158">Using PowerShell</span></span>

<span data-ttu-id="e96c3-159">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e96c3-159">Do the following:</span></span> 
1. <span data-ttu-id="e96c3-160">将 [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与参数结合使用 ```EnablePublicCloudAccess``` ，以控制用户是否可以与 Skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e96c3-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="e96c3-161">设置参数以 ```true``` 允许团队用户与 Skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="e96c3-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="e96c3-162">可以使用该 ```EnablePublicCloudAudioVideoAccess``` 参数启用/禁用音频/视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="e96c3-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="e96c3-163">将 [CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与设置的参数结合使用， ```Provider``` ```"WindowsLive"``` 以便团队用户可以与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="e96c3-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e96c3-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="e96c3-164">Related topics</span></span>

- [<span data-ttu-id="e96c3-165">管理团队中的外部访问</span><span class="sxs-lookup"><span data-stu-id="e96c3-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="e96c3-166">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="e96c3-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
