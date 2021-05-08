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
description: 了解如何在用于内容共享的Teams管理会议策略设置。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598712"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="6663b-103">会议策略设置 - 内容共享</span><span class="sxs-lookup"><span data-stu-id="6663b-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="6663b-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="6663b-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="6663b-105">本文介绍与内容共享相关的以下会议策略设置：</span><span class="sxs-lookup"><span data-stu-id="6663b-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="6663b-106">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="6663b-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="6663b-107">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="6663b-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="6663b-108">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="6663b-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="6663b-109">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="6663b-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="6663b-110">允许白板</span><span class="sxs-lookup"><span data-stu-id="6663b-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="6663b-111">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="6663b-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="6663b-112">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="6663b-112">Screen sharing mode</span></span>

<span data-ttu-id="6663b-113">此设置是按组织者策略和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="6663b-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="6663b-114">此设置控制是否在用户的会议中允许桌面和窗口共享。</span><span class="sxs-lookup"><span data-stu-id="6663b-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="6663b-115">未分配任何策略的会议参与者 (例如，匿名、嘉宾、B2B和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="6663b-116">设置值</span><span class="sxs-lookup"><span data-stu-id="6663b-116">Setting value</span></span> |<span data-ttu-id="6663b-117">行为</span><span class="sxs-lookup"><span data-stu-id="6663b-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="6663b-118">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="6663b-118">**Entire screen**</span></span>    | <span data-ttu-id="6663b-119">会议中可以实现完全的桌面共享和应用共享</span><span class="sxs-lookup"><span data-stu-id="6663b-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="6663b-120">**单个应用程序**</span><span class="sxs-lookup"><span data-stu-id="6663b-120">**Single application**</span></span>   | <span data-ttu-id="6663b-121">会议中允许应用共享</span><span class="sxs-lookup"><span data-stu-id="6663b-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="6663b-122">**禁用**</span><span class="sxs-lookup"><span data-stu-id="6663b-122">**Disabled**</span></span>     |<span data-ttu-id="6663b-123">会议中关闭了屏幕共享和应用共享。</span><span class="sxs-lookup"><span data-stu-id="6663b-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="6663b-124">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="6663b-124">Let's look at the following example.</span></span>

|<span data-ttu-id="6663b-125">用户</span><span class="sxs-lookup"><span data-stu-id="6663b-125">User</span></span> |<span data-ttu-id="6663b-126">会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-126">Meeting policy</span></span> |<span data-ttu-id="6663b-127">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="6663b-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6663b-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="6663b-128">Daniela</span></span>  | <span data-ttu-id="6663b-129">全局</span><span class="sxs-lookup"><span data-stu-id="6663b-129">Global</span></span>   | <span data-ttu-id="6663b-130">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="6663b-130">Entire screen</span></span> |
|<span data-ttu-id="6663b-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="6663b-131">Amanda</span></span>   | <span data-ttu-id="6663b-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6663b-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="6663b-133">已禁用</span><span class="sxs-lookup"><span data-stu-id="6663b-133">Disabled</span></span> |

<span data-ttu-id="6663b-134">由 Daniela 主持的会议允许会议参与者分享他们的整个屏幕或特定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6663b-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="6663b-135">如果 Amanda 加入 Daniela 的会议，Amanda 则无法分享她的屏幕或特定的应用程序，因为她已禁用她的策略设置。</span><span class="sxs-lookup"><span data-stu-id="6663b-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="6663b-136">在 Amanda 主持的会议中，无论分配给他们的屏幕共享模式策略是什么，都不允许任何人共享他们的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="6663b-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="6663b-137">因此，Daniela 无法共享她的屏幕或 Amanda 会议中的单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="6663b-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="6663b-138">目前，如果用户使用谷歌浏览器，就无法在 Teams 会议中播放视频或分享屏幕。</span><span class="sxs-lookup"><span data-stu-id="6663b-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="6663b-139">允许参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="6663b-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="6663b-140">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-140">This setting is a per-user policy.</span></span> <span data-ttu-id="6663b-141">此设置可控制用户是否可以将共享桌面或窗口的控制权交给其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="6663b-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="6663b-142">若要想进行控制，请将鼠标悬停在屏幕上方。</span><span class="sxs-lookup"><span data-stu-id="6663b-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="6663b-143">如果为用户开启此设置，则在共享会话中的顶部栏中会显示 **“授予控制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="6663b-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![显示 “授予控制” 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="6663b-145">如果已关闭用户的设置，则无法使用 **“授予控制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="6663b-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示“授予控制”选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="6663b-147">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="6663b-147">Let's look at the following example.</span></span>

|<span data-ttu-id="6663b-148">用户</span><span class="sxs-lookup"><span data-stu-id="6663b-148">User</span></span> |<span data-ttu-id="6663b-149">会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-149">Meeting policy</span></span>  |<span data-ttu-id="6663b-150">允许参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="6663b-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6663b-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="6663b-151">Daniela</span></span>   | <span data-ttu-id="6663b-152">全局</span><span class="sxs-lookup"><span data-stu-id="6663b-152">Global</span></span>   | <span data-ttu-id="6663b-153">开</span><span class="sxs-lookup"><span data-stu-id="6663b-153">On</span></span>       |
|<span data-ttu-id="6663b-154">Babek</span><span class="sxs-lookup"><span data-stu-id="6663b-154">Babek</span></span>    | <span data-ttu-id="6663b-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6663b-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6663b-156">关闭</span><span class="sxs-lookup"><span data-stu-id="6663b-156">Off</span></span>   |

<span data-ttu-id="6663b-157">Daniela 可以将共享桌面或窗口的控制权授予由 Babek 组织的会议的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="6663b-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="6663b-158">但是，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="6663b-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="6663b-159">若要使用 PowerShell 来控制可以授予控制权或接受控制权请求的人选，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6663b-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6663b-160">若要在共享过程中授予并控制共享内容，双方必须都使用 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="6663b-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="6663b-161">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="6663b-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="6663b-162">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="6663b-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="6663b-163">允许外部参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="6663b-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="6663b-164">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-164">This setting is a per-user policy.</span></span> <span data-ttu-id="6663b-165">无论组织是否为用户设置了此策略，无论会议组织者设置什么，都无法控制外部参与者可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="6663b-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="6663b-166">该参数控制是否可以让外部参与者控制或请求控制共享者的屏幕，这取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="6663b-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="6663b-167">Teams 会议的外部与会者可分为以下几类:</span><span class="sxs-lookup"><span data-stu-id="6663b-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="6663b-168">匿名用户</span><span class="sxs-lookup"><span data-stu-id="6663b-168">Anonymous user</span></span>
- <span data-ttu-id="6663b-169">来宾用户</span><span class="sxs-lookup"><span data-stu-id="6663b-169">Guest users</span></span>  
- <span data-ttu-id="6663b-170">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="6663b-170">B2B user</span></span>
- <span data-ttu-id="6663b-171">联合用户</span><span class="sxs-lookup"><span data-stu-id="6663b-171">Federated user</span></span>  

<span data-ttu-id="6663b-172">联合用户在共享时是否可以将控制权交给外部用户，由组织中的 **允许外部参与者授予或请求控制权** 设置控制。</span><span class="sxs-lookup"><span data-stu-id="6663b-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="6663b-173">要使用 PowerShell 来控制外部参与者是否可以授予控制权或接受控制权请求，请使用AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6663b-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="6663b-174">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="6663b-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="6663b-175">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-175">This is a per-user policy.</span></span> <span data-ttu-id="6663b-176">此设置可控制用户是否可以在会议中共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="6663b-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="6663b-177">外部用户，包括匿名用户、来宾用户和联合用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="6663b-178">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="6663b-178">Let's look at the following example.</span></span>

|<span data-ttu-id="6663b-179">用户</span><span class="sxs-lookup"><span data-stu-id="6663b-179">User</span></span> |<span data-ttu-id="6663b-180">会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-180">Meeting policy</span></span>  |<span data-ttu-id="6663b-181">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="6663b-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6663b-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="6663b-182">Daniela</span></span>   | <span data-ttu-id="6663b-183">全局</span><span class="sxs-lookup"><span data-stu-id="6663b-183">Global</span></span>   | <span data-ttu-id="6663b-184">开</span><span class="sxs-lookup"><span data-stu-id="6663b-184">On</span></span>       |
|<span data-ttu-id="6663b-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="6663b-185">Amanda</span></span>   | <span data-ttu-id="6663b-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6663b-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6663b-187">关闭</span><span class="sxs-lookup"><span data-stu-id="6663b-187">Off</span></span>   |

<span data-ttu-id="6663b-188">Amanda 无法在会议上共享 PowerPoint 幻灯片，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="6663b-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="6663b-189">Daniela 可以分享 PowerPoint 幻灯片，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="6663b-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="6663b-190">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，尽管她不能共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="6663b-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="6663b-191">允许白板</span><span class="sxs-lookup"><span data-stu-id="6663b-191">Allow whiteboard</span></span>

<span data-ttu-id="6663b-192">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-192">This setting is a per-user policy.</span></span> <span data-ttu-id="6663b-193">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="6663b-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="6663b-194">外部用户，包括匿名用户、B2B用户和联盟用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="6663b-195">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="6663b-195">Let's look at the following example.</span></span>

|<span data-ttu-id="6663b-196">用户</span><span class="sxs-lookup"><span data-stu-id="6663b-196">User</span></span> |<span data-ttu-id="6663b-197">会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-197">Meeting policy</span></span>  |<span data-ttu-id="6663b-198">允许白板</span><span class="sxs-lookup"><span data-stu-id="6663b-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6663b-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="6663b-199">Daniela</span></span>   | <span data-ttu-id="6663b-200">全局</span><span class="sxs-lookup"><span data-stu-id="6663b-200">Global</span></span>   | <span data-ttu-id="6663b-201">开</span><span class="sxs-lookup"><span data-stu-id="6663b-201">On</span></span>       |
|<span data-ttu-id="6663b-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="6663b-202">Amanda</span></span>   | <span data-ttu-id="6663b-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6663b-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="6663b-204">关闭</span><span class="sxs-lookup"><span data-stu-id="6663b-204">Off</span></span>   |

<span data-ttu-id="6663b-205">Amanda 不能在会议上共享白板，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="6663b-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="6663b-206">Daniela 可以共享白板，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="6663b-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="6663b-207">允许共享的笔记</span><span class="sxs-lookup"><span data-stu-id="6663b-207">Allow shared notes</span></span>

<span data-ttu-id="6663b-208">此设置是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-208">This setting is a per-user policy.</span></span> <span data-ttu-id="6663b-209">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="6663b-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="6663b-210">外部用户，包括匿名用户、B2B用户和联盟用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="6663b-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="6663b-211">" **会议笔记"** 选项卡当前仅在参与者少于 20 人的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="6663b-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="6663b-212">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="6663b-212">Let's look at the following example.</span></span>

|<span data-ttu-id="6663b-213">用户</span><span class="sxs-lookup"><span data-stu-id="6663b-213">User</span></span> |<span data-ttu-id="6663b-214">会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-214">Meeting policy</span></span>  |<span data-ttu-id="6663b-215">允许共享的笔记</span><span class="sxs-lookup"><span data-stu-id="6663b-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6663b-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="6663b-216">Daniela</span></span>   | <span data-ttu-id="6663b-217">全局</span><span class="sxs-lookup"><span data-stu-id="6663b-217">Global</span></span>   | <span data-ttu-id="6663b-218">开</span><span class="sxs-lookup"><span data-stu-id="6663b-218">On</span></span>       |
|<span data-ttu-id="6663b-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="6663b-219">Amanda</span></span>   | <span data-ttu-id="6663b-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="6663b-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="6663b-221">关闭</span><span class="sxs-lookup"><span data-stu-id="6663b-221">Off</span></span> |

<span data-ttu-id="6663b-222">Daniela 可以在 Amanda 的会议上做笔记，而 Amanda 不能在任何会议上做笔记。</span><span class="sxs-lookup"><span data-stu-id="6663b-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="6663b-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="6663b-223">Related topics</span></span>

- [<span data-ttu-id="6663b-224">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="6663b-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6663b-225">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="6663b-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="6663b-226">从用户删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="6663b-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
