---
title: 管理参与者和来宾的会议策略
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理参与者和来宾的会议策略设置。
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598698"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="652b6-103">会议策略设置 - 参与者&来宾</span><span class="sxs-lookup"><span data-stu-id="652b6-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="652b6-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="652b6-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="652b6-105">这些设置控制哪些会议参与者在获准参加会议之前在大厅中等待，以及允许他们参加会议的参与级别。</span><span class="sxs-lookup"><span data-stu-id="652b6-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="652b6-106">让匿名人员启动会议</span><span class="sxs-lookup"><span data-stu-id="652b6-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="652b6-107">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="652b6-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="652b6-108">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="652b6-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="652b6-109">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="652b6-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="652b6-110">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="652b6-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="652b6-111">用于加入会议的选项因每个 Teams 组的设置和连接方法而异。</span><span class="sxs-lookup"><span data-stu-id="652b6-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="652b6-112">如果你的群组有音频会议，并使用它进行连接，请参阅 [音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="652b6-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="652b6-113">如果你的 Teams 组没有音频会议，请参阅 [在 Teams 中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="652b6-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="652b6-114">让匿名人员启动会议</span><span class="sxs-lookup"><span data-stu-id="652b6-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="652b6-115">此设置是一个按组织者的策略，允许召开无领导电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="652b6-116">此设置控制拨入用户是否可以在没有组织中经过身份验证的用户参加会议的情况下加入会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="652b6-117">默认情况下，此设置已关闭，这意味着拨入用户将在大厅中等待，直到组织中经过身份验证的用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="652b6-118">如果此设置已关闭，并且拨入用户先加入会议并放置在大厅中，则组织用户必须通过 Teams 客户端加入会议，以允许用户从大厅访问。</span><span class="sxs-lookup"><span data-stu-id="652b6-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="652b6-119">拨入用户没有可用的大厅控件。</span><span class="sxs-lookup"><span data-stu-id="652b6-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="652b6-120">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="652b6-120">Automatically admit people</span></span>

<span data-ttu-id="652b6-121">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="652b6-121">This is a per-organizer policy.</span></span> <span data-ttu-id="652b6-122">此设置控制用户是直接加入会议，还是等待大厅，直到经过身份验证的用户获准。</span><span class="sxs-lookup"><span data-stu-id="652b6-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="652b6-123">此设置不适用于拨入用户。</span><span class="sxs-lookup"><span data-stu-id="652b6-123">This setting does not apply to dial-in users.</span></span>

![显示与大厅中用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="652b6-125">会议组织者可以在会议 **邀请中** 单击"会议选项"，更改他们计划的每个会议的此设置。</span><span class="sxs-lookup"><span data-stu-id="652b6-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="652b6-126">在会议选项中，设置标记为"谁可以绕过大厅"。</span><span class="sxs-lookup"><span data-stu-id="652b6-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="652b6-127">如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="652b6-128">设置值</span><span class="sxs-lookup"><span data-stu-id="652b6-128">Setting value</span></span>  |<span data-ttu-id="652b6-129">联接行为</span><span class="sxs-lookup"><span data-stu-id="652b6-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="652b6-130">**所有人**</span><span class="sxs-lookup"><span data-stu-id="652b6-130">**Everyone**</span></span>   |<span data-ttu-id="652b6-131">所有会议参与者都直接加入会议，无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="652b6-132">这包括经过身份验证的用户、来自受信任组织的外部用户 (联合) 、来宾和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="652b6-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="652b6-133">**组织与联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="652b6-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="652b6-134">组织中经过身份验证的用户（包括来宾用户和来自受信任组织的用户）可以直接加入会议，无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="652b6-135">匿名用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="652b6-136">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="652b6-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="652b6-137">组织中经过身份验证的用户（包括来宾用户）可以直接加入会议，无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="652b6-138">来自受信任组织和匿名用户的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="652b6-139">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="652b6-139">This is the default setting.</span></span>           |
|<span data-ttu-id="652b6-140">**仅组织者**</span><span class="sxs-lookup"><span data-stu-id="652b6-140">**Organizer only**</span></span>    |<span data-ttu-id="652b6-141">只有会议组织者可以直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="652b6-142">其他所有人（包括组织中经过身份验证的用户、来宾用户、来自受信任组织的用户和匿名用户）必须在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="652b6-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="652b6-143">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="652b6-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="652b6-144">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="652b6-144">This is a per-organizer policy.</span></span> <span data-ttu-id="652b6-145">此设置控制通过电话拨入的人是直接加入会议还是等待在大厅中，而不考虑" **自动允许人员"** 设置。</span><span class="sxs-lookup"><span data-stu-id="652b6-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="652b6-146">默认情况下，此设置已关闭。</span><span class="sxs-lookup"><span data-stu-id="652b6-146">By default, this setting is turned off.</span></span> <span data-ttu-id="652b6-147">当此设置关闭时，拨入用户将在大厅中等待，直到组织用户使用 Teams 客户端加入会议并准许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="652b6-148">启用此设置后，当组织用户加入会议时，拨入用户将自动加入会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="652b6-149">如果拨入用户在组织用户加入会议之前加入会议，他们将被放置在大厅中，直到组织用户使用 Teams 客户端加入会议并准许他们加入。</span><span class="sxs-lookup"><span data-stu-id="652b6-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="652b6-150">如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。</span><span class="sxs-lookup"><span data-stu-id="652b6-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="652b6-151">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="652b6-151">Enable live captions</span></span>

<span data-ttu-id="652b6-152">此设置是按用户的策略，在会议期间适用。</span><span class="sxs-lookup"><span data-stu-id="652b6-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="652b6-153">此设置控制" **启用实时** 字幕"选项是否可供用户在用户参加的会议中打开和关闭实时字幕。</span><span class="sxs-lookup"><span data-stu-id="652b6-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示"启用实时字幕"选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="652b6-155">设置值</span><span class="sxs-lookup"><span data-stu-id="652b6-155">Setting value</span></span> |<span data-ttu-id="652b6-156">行为</span><span class="sxs-lookup"><span data-stu-id="652b6-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="652b6-157">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="652b6-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="652b6-158">在会议期间，用户不会自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="652b6-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="652b6-159">用户会看到溢出 **菜单中的"** 启用实时字幕" (...) 打开它们。 </span><span class="sxs-lookup"><span data-stu-id="652b6-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="652b6-160">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="652b6-160">This is the default setting.</span></span> |
|<span data-ttu-id="652b6-161">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="652b6-161">**Disabled**</span></span>     | <span data-ttu-id="652b6-162">会议期间为用户禁用了实时字幕。</span><span class="sxs-lookup"><span data-stu-id="652b6-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="652b6-163">用户没有启用它们的选项。</span><span class="sxs-lookup"><span data-stu-id="652b6-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="652b6-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="652b6-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="652b6-165">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="652b6-165">Allow chat in meetings</span></span>

<span data-ttu-id="652b6-166">此设置是每个参与者的设置。</span><span class="sxs-lookup"><span data-stu-id="652b6-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="652b6-167">此设置控制是否在用户的会议中允许会议聊天。</span><span class="sxs-lookup"><span data-stu-id="652b6-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="652b6-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="652b6-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="652b6-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="652b6-169">Related topics</span></span>

- [<span data-ttu-id="652b6-170">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="652b6-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="652b6-171">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="652b6-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="652b6-172">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="652b6-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
