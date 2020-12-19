---
title: Teams 中的用户状态
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 了解 Teams 中的状态以及状态功能的管理设置。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff5a13d6b31527138b71d2ad3b2387f827933eda
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616946"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="d69b0-103">Teams 中的用户状态</span><span class="sxs-lookup"><span data-stu-id="d69b0-103">User presence in Teams</span></span>

<span data-ttu-id="d69b0-104">状态是 Microsoft Teams（和所有 Microsoft 365 或 Office 365）中用户配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="d69b0-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365).</span></span> <span data-ttu-id="d69b0-105">状态表示用户当前对其他用户的可用性和状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-105">Presence indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="d69b0-106">默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。</span><span class="sxs-lookup"><span data-stu-id="d69b0-106">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span> <span data-ttu-id="d69b0-107">当你在移动设备上刷新页面时，将在 Web 和桌面版本上实时更新状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-107">Presence is updated in real time on the web and desktop versions when you refresh the page on mobile.</span></span>

 > [!Note]
 > <span data-ttu-id="d69b0-108">有关不同平台上 Teams 用户配置文件的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="d69b0-108">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="d69b0-109">Teams 中的状态</span><span class="sxs-lookup"><span data-stu-id="d69b0-109">Presence states in Teams</span></span>

|<span data-ttu-id="d69b0-110">用户配置</span><span class="sxs-lookup"><span data-stu-id="d69b0-110">User configured</span></span>|<span data-ttu-id="d69b0-111">应用配置</span><span class="sxs-lookup"><span data-stu-id="d69b0-111">App configured</span></span>|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="d69b0-113">在线</span><span class="sxs-lookup"><span data-stu-id="d69b0-113">Available</span></span>|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="d69b0-115">在线</span><span class="sxs-lookup"><span data-stu-id="d69b0-115">Available</span></span>|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) <span data-ttu-id="d69b0-117">在线但外出。</span><span class="sxs-lookup"><span data-stu-id="d69b0-117">Available, Out of Office.</span></span> <span data-ttu-id="d69b0-118">注意：在用户设置“自动答复”的时间段内，将自动设置“外出”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-118">Note: Out of office is automatically set for the periods of time where the user sets "automatic replies".</span></span> <span data-ttu-id="d69b0-119">如果用户在这段时间内使用应用，则可能会显示双重状态，例如“在线但外出”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-119">If the user is using the app during these periods of time, a dual presence might be shown, such as "Out of office, available".</span></span> |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="d69b0-121">忙碌</span><span class="sxs-lookup"><span data-stu-id="d69b0-121">Busy</span></span> |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="d69b0-123">忙碌</span><span class="sxs-lookup"><span data-stu-id="d69b0-123">Busy</span></span>  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) <span data-ttu-id="d69b0-125">通话中</span><span class="sxs-lookup"><span data-stu-id="d69b0-125">In a call</span></span>|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) <span data-ttu-id="d69b0-127">会议中</span><span class="sxs-lookup"><span data-stu-id="d69b0-127">In a meeting</span></span> |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="d69b0-129">通话中但外出</span><span class="sxs-lookup"><span data-stu-id="d69b0-129">On a call, out of office</span></span>|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) <span data-ttu-id="d69b0-131">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="d69b0-131">Do not disturb</span></span> ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) <span data-ttu-id="d69b0-133">正在演示</span><span class="sxs-lookup"><span data-stu-id="d69b0-133">Presenting</span></span>|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) <span data-ttu-id="d69b0-135">专注。</span><span class="sxs-lookup"><span data-stu-id="d69b0-135">Focusing.</span></span> <span data-ttu-id="d69b0-136">当用户在日历的 MyAnalytics/Insights 中安排专注时间时，就会发生专注。</span><span class="sxs-lookup"><span data-stu-id="d69b0-136">Focus happens when the users schedule focus time in MyAnalytics/Insights in their calendars.</span></span>|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="d69b0-138">离开</span><span class="sxs-lookup"><span data-stu-id="d69b0-138">Away</span></span>| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="d69b0-140">离开</span><span class="sxs-lookup"><span data-stu-id="d69b0-140">Away</span></span>|
|| <span data-ttu-id="d69b0-141">![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线 *时间* 离开</span><span class="sxs-lookup"><span data-stu-id="d69b0-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) <span data-ttu-id="d69b0-143">马上回来</span><span class="sxs-lookup"><span data-stu-id="d69b0-143">Be right back</span></span>| |
|![带 x 的灰色圆圈，表示脱机](media/Presence_Offline.png) <span data-ttu-id="d69b0-145">显示为脱机</span><span class="sxs-lookup"><span data-stu-id="d69b0-145">Appear offline</span></span>|![带 x 的灰色圆圈，表示脱机](media/Presence_Offline.png) <span data-ttu-id="d69b0-147">脱机。</span><span class="sxs-lookup"><span data-stu-id="d69b0-147">Offline.</span></span>  <span data-ttu-id="d69b0-148">当用户在几分钟内未登录其任何设备时，他们将显示为脱机。</span><span class="sxs-lookup"><span data-stu-id="d69b0-148">When users aren't logged in on any of their devices for a few minutes, they appear offline.</span></span> | |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) <span data-ttu-id="d69b0-150">未知状态</span><span class="sxs-lookup"><span data-stu-id="d69b0-150">Status unknown</span></span>|
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) <span data-ttu-id="d69b0-152">外出。</span><span class="sxs-lookup"><span data-stu-id="d69b0-152">Out of Office.</span></span> <span data-ttu-id="d69b0-153">设置自动答复时，将使用“外出”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-153">Out of Office is used when an automatic reply is set.</span></span> <span data-ttu-id="d69b0-154">（仅适用于 Outlook。）</span><span class="sxs-lookup"><span data-stu-id="d69b0-154">(Available in Outlook only.)</span></span> |
|||

<span data-ttu-id="d69b0-155">应用配置的状态基于用户活动（在线、离开）、Outlook 日历状态（会议中）或 Teams 应用状态（通话中、正在演示）。</span><span class="sxs-lookup"><span data-stu-id="d69b0-155">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="d69b0-156">当根据你的日历，你正处于专注模式时，“**专注**”将是人们在 Teams 中看到的状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-156">When you're in focus mode based on your calendar, **Focusing** will be the state people see in Teams.</span></span> <span data-ttu-id="d69b0-157">在其他产品中，专注模式将显示为“**请勿打扰**”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-157">Focus mode will display as **Do not disturb** in other products.</span></span>

<span data-ttu-id="d69b0-158">当你锁定计算机或计算机进入空闲或睡眠模式时，你当前的状态将更改为“离开”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-158">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="d69b0-159">在移动设备上，每当 Teams 应用处于后台时，你的状态就会更改为“离开”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-159">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="d69b0-160">用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。</span><span class="sxs-lookup"><span data-stu-id="d69b0-160">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="d69b0-161">如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。</span><span class="sxs-lookup"><span data-stu-id="d69b0-161">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="d69b0-162">无论用户处于何种状态，他们都能在 Teams 中收到发送给他们的所有聊天消息。</span><span class="sxs-lookup"><span data-stu-id="d69b0-162">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="d69b0-163">用户在所有状态下都可以接听呼叫，但“请勿打扰”状态除外，在这种状态下，来电会转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="d69b0-163">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="d69b0-164">如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-164">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="d69b0-165">用户可以在 Teams 中依次转到“设置” > “隐私”，向自己的优先访问列表添加人员。</span><span class="sxs-lookup"><span data-stu-id="d69b0-165">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="d69b0-166">即使用户的状态设置为“请勿打扰”，拥有优先访问权限的人也可以与该用户联系。</span><span class="sxs-lookup"><span data-stu-id="d69b0-166">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

### <a name="dual-presence"></a><span data-ttu-id="d69b0-167">双重状态</span><span class="sxs-lookup"><span data-stu-id="d69b0-167">Dual presence</span></span>

  <span data-ttu-id="d69b0-168">状态对大多数用户的工作方式是由日历中的事件或设备事件（如呼叫）驱动的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-168">The way presence works for most users is motivated by the events in the calendar or device events, such as a call.</span></span> <span data-ttu-id="d69b0-169">用户可以通过手动设置状态来覆盖 UI 中的此状态，这些状态具有一定的过期时间。</span><span class="sxs-lookup"><span data-stu-id="d69b0-169">The user can override this status in the UI by manually setting states, which have some expiration time.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="d69b0-170">用户配置的状态过期</span><span class="sxs-lookup"><span data-stu-id="d69b0-170">User configured states expiration</span></span>

<span data-ttu-id="d69b0-171">当用户选择特定状态时，它优先于任何应用活动更新。</span><span class="sxs-lookup"><span data-stu-id="d69b0-171">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="d69b0-172">例如，如果用户将自己设置为“请勿打扰”，则即使她出席会议或接听电话，她的状态仍将保持为“请勿打扰”。</span><span class="sxs-lookup"><span data-stu-id="d69b0-172">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="d69b0-173">用户配置的状态在 Teams 中具有默认的过期设置，以防止用户在一段时间后显示可能不相关的状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-173">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="d69b0-174">用户配置的状态</span><span class="sxs-lookup"><span data-stu-id="d69b0-174">User configured state</span></span>|<span data-ttu-id="d69b0-175">默认到期时间</span><span class="sxs-lookup"><span data-stu-id="d69b0-175">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="d69b0-176">忙碌</span><span class="sxs-lookup"><span data-stu-id="d69b0-176">Busy</span></span>|<span data-ttu-id="d69b0-177">1 天</span><span class="sxs-lookup"><span data-stu-id="d69b0-177">1 day</span></span>|
| <span data-ttu-id="d69b0-178">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="d69b0-178">Do not disturb</span></span>|<span data-ttu-id="d69b0-179">1 天</span><span class="sxs-lookup"><span data-stu-id="d69b0-179">1 day</span></span>|
| <span data-ttu-id="d69b0-180">其他</span><span class="sxs-lookup"><span data-stu-id="d69b0-180">Others</span></span>|<span data-ttu-id="d69b0-181">7 天</span><span class="sxs-lookup"><span data-stu-id="d69b0-181">7 days</span></span>|
|||

> [!NOTE]
> <span data-ttu-id="d69b0-182">用户还可以手动配置其状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d69b0-182">A user can also configure manually a duration for her presence.</span></span> <span data-ttu-id="d69b0-183">例如，用户可以将自己设置为“显示为脱机”，直到明天早上。</span><span class="sxs-lookup"><span data-stu-id="d69b0-183">For instance, a user can set herself as Appear offline until tomorrow morning.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="d69b0-184">比较 Teams 与 Skype for Business 中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="d69b0-184">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="d69b0-185">以下管理员设置在 Skype for Business 和 Teams 中是不同的：</span><span class="sxs-lookup"><span data-stu-id="d69b0-185">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="d69b0-186">在 Teams 中，状态共享对组织中的用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-186">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="d69b0-187">Teams 中没有隐私（定义了谁能看到状态）配置。</span><span class="sxs-lookup"><span data-stu-id="d69b0-187">Privacy (where you define who can see presence) configuration isn't available in Teams.</span></span>
- <span data-ttu-id="d69b0-188">在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-188">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="d69b0-189">在“聊天”>“联系人”或“通话”>“联系人”下，可以看到用户的联系人列表（如果 Skype for Business 中有）。</span><span class="sxs-lookup"><span data-stu-id="d69b0-189">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="d69b0-190">在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-190">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="d69b0-191">如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-191">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="d69b0-192">如果组织还使用 Skype for Business，在 Teams 中“上次上线”或“离开时间”指示器对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="d69b0-192">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="d69b0-193">暂不支持 Teams 管理员自定义这些设置。</span><span class="sxs-lookup"><span data-stu-id="d69b0-193">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a><span data-ttu-id="d69b0-194">比较 Teams 与 Microsoft Outlook 中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="d69b0-194">Admin settings in Teams compared to Microsoft Outlook</span></span>

<span data-ttu-id="d69b0-195">对于同一组织中的联系人，Outlook 2013 桌面版及更高版本应用支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-195">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later for contacts in the same organization.</span></span>

<span data-ttu-id="d69b0-196">如果用户帐户的升级模式策略设置为 TeamsOnly，则 Outlook 将与 Teams 进行通信来获取状态。</span><span class="sxs-lookup"><span data-stu-id="d69b0-196">If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence.</span></span> <span data-ttu-id="d69b0-197">如果用户帐户未设置为 TeamsOnly，则 Outlook 将与 Skype for Business 进行通信。</span><span class="sxs-lookup"><span data-stu-id="d69b0-197">If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="d69b0-198">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="d69b0-198">Coexistence with Skype for Business</span></span>

<span data-ttu-id="d69b0-199">若要详细了解 Teams 状态如何在组织还使用 Skype for Business 时发挥作用，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="d69b0-199">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses Skype for Business.</span></span>
