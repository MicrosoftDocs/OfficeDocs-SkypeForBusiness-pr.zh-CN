---
title: 与 Microsoft 团队和 Skype for business 共存
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到团队-共存
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955959"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a><span data-ttu-id="50deb-103">与团队和 Skype for business 共存</span><span class="sxs-lookup"><span data-stu-id="50deb-103">Coexistence with Teams and Skype for Business</span></span>

<span data-ttu-id="50deb-104">本文概述了在同一组织中运行团队和 Skype for business 客户端时可能遇到的问题，无论使用的是何种模式和使用哪种升级方法：</span><span class="sxs-lookup"><span data-stu-id="50deb-104">This article summarizes behavior that may be experienced when running both Teams and Skype for Business clients in the same organization, regardless of what mode and what upgrade method is used:</span></span>

- [<span data-ttu-id="50deb-105">会议</span><span class="sxs-lookup"><span data-stu-id="50deb-105">Meetings</span></span>](#meetings)
- [<span data-ttu-id="50deb-106">交互性</span><span class="sxs-lookup"><span data-stu-id="50deb-106">Interoperability</span></span>](#interoperability)
- [<span data-ttu-id="50deb-107">团队对话-互操作与本机线程</span><span class="sxs-lookup"><span data-stu-id="50deb-107">Teams conversations-Interop versus native threads</span></span>](#teams-conversations---interop-versus-native-threads)
- [<span data-ttu-id="50deb-108">状态</span><span class="sxs-lookup"><span data-stu-id="50deb-108">Presence</span></span>](#presence)
- [<span data-ttu-id="50deb-109">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="50deb-109">Federation</span></span>](#federation)
- [<span data-ttu-id="50deb-110">联系人</span><span class="sxs-lookup"><span data-stu-id="50deb-110">Contacts</span></span>](#contacts)



## <a name="meetings"></a><span data-ttu-id="50deb-111">会议</span><span class="sxs-lookup"><span data-stu-id="50deb-111">Meetings</span></span>

<span data-ttu-id="50deb-112">无论其模式如何，用户始终可以加入受邀的任何类型的会议，无论是 Skype for business 还是团队。</span><span class="sxs-lookup"><span data-stu-id="50deb-112">Regardless of their mode, users can always join any type of meeting they are invited to, whether it is Skype for Business or Teams.</span></span>  <span data-ttu-id="50deb-113">但是，用户必须使用与会议类型匹配的相应客户端加入会议：</span><span class="sxs-lookup"><span data-stu-id="50deb-113">However, users must join the meeting with a corresponding client that matches the meeting type:</span></span>

- <span data-ttu-id="50deb-114">如果会议是团队会议，则所有参与者 (他们是 TeamsOnly、孤岛还是 Skype for business 用户) 使用团队客户加入会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-114">If the meeting is a Teams meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Teams client to join the meeting.</span></span> <span data-ttu-id="50deb-115">如果未安装团队，则在尝试加入会议时，用户将转到 web。</span><span class="sxs-lookup"><span data-stu-id="50deb-115">If Teams is not installed, the user will be directed to the web, upon attempting to join a meeting.</span></span>

- <span data-ttu-id="50deb-116">如果会议是 Skype for business 会议，则所有 (参与者无论是 TeamsOnly、孤岛还是 Skype for business 用户) 使用 Skype for business 客户端加入会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-116">If the meeting is a Skype for Business meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Skype for Business client to join the meeting.</span></span> <span data-ttu-id="50deb-117">如果未安装 Skype for Business 客户端，用户将通过 Skype 会议应用定向到 web 以加入。</span><span class="sxs-lookup"><span data-stu-id="50deb-117">If the Skype for Business client is not installed, the user will be directed to the web to join via the Skype Meeting App.</span></span>

<span data-ttu-id="50deb-118">组织会议时，计划的会议类型基于组织者的模式，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="50deb-118">When organizing meetings, the meeting type that gets scheduled is based on the mode of the organizer, as shown in the following table:</span></span>

| <span data-ttu-id="50deb-119">组织者模式</span><span class="sxs-lookup"><span data-stu-id="50deb-119">Mode of organizer</span></span>    |      <span data-ttu-id="50deb-120">行为</span><span class="sxs-lookup"><span data-stu-id="50deb-120">Behavior</span></span> |
| :------------------ | :---------------- |
| <span data-ttu-id="50deb-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="50deb-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span></span> |    <span data-ttu-id="50deb-122">在团队中安排的所有会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-122">All meetings scheduled in Teams.</span></span> <span data-ttu-id="50deb-123">Outlook 中不提供 Skype for business 加载项。</span><span class="sxs-lookup"><span data-stu-id="50deb-123">Skype for Business add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="50deb-124">SfbWithTeamsCollab, SfbOnly</span><span class="sxs-lookup"><span data-stu-id="50deb-124">SfbWithTeamsCollab, SfbOnly</span></span>   | <span data-ttu-id="50deb-125">Skype for Business 中安排的所有会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-125">All meetings scheduled in Skype for Business.</span></span> <span data-ttu-id="50deb-126">"团队外接程序" 在 Outlook 中不可用。</span><span class="sxs-lookup"><span data-stu-id="50deb-126">Teams add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="50deb-127">孤岛</span><span class="sxs-lookup"><span data-stu-id="50deb-127">Islands</span></span> | <span data-ttu-id="50deb-128">默认情况下，可以在 Skype for Business 或团队中安排会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-128">By default, meetings can be scheduled in either Skype for Business or Teams.</span></span> <span data-ttu-id="50deb-129">Outlook 中提供了这两个加载项。</span><span class="sxs-lookup"><span data-stu-id="50deb-129">Both add-ins are available in Outlook.</span></span> <span data-ttu-id="50deb-130">但是，你可以选择要求在 TeamsMeetingPolicy 中的用户始终通过使用 PreferredMeetingProviderForIslandsMode = 团队向团队分配会议实例来安排团队中的会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-130">However, you can optionally require that users in Islands always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.</span></span>| 


## <a name="interoperability"></a><span data-ttu-id="50deb-131">交互性</span><span class="sxs-lookup"><span data-stu-id="50deb-131">Interoperability</span></span>

<span data-ttu-id="50deb-132">在某些情况下，团队支持与 Skype for Business ) 互操作性 ( "互操作"。</span><span class="sxs-lookup"><span data-stu-id="50deb-132">Teams supports interoperability (“interop”) with Skype for Business in certain scenarios.</span></span> <span data-ttu-id="50deb-133">互操作通信指的是 Skype for Business 用户与团队用户之间的聊天或通话。</span><span class="sxs-lookup"><span data-stu-id="50deb-133">Interop communication refers to a chat or call between a Skype for Business user and a Teams user.</span></span>  <span data-ttu-id="50deb-134">互操作通信仅在两个用户之间可用;不支持多方聊天/通话或添加其他用户。</span><span class="sxs-lookup"><span data-stu-id="50deb-134">Interop communication is only possible between two users; multi-party chat/calling or adding additional users is not supported.</span></span>

<span data-ttu-id="50deb-135">当满足以下每个条件时，将创建两个用户之间的互操作聊天或呼叫：</span><span class="sxs-lookup"><span data-stu-id="50deb-135">An interop chat or call between two users is created when each of the following are true:</span></span>

- <span data-ttu-id="50deb-136">一个用户使用的是团队，另一个用户使用的是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="50deb-136">One user is using Teams and the other is using Skype for Business.</span></span>

- <span data-ttu-id="50deb-137">初始通信的收件人模式不是孤岛 (否则，如果两个用户都在同一个组织中，则通信将位于同一客户端) 。</span><span class="sxs-lookup"><span data-stu-id="50deb-137">The mode of the recipient of the initial communication is NOT Islands (otherwise the communication would land in the same client) if both users are in the same organization.</span></span> <span data-ttu-id="50deb-138">在联合方案中，发送用户使用团队，而收件人不处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="50deb-138">In federated scenarios, the sending user is using Teams, and the recipient is not in TeamsOnly mode.</span></span> 

- <span data-ttu-id="50deb-139">团队用户还没有驻留在本地的 Skype for business 帐户。</span><span class="sxs-lookup"><span data-stu-id="50deb-139">The Teams user does NOT also have a Skype for Business account homed on-premises.</span></span> 

<span data-ttu-id="50deb-140">在互操作通信中，聊天仅为纯文本。</span><span class="sxs-lookup"><span data-stu-id="50deb-140">Within the interop communication, chat is plain-text only.</span></span> <span data-ttu-id="50deb-141">此外，在 *互操作聊天中*不能进行文件共享和屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="50deb-141">In addition, file sharing and screen sharing are not possible *in the interop chat itself*.</span></span> <span data-ttu-id="50deb-142">但是，互操作对话中的用户可以通过创建按需会议（如下所述）轻松实现文件和/或屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="50deb-142">However, users in an interop conversation can easily achieve file and/or screen sharing by creating an on-demand meeting, from within the interop chat, as described below:</span></span>

- <span data-ttu-id="50deb-143">如果团队用户尝试共享其屏幕，将自动创建按需团队会议，并将邀请链接发送到 Skype for Business 用户的客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-143">If the Teams user attempts to share their screen, an on-demand Teams meeting is automatically created and an invite link to that meeting is sent to the Skype for Business user’s client.</span></span> <span data-ttu-id="50deb-144">单击该链接后，Skype for Business 用户将打开团队并加入会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-144">Upon clicking the link, the Skype for Business user will open Teams and join the meeting.</span></span> <span data-ttu-id="50deb-145">两个用户现在都在团队会议中，可以根据需要进行共享。</span><span class="sxs-lookup"><span data-stu-id="50deb-145">Both users are now in a Teams meeting and can share as needed.</span></span>

- <span data-ttu-id="50deb-146">如果 Skype for Business 用户使用的是2018或更高版本的客户端，并且尝试共享任何内容，则会自动创建一个按需 Skype for business 会议，并将邀请链接发送到团队用户的客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-146">If the Skype for Business user is using a client from 2018 or later and attempts to share any content, an on-demand Skype for Business meeting is automatically created and an invite link to that meeting is sent to the Teams user’s client.</span></span> <span data-ttu-id="50deb-147">单击该链接后，团队用户将尝试加入 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="50deb-147">Upon clicking the link, the Teams user will attempt to join the Skype for Business meeting.</span></span> <span data-ttu-id="50deb-148">如果团队用户安装了 Skype for Business 客户端，它将打开，并且系统会提示用户登录 (（如果尚未登录) ）。</span><span class="sxs-lookup"><span data-stu-id="50deb-148">If the Teams user has the Skype for Business client installed, it will open and the user is prompted to sign in (if not already signed in).</span></span>  <span data-ttu-id="50deb-149">如果团队用户没有安装 Skype for business 客户端，系统将提示用户使用 web 版本。</span><span class="sxs-lookup"><span data-stu-id="50deb-149">If the Teams user does not have the Skype for Business client installed, the user will be prompted to use the web version.</span></span> <span data-ttu-id="50deb-150">这两个用户登录后，他们都在 Skype for business 会议中，并且可以根据需要进行共享。</span><span class="sxs-lookup"><span data-stu-id="50deb-150">Once both users are signed in, they are in a Skype for Business meeting and can share as needed.</span></span>

## <a name="teams-conversations---interop-versus-native-threads"></a><span data-ttu-id="50deb-151">团队对话-互操作与本机线程</span><span class="sxs-lookup"><span data-stu-id="50deb-151">Teams conversations - Interop versus native threads</span></span>

<span data-ttu-id="50deb-152">由于互操作通信不支持本机团队对话的所有功能，因此团队客户为团队到团队和团队到 Skype for business 通信保留单独的对话线程。</span><span class="sxs-lookup"><span data-stu-id="50deb-152">Because interop communications do not support all the features of native Teams conversation, the Teams client maintains separate conversation threads for Teams-to-Teams and Teams-to-Skype for Business communication.</span></span> <span data-ttu-id="50deb-153">这些对话在用户界面中的呈现方式不同：互操作线程可以通过以下方式与常规本机团队线程区别：</span><span class="sxs-lookup"><span data-stu-id="50deb-153">These conversations are rendered differently in the user interface: Interop threads can be differentiated from a regular native Teams thread by:</span></span>

- <span data-ttu-id="50deb-154">缺少格式文本、文件/屏幕共享的控件，无法添加用户。</span><span class="sxs-lookup"><span data-stu-id="50deb-154">Lack of controls for rich text, file/screen sharing, inability to add users.</span></span>
- <span data-ttu-id="50deb-155">对目标用户的图标的修改，显示 Skype for business 的 "S"。</span><span class="sxs-lookup"><span data-stu-id="50deb-155">A modification to the target user’s icon, showing an “S” for Skype for Business.</span></span>

<span data-ttu-id="50deb-156">以下屏幕截图显示了这些差异：</span><span class="sxs-lookup"><span data-stu-id="50deb-156">These differences are shown in the following screenshots:</span></span>

<span data-ttu-id="50deb-157">与用户 G3 测试的本机团队间对话</span><span class="sxs-lookup"><span data-stu-id="50deb-157">A native Teams-to-Teams conversation with User G3 Test</span></span>

![显示本机团队间对话的图表](media/teams-upgrade-native-thread.png)

<span data-ttu-id="50deb-159">具有相同用户 G3 测试的互操作对话</span><span class="sxs-lookup"><span data-stu-id="50deb-159">An interop conversation with the same User G3 Test</span></span>

![显示互操作团队到团队对话的图表](media/teams-upgrade-interop-thread.png)

<span data-ttu-id="50deb-161">一旦创建了对话线程，其类型将永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="50deb-161">Once a conversation thread is created, its type never changes.</span></span> <span data-ttu-id="50deb-162">创建后，团队中的互操作线程将始终路由到目标用户的 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-162">Once created, an interop thread in Teams will always route to the target user’s Skype for Business client.</span></span> <span data-ttu-id="50deb-163">本机线程将始终路由到目标用户的团队客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-163">A native thread will always route to the target user’s Teams client.</span></span>  <span data-ttu-id="50deb-164">如果收件人用户的模式发生更改，则该用户的现有团队线程将不再运行，并且将在该聊天上显示一条注释，其中包含用于启动新的本机对话的链接，如以下屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="50deb-164">If a recipient user’s mode changes, existing Teams threads to that user will no longer function and a note will be displayed on that chat with a link to start a new native conversation as shown in the following screenshot.</span></span>


![显示已升级的 Skype for Business 用户的聊天的图表](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a><span data-ttu-id="50deb-166">状态</span><span class="sxs-lookup"><span data-stu-id="50deb-166">Presence</span></span>

<span data-ttu-id="50deb-167">特定用户的状态基于通过客户端提供的服务中的用户活动。</span><span class="sxs-lookup"><span data-stu-id="50deb-167">Presence for a given user is based on the user’s activity in the service via the client.</span></span> <span data-ttu-id="50deb-168">随后将发布联机状态，供其他用户查看。</span><span class="sxs-lookup"><span data-stu-id="50deb-168">The presence is then published for other users to see.</span></span>  <span data-ttu-id="50deb-169">Skype for Business 和团队是具有单独客户端的独立服务，因此每个服务都有其自己的状态供用户使用。</span><span class="sxs-lookup"><span data-stu-id="50deb-169">Skype for Business and Teams are separate services with separate clients, so each service has its own presence state for a user.</span></span>   <span data-ttu-id="50deb-170">团队和 Skype for Business Online 中的状态服务也有同步。</span><span class="sxs-lookup"><span data-stu-id="50deb-170">There is also synchronization between the presence services in Teams and in Skype for Business Online.</span></span>  <span data-ttu-id="50deb-171">这允许一个服务可能会在需要时从其他服务中发布用户的状态。</span><span class="sxs-lookup"><span data-stu-id="50deb-171">This allows one service to potentially publish the presence of the user from the other service if needed.</span></span> 

<span data-ttu-id="50deb-172">状态发布行为基于用户模式。</span><span class="sxs-lookup"><span data-stu-id="50deb-172">Presence publishing behavior is based on the user’s mode.</span></span> <span data-ttu-id="50deb-173">有三种基本情况：</span><span class="sxs-lookup"><span data-stu-id="50deb-173">There are three basic cases:</span></span>

- <span data-ttu-id="50deb-174">如果用户处于 TeamsOnly 模式，则所有其他用户可查看该用户的团队状态，无论他们使用的是哪种客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-174">If a user is in TeamsOnly mode, all other users see Teams presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="50deb-175">如果用户处于任何 Skype for Business 模式，则所有其他用户都可以查看该用户的 Skype for business 状态，无论他们使用哪种客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-175">If a user is in any of the Skype for Business modes, all other users see Skype for Business presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="50deb-176">如果用户处于 "孤岛" 模式，在 Skype for business 中发布的联机状态和团队是独立的，因此对同一组织中的用户显示的状态将取决于其他用户的客户端。</span><span class="sxs-lookup"><span data-stu-id="50deb-176">If a user is in Islands mode, presence published in Skype for Business and Teams are independent, so the presence shown to users within the same organization will depend on the client of the other user.</span></span> <span data-ttu-id="50deb-177">联合组织中的用户将根据其 Skype for business 活动查看该用户的状态，因为在 Skype for business 中，联盟模式用户的联盟流量。</span><span class="sxs-lookup"><span data-stu-id="50deb-177">Users in federated organizations will see presence of that user based on their Skype for Business activity, since federated traffic to an Islands mode user lands in Skype for Business.</span></span>

<span data-ttu-id="50deb-178">例如，假设用户 A 处于孤岛模式。</span><span class="sxs-lookup"><span data-stu-id="50deb-178">For example, Assume User A is in Islands mode.</span></span> <span data-ttu-id="50deb-179">如果用户 A 在团队中处于活动状态，但未登录到 Skype for business，则其他用户将从其团队客户端看到用户 A 是活动的，但在其 Skype for Business 客户端中，他们将把用户 A 设为 "脱机"。</span><span class="sxs-lookup"><span data-stu-id="50deb-179">If User A is active in Teams but is not signed in to Skype for Business, other users would see User A as active from their Teams client, but in their Skype for Business client they would see User A as offline.</span></span> <span data-ttu-id="50deb-180">这是设计使然，因为如果用户不在运行客户端，则无法访问用户 A。</span><span class="sxs-lookup"><span data-stu-id="50deb-180">This is by design, since User A cannot be reached if they are not running the client.</span></span> 


## <a name="federation"></a><span data-ttu-id="50deb-181">联合身份验证</span><span class="sxs-lookup"><span data-stu-id="50deb-181">Federation</span></span>

<span data-ttu-id="50deb-182">从团队到其他使用 Skype for Business 的用户的联盟要求团队用户在 Skype for business 中托管用户处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="50deb-182">Federation from Teams to another user using Skype for Business requires the Teams user to be homed online in Skype for Business.</span></span> <span data-ttu-id="50deb-183">TeamsUpgradePolicy 控制传入联盟聊天和呼叫的路由。</span><span class="sxs-lookup"><span data-stu-id="50deb-183">TeamsUpgradePolicy governs routing for incoming federated chats and calls.</span></span> <span data-ttu-id="50deb-184">除 "孤岛" 模式之外，联合路由行为与相同租户方案相同。</span><span class="sxs-lookup"><span data-stu-id="50deb-184">Federated routing behavior is the same as for same-tenant scenarios, except in Islands mode.</span></span> <span data-ttu-id="50deb-185">当收件人处于 "孤岛" 模式时：</span><span class="sxs-lookup"><span data-stu-id="50deb-185">When recipients are in Islands mode:</span></span>

- <span data-ttu-id="50deb-186">在 Skype for Business 中从团队土地发起的聊天和通话（如果收件人位于联合租户中）。</span><span class="sxs-lookup"><span data-stu-id="50deb-186">Chats and calls initiated from Teams land in Skype for Business if the recipient is in a federated tenant.</span></span>
- <span data-ttu-id="50deb-187">如果收件人位于同一个租户中，则从团队中的团队土地发起聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="50deb-187">Chats and calls initiated from Teams land in Teams if the recipient is in the same tenant.</span></span>
- <span data-ttu-id="50deb-188">通过 Skype for Business 发起的聊天和通话始终位于 Skype for business 中。</span><span class="sxs-lookup"><span data-stu-id="50deb-188">Chats and calls initiated from Skype for Business always land in Skype for Business.</span></span>

<span data-ttu-id="50deb-189">联合聊天既可以是本机线程，也可以是互操作线程。</span><span class="sxs-lookup"><span data-stu-id="50deb-189">A federated chat can either be a native thread or an interop thread.</span></span> <span data-ttu-id="50deb-190">请参阅 [团队对话---互操作与本机线程](#teams-conversations---interop-versus-native-threads)。</span><span class="sxs-lookup"><span data-stu-id="50deb-190">See [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).</span></span>

- <span data-ttu-id="50deb-191">如果接收方和发件人都在 TeamsOnly 升级模式中，则对话将是一个本机聊天体验，包括所有丰富的消息传递和呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="50deb-191">If the receiver and sender are both in TeamsOnly upgrade mode, the conversation will be a native chat experience which includes all the rich messaging and calling capabilities.</span></span> <span data-ttu-id="50deb-192">若要了解详细信息，请阅读 [团队中的外部 (联盟) 用户的本机聊天体验](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="50deb-192">To learn more, read [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span> 

- <span data-ttu-id="50deb-193">如果其中一个对话参与者未处于 TeamsOnly 升级模式，则对话将保持带有纯文本消息的互操作体验。</span><span class="sxs-lookup"><span data-stu-id="50deb-193">If either of the conversation participants is NOT in TeamsOnly upgrade mode, the conversation remains an interop experience with text-only messages.</span></span> <span data-ttu-id="50deb-194">用户界面以与同一租户互操作线程类似的方式公开联盟聊天，但存在指示用户是外部用户的注释。</span><span class="sxs-lookup"><span data-stu-id="50deb-194">The user interface exposes federated chats in a similar manner to same-tenant interop threads, except there is a note indicating the user is external.</span></span>

<span data-ttu-id="50deb-195">有关更多详细信息，请参阅 [管理 Microsoft 团队中的外部访问](manage-external-access.md) 和 [团队中的外部 (联盟) 用户的本机聊天体验](native-chat-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="50deb-195">For more details, see [Manage external access in Microsoft Teams](manage-external-access.md) and [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span>

## <a name="contacts"></a><span data-ttu-id="50deb-196">联系人</span><span class="sxs-lookup"><span data-stu-id="50deb-196">Contacts</span></span>

<span data-ttu-id="50deb-197">团队和 Skype for business 具有单独的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="50deb-197">Teams and Skype for Business have separate lists of contacts.</span></span> <span data-ttu-id="50deb-198">这意味着在一个系统中所做的添加、删除和修改不会与其他系统同步。</span><span class="sxs-lookup"><span data-stu-id="50deb-198">This means that contact additions, removal, and modifications made in one system are not synchronized to the other system.</span></span> <span data-ttu-id="50deb-199">但是，如果发生两个特定事件之一，来自 Skype for Business 的联系人会自动复制到团队中：</span><span class="sxs-lookup"><span data-stu-id="50deb-199">However, contacts from Skype for Business are automatically copied over to Teams when either of two specific events occur:</span></span> 

- <span data-ttu-id="50deb-200">对于任何 Skype for Business Online 用户，当他们第一次登录到团队时，Skype for Business 中的联系人将被复制到团队。</span><span class="sxs-lookup"><span data-stu-id="50deb-200">For any Skype for Business Online user, the first time they log onto Teams, contacts from Skype for Business will be copied over to Teams.</span></span>  <span data-ttu-id="50deb-201">对于在 Skype for Business 服务器中使用本地帐户的用户，此行为不可用。</span><span class="sxs-lookup"><span data-stu-id="50deb-201">This behavior is not available for users with an on-premises account in Skype for Business Server.</span></span>  

- <span data-ttu-id="50deb-202">将用户升级到 TeamsOnly 后 (通过分配 TeamsUpgradePolicy 或通过移动 Move-csuser MoveToTeams) ，当用户下次登录到团队时，Skype for Business 中的现有联系人将与已在团队中的现有联系人合并。</span><span class="sxs-lookup"><span data-stu-id="50deb-202">After a user is upgraded to TeamsOnly (either via assigning TeamsUpgradePolicy or via Move-CsUser -MoveToTeams), the next time a user logs into Teams, existing contacts in Skype for Business will be merged with existing contacts already in Teams.</span></span> <span data-ttu-id="50deb-203">无论用户的 Skype for Business 帐户是托管内部还是联机，都会发生此行为。</span><span class="sxs-lookup"><span data-stu-id="50deb-203">This behavior happens whether the user’s Skype for Business Account is homed on-premises or online.</span></span> 

<span data-ttu-id="50deb-204">在这两种情况下，从 Skype for Business 到团队的联系人之间的转移是异步的，因此可能需要几分钟才能使联系人显示在团队中。</span><span class="sxs-lookup"><span data-stu-id="50deb-204">In both cases, the transfer of contacts from Skype for Business to Teams is asynchronous so it may be a few minutes before contacts appear in Teams.</span></span> <span data-ttu-id="50deb-205">上述两个事件是触发副本的起因。</span><span class="sxs-lookup"><span data-stu-id="50deb-205">The two events above are what trigger the copy.</span></span>  

## <a name="related-links"></a><span data-ttu-id="50deb-206">相关链接</span><span class="sxs-lookup"><span data-stu-id="50deb-206">Related links</span></span>

[<span data-ttu-id="50deb-207">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="50deb-207">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="50deb-208">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="50deb-208">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="50deb-209">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="50deb-209">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="50deb-210">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="50deb-210">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="50deb-211">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="50deb-211">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="50deb-212">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="50deb-212">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

