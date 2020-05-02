---
title: Microsoft Teams 应用权限和考虑事项
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理员可以了解 Microsoft 团队应用从其组织请求哪些数据和权限。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ed1e7d4f90fa1be96ac48f376c3cb1b939a39c4
ms.sourcegitcommit: 3325fd9de57367e9dd60685d1fef096921441a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997183"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="0e15b-103">Microsoft Teams 应用权限和考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="0e15b-104">通过 Microsoft Teams 应用可以将一项或多项功能汇聚到一个可以安装、升级和卸载的_应用包_。</span><span class="sxs-lookup"><span data-stu-id="0e15b-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="0e15b-105">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="0e15b-105">The capabilities include:</span></span>

- <span data-ttu-id="0e15b-106">聊天机器人</span><span class="sxs-lookup"><span data-stu-id="0e15b-106">Bots</span></span>
- <span data-ttu-id="0e15b-107">消息传递扩展</span><span class="sxs-lookup"><span data-stu-id="0e15b-107">Messaging extensions</span></span>
- <span data-ttu-id="0e15b-108">选项卡</span><span class="sxs-lookup"><span data-stu-id="0e15b-108">Tabs</span></span>
- <span data-ttu-id="0e15b-109">连接器</span><span class="sxs-lookup"><span data-stu-id="0e15b-109">Connectors</span></span>

<span data-ttu-id="0e15b-110">从策略角度来看，应用由用户许可并由 IT 管理。</span><span class="sxs-lookup"><span data-stu-id="0e15b-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="0e15b-111">但是，大多数情况下，应用的权限和风险配置文件由应用所包含功能的权限和风险配置文件定义。</span><span class="sxs-lookup"><span data-stu-id="0e15b-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="0e15b-112">因此，本文主要介绍功能级别的权限和考虑事项。</span><span class="sxs-lookup"><span data-stu-id="0e15b-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="0e15b-113">下文所列大写字母的权限（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）未出现在 [Microsoft Teams 开发人员文档](https://aka.ms/teamsdevdocs)或 [Microsoft Graph 的权限](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中的任何地方。</span><span class="sxs-lookup"><span data-stu-id="0e15b-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="0e15b-114">使用它们只是为了在本文中进行简要说明。</span><span class="sxs-lookup"><span data-stu-id="0e15b-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="0e15b-116">决策点</span><span class="sxs-lookup"><span data-stu-id="0e15b-116">Decision point</span></span>|<ul><li><span data-ttu-id="0e15b-117">使用下表作为指南，了解正在调查的应用所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="0e15b-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="0e15b-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0e15b-119">Next step</span></span>|<ul><li><span data-ttu-id="0e15b-120">研究应用或服务本身，确定是否希望允许在组织内访问它。</span><span class="sxs-lookup"><span data-stu-id="0e15b-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="0e15b-121">例如，bot 从用户发送和接收消息，除了企业自定义机器人外，它们位于合规性边界之外。</span><span class="sxs-lookup"><span data-stu-id="0e15b-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="0e15b-122">因此，任何包含机器人的应用都需要这些权限，并且至少具有该风险配置文件。</span><span class="sxs-lookup"><span data-stu-id="0e15b-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="0e15b-123">全局应用权限和注意事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="0e15b-124">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-124">Required permissions</span></span>

<span data-ttu-id="0e15b-125">无</span><span class="sxs-lookup"><span data-stu-id="0e15b-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="0e15b-126">可选权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-126">Optional permissions</span></span>

<span data-ttu-id="0e15b-127">无</span><span class="sxs-lookup"><span data-stu-id="0e15b-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="0e15b-128">考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-128">Considerations</span></span>

<span data-ttu-id="0e15b-129">应用必须公开它所使用的数据以及数据在其使用条款和隐私策略链接中的用途。</span><span class="sxs-lookup"><span data-stu-id="0e15b-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span></td>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="0e15b-130">机器人和消息扩展</span><span class="sxs-lookup"><span data-stu-id="0e15b-130">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="0e15b-131">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-131">Required permissions</span></span>

- <span data-ttu-id="0e15b-132">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="0e15b-132">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="0e15b-133">聊天机器人可以接收来自用户的消息以及回复用户。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0e15b-133">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="0e15b-134">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="0e15b-134">POST_MESSAGE_USER.</span></span> <span data-ttu-id="0e15b-135">用户将消息发送到 bot 后，机器人可以随时发送用户直接消息（也称为*主动消息*）。</span><span class="sxs-lookup"><span data-stu-id="0e15b-135">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="0e15b-136">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="0e15b-136">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="0e15b-137">添加到团队的聊天机器人可以获取团队中的频道的名称和 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="0e15b-137">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="0e15b-138">可选权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-138">Optional permissions</span></span>

- <span data-ttu-id="0e15b-139">3x3.</span><span class="sxs-lookup"><span data-stu-id="0e15b-139">IDENTITY.</span></span> <span data-ttu-id="0e15b-140">当它在频道中使用时，应用的智能机器人可以访问团队成员的基本标识信息（名字、姓氏、用户主体名称 [UPN]、电子邮件地址）;在个人或群组聊天中使用时，机器人可以访问这些用户的相同信息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-140">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="0e15b-141">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="0e15b-141">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="0e15b-142">允许应用的 bot 随时向任何团队成员发送（主动）消息，即使用户以前从未与 bot 聊天。</span><span class="sxs-lookup"><span data-stu-id="0e15b-142">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="0e15b-143">以下内容不是显式权限，而是通过 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用机器人的范围（在清单中声明）进行隐含：</span><span class="sxs-lookup"><span data-stu-id="0e15b-143">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="0e15b-144">RECEIVE_MESSAGE_PERSONAL，REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="0e15b-144">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="0e15b-145">RECEIVE_MESSAGE_GROUPCHAT，REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="0e15b-145">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="0e15b-146">RECEIVE_MESSAGE_TEAM，REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="0e15b-146">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="0e15b-147">SEND_FILES，RECEIVE_FILES。<sup>2</sup>控制机器人是否可以在个人聊天中发送和接收文件（对于群组聊天或频道尚不支持）。</span><span class="sxs-lookup"><span data-stu-id="0e15b-147">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="0e15b-148">考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-148">Considerations</span></span>

- <span data-ttu-id="0e15b-149">Bot 只能访问已添加的团队或已安装他们的用户。</span><span class="sxs-lookup"><span data-stu-id="0e15b-149">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="0e15b-150">Bot 仅接收用户明确提及的消息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-150">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="0e15b-151">此数据将离开公司网络。</span><span class="sxs-lookup"><span data-stu-id="0e15b-151">This data leaves the corporate network.</span></span>

- <span data-ttu-id="0e15b-152">机器人只能回复所提及的对话。</span><span class="sxs-lookup"><span data-stu-id="0e15b-152">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="0e15b-153">在用户使用机器人 conversed 后，如果 bot 存储该用户的 ID，它可以随时发送该用户直接消息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-153">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="0e15b-154">从理论上讲，bot 邮件包含指向网络钓鱼或恶意网站的链接，但用户可以通过 Microsoft、租户管理员或由 Microsoft 全局阻止。</span><span class="sxs-lookup"><span data-stu-id="0e15b-154">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="0e15b-155">Bot 可以为应用添加到的团队成员或个人或群组聊天中的单个用户检索和存储非常基本的标识信息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-155">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="0e15b-156">若要获取有关这些用户的详细信息，机器人必须要求他们登录到 Azure Active Directory （Azure AD）</span><span class="sxs-lookup"><span data-stu-id="0e15b-156">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD)</span></span>

- <span data-ttu-id="0e15b-157">机器人可以检索团队中的频道列表，并可以存储这些频道的列表;此数据将离开公司网络。</span><span class="sxs-lookup"><span data-stu-id="0e15b-157">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="0e15b-158">将文件发送到机器人时，该文件将离开公司网络。</span><span class="sxs-lookup"><span data-stu-id="0e15b-158">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="0e15b-159">发送和接收文件需要对每个文件进行用户审批。</span><span class="sxs-lookup"><span data-stu-id="0e15b-159">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="0e15b-160">默认情况下，bot 无法代表用户执行操作，但机器人可以让用户登录;一旦用户登录，bot 将拥有一个访问令牌，它可以执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="0e15b-160">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="0e15b-161">这些附加内容的具体内容取决于 bot 和用户登录的位置： bot 是注册的 Azure AD 应用https://apps.dev.microsoft.com/ ，并且可以拥有自己的权限集。</span><span class="sxs-lookup"><span data-stu-id="0e15b-161">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="0e15b-162">只要向团队中添加或删除用户，就会通知机器人。</span><span class="sxs-lookup"><span data-stu-id="0e15b-162">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="0e15b-163">Bot 看不到用户的 IP 地址或其他引用信息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-163">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="0e15b-164">所有信息均来自 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0e15b-164">All information comes from Microsoft.</span></span> <span data-ttu-id="0e15b-165">（有一个例外：如果机器人实现自己的登录体验，登录用户界面将看到用户的 IP 地址和引用信息。）</span><span class="sxs-lookup"><span data-stu-id="0e15b-165">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="0e15b-166">另一方面，邮件扩展功能请参阅用户的 IP 地址和引用信息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-166">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="0e15b-167">应用指南（和我们的 AppSource 审查流程）需要在向用户发布个人聊天消息（通过 POST_MESSAGE_TEAM 权限）时决定是否有效。</span><span class="sxs-lookup"><span data-stu-id="0e15b-167">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="0e15b-168">在滥用的情况下，用户可以阻止机器人，租户管理员可以阻止该应用，并且 Microsoft 可以在必要时集中阻止机器人。</span><span class="sxs-lookup"><span data-stu-id="0e15b-168">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="0e15b-169"><sup>1</sup>某些机器人仅发送邮件（POST_MESSAGE_USER）。</span><span class="sxs-lookup"><span data-stu-id="0e15b-169"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="0e15b-170">它们称为 "仅通知" 功能人员，但术语没有指允许或不允许机器人执行的操作，这意味着机器人不希望公开会话体验。</span><span class="sxs-lookup"><span data-stu-id="0e15b-170">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="0e15b-171">团队使用此字段在 UI 中禁用通常启用的功能;与确实公开会话体验的 bot 相比，机器人不受允许的功能。</span><span class="sxs-lookup"><span data-stu-id="0e15b-171">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="0e15b-172"><sup>2</sup>由应用程序的 supportsFiles 文件中的 bot 对象上的布尔属性控制。</span><span class="sxs-lookup"><span data-stu-id="0e15b-172"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="0e15b-173">如果机器人有自己的登录，则在用户第一次登录时有另一种不同的同意体验。</span><span class="sxs-lookup"><span data-stu-id="0e15b-173">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="0e15b-174">目前，与团队应用（机器人、选项卡、连接器或消息扩展）内的任何功能相关联的 Azure AD 权限完全独立于此处列出的团队权限。</span><span class="sxs-lookup"><span data-stu-id="0e15b-174">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="0e15b-175">选项卡</span><span class="sxs-lookup"><span data-stu-id="0e15b-175">Tabs</span></span>

<span data-ttu-id="0e15b-176">选项卡是在团队内运行的网站。</span><span class="sxs-lookup"><span data-stu-id="0e15b-176">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="0e15b-177">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-177">Required permissions</span></span>

<span data-ttu-id="0e15b-178">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="0e15b-178">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="0e15b-179">可选权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-179">Optional permissions</span></span>

<span data-ttu-id="0e15b-180">无（当前）</span><span class="sxs-lookup"><span data-stu-id="0e15b-180">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="0e15b-181">考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-181">Considerations</span></span>

- <span data-ttu-id="0e15b-182">选项卡的风险配置文件与在浏览器选项卡中运行的同一网站几乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="0e15b-182">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="0e15b-183">选项卡还获取正在运行的上下文，其中包括当前用户的登录名和 UPN、当前用户的 Azure AD 对象 ID、当前用户的 Azure AD 对象 ID、它所在的 Office 365 组的 ID （如果是团队）、租户 ID 以及用户的当前区域设置。</span><span class="sxs-lookup"><span data-stu-id="0e15b-183">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="0e15b-184">但是，若要将这些 Id 映射到用户的信息，选项卡将必须使用户登录到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="0e15b-184">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="0e15b-185">连接器</span><span class="sxs-lookup"><span data-stu-id="0e15b-185">Connectors</span></span>

<span data-ttu-id="0e15b-186">当发生外部系统中的事件时，连接器将消息发送到频道。</span><span class="sxs-lookup"><span data-stu-id="0e15b-186">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="0e15b-187">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-187">Required permissions</span></span>

<span data-ttu-id="0e15b-188">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="0e15b-188">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="0e15b-189">可选权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-189">Optional permissions</span></span>

<span data-ttu-id="0e15b-190">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="0e15b-190">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="0e15b-191">某些连接器支持可操作的消息，这些消息允许用户将目标回复发布到连接器消息，例如，将响应添加到 GitHub 问题或将日期添加到 Trello 卡。</span><span class="sxs-lookup"><span data-stu-id="0e15b-191">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="0e15b-192">考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-192">Considerations</span></span>

- <span data-ttu-id="0e15b-193">发布连接器消息的系统不知道它的发件人或接收邮件的人员：不透露有关该收件人的任何信息。</span><span class="sxs-lookup"><span data-stu-id="0e15b-193">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="0e15b-194">（Microsoft 是实际的收件人，而不是租户;Microsoft 会向该频道发送实际帖子。）</span><span class="sxs-lookup"><span data-stu-id="0e15b-194">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="0e15b-195">将连接器消息发送到频道时，任何数据都不会离开公司网络。</span><span class="sxs-lookup"><span data-stu-id="0e15b-195">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="0e15b-196">支持可操作消息的连接器（REPLYTO_CONNECTOR_MESSAGE 权限）也看不到 IP 地址和引用信息;此信息将发送到 Microsoft，然后路由到以前在连接器门户中注册到 Microsoft 的 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="0e15b-196">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="0e15b-197">每次为通道配置连接器时，都会创建该连接器实例的唯一 URL。</span><span class="sxs-lookup"><span data-stu-id="0e15b-197">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="0e15b-198">如果该连接器实例已删除，则无法再使用该 URL。</span><span class="sxs-lookup"><span data-stu-id="0e15b-198">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="0e15b-199">连接器消息不能包含文件附件。</span><span class="sxs-lookup"><span data-stu-id="0e15b-199">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="0e15b-200">连接器实例 URL 应视为机密/机密：拥有该 URL 的任何人都可以发布到该 url，例如电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0e15b-200">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="0e15b-201">因此，存在垃圾邮件或链接到网络钓鱼或恶意软件站点的风险。</span><span class="sxs-lookup"><span data-stu-id="0e15b-201">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="0e15b-202">如果发生这种情况，团队所有者可以删除连接器实例。</span><span class="sxs-lookup"><span data-stu-id="0e15b-202">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="0e15b-203">如果发送连接器消息的服务遭到破坏并开始发送垃圾邮件/网络钓鱼/恶意软件链接，租户管理员可以阻止创建新的连接器实例，并且 Microsoft 可以集中阻止它们。</span><span class="sxs-lookup"><span data-stu-id="0e15b-203">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="0e15b-204">目前尚不能知道哪些连接器支持可操作的消息（REPLYTO_CONNECTOR_MESSAGE 权限）。</span><span class="sxs-lookup"><span data-stu-id="0e15b-204">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="0e15b-205">传出 webhooks</span><span class="sxs-lookup"><span data-stu-id="0e15b-205">Outgoing webhooks</span></span>

<span data-ttu-id="0e15b-206">*传出 webhooks*由团队所有者或团队成员动态创建。</span><span class="sxs-lookup"><span data-stu-id="0e15b-206">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="0e15b-207">它们不是团队应用的功能;包含此信息是为了实现完整性。</span><span class="sxs-lookup"><span data-stu-id="0e15b-207">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="0e15b-208">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-208">Required permissions</span></span>

<span data-ttu-id="0e15b-209">RECEIVE_MESSAGE，REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="0e15b-209">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="0e15b-210">可接收来自用户的消息并答复他们。</span><span class="sxs-lookup"><span data-stu-id="0e15b-210">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="0e15b-211">可选权限</span><span class="sxs-lookup"><span data-stu-id="0e15b-211">Optional permissions</span></span>

<span data-ttu-id="0e15b-212">无</span><span class="sxs-lookup"><span data-stu-id="0e15b-212">None</span></span>

### <a name="considerations"></a><span data-ttu-id="0e15b-213">考虑事项</span><span class="sxs-lookup"><span data-stu-id="0e15b-213">Considerations</span></span>

- <span data-ttu-id="0e15b-214">传出 webhooks 类似于 bot，但权限较少。</span><span class="sxs-lookup"><span data-stu-id="0e15b-214">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="0e15b-215">它们必须明确提及，就像机器人一样。</span><span class="sxs-lookup"><span data-stu-id="0e15b-215">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="0e15b-216">注册传出 webhook 后，将生成一个机密，它允许传出 webhook 验证发件人是否为 Microsoft 团队，而不是恶意攻击者。</span><span class="sxs-lookup"><span data-stu-id="0e15b-216">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="0e15b-217">此机密应保密;有权访问的任何人都可以模仿 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="0e15b-217">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="0e15b-218">如果机密遭到破坏，则可以删除并重新创建传出 webhook，并且将生成新的密码。</span><span class="sxs-lookup"><span data-stu-id="0e15b-218">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="0e15b-219">尽管可以创建不验证机密的传出 webhook，但我们建议您不要使用它。</span><span class="sxs-lookup"><span data-stu-id="0e15b-219">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="0e15b-220">除了接收和答复邮件之外，传出 webhooks 无法主动发送邮件、无法发送或接收文件，他们也无法执行除接收和答复邮件之外的任何其他机器人功能。</span><span class="sxs-lookup"><span data-stu-id="0e15b-220">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
