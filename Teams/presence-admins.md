---
title: Teams 中的用户状态
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 向管理员介绍了 Teams 中的用户状态。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863193"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="9cf7b-103">Teams 中的用户状态</span><span class="sxs-lookup"><span data-stu-id="9cf7b-103">User presence in Teams</span></span>

<span data-ttu-id="9cf7b-104">状态显示在 Microsoft Teams（以及整个 Office 365）的用户配置文件中，用于向其他用户指明用户的当前状态。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="9cf7b-105">默认情况下，使用 Teams 的组织中的任何人都可以（几乎实时）查看其他用户是否在线。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cf7b-106">如果在将用户移动到“仅 Teams”\*\*\*\* 模式后卸载 Skype for Business 客户端，则在 Outlook 和其他 Office 应用程序中，状态将停止工作。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="9cf7b-107">状态在 Teams 中显示良好。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-107">Presence works fine in Teams.</span></span> <span data-ttu-id="9cf7b-108">解决方法：若要在 Outlook（和其他 Office 应用）中查看状态，必须安装 Skype for Business，即使是在“仅 Teams”\*\*\*\* 模式下运行 Teams，也不例外。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="9cf7b-109">Microsoft 已发现此问题，并正在着手修复它。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="9cf7b-110">Outlook 2013 桌面应用及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="9cf7b-111">Teams 中的状态</span><span class="sxs-lookup"><span data-stu-id="9cf7b-111">Presence states in Teams</span></span>

<span data-ttu-id="9cf7b-112">Teams 中的用户状态如下：</span><span class="sxs-lookup"><span data-stu-id="9cf7b-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="9cf7b-113">用户配置</span><span class="sxs-lookup"><span data-stu-id="9cf7b-113">User configured</span></span>|<span data-ttu-id="9cf7b-114">应用配置</span><span class="sxs-lookup"><span data-stu-id="9cf7b-114">App configured</span></span>|
|:--- |:---|
| ![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="9cf7b-116">在线</span><span class="sxs-lookup"><span data-stu-id="9cf7b-116">Available</span></span>|![实心绿色复选标记，表示在线状态](media/Presence_Available.png) <span data-ttu-id="9cf7b-118">在线</span><span class="sxs-lookup"><span data-stu-id="9cf7b-118">Available</span></span>|
|| ![空心绿色复选标记，表示在线但外出](media/Presence_Available_OOF.png) <span data-ttu-id="9cf7b-120">在线但外出</span><span class="sxs-lookup"><span data-stu-id="9cf7b-120">Available, Out of Office</span></span> |
|  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="9cf7b-122">忙碌</span><span class="sxs-lookup"><span data-stu-id="9cf7b-122">Busy</span></span> |  ![实心红色圆圈，表示忙碌](media/Presence_Busy.png) <span data-ttu-id="9cf7b-124">忙碌</span><span class="sxs-lookup"><span data-stu-id="9cf7b-124">Busy</span></span>  |
|| ![实心红色圆圈，表示通话忙](media/Presence_Busy.png) <span data-ttu-id="9cf7b-126">通话中</span><span class="sxs-lookup"><span data-stu-id="9cf7b-126">On a call</span></span>|
|| ![实心红色圆圈，表示开会忙](media/Presence_Busy.png) <span data-ttu-id="9cf7b-128">会议中</span><span class="sxs-lookup"><span data-stu-id="9cf7b-128">In a meeting</span></span> |
|| ![空心红色圆圈，表示忙碌](media/Presence_Busy_OOF.png) <span data-ttu-id="9cf7b-130">通话中但外出</span><span class="sxs-lookup"><span data-stu-id="9cf7b-130">On a call, out of office</span></span>|
|  ![带白线的红色圆圈，表示请勿打扰](media/Presence_DND.png) <span data-ttu-id="9cf7b-132">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="9cf7b-132">Do not disturb</span></span> ||
|| ![带白线的红色圆圈，表示正在演示](media/Presence_DND.png) <span data-ttu-id="9cf7b-134">正在演示</span><span class="sxs-lookup"><span data-stu-id="9cf7b-134">Presenting</span></span>|
|| ![带白线的红色圆圈，表示专注](media/Presence_DND.png) <span data-ttu-id="9cf7b-136">专注</span><span class="sxs-lookup"><span data-stu-id="9cf7b-136">Focusing</span></span>|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="9cf7b-138">离开</span><span class="sxs-lookup"><span data-stu-id="9cf7b-138">Away</span></span>| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="9cf7b-140">离开</span><span class="sxs-lookup"><span data-stu-id="9cf7b-140">Away</span></span>|
|| <span data-ttu-id="9cf7b-141">![黄色时钟图标，表示离开](media/Presence_Away.png)上次上线*时间*离开</span><span class="sxs-lookup"><span data-stu-id="9cf7b-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色时钟图标，表示离开但马上回来](media/Presence_Away.png) <span data-ttu-id="9cf7b-143">马上回来</span><span class="sxs-lookup"><span data-stu-id="9cf7b-143">Be right back</span></span>| |
|| ![黄色时钟图标，表示下班离开](media/Presence_Away.png)  <span data-ttu-id="9cf7b-145">下班</span><span class="sxs-lookup"><span data-stu-id="9cf7b-145">Off Work</span></span>|
|| ![带 x 的灰色圆圈，表示离线](media/Presence_Offline.png) <span data-ttu-id="9cf7b-147">离线</span><span class="sxs-lookup"><span data-stu-id="9cf7b-147">Offline</span></span> |
|| ![空心灰色圆圈，表示未知状态](media/Presence_Unknown.png) <span data-ttu-id="9cf7b-149">未知状态</span><span class="sxs-lookup"><span data-stu-id="9cf7b-149">Status unknown</span></span>|
||![带对角线的空心红色圆圈，表示已屏蔽](media/Presence_Blocked.png) <span data-ttu-id="9cf7b-151">已屏蔽</span><span class="sxs-lookup"><span data-stu-id="9cf7b-151">Blocked</span></span> |
|| ![带箭头的紫色圆圈，表示外出](media/Presence_OOF.png) <span data-ttu-id="9cf7b-153">外出</span><span class="sxs-lookup"><span data-stu-id="9cf7b-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="9cf7b-154">用户可以手动将自己的当前状态设置为某些选项，他们的状态会反映给其他所有用户。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="9cf7b-155">更多用户状态详细信息也会自动更新。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="9cf7b-156">根据用户活动（在线、离开）、Outlook 日历状态（会议中）或 Teams 应用状态（通话中、正在演示）更改为列表中缩进的状态。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="9cf7b-157">有 15 分钟的非活动超时，超过此时间就会将当前状态重置为“离开”。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="9cf7b-158">用户会在 Teams 中收到发送给他们的所有聊天消息，而不管其状态如何。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="9cf7b-159">如果用户在某人向其发送消息时处于离线状态，便会在下次在线时在 Teams 中看到聊天消息。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="9cf7b-160">如果用户处于“请勿打扰”状态，用户仍会收到聊天消息，但不会看到横幅通知。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="9cf7b-161">用户在所有状态下都可以接听来电，但“请勿打扰”状态除外，在这种状态下，来电会转接到语音信箱。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="9cf7b-162">如果呼叫接收人屏蔽了呼叫方，来电不会转接，且呼叫方会看到呼叫接收人的状态为“离线”。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="9cf7b-163">用户可以在 Teams 中依次转到“设置”\*\*\*\* > “隐私”\*\*\*\*，向自己的优先访问列表添加人员。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="9cf7b-164">添加到优先访问列表的人员可以联系用户，即使用户处于“请勿打扰”状态，也不例外。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="9cf7b-165">比较 Teams 与 Skype for Business 中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="9cf7b-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="9cf7b-166">以下管理员设置在 Skype for Business 和 Teams 中是不同的：</span><span class="sxs-lookup"><span data-stu-id="9cf7b-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="9cf7b-167">在 Teams 中，状态共享对组织中的用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="9cf7b-168">Teams 中没有隐私（定义了谁能看到状态）配置。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="9cf7b-169">在 Teams 中，“与所有人(包括联合服务)共享状态”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="9cf7b-170">在“聊天”>“联系人”\*\*\*\* 或“通话”>“联系人”\*\*\*\* 下，可以看到用户的联系人列表（如果 Skype for Business 中有）。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="9cf7b-171">在 Teams 中，“客户端请勿打扰”和“特许”功能对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="9cf7b-172">如果 Teams 已与 Outlook 集成，“日历(包括外出和其他日历信息)集成”对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="9cf7b-173">如果组织还使用 Skype for Business，在 Teams 中“上次上线”\*\* 或“离开时间”\*\* 指示器对用户始终是启用的。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf7b-174">暂不支持 Teams 管理员自定义这些设置。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="9cf7b-175">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="9cf7b-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="9cf7b-176">若要详细了解 Teams 状态如何在组织还使用 Skype for Business 时发挥作用，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="9cf7b-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
