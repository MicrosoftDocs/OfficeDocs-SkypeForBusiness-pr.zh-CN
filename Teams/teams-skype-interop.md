---
title: Teams 和 Skype 互操作性
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 了解组织中 Teams 用户与 Skype (Consumer) 互操作性。
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055644"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="ad4ed-103">Teams 和 Skype 互操作性</span><span class="sxs-lookup"><span data-stu-id="ad4ed-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="ad4ed-104">本文概述了 Microsoft Teams 与 Skype (Consumer) 之间的互操作性) 。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="ad4ed-105">了解 Teams 用户和 Skype 用户如何通过聊天和通话以及适用管理控件进行通信。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="ad4ed-106">你组织的 Teams 用户可以使用其电子邮件地址与 Skype 用户聊天和呼叫 Skype 用户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="ad4ed-107">Teams 用户可以搜索并开始与 Skype 用户进行一对一纯文本对话或音频/视频通话。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="ad4ed-108">Skype 用户可以搜索并启动一对一纯文本对话或与 Teams 用户的音频/视频通话。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="ad4ed-109">在 Android 和 iOS 客户端的桌面、web 和移动设备上 (Teams 和 Skype) 提供这些功能。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="ad4ed-110">为获得最佳体验，我们建议使用 Skype 版本 8.58 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="ad4ed-111">本文中讨论的 Teams 和 Skype 互操作功能在 GCC、GCC High 或 DOD 部署或私有云环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="ad4ed-112">聊天和通话体验</span><span class="sxs-lookup"><span data-stu-id="ad4ed-112">Chat and calling experience</span></span>

<span data-ttu-id="ad4ed-113">下面是聊天和通话体验的概述。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="ad4ed-114">Teams 用户启动与 Skype 用户的聊天或通话</span><span class="sxs-lookup"><span data-stu-id="ad4ed-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="ad4ed-115">Teams 用户可以通过在新聊天或搜索栏中键入其电子邮件地址来搜索 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="ad4ed-116">然后，Teams 用户可以在搜索结果中选择 Skype 用户以开始聊天或呼叫他们。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="ad4ed-117">Skype 用户可能会选择不在搜索结果中显示。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="ad4ed-118">在这种情况下，它们不会显示在 Teams 的搜索结果中，而 Teams 用户无法找到它们。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="ad4ed-119">Skype 用户启动与 Teams 用户的聊天或通话</span><span class="sxs-lookup"><span data-stu-id="ad4ed-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="ad4ed-120">Skype 用户可以使用 Teams 用户的电子邮件地址搜索并开始与 Teams 用户聊天。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="ad4ed-121">Teams 用户收到来自 Skype 用户的新消息的通知，并且必须首先接受该消息，然后才能回复消息。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="ad4ed-122">如果 Teams 用户选择 **"接受**"，则接受对话，并且两个用户都可以聊天和呼叫对方。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="ad4ed-123">如果 Teams **用户选择"** 阻止"，则对话将被阻止，来自该 Skype 用户的后续消息和呼叫将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="ad4ed-124">如果 Teams 用户选择" **查看** 消息"，消息会显示在 Teams 中，这有助于用户决定是接受还是阻止对话。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="ad4ed-125">如果你从 Skype for Business 升级到 Teams，并且你的用户为"仅 Teams"模式，则 Skype 用户与 Teams 用户的聊天和通话将传递到 Teams。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="ad4ed-126">如果你的用户在群岛模式下，Skype 用户与 Teams 用户的聊天和通话将传递到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="ad4ed-127">Teams 用户阻止或取消阻止 Skype 用户</span><span class="sxs-lookup"><span data-stu-id="ad4ed-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="ad4ed-128">Teams 用户接受或阻止 Skype 用户的初始对话请求后，他们可以选择随时阻止或取消阻止该用户。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="ad4ed-129">他们可以在对话中或在 Teams 中的隐私设置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="ad4ed-130">Skype 用户不会知道他们已被阻止。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="ad4ed-131">Teams 中已阻止的 Skype 用户以及其他人和公共电话交换网 (PSTN) 电话号码将列在 Teams 中用户阻止的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="ad4ed-132">限制</span><span class="sxs-lookup"><span data-stu-id="ad4ed-132">Limitations</span></span>

- <span data-ttu-id="ad4ed-133">对话仅包含文本。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-133">Conversations are text-only.</span></span> <span data-ttu-id="ad4ed-134">这意味着没有丰富的格式、@mentions、表情符号或其他任何可在本机 Teams 聊天体验中 [提供的聊天功能](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="ad4ed-135">对话是一对一的。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="ad4ed-136">不支持群组聊天。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="ad4ed-137">Teams 用户和 Skype 用户无法看到彼此的存在状态。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="ad4ed-138">不支持使用 Skype ID 或电话号码搜索 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="ad4ed-139">Skype 用户无法呼叫设置了呼叫转发到其他用户号码、代理人号码或公用电话交换网的 Teams 用户 (PSTN) 号码。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="ad4ed-140">仅支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="ad4ed-141">不支持互操作升级、组呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="ad4ed-142">不支持代理人代表 Teams 用户呼叫 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="ad4ed-143">不支持通过聊天进行屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="ad4ed-144">设置 Teams 用户是否可以与 Skype 用户通信</span><span class="sxs-lookup"><span data-stu-id="ad4ed-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="ad4ed-145">作为管理员，可以使用 Microsoft Teams 管理中心或 PowerShell 设置外部访问设置，以控制你组织中 Teams 用户是否可以与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="ad4ed-146">默认情况下，此功能已针对新租户启用。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="ad4ed-147">但是，有一个先决条件是，以下 DNS SRV 记录需要由 IT 管理员配置（如果尚未可用于你的域，例如 _sipfederationtls.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="ad4ed-148">**服务**：sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ad4ed-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="ad4ed-149">**协议**：TCP</span><span class="sxs-lookup"><span data-stu-id="ad4ed-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="ad4ed-150">**优先级**：100</span><span class="sxs-lookup"><span data-stu-id="ad4ed-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="ad4ed-151">**权重**：1</span><span class="sxs-lookup"><span data-stu-id="ad4ed-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="ad4ed-152">**端口**：5061</span><span class="sxs-lookup"><span data-stu-id="ad4ed-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="ad4ed-153">**目标**：sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ad4ed-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="ad4ed-154">如果你从 Skype for Business 升级到 Teams，你在 Skype for Business 管理中心配置的外部通信设置将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ad4ed-155">在 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="ad4ed-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="ad4ed-156">在 Microsoft Teams 管理中心，转到 **组织范围的** 设置"外部访问"，然后打开"用户可以与  >  **Skype 用户通信"。**</span><span class="sxs-lookup"><span data-stu-id="ad4ed-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="ad4ed-157">有关如何配置此和其他外部访问设置的分步指南，请参阅"在 Teams 中管理[外部访问"。](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="ad4ed-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ad4ed-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad4ed-158">Using PowerShell</span></span>

<span data-ttu-id="ad4ed-159">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ad4ed-159">Do the following:</span></span> 
1. <span data-ttu-id="ad4ed-160">将 [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与参数一起用于控制 ```EnablePublicCloudAccess``` Teams 用户是否可以与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="ad4ed-161">设置参数以 ```true``` 允许 Teams 用户与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="ad4ed-162">可以使用该 ```EnablePublicCloudAudioVideoAccess``` 参数来启用/禁用音频/视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="ad4ed-163">将 [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与参数集一起使用，以便 ```Provider``` ```"WindowsLive"``` Teams 用户可以与 Skype 用户通信。</span><span class="sxs-lookup"><span data-stu-id="ad4ed-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad4ed-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad4ed-164">Related topics</span></span>

- [<span data-ttu-id="ad4ed-165">在 Teams 中管理外部访问</span><span class="sxs-lookup"><span data-stu-id="ad4ed-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="ad4ed-166">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="ad4ed-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
