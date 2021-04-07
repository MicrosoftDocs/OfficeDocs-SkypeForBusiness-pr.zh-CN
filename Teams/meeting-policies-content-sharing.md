---
title: 管理内容共享的会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理用于内容共享的会议策略设置。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598712"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="8180a-103">会议策略设置 - 内容共享</span><span class="sxs-lookup"><span data-stu-id="8180a-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="8180a-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="8180a-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="8180a-105">本文介绍与内容共享相关的以下会议策略设置：</span><span class="sxs-lookup"><span data-stu-id="8180a-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="8180a-106">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="8180a-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="8180a-107">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="8180a-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="8180a-108">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="8180a-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="8180a-109">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="8180a-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="8180a-110">允许白板</span><span class="sxs-lookup"><span data-stu-id="8180a-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="8180a-111">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="8180a-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="8180a-112">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="8180a-112">Screen sharing mode</span></span>

<span data-ttu-id="8180a-113">此设置是按组织者策略和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="8180a-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="8180a-114">此设置控制是否在用户的会议中允许桌面和窗口共享。</span><span class="sxs-lookup"><span data-stu-id="8180a-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="8180a-115">未分配任何策略的会议参与者 (匿名、来宾、B2B 和联合) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="8180a-116">设置值</span><span class="sxs-lookup"><span data-stu-id="8180a-116">Setting value</span></span> |<span data-ttu-id="8180a-117">行为</span><span class="sxs-lookup"><span data-stu-id="8180a-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="8180a-118">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="8180a-118">**Entire screen**</span></span>    | <span data-ttu-id="8180a-119">会议允许完全桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="8180a-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="8180a-120">**单个应用程序**</span><span class="sxs-lookup"><span data-stu-id="8180a-120">**Single application**</span></span>   | <span data-ttu-id="8180a-121">会议允许应用程序共享</span><span class="sxs-lookup"><span data-stu-id="8180a-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="8180a-122">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="8180a-122">**Disabled**</span></span>     |<span data-ttu-id="8180a-123">会议中的屏幕共享和应用程序共享已关闭。</span><span class="sxs-lookup"><span data-stu-id="8180a-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="8180a-124">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="8180a-124">Let's look at the following example.</span></span>

|<span data-ttu-id="8180a-125">用户</span><span class="sxs-lookup"><span data-stu-id="8180a-125">User</span></span> |<span data-ttu-id="8180a-126">会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-126">Meeting policy</span></span> |<span data-ttu-id="8180a-127">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="8180a-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8180a-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="8180a-128">Daniela</span></span>  | <span data-ttu-id="8180a-129">全局</span><span class="sxs-lookup"><span data-stu-id="8180a-129">Global</span></span>   | <span data-ttu-id="8180a-130">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="8180a-130">Entire screen</span></span> |
|<span data-ttu-id="8180a-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="8180a-131">Amanda</span></span>   | <span data-ttu-id="8180a-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8180a-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="8180a-133">已禁用</span><span class="sxs-lookup"><span data-stu-id="8180a-133">Disabled</span></span> |

<span data-ttu-id="8180a-134">Daniela 主持的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="8180a-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="8180a-135">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为禁用了策略设置。</span><span class="sxs-lookup"><span data-stu-id="8180a-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="8180a-136">在 Amanda 主持的会议中，不允许任何人共享其屏幕或单个应用程序，而不考虑分配给他们的屏幕共享模式策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="8180a-137">因此，Daniela 无法共享她的屏幕或 Amanda 会议中的单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="8180a-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="8180a-138">目前，如果用户使用的是 Google Chrome，则他们无法播放视频或在 Teams 会议中共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="8180a-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="8180a-139">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="8180a-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="8180a-140">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-140">This setting is a per-user policy.</span></span> <span data-ttu-id="8180a-141">此设置控制用户是否可以将共享桌面或窗口控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="8180a-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="8180a-142">若要进行控制，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="8180a-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="8180a-143">如果为用户启用此设置，共享会话中的顶部栏中会显示"授予控制权"选项。</span><span class="sxs-lookup"><span data-stu-id="8180a-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![显示"授予控制权"选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="8180a-145">如果为用户关闭设置，则"授予 **控制权** "选项不可用。</span><span class="sxs-lookup"><span data-stu-id="8180a-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示"授予控制权"选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="8180a-147">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="8180a-147">Let's look at the following example.</span></span>

|<span data-ttu-id="8180a-148">用户</span><span class="sxs-lookup"><span data-stu-id="8180a-148">User</span></span> |<span data-ttu-id="8180a-149">会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-149">Meeting policy</span></span>  |<span data-ttu-id="8180a-150">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="8180a-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8180a-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="8180a-151">Daniela</span></span>   | <span data-ttu-id="8180a-152">全局</span><span class="sxs-lookup"><span data-stu-id="8180a-152">Global</span></span>   | <span data-ttu-id="8180a-153">开</span><span class="sxs-lookup"><span data-stu-id="8180a-153">On</span></span>       |
|<span data-ttu-id="8180a-154">Babek</span><span class="sxs-lookup"><span data-stu-id="8180a-154">Babek</span></span>    | <span data-ttu-id="8180a-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8180a-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="8180a-156">关</span><span class="sxs-lookup"><span data-stu-id="8180a-156">Off</span></span>   |

<span data-ttu-id="8180a-157">Daniela 可以将共享桌面或窗口的控制权授予由 Babek 组织的会议的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="8180a-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="8180a-158">但是，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="8180a-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="8180a-159">若要使用 PowerShell 控制谁可以授予控制权或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8180a-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8180a-160">若要在共享期间授予并控制共享内容，双方必须使用 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="8180a-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="8180a-161">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="8180a-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="8180a-162">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="8180a-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="8180a-163">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="8180a-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="8180a-164">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-164">This setting is a per-user policy.</span></span> <span data-ttu-id="8180a-165">无论组织是否为用户设置了此策略，无论会议组织者设置什么，都无法控制外部参与者可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="8180a-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="8180a-166">此参数控制是否可以向外部参与者提供对共享者屏幕的控制或请求控制权，具体取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="8180a-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="8180a-167">Teams 会议的外部参与者可分类如下：</span><span class="sxs-lookup"><span data-stu-id="8180a-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="8180a-168">匿名用户</span><span class="sxs-lookup"><span data-stu-id="8180a-168">Anonymous user</span></span>
- <span data-ttu-id="8180a-169">来宾用户</span><span class="sxs-lookup"><span data-stu-id="8180a-169">Guest users</span></span>  
- <span data-ttu-id="8180a-170">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="8180a-170">B2B user</span></span>
- <span data-ttu-id="8180a-171">联合用户</span><span class="sxs-lookup"><span data-stu-id="8180a-171">Federated user</span></span>  

<span data-ttu-id="8180a-172">联合用户是否可以在共享时向外部用户授予控制权，同时受允许外部参与者提供或请求其组织中控制设置的控制。</span><span class="sxs-lookup"><span data-stu-id="8180a-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="8180a-173">若要使用 PowerShell 控制外部参与者是否可以授予控制权或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8180a-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="8180a-174">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="8180a-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="8180a-175">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-175">This is a per-user policy.</span></span> <span data-ttu-id="8180a-176">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="8180a-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="8180a-177">外部用户（包括匿名用户、来宾用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="8180a-178">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="8180a-178">Let's look at the following example.</span></span>

|<span data-ttu-id="8180a-179">用户</span><span class="sxs-lookup"><span data-stu-id="8180a-179">User</span></span> |<span data-ttu-id="8180a-180">会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-180">Meeting policy</span></span>  |<span data-ttu-id="8180a-181">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="8180a-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8180a-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="8180a-182">Daniela</span></span>   | <span data-ttu-id="8180a-183">全局</span><span class="sxs-lookup"><span data-stu-id="8180a-183">Global</span></span>   | <span data-ttu-id="8180a-184">开</span><span class="sxs-lookup"><span data-stu-id="8180a-184">On</span></span>       |
|<span data-ttu-id="8180a-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="8180a-185">Amanda</span></span>   | <span data-ttu-id="8180a-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8180a-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="8180a-187">关</span><span class="sxs-lookup"><span data-stu-id="8180a-187">Off</span></span>   |

<span data-ttu-id="8180a-188">即使 Amanda 是会议组织者，她也无法共享会议中 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="8180a-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="8180a-189">即使会议由 Amanda 组织，Daniela 也可以共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="8180a-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="8180a-190">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，即使她无法共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="8180a-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="8180a-191">允许白板</span><span class="sxs-lookup"><span data-stu-id="8180a-191">Allow whiteboard</span></span>

<span data-ttu-id="8180a-192">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-192">This setting is a per-user policy.</span></span> <span data-ttu-id="8180a-193">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="8180a-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="8180a-194">外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="8180a-195">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="8180a-195">Let's look at the following example.</span></span>

|<span data-ttu-id="8180a-196">用户</span><span class="sxs-lookup"><span data-stu-id="8180a-196">User</span></span> |<span data-ttu-id="8180a-197">会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-197">Meeting policy</span></span>  |<span data-ttu-id="8180a-198">允许白板</span><span class="sxs-lookup"><span data-stu-id="8180a-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="8180a-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="8180a-199">Daniela</span></span>   | <span data-ttu-id="8180a-200">全局</span><span class="sxs-lookup"><span data-stu-id="8180a-200">Global</span></span>   | <span data-ttu-id="8180a-201">开</span><span class="sxs-lookup"><span data-stu-id="8180a-201">On</span></span>       |
|<span data-ttu-id="8180a-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="8180a-202">Amanda</span></span>   | <span data-ttu-id="8180a-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8180a-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="8180a-204">关</span><span class="sxs-lookup"><span data-stu-id="8180a-204">Off</span></span>   |

<span data-ttu-id="8180a-205">Amanda 不能共享会议中的白板，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="8180a-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="8180a-206">Daniela 可以共享白板，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="8180a-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="8180a-207">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="8180a-207">Allow shared notes</span></span>

<span data-ttu-id="8180a-208">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-208">This setting is a per-user policy.</span></span> <span data-ttu-id="8180a-209">此设置控制用户是否可以在会议创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="8180a-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="8180a-210">外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="8180a-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="8180a-211">" **会议笔记"** 选项卡当前仅在参与者少于 20 人的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="8180a-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="8180a-212">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="8180a-212">Let's look at the following example.</span></span>

|<span data-ttu-id="8180a-213">用户</span><span class="sxs-lookup"><span data-stu-id="8180a-213">User</span></span> |<span data-ttu-id="8180a-214">会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-214">Meeting policy</span></span>  |<span data-ttu-id="8180a-215">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="8180a-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8180a-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="8180a-216">Daniela</span></span>   | <span data-ttu-id="8180a-217">全局</span><span class="sxs-lookup"><span data-stu-id="8180a-217">Global</span></span>   | <span data-ttu-id="8180a-218">开</span><span class="sxs-lookup"><span data-stu-id="8180a-218">On</span></span>       |
|<span data-ttu-id="8180a-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="8180a-219">Amanda</span></span>   | <span data-ttu-id="8180a-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="8180a-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="8180a-221">关</span><span class="sxs-lookup"><span data-stu-id="8180a-221">Off</span></span> |

<span data-ttu-id="8180a-222">Daniela 可以在 Amanda 的会议中做笔记，而 Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="8180a-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="8180a-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="8180a-223">Related topics</span></span>

- [<span data-ttu-id="8180a-224">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="8180a-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8180a-225">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="8180a-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="8180a-226">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="8180a-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
