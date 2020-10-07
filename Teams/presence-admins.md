---
title: Teams 中的用户状态
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 了解团队中的状态状态以及状态功能的管理设置。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369207"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="95df6-103">Teams 中的用户状态</span><span class="sxs-lookup"><span data-stu-id="95df6-103">User presence in Teams</span></span>

<span data-ttu-id="95df6-104">"状态" 是 Microsoft 团队中的用户配置文件的一部分 (和整个 Microsoft 365 或 Office 365) ，用于指示用户的当前可用性和其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="95df6-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="95df6-105">默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。</span><span class="sxs-lookup"><span data-stu-id="95df6-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="95df6-106">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="95df6-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="95df6-107">有关不同平台上的团队用户配置文件的详细信息，请参阅 [按平台的团队功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="95df6-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="95df6-108">Teams 中的状态</span><span class="sxs-lookup"><span data-stu-id="95df6-108">Presence states in Teams</span></span>

|<span data-ttu-id="95df6-109">用户配置</span><span class="sxs-lookup"><span data-stu-id="95df6-109">User configured</span></span>|<span data-ttu-id="95df6-110">应用配置</span><span class="sxs-lookup"><span data-stu-id="95df6-110">App configured</span></span>|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="95df6-112">在线</span><span class="sxs-lookup"><span data-stu-id="95df6-112">Available</span></span>|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="95df6-114">在线</span><span class="sxs-lookup"><span data-stu-id="95df6-114">Available</span></span>|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) <span data-ttu-id="95df6-116">在线但外出</span><span class="sxs-lookup"><span data-stu-id="95df6-116">Available, Out of Office</span></span> |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="95df6-118">忙碌</span><span class="sxs-lookup"><span data-stu-id="95df6-118">Busy</span></span> |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="95df6-120">忙碌</span><span class="sxs-lookup"><span data-stu-id="95df6-120">Busy</span></span>  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) <span data-ttu-id="95df6-122">通话中</span><span class="sxs-lookup"><span data-stu-id="95df6-122">On a call</span></span>|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) <span data-ttu-id="95df6-124">会议中</span><span class="sxs-lookup"><span data-stu-id="95df6-124">In a meeting</span></span> |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="95df6-126">通话中但外出</span><span class="sxs-lookup"><span data-stu-id="95df6-126">On a call, out of office</span></span>|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) <span data-ttu-id="95df6-128">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="95df6-128">Do not disturb</span></span> ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) <span data-ttu-id="95df6-130">正在演示</span><span class="sxs-lookup"><span data-stu-id="95df6-130">Presenting</span></span>|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) <span data-ttu-id="95df6-132">专注</span><span class="sxs-lookup"><span data-stu-id="95df6-132">Focusing</span></span>|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="95df6-134">离开</span><span class="sxs-lookup"><span data-stu-id="95df6-134">Away</span></span>| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="95df6-136">离开</span><span class="sxs-lookup"><span data-stu-id="95df6-136">Away</span></span>|
|| <span data-ttu-id="95df6-137">![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线*时间*离开</span><span class="sxs-lookup"><span data-stu-id="95df6-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) <span data-ttu-id="95df6-139">马上回来</span><span class="sxs-lookup"><span data-stu-id="95df6-139">Be right back</span></span>| |
|![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) <span data-ttu-id="95df6-141">显示为脱机</span><span class="sxs-lookup"><span data-stu-id="95df6-141">Appear offline</span></span> | ![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) <span data-ttu-id="95df6-143">离线</span><span class="sxs-lookup"><span data-stu-id="95df6-143">Offline</span></span>| |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) <span data-ttu-id="95df6-145">未知状态</span><span class="sxs-lookup"><span data-stu-id="95df6-145">Status unknown</span></span>|
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) <span data-ttu-id="95df6-147">外出</span><span class="sxs-lookup"><span data-stu-id="95df6-147">Out of Office</span></span>|
|||

<span data-ttu-id="95df6-148">应用配置的状态状态基于用户活动 (可用、离开) 、Outlook 日历状态 (在会议) 或团队应用状态 (在通话中，演示) 。</span><span class="sxs-lookup"><span data-stu-id="95df6-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="95df6-149">请注意，当你处于基于你的日历的焦点模式时，焦点将是用户在团队中看到的状态，但它将在其他产品中显示为 "请勿打扰"。</span><span class="sxs-lookup"><span data-stu-id="95df6-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="95df6-150">当您锁定计算机或计算机进入空闲或睡眠模式时，当前状态将更改为 "离开"。</span><span class="sxs-lookup"><span data-stu-id="95df6-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="95df6-151">在移动设备上，只要团队应用处于后台，你的状态将更改为 "离开"。</span><span class="sxs-lookup"><span data-stu-id="95df6-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="95df6-152">用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。</span><span class="sxs-lookup"><span data-stu-id="95df6-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="95df6-153">如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。</span><span class="sxs-lookup"><span data-stu-id="95df6-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="95df6-154">如果用户状态设置为 "请勿打扰"，则用户仍将收到聊天消息，但不显示标题通知。</span><span class="sxs-lookup"><span data-stu-id="95df6-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="95df6-155">用户接收除 "请勿打扰" 之外的所有状态的呼叫，传入呼叫转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="95df6-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="95df6-156">如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。</span><span class="sxs-lookup"><span data-stu-id="95df6-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="95df6-157">用户可以在 Teams 中依次转到“设置”\*\*\*\* > “隐私”\*\*\*\*，向自己的优先访问列表添加人员。</span><span class="sxs-lookup"><span data-stu-id="95df6-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="95df6-158">如果用户的状态设置为 "请勿打扰"，则具有优先级访问权限的人员可以联系用户。</span><span class="sxs-lookup"><span data-stu-id="95df6-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="95df6-159">用户配置状态过期</span><span class="sxs-lookup"><span data-stu-id="95df6-159">User configured states expiration</span></span>
<span data-ttu-id="95df6-160">当用户选择特定的状态时，它优先于任何应用活动更新。</span><span class="sxs-lookup"><span data-stu-id="95df6-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="95df6-161">例如，如果用户将她设置为 "请勿打扰"，她的状态将保持为 "请勿打扰"，即使她出席会议或接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="95df6-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="95df6-162">用户配置的状态在团队中具有默认过期设置，以防止用户显示一段时间后可能不相关的状态。</span><span class="sxs-lookup"><span data-stu-id="95df6-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="95df6-163">用户配置状态</span><span class="sxs-lookup"><span data-stu-id="95df6-163">User configured state</span></span>|<span data-ttu-id="95df6-164">默认过期</span><span class="sxs-lookup"><span data-stu-id="95df6-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="95df6-165">忙碌</span><span class="sxs-lookup"><span data-stu-id="95df6-165">Busy</span></span>|<span data-ttu-id="95df6-166">1天</span><span class="sxs-lookup"><span data-stu-id="95df6-166">1 day</span></span>|
| <span data-ttu-id="95df6-167">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="95df6-167">Do not disturb</span></span>|<span data-ttu-id="95df6-168">1天</span><span class="sxs-lookup"><span data-stu-id="95df6-168">1 day</span></span>|
| <span data-ttu-id="95df6-169">则</span><span class="sxs-lookup"><span data-stu-id="95df6-169">Others</span></span>|<span data-ttu-id="95df6-170">7天</span><span class="sxs-lookup"><span data-stu-id="95df6-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="95df6-171">比较 Teams 与 Skype for Business 中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="95df6-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="95df6-172">以下管理员设置在 Skype for Business 和 Teams 中是不同的：</span><span class="sxs-lookup"><span data-stu-id="95df6-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="95df6-173">在 Teams 中，状态共享对组织中的用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="95df6-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="95df6-174">Teams 中没有隐私（定义了谁能看到状态）配置。</span><span class="sxs-lookup"><span data-stu-id="95df6-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="95df6-175">在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="95df6-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="95df6-176">在“聊天”>“联系人”\*\*\*\* 或“通话”>“联系人”\*\*\*\* 下，可以看到用户的联系人列表（如果 Skype for Business 中有）。</span><span class="sxs-lookup"><span data-stu-id="95df6-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="95df6-177">在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="95df6-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="95df6-178">如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="95df6-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="95df6-179">如果组织还使用 Skype for Business，在 Teams 中“上次上线”\*\* 或“离开时间”\*\* 指示器对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="95df6-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="95df6-180">暂不支持 Teams 管理员自定义这些设置。</span><span class="sxs-lookup"><span data-stu-id="95df6-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="95df6-181">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="95df6-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="95df6-182">若要详细了解 Teams 状态如何在组织还使用 Skype for Business 时发挥作用，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="95df6-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
