---
title: 团队中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 信息管理员需要了解团队中的状态。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244823"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="4097d-103">团队中的用户状态</span><span class="sxs-lookup"><span data-stu-id="4097d-103">User presence in Teams</span></span>

<span data-ttu-id="4097d-104">联机状态是 Microsoft 团队 (以及整个 Office 365) 中的用户配置文件的一部分-并指示用户的当前可用性和组织中其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="4097d-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="4097d-105">默认情况下, 使用团队的组织中的任何人都可以几乎实时看到-无论其他用户是否在线提供。</span><span class="sxs-lookup"><span data-stu-id="4097d-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="4097d-106">团队中的状态</span><span class="sxs-lookup"><span data-stu-id="4097d-106">Presence states in Teams</span></span>

<span data-ttu-id="4097d-107">团队中可用的用户状态包括:</span><span class="sxs-lookup"><span data-stu-id="4097d-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="4097d-108">用户配置</span><span class="sxs-lookup"><span data-stu-id="4097d-108">User configured</span></span>|<span data-ttu-id="4097d-109">已配置应用</span><span class="sxs-lookup"><span data-stu-id="4097d-109">App configured</span></span>|
|:--- |:---|
| ![稳定绿色的 chek 标记, 指示可用状态](media/Presence_Available.png) <span data-ttu-id="4097d-111">有空</span><span class="sxs-lookup"><span data-stu-id="4097d-111">Available</span></span>|![稳定绿色的 chek 标记, 指示可用状态](media/Presence_Available.png) <span data-ttu-id="4097d-113">有空</span><span class="sxs-lookup"><span data-stu-id="4097d-113">Available</span></span>|
|| ![打开绿色的 chek 标记, 指示可用的 oof](media/Presence_Available_OOF.png) <span data-ttu-id="4097d-115">可用, 外出</span><span class="sxs-lookup"><span data-stu-id="4097d-115">Available, Out of Office</span></span> |
|  ![红色实心圆圈, 表示占线](media/Presence_Busy.png) <span data-ttu-id="4097d-117">/</span><span class="sxs-lookup"><span data-stu-id="4097d-117">Busy</span></span> |  ![红色实心圆圈, 表示占线](media/Presence_Busy.png) <span data-ttu-id="4097d-119">/</span><span class="sxs-lookup"><span data-stu-id="4097d-119">Busy</span></span>  |
|| ![红色实心圆圈, 表示通话中的占线](media/Presence_Busy.png) <span data-ttu-id="4097d-121">在通话中</span><span class="sxs-lookup"><span data-stu-id="4097d-121">In a call</span></span>|
|| ![红色实心圆圈, 表示会议中的忙](media/Presence_Busy.png) <span data-ttu-id="4097d-123">在会议中</span><span class="sxs-lookup"><span data-stu-id="4097d-123">In a meeting</span></span> |
|| ![打开红色圆圈, 指示繁忙的 oof](media/Presence_Busy_OOF.png) <span data-ttu-id="4097d-125">在通话中, 外出</span><span class="sxs-lookup"><span data-stu-id="4097d-125">In a call, out of office</span></span>|
|  ![带白线的红色圆圈, 指示 "请勿打扰"](media/Presence_DND.png) <span data-ttu-id="4097d-127">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="4097d-127">Do not disturb</span></span> ||
|| ![带有白色线的红色圆圈, 指示演示](media/Presence_DND.png) <span data-ttu-id="4097d-129">演示</span><span class="sxs-lookup"><span data-stu-id="4097d-129">Presenting</span></span>|
| ![黄色时钟图标, 表示离开](media/Presence_Away.png) <span data-ttu-id="4097d-131">离开</span><span class="sxs-lookup"><span data-stu-id="4097d-131">Away</span></span>| ![黄色时钟图标, 表示离开](media/Presence_Away.png) <span data-ttu-id="4097d-133">离开</span><span class="sxs-lookup"><span data-stu-id="4097d-133">Away</span></span>|
|| <span data-ttu-id="4097d-134">![黄色时钟图标, 指示离开](media/Presence_Away.png)上次看到的*时间*</span><span class="sxs-lookup"><span data-stu-id="4097d-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色时钟图标, 表示离开, 马上回来](media/Presence_Away.png) <span data-ttu-id="4097d-136">马上回来</span><span class="sxs-lookup"><span data-stu-id="4097d-136">Be right back</span></span>| |
|| ![黄色时钟图标, 指示离开、离开工作](media/Presence_Away.png)  <span data-ttu-id="4097d-138">关闭工作</span><span class="sxs-lookup"><span data-stu-id="4097d-138">Off Work</span></span>|
|| ![带有 x 的灰色圆圈, 指示离线](media/Presence_Offline.png) <span data-ttu-id="4097d-140">脱机</span><span class="sxs-lookup"><span data-stu-id="4097d-140">Offline</span></span> |
|| ![打开灰色圆圈, 指示状态未知](media/Presence_Unknown.png) <span data-ttu-id="4097d-142">状态未知</span><span class="sxs-lookup"><span data-stu-id="4097d-142">Status unknown</span></span>|
||![以对角线打开红色圆圈, 指示已阻止](media/Presence_Blocked.png) <span data-ttu-id="4097d-144">已阻止</span><span class="sxs-lookup"><span data-stu-id="4097d-144">Blocked</span></span> |
|| ![带箭头的紫色圆圈, 表示外出](media/Presence_OOF.png) <span data-ttu-id="4097d-146">外出</span><span class="sxs-lookup"><span data-stu-id="4097d-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="4097d-147">用户可以手动将其当前状态设置为某些选项, 其状态将反映给所有其他用户。</span><span class="sxs-lookup"><span data-stu-id="4097d-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="4097d-148">其他用户状态详细信息也会根据用户活动 (如 "可用" 或 "离开")、Outlook 日历状态 (如 "会议") 或团队应用状态 (正在进行的调用) 自动更新, 以显示在列表中缩进的状态。</span><span class="sxs-lookup"><span data-stu-id="4097d-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="4097d-149">有15分钟的不活动超时, 用户的当前状态将重置为 "离开"。</span><span class="sxs-lookup"><span data-stu-id="4097d-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="4097d-150">用户可以指定谁可以断开连接 (联系他们替代 "请勿打扰" 设置)。</span><span class="sxs-lookup"><span data-stu-id="4097d-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="4097d-151">这些设置在应用内可用。</span><span class="sxs-lookup"><span data-stu-id="4097d-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="4097d-152">与 Skype for business 相比, 团队中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="4097d-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="4097d-153">以下管理员设置 Skype for business 在团队中有所不同:</span><span class="sxs-lookup"><span data-stu-id="4097d-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="4097d-154">在团队中, 始终为组织中的用户启用联机状态共享。</span><span class="sxs-lookup"><span data-stu-id="4097d-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="4097d-155">隐私 (决定谁可以查看状态) 配置在团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="4097d-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="4097d-156">始终为团队中的用户启用与每个人 (包括联合服务) 的联机状态共享。</span><span class="sxs-lookup"><span data-stu-id="4097d-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="4097d-157">他们的联系人列表 (如果他们在 Skype for Business 中) 在 "**聊天 > 联系人**" 或 "**通话 > 联系人**" 下可见。</span><span class="sxs-lookup"><span data-stu-id="4097d-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="4097d-158">对于团队中的用户, 将始终启用客户端 "请勿打扰" 和 "特许" 功能。</span><span class="sxs-lookup"><span data-stu-id="4097d-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="4097d-159">日历 (包括外出和其他日历信息) 对于团队中的用户, 如果与 Outlook 集成, 则始终为其启用集成。</span><span class="sxs-lookup"><span data-stu-id="4097d-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="4097d-160">始终\*\* 为团队中的用户启用 "*自*(如果在具有 Skype for business 的双重环境中)" 指示器。</span><span class="sxs-lookup"><span data-stu-id="4097d-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="4097d-161">团队管理员自定义这些设置的能力目前不受支持。</span><span class="sxs-lookup"><span data-stu-id="4097d-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="4097d-162">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="4097d-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="4097d-163">请参阅与 skype for business[共存](coexistence-chat-calls-presence.md), 了解有关在与 Skype for business 共存时团队是否正常工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4097d-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
