---
title: Teams 中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: 信息管理员需要了解有关在团队中的状态。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75710a428273a38954de38ef5b6094d412aa3085
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640967"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="fd240-103">Teams 中的用户状态</span><span class="sxs-lookup"><span data-stu-id="fd240-103">User Presence in Teams</span></span>

<span data-ttu-id="fd240-104">状态的用户配置文件中的 Microsoft 团队 （和整个 Office 365） – 的一部分，指示用户的当前的可用性和向组织中的其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="fd240-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="fd240-105">默认情况下使用团队您组织中的任何人都可以看到联机其他用户时可用。</span><span class="sxs-lookup"><span data-stu-id="fd240-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="fd240-106">团队中的状态</span><span class="sxs-lookup"><span data-stu-id="fd240-106">Presence states in Teams</span></span>

<span data-ttu-id="fd240-107">在工作组中可用的用户显示状态是：</span><span class="sxs-lookup"><span data-stu-id="fd240-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="fd240-108">配置用户</span><span class="sxs-lookup"><span data-stu-id="fd240-108">User configured</span></span>|<span data-ttu-id="fd240-109">应用程序配置</span><span class="sxs-lookup"><span data-stu-id="fd240-109">App configured</span></span>|
|:--- |:---|
| ![状态可用](media/Presence_Available.png) <span data-ttu-id="fd240-111">有空</span><span class="sxs-lookup"><span data-stu-id="fd240-111">Available</span></span>|![状态可用](media/Presence_Available.png) <span data-ttu-id="fd240-113">有空</span><span class="sxs-lookup"><span data-stu-id="fd240-113">Available</span></span>|
|| ![可用 oof](media/Presence_Available_OOF.png) <span data-ttu-id="fd240-115">可用外出</span><span class="sxs-lookup"><span data-stu-id="fd240-115">Available, Out of Office</span></span> |
|  ![忙](media/Presence_Busy.png) <span data-ttu-id="fd240-117">忙</span><span class="sxs-lookup"><span data-stu-id="fd240-117">Busy</span></span> |  ![忙](media/Presence_Busy.png) <span data-ttu-id="fd240-119">忙</span><span class="sxs-lookup"><span data-stu-id="fd240-119">Busy</span></span>  |
|| ![忙](media/Presence_Busy.png) <span data-ttu-id="fd240-121">呼叫中</span><span class="sxs-lookup"><span data-stu-id="fd240-121">In a call</span></span>|
|| ![忙](media/Presence_Busy.png) <span data-ttu-id="fd240-123">在会议中</span><span class="sxs-lookup"><span data-stu-id="fd240-123">In a meeting</span></span> |
|| ![忙 oof](media/Presence_Busy_OOF.png) <span data-ttu-id="fd240-125">在调用中，不在办公室</span><span class="sxs-lookup"><span data-stu-id="fd240-125">In a call, out of office</span></span>|
|  ![请勿打扰](media/Presence_DND.png) <span data-ttu-id="fd240-127">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="fd240-127">Do not disturb</span></span> ||
|| ![请勿打扰](media/Presence_DND.png) <span data-ttu-id="fd240-129">演示</span><span class="sxs-lookup"><span data-stu-id="fd240-129">Presenting</span></span>|
| ![离开](media/Presence_Away.png) <span data-ttu-id="fd240-131">离开</span><span class="sxs-lookup"><span data-stu-id="fd240-131">Away</span></span>| ![离开](media/Presence_Away.png) <span data-ttu-id="fd240-133">离开</span><span class="sxs-lookup"><span data-stu-id="fd240-133">Away</span></span>|
|| <span data-ttu-id="fd240-134">![离开](media/Presence_Away.png)离开最后一个看到*时间*</span><span class="sxs-lookup"><span data-stu-id="fd240-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![离开](media/Presence_Away.png) <span data-ttu-id="fd240-136">马上回来</span><span class="sxs-lookup"><span data-stu-id="fd240-136">Be right back</span></span>| |
|| ![离开](media/Presence_Away.png)  <span data-ttu-id="fd240-138">Off Work-下班</span><span class="sxs-lookup"><span data-stu-id="fd240-138">Off Work</span></span>|
|| ![脱机](media/Presence_Offline.png) <span data-ttu-id="fd240-140">脱机</span><span class="sxs-lookup"><span data-stu-id="fd240-140">Offline</span></span> |
|| ![未知](media/Presence_Unknown.png) <span data-ttu-id="fd240-142">状态未知</span><span class="sxs-lookup"><span data-stu-id="fd240-142">Status unknown</span></span>|
||![被阻止](media/Presence_Blocked.png) <span data-ttu-id="fd240-144">已阻止</span><span class="sxs-lookup"><span data-stu-id="fd240-144">Blocked</span></span> |
|| ![外出](media/Presence_OOF.png) <span data-ttu-id="fd240-146">外出</span><span class="sxs-lookup"><span data-stu-id="fd240-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="fd240-147">用户可以手动将其当前的状态设置为一些选项，并向所有其他用户获取反映其状态。</span><span class="sxs-lookup"><span data-stu-id="fd240-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="fd240-148">此外会自动基于用户活动 （如空闲或离开）、 Outlook 日历状态 （例如，如会议中所示） 或团队应用程序状态更新其他用户状态详细信息 (呼叫中，演示)，对列表中缩进的状态。</span><span class="sxs-lookup"><span data-stu-id="fd240-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="fd240-149">为 15 分钟无活动超时，其后用户的当前状态将重置为离开。</span><span class="sxs-lookup"><span data-stu-id="fd240-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="fd240-150">用户可以指定谁可以直拨 （联系它们替代请勿打扰的设置）。</span><span class="sxs-lookup"><span data-stu-id="fd240-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="fd240-151">这些设置是可在应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd240-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="fd240-152">不 for Business 的 Skype 团队。</span><span class="sxs-lookup"><span data-stu-id="fd240-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="fd240-153">Skype for Business 中的以下管理设置是团队中的不同：</span><span class="sxs-lookup"><span data-stu-id="fd240-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="fd240-154">状态始终启用共享团队中的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="fd240-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="fd240-155">隐私 （确定谁可以看到的状态） 配置不在工作组中可用。</span><span class="sxs-lookup"><span data-stu-id="fd240-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="fd240-156">团队中的用户始终启用共享与所有人 （包括联盟服务） 的状态。</span><span class="sxs-lookup"><span data-stu-id="fd240-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="fd240-157">可见或**呼叫 > 联系人**下**聊天 > 联系人**其联系人列表 （如果有一个 SfB 中）。</span><span class="sxs-lookup"><span data-stu-id="fd240-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="fd240-158">团队中的用户始终启用客户端请勿打扰和突破性的功能。</span><span class="sxs-lookup"><span data-stu-id="fd240-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="fd240-159">（包括 OOF & 其他日历信息） 的日历集成始终启用团队中的用户，如果与 Outlook 集成。</span><span class="sxs-lookup"><span data-stu-id="fd240-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="fd240-160">*上一次发现*或*离开相*（如果使用 Skype for Business 的双环境中） 标记始终启用团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="fd240-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>
- <span data-ttu-id="fd240-161">未启用团队中的用户设置自定义状态。</span><span class="sxs-lookup"><span data-stu-id="fd240-161">Setting a custom presence status is not enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="fd240-162">当前不支持团队管理员能够自定义这些设置。</span><span class="sxs-lookup"><span data-stu-id="fd240-162">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="fd240-163">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="fd240-163">Coexistence with Skype for Business</span></span>

<span data-ttu-id="fd240-164">有关与 for Business 的 Skype 共存时，团队状态的工作方式的详细信息，请参阅[使用 Skype for Business 的共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="fd240-164">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 