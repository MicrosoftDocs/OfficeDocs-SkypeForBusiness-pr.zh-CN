---
title: Teams和Skype互操作性
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
description: 了解组织中用户与Teams使用者用户Skype (互操作性) 功能。
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093952"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="ca9af-103">Teams和Skype互操作性</span><span class="sxs-lookup"><span data-stu-id="ca9af-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="ca9af-104">本文概述了使用者与使用者之间Microsoft Teams Skype (互操作性) 。</span><span class="sxs-lookup"><span data-stu-id="ca9af-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="ca9af-105">了解如何Teams用户Skype用户可以通过聊天和呼叫以及所应用的管理控件进行通信。</span><span class="sxs-lookup"><span data-stu-id="ca9af-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="ca9af-106">Teams组织的用户可以使用其电子邮件地址Skype聊天和呼叫用户，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ca9af-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="ca9af-107">Teams用户可以搜索并启动一对一纯文本对话或与用户进行的音频/视频Skype通话。</span><span class="sxs-lookup"><span data-stu-id="ca9af-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="ca9af-108">Skype用户可以搜索并启动一对一纯文本对话或与用户进行的音频/视频Teams通话。</span><span class="sxs-lookup"><span data-stu-id="ca9af-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="ca9af-109">这些功能在 Android 和 iOS (桌面、Web 和移动设备上) 客户端Teams Skype。</span><span class="sxs-lookup"><span data-stu-id="ca9af-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="ca9af-110">为获得最佳体验，我们建议Skype 8.58 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="ca9af-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="ca9af-111">本文Teams和 Skype 互操作功能在 GCC、GCC High 或 DOD 部署或私有云环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="ca9af-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="ca9af-112">聊天和通话体验</span><span class="sxs-lookup"><span data-stu-id="ca9af-112">Chat and calling experience</span></span>

<span data-ttu-id="ca9af-113">下面是聊天和通话体验的概述。</span><span class="sxs-lookup"><span data-stu-id="ca9af-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="ca9af-114">Teams用户启动与用户聊天或Skype通话</span><span class="sxs-lookup"><span data-stu-id="ca9af-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="ca9af-115">Teams用户可以通过Skype聊天或搜索栏中键入其电子邮件地址来搜索用户。</span><span class="sxs-lookup"><span data-stu-id="ca9af-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="ca9af-116">然后Teams用户可以在搜索结果中选择Skype用户以开始聊天或呼叫他们。</span><span class="sxs-lookup"><span data-stu-id="ca9af-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="ca9af-117">用户Skype选择不显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="ca9af-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="ca9af-118">在这种情况下，它们不会显示在搜索的搜索结果中Teams Teams用户无法找到它们。</span><span class="sxs-lookup"><span data-stu-id="ca9af-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="ca9af-119">Skype用户启动与用户聊天或Teams通话</span><span class="sxs-lookup"><span data-stu-id="ca9af-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="ca9af-120">Skype用户可以使用其电子邮件地址搜索Teams用户开始聊天。</span><span class="sxs-lookup"><span data-stu-id="ca9af-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="ca9af-121">通知Teams用户有来自新用户的新Skype，并且必须首先接受该消息，然后才能答复它。</span><span class="sxs-lookup"><span data-stu-id="ca9af-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="ca9af-122">如果Teams选择"接受"，则接受对话，并且两个用户都可以聊天和呼叫对方。</span><span class="sxs-lookup"><span data-stu-id="ca9af-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="ca9af-123">如果Teams选择"阻止"，则会话将被阻止，来自该用户的后续消息Skype调用将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ca9af-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="ca9af-124">如果用户Teams"查看消息"，消息会显示在 Teams 中，这有助于用户决定是接受还是阻止对话。</span><span class="sxs-lookup"><span data-stu-id="ca9af-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="ca9af-125">如果你从 Skype for Business 升级到 Teams 并且你的用户进入 Teams 仅模式，则来自 Skype 用户的聊天和呼叫将传递到 Teams 用户Teams。</span><span class="sxs-lookup"><span data-stu-id="ca9af-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="ca9af-126">如果你的用户在群岛模式下，来自Skype用户的聊天Teams呼叫将传递到Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="ca9af-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="ca9af-127">Teams用户阻止或取消阻止Skype用户</span><span class="sxs-lookup"><span data-stu-id="ca9af-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="ca9af-128">在Teams用户接受或阻止来自用户的初始Skype请求后，他们可以选择随时阻止或取消阻止该用户。</span><span class="sxs-lookup"><span data-stu-id="ca9af-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="ca9af-129">他们可以在对话中或在对话中的隐私设置中Teams。</span><span class="sxs-lookup"><span data-stu-id="ca9af-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="ca9af-130">Skype用户不会知道他们已被阻止。</span><span class="sxs-lookup"><span data-stu-id="ca9af-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="ca9af-131">阻止Skype用户以及其他人和公共电话交换网 (PSTN) 电话号码（Teams 用户已被阻止）列在 Teams 中用户的阻止联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="ca9af-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="ca9af-132">限制</span><span class="sxs-lookup"><span data-stu-id="ca9af-132">Limitations</span></span>

- <span data-ttu-id="ca9af-133">对话是纯文本对话。</span><span class="sxs-lookup"><span data-stu-id="ca9af-133">Conversations are text-only.</span></span> <span data-ttu-id="ca9af-134">这意味着没有丰富的格式、@mentions、表情符号或其他任何在本机聊天体验中可用的Teams[功能](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ca9af-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="ca9af-135">对话是一对一的。</span><span class="sxs-lookup"><span data-stu-id="ca9af-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="ca9af-136">不支持群组聊天。</span><span class="sxs-lookup"><span data-stu-id="ca9af-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="ca9af-137">Teams用户Skype用户无法看到对方的状态。</span><span class="sxs-lookup"><span data-stu-id="ca9af-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="ca9af-138">不支持使用Skype ID 或电话号码Skype搜索用户。</span><span class="sxs-lookup"><span data-stu-id="ca9af-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="ca9af-139">Skype用户无法呼叫设置了呼叫Teams其他用户号码、代理人号码或公用电话交换网 (PSTN) 号码的用户。</span><span class="sxs-lookup"><span data-stu-id="ca9af-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="ca9af-140">仅支持语音邮件。</span><span class="sxs-lookup"><span data-stu-id="ca9af-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="ca9af-141">不支持互操作升级、群组通话和会议。</span><span class="sxs-lookup"><span data-stu-id="ca9af-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="ca9af-142">不支持代理人代表Skype呼叫用户Teams权限。</span><span class="sxs-lookup"><span data-stu-id="ca9af-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="ca9af-143">不支持通过聊天进行屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="ca9af-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="ca9af-144">设置Teams用户是否可以与Skype通信</span><span class="sxs-lookup"><span data-stu-id="ca9af-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="ca9af-145">作为管理员，可以使用 Microsoft Teams 管理中心或 PowerShell 设置外部访问设置，控制Teams用户是否可以与Skype通信。</span><span class="sxs-lookup"><span data-stu-id="ca9af-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="ca9af-146">默认情况下，此功能已针对新租户启用。</span><span class="sxs-lookup"><span data-stu-id="ca9af-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="ca9af-147">但是，有一个先决条件是，以下 DNS SRV 记录需要由 IT 管理员配置（如果尚未适用于你的域，例如 _sipfederationtls.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ca9af-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="ca9af-148">**服务**：sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ca9af-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="ca9af-149">**协议**：TCP</span><span class="sxs-lookup"><span data-stu-id="ca9af-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="ca9af-150">**优先级**：100</span><span class="sxs-lookup"><span data-stu-id="ca9af-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="ca9af-151">**权重**：1</span><span class="sxs-lookup"><span data-stu-id="ca9af-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="ca9af-152">**端口**：5061</span><span class="sxs-lookup"><span data-stu-id="ca9af-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="ca9af-153">**目标**：sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ca9af-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="ca9af-154">如果从 Skype for Business 升级到 Teams，在 Skype for Business 管理中心配置的外部通信设置将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="ca9af-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="ca9af-155">在 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="ca9af-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="ca9af-156">在Microsoft Teams管理中心，转到"**组织范围的** 设置""外部访问"，然后打开"用户可以与Skype  >  **通信"。**</span><span class="sxs-lookup"><span data-stu-id="ca9af-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="ca9af-157">有关如何配置此设置和其他外部访问设置的分步指南，请参阅在 Teams 中管理[外部访问](./manage-external-access.md#allow-or-block-domains)。</span><span class="sxs-lookup"><span data-stu-id="ca9af-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="ca9af-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca9af-158">Using PowerShell</span></span>

<span data-ttu-id="ca9af-159">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ca9af-159">Do the following:</span></span> 
1. <span data-ttu-id="ca9af-160">将[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet 与 参数一起Teams用户是否可以与 ```EnablePublicCloudAccess``` Skype通信。</span><span class="sxs-lookup"><span data-stu-id="ca9af-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="ca9af-161">将 参数设置为 ```true``` 可让Teams与用户Skype通信。</span><span class="sxs-lookup"><span data-stu-id="ca9af-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="ca9af-162">可以使用 参数 ```EnablePublicCloudAudioVideoAccess``` 来启用/禁用音频/视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="ca9af-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="ca9af-163">将[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet 与参数设置为 一起Teams，以便用户能够 ```Provider``` ```"WindowsLive"``` 与Skype通信。</span><span class="sxs-lookup"><span data-stu-id="ca9af-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca9af-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="ca9af-164">Related topics</span></span>

- [<span data-ttu-id="ca9af-165">管理 Teams 中的外部Teams</span><span class="sxs-lookup"><span data-stu-id="ca9af-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="ca9af-166">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="ca9af-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)