---
title: Teams 中的用户状态
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 有关工作组中的状态的管理员信息。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b829fbffa728d3449ba19466d0a2cb85f266c9c2
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010595"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="f3957-103">Teams 中的用户状态</span><span class="sxs-lookup"><span data-stu-id="f3957-103">User presence in Teams</span></span>

<span data-ttu-id="f3957-104">状态是 Microsoft 团队（以及整个 Office 365）中的用户配置文件的一部分，用于指示用户的当前可用性和其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="f3957-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="f3957-105">默认情况下，使用团队的组织中的任何人都可以在其他用户联机时查看（几乎实时）。</span><span class="sxs-lookup"><span data-stu-id="f3957-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3957-106">如果在将用户移动到“仅 Teams”\*\*\*\* 模式后卸载 Skype for Business 客户端，则在 Outlook 和其他 Office 应用程序中，状态将停止工作。</span><span class="sxs-lookup"><span data-stu-id="f3957-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="f3957-107">状态在 Teams 中显示良好。</span><span class="sxs-lookup"><span data-stu-id="f3957-107">Presence works fine in Teams.</span></span> <span data-ttu-id="f3957-108">解决方法：若要在 Outlook （以及其他 Office 应用）中查看状态，必须安装 Skype for business，即使你是在 "**仅团队**" 模式下运行团队也是如此。</span><span class="sxs-lookup"><span data-stu-id="f3957-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="f3957-109">Microsoft 已发现此问题且正在开发修补程序。</span><span class="sxs-lookup"><span data-stu-id="f3957-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="f3957-110">Outlook 中的团队状态在 Outlook 2013 桌面应用和更高版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="f3957-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="f3957-111">团队中的状态</span><span class="sxs-lookup"><span data-stu-id="f3957-111">Presence states in Teams</span></span>

<span data-ttu-id="f3957-112">团队中可用的用户状态包括：</span><span class="sxs-lookup"><span data-stu-id="f3957-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="f3957-113">用户配置</span><span class="sxs-lookup"><span data-stu-id="f3957-113">User configured</span></span>|<span data-ttu-id="f3957-114">已配置应用</span><span class="sxs-lookup"><span data-stu-id="f3957-114">App configured</span></span>|
|:--- |:---|
| ![稳定绿色复选标记，指示可用状态](media/Presence_Available.png) <span data-ttu-id="f3957-116">有空</span><span class="sxs-lookup"><span data-stu-id="f3957-116">Available</span></span>|![稳定绿色复选标记，指示可用状态](media/Presence_Available.png) <span data-ttu-id="f3957-118">有空</span><span class="sxs-lookup"><span data-stu-id="f3957-118">Available</span></span>|
|| ![打开绿色复选标记，表示可用的 oof](media/Presence_Available_OOF.png) <span data-ttu-id="f3957-120">可用，外出</span><span class="sxs-lookup"><span data-stu-id="f3957-120">Available, Out of Office</span></span> |
|  ![红色实心圆圈表示占线](media/Presence_Busy.png) <span data-ttu-id="f3957-122">/</span><span class="sxs-lookup"><span data-stu-id="f3957-122">Busy</span></span> |  ![红色实心圆圈表示占线](media/Presence_Busy.png) <span data-ttu-id="f3957-124">/</span><span class="sxs-lookup"><span data-stu-id="f3957-124">Busy</span></span>  |
|| ![红色实心圆圈表示通话中的占线](media/Presence_Busy.png) <span data-ttu-id="f3957-126">在通话中</span><span class="sxs-lookup"><span data-stu-id="f3957-126">In a call</span></span>|
|| ![纯红色圆圈表示会议中的忙](media/Presence_Busy.png) <span data-ttu-id="f3957-128">在会议中</span><span class="sxs-lookup"><span data-stu-id="f3957-128">In a meeting</span></span> |
|| ![打开红色圆圈，表示占线](media/Presence_Busy_OOF.png) <span data-ttu-id="f3957-130">在通话中，外出</span><span class="sxs-lookup"><span data-stu-id="f3957-130">In a call, out of office</span></span>|
|  ![带白线的红色圆圈表示 "请勿打扰"](media/Presence_DND.png) <span data-ttu-id="f3957-132">请勿打扰</span><span class="sxs-lookup"><span data-stu-id="f3957-132">Do not disturb</span></span> ||
|| ![带有白色线的红色圆圈表示演示](media/Presence_DND.png) <span data-ttu-id="f3957-134">演示</span><span class="sxs-lookup"><span data-stu-id="f3957-134">Presenting</span></span>|
|| ![带白线的红色圆圈表示焦点](media/Presence_DND.png) <span data-ttu-id="f3957-136">介绍</span><span class="sxs-lookup"><span data-stu-id="f3957-136">Focusing</span></span>|
| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="f3957-138">离开</span><span class="sxs-lookup"><span data-stu-id="f3957-138">Away</span></span>| ![黄色时钟图标，表示离开](media/Presence_Away.png) <span data-ttu-id="f3957-140">离开</span><span class="sxs-lookup"><span data-stu-id="f3957-140">Away</span></span>|
|| <span data-ttu-id="f3957-141">![黄色时钟图标，表示离开](media/Presence_Away.png)上次看到的*时间*</span><span class="sxs-lookup"><span data-stu-id="f3957-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![黄色时钟图标，表示离开，马上回来](media/Presence_Away.png) <span data-ttu-id="f3957-143">马上回来</span><span class="sxs-lookup"><span data-stu-id="f3957-143">Be right back</span></span>| |
|| ![黄色时钟图标，表示离开，不起作用](media/Presence_Away.png)  <span data-ttu-id="f3957-145">关闭工作</span><span class="sxs-lookup"><span data-stu-id="f3957-145">Off Work</span></span>|
|| ![X 的灰色圆圈表示离线](media/Presence_Offline.png) <span data-ttu-id="f3957-147">脱机</span><span class="sxs-lookup"><span data-stu-id="f3957-147">Offline</span></span> |
|| ![打开灰色圆圈，指示状态未知](media/Presence_Unknown.png) <span data-ttu-id="f3957-149">状态未知</span><span class="sxs-lookup"><span data-stu-id="f3957-149">Status unknown</span></span>|
||![以对角线打开红色圆圈，指示被阻止](media/Presence_Blocked.png) <span data-ttu-id="f3957-151">已阻止</span><span class="sxs-lookup"><span data-stu-id="f3957-151">Blocked</span></span> |
|| ![带箭头的紫色圆圈表示外出](media/Presence_OOF.png) <span data-ttu-id="f3957-153">外出</span><span class="sxs-lookup"><span data-stu-id="f3957-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="f3957-154">用户可以手动将其当前状态设置为某些选项，其状态将反映给所有其他用户。</span><span class="sxs-lookup"><span data-stu-id="f3957-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="f3957-155">更多用户状态详细信息也会自动更新。</span><span class="sxs-lookup"><span data-stu-id="f3957-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="f3957-156">这些更改基于用户活动（可用、离开）、Outlook 日历状态（在会议中）或团队应用状态（正在进行的调用），以及列表中缩进的状态。</span><span class="sxs-lookup"><span data-stu-id="f3957-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> 

<span data-ttu-id="f3957-157">15分钟不活动超时，在这种情况下，当前状态将重置为 "离开"。</span><span class="sxs-lookup"><span data-stu-id="f3957-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="f3957-158">用户可以指定谁可以中断（这意味着无论 "请勿打扰" 状态，请与他们联系）。</span><span class="sxs-lookup"><span data-stu-id="f3957-158">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="f3957-159">这些设置在团队客户端中可用。</span><span class="sxs-lookup"><span data-stu-id="f3957-159">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="f3957-160">与 Skype for business 相比，团队中的管理员设置</span><span class="sxs-lookup"><span data-stu-id="f3957-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="f3957-161">以下管理员设置 Skype for business 在团队中有所不同：</span><span class="sxs-lookup"><span data-stu-id="f3957-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="f3957-162">在团队中，始终为组织中的用户启用联机状态共享。</span><span class="sxs-lookup"><span data-stu-id="f3957-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="f3957-163">隐私（定义谁可以查看状态）配置在团队中不可用。</span><span class="sxs-lookup"><span data-stu-id="f3957-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="f3957-164">始终为团队中的用户启用与每个人（包括联合服务）的联机状态共享。</span><span class="sxs-lookup"><span data-stu-id="f3957-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="f3957-165">他们的联系人列表（如果他们在 Skype for Business 中）在 "**聊天 > 联系人**" 或 "**通话 > 联系人**" 下可见。</span><span class="sxs-lookup"><span data-stu-id="f3957-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="f3957-166">对于团队中的用户，将始终启用客户端 "请勿打扰" 和 "特许" 功能。</span><span class="sxs-lookup"><span data-stu-id="f3957-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="f3957-167">日历（包括外出和其他日历信息）在团队与 Outlook 集成时，将始终为用户启用集成。</span><span class="sxs-lookup"><span data-stu-id="f3957-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="f3957-168">如果组织还使用 Skype for Business，则 "*最后一次看到*" 或 "*离开*" 将始终为团队中的用户启用指示器。</span><span class="sxs-lookup"><span data-stu-id="f3957-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="f3957-169">团队管理员自定义这些设置的能力目前不受支持。</span><span class="sxs-lookup"><span data-stu-id="f3957-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="f3957-170">与 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="f3957-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="f3957-171">有关您的组织还使用 Skype for business 时团队的工作原理的详细信息，请参阅[与 Skype for Business 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="f3957-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
