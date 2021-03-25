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
description: 管理员可以了解 Microsoft Teams 应用正在向组织请求哪些数据和权限。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120854"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="64087-103">Microsoft Teams 应用权限和考虑事项</span><span class="sxs-lookup"><span data-stu-id="64087-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="64087-104">Microsoft Teams 应用是一种将一个或多个功能聚合到可安装、升级和卸载的应用包的方法。</span><span class="sxs-lookup"><span data-stu-id="64087-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="64087-105">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="64087-105">The capabilities include:</span></span>

- <span data-ttu-id="64087-106">机器人</span><span class="sxs-lookup"><span data-stu-id="64087-106">Bots</span></span>
- <span data-ttu-id="64087-107">消息传送扩展</span><span class="sxs-lookup"><span data-stu-id="64087-107">Messaging extensions</span></span>
- <span data-ttu-id="64087-108">选项卡</span><span class="sxs-lookup"><span data-stu-id="64087-108">Tabs</span></span>
- <span data-ttu-id="64087-109">连接器</span><span class="sxs-lookup"><span data-stu-id="64087-109">Connectors</span></span>

<span data-ttu-id="64087-110">应用由用户许可，由 IT 从策略角度进行管理。</span><span class="sxs-lookup"><span data-stu-id="64087-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="64087-111">但是，大多数情况下，应用的权限和风险配置文件由应用包含的功能的权限和风险配置文件定义。</span><span class="sxs-lookup"><span data-stu-id="64087-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="64087-112">因此，本文重点介绍功能级别的权限和注意事项。</span><span class="sxs-lookup"><span data-stu-id="64087-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="64087-113">下面以大写字母列出的权限（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）不会显示在 [Microsoft Teams](/microsoftteams/platform/overview) 开发人员文档或 [Microsoft Graph](/graph/permissions-reference)的权限中。</span><span class="sxs-lookup"><span data-stu-id="64087-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](/microsoftteams/platform/overview) or the [permissions for Microsoft Graph](/graph/permissions-reference).</span></span> <span data-ttu-id="64087-114">它们只是本文的描述性简写。</span><span class="sxs-lookup"><span data-stu-id="64087-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="64087-115">标题</span><span class="sxs-lookup"><span data-stu-id="64087-115">Title</span></span>   | <span data-ttu-id="64087-116">描述</span><span class="sxs-lookup"><span data-stu-id="64087-116">Description</span></span>    |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="64087-118">决策点</span><span class="sxs-lookup"><span data-stu-id="64087-118">Decision point</span></span>|<ul><li><span data-ttu-id="64087-119">使用下表作为指南，了解正在调查的应用正在请求哪些权限。</span><span class="sxs-lookup"><span data-stu-id="64087-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="64087-121">后续步骤</span><span class="sxs-lookup"><span data-stu-id="64087-121">Next step</span></span>|<ul><li><span data-ttu-id="64087-122">研究应用或服务本身，确定是否允许在组织中访问它。</span><span class="sxs-lookup"><span data-stu-id="64087-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="64087-123">例如，机器人发送和接收来自用户的消息，并且（企业自定义机器人除外）位于符合性边界之外。</span><span class="sxs-lookup"><span data-stu-id="64087-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="64087-124">因此，包含机器人的任何应用都需要这些权限，并且至少具有该风险配置文件。</span><span class="sxs-lookup"><span data-stu-id="64087-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="64087-125">另请参阅 [请求 Microsoft Teams 选项卡的设备权限](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。</span><span class="sxs-lookup"><span data-stu-id="64087-125">See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="64087-126">全局应用权限和注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64087-127">所需权限</span><span class="sxs-lookup"><span data-stu-id="64087-127">Required permissions</span></span>

<span data-ttu-id="64087-128">无</span><span class="sxs-lookup"><span data-stu-id="64087-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64087-129">可选权限</span><span class="sxs-lookup"><span data-stu-id="64087-129">Optional permissions</span></span>

<span data-ttu-id="64087-130">无</span><span class="sxs-lookup"><span data-stu-id="64087-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="64087-131">注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-131">Considerations</span></span>

- <span data-ttu-id="64087-132">应用必须披露它使用哪些数据，以及该数据在其使用条款和隐私策略链接中用于哪些内容。</span><span class="sxs-lookup"><span data-stu-id="64087-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="64087-133">[特定于资源的许可](resource-specific-consent.md) 提供应用可以请求的一组权限，该权限显示在应用的安装屏幕上。</span><span class="sxs-lookup"><span data-stu-id="64087-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="64087-134">若要详细了解特定于资源的许可权限，请参阅 [Graph 权限参考](/graph/permissions-reference#teams-resource-specific-consent-permissions)。</span><span class="sxs-lookup"><span data-stu-id="64087-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="64087-135">应用可能还需要除特定于资源的许可权限外的权限。</span><span class="sxs-lookup"><span data-stu-id="64087-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="64087-136">安装应用后，应用可以通过许可提示请求 Graph 权限。</span><span class="sxs-lookup"><span data-stu-id="64087-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="64087-137">有关详细信息，请参阅了解 [Azure AD 应用程序许可体验](/azure/active-directory/develop/application-consent-experience)。</span><span class="sxs-lookup"><span data-stu-id="64087-137">To learn more, see [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="64087-138">可以在 Azure 门户中配置 API 权限和许可。</span><span class="sxs-lookup"><span data-stu-id="64087-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="64087-139">有关详细信息，请参阅 [Azure Active Directory 许可框架](/azure/active-directory/develop/consent-framework)。</span><span class="sxs-lookup"><span data-stu-id="64087-139">To learn more, see [Azure Active Directory consent framework](/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="64087-140">机器人和消息传送扩展</span><span class="sxs-lookup"><span data-stu-id="64087-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64087-141">所需权限</span><span class="sxs-lookup"><span data-stu-id="64087-141">Required permissions</span></span>

- <span data-ttu-id="64087-142">RECEIVE_MESSAGE，REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="64087-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="64087-143">机器人可以接收来自用户的消息并回复它们。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="64087-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="64087-144">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="64087-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="64087-145">在用户向机器人发送消息后，机器人可以发送用户直接消息 (也称 *主动* 消息。</span><span class="sxs-lookup"><span data-stu-id="64087-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="64087-146">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="64087-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="64087-147">添加到团队的机器人可以获取团队中频道的名称和 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="64087-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64087-148">可选权限</span><span class="sxs-lookup"><span data-stu-id="64087-148">Optional permissions</span></span>

- <span data-ttu-id="64087-149">IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="64087-149">IDENTITY.</span></span> <span data-ttu-id="64087-150">在通道中使用时，应用的机器人可以访问团队成员的基本标识信息 (名字、姓氏、用户主体名称 [UPN]、电子邮件地址) ;在个人聊天或群组聊天中使用时，机器人可以访问这些用户的相同信息。</span><span class="sxs-lookup"><span data-stu-id="64087-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="64087-151">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="64087-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="64087-152">允许应用的机器人随时向任何团队成员 (主动) 消息，即使用户以前从未与机器人交谈。</span><span class="sxs-lookup"><span data-stu-id="64087-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="64087-153">以下不是显式权限，但由 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用机器人的范围（在清单中声明）所暗示：</span><span class="sxs-lookup"><span data-stu-id="64087-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="64087-154">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="64087-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="64087-155">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="64087-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="64087-156">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="64087-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="64087-157">SEND_FILES，RECEIVE_FILES。<sup>2</sup> 控制机器人是否可以在个人聊天中发送和接收文件， (聊天或聊天通道) 。</span><span class="sxs-lookup"><span data-stu-id="64087-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="64087-158">注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-158">Considerations</span></span>

- <span data-ttu-id="64087-159">机器人只能访问已添加到的团队或已安装机器人的用户。</span><span class="sxs-lookup"><span data-stu-id="64087-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="64087-160">机器人仅接收用户明确提及它们的消息。</span><span class="sxs-lookup"><span data-stu-id="64087-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="64087-161">此数据离开企业网络。</span><span class="sxs-lookup"><span data-stu-id="64087-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="64087-162">机器人只能回复提及它们的对话。</span><span class="sxs-lookup"><span data-stu-id="64087-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="64087-163">在用户与机器人交谈后，如果机器人存储该用户的 ID，则它随时都可以向该用户发送直接消息。</span><span class="sxs-lookup"><span data-stu-id="64087-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="64087-164">从理论上讲，机器人消息可以包含指向钓鱼或恶意软件网站的链接，但用户、租户管理员或 Microsoft 可以全局阻止机器人。</span><span class="sxs-lookup"><span data-stu-id="64087-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="64087-165">机器人可以检索 (，并) 应用已添加到的团队成员或个人或群组聊天中的单个用户的基本标识信息。</span><span class="sxs-lookup"><span data-stu-id="64087-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="64087-166">若要获取有关这些用户的进一步信息，机器人必须要求他们登录到 Azure AD (Azure Active Directory) 。</span><span class="sxs-lookup"><span data-stu-id="64087-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="64087-167">机器人可以检索 (，并) 团队中的频道列表;此数据会离开企业网络。</span><span class="sxs-lookup"><span data-stu-id="64087-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="64087-168">将文件发送到机器人时，该文件会离开企业网络。</span><span class="sxs-lookup"><span data-stu-id="64087-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="64087-169">发送和接收文件需要用户批准每个文件。</span><span class="sxs-lookup"><span data-stu-id="64087-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="64087-170">默认情况下，机器人无法代表用户操作，但机器人可以请求用户登录;用户登录后，机器人将拥有一个访问令牌，可以使用该令牌执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="64087-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="64087-171">这些附加内容完全取决于机器人以及用户登录位置：机器人是注册到 的 Azure AD 应用，可以有自己的权限 https://apps.dev.microsoft.com/ 集。</span><span class="sxs-lookup"><span data-stu-id="64087-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="64087-172">每当向团队添加或删除用户时，都会通知机器人。</span><span class="sxs-lookup"><span data-stu-id="64087-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="64087-173">机器人看不到用户的 IP 地址或其他引用网站信息。</span><span class="sxs-lookup"><span data-stu-id="64087-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="64087-174">所有信息都来自 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="64087-174">All information comes from Microsoft.</span></span> <span data-ttu-id="64087-175"> (有一个例外：如果机器人实现了自己的登录体验，则登录 UI 将看到用户的 IP 地址和引用网站信息。) </span><span class="sxs-lookup"><span data-stu-id="64087-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="64087-176">另一方面，消息传送扩展会查看用户的 IP 地址和引用网站信息。</span><span class="sxs-lookup"><span data-stu-id="64087-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="64087-177">应用 (以及我们的 AppSource 评审) 需要自行决定是否出于有效目的 (通过 POST_MESSAGE_TEAM 权限) 用户发布个人聊天消息。</span><span class="sxs-lookup"><span data-stu-id="64087-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="64087-178">如果滥用，用户可以阻止机器人，租户管理员可以阻止应用，并且 Microsoft 可以在必要时集中阻止机器人。</span><span class="sxs-lookup"><span data-stu-id="64087-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="64087-179"><sup>1</sup> 某些机器人仅向 (POST_MESSAGE_USER) 。</span><span class="sxs-lookup"><span data-stu-id="64087-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="64087-180">它们称为"仅通知"机器人，但术语不是指允许或不允许机器人执行什么操作，这意味着机器人不希望公开聊天体验。</span><span class="sxs-lookup"><span data-stu-id="64087-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="64087-181">Teams 使用此字段禁用通常启用的 UI 中的功能;与公开聊天体验的机器人相比，机器人在允许执行哪些操作方面没有限制。</span><span class="sxs-lookup"><span data-stu-id="64087-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="64087-182"><sup>2</sup> 由应用的文件的 manifest.js对象上的 supportsFiles Boolean 属性控制。</span><span class="sxs-lookup"><span data-stu-id="64087-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="64087-183">如果机器人有其自己的登录，则用户首次登录时，会经历另一种不同的许可体验。</span><span class="sxs-lookup"><span data-stu-id="64087-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="64087-184">目前，与 Teams 应用内的任何功能关联的 Azure AD 权限 (机器人、选项卡、连接器或消息传送扩展) 完全独立于此处列出的 Teams 权限。</span><span class="sxs-lookup"><span data-stu-id="64087-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="64087-185">选项卡</span><span class="sxs-lookup"><span data-stu-id="64087-185">Tabs</span></span>

<span data-ttu-id="64087-186">选项卡是在 Teams 中运行的网站。</span><span class="sxs-lookup"><span data-stu-id="64087-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64087-187">所需权限</span><span class="sxs-lookup"><span data-stu-id="64087-187">Required permissions</span></span>

<span data-ttu-id="64087-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="64087-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64087-189">可选权限</span><span class="sxs-lookup"><span data-stu-id="64087-189">Optional permissions</span></span>

<span data-ttu-id="64087-190">当前 (无) </span><span class="sxs-lookup"><span data-stu-id="64087-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="64087-191">注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-191">Considerations</span></span>

- <span data-ttu-id="64087-192">选项卡的风险配置文件几乎与在浏览器选项卡中运行的同一网站相同。</span><span class="sxs-lookup"><span data-stu-id="64087-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="64087-193">选项卡还会获取其运行上下文，包括当前用户的登录名和 UPN、当前用户的 Azure AD 对象 ID、驻留在 (的 Microsoft 365 组的 ID（如果是团队) 、租户 ID 和用户的当前区域设置）。</span><span class="sxs-lookup"><span data-stu-id="64087-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="64087-194">但是，若要将这些 ID 映射到用户的信息，该选项卡必须让用户登录到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="64087-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="64087-195">连接器</span><span class="sxs-lookup"><span data-stu-id="64087-195">Connectors</span></span>

<span data-ttu-id="64087-196">当外部系统中发生事件时，连接器将消息发送到通道。</span><span class="sxs-lookup"><span data-stu-id="64087-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64087-197">所需权限</span><span class="sxs-lookup"><span data-stu-id="64087-197">Required permissions</span></span>

<span data-ttu-id="64087-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="64087-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64087-199">可选权限</span><span class="sxs-lookup"><span data-stu-id="64087-199">Optional permissions</span></span>

<span data-ttu-id="64087-200">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="64087-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="64087-201">某些连接器支持可操作的消息，允许用户向连接器消息发布定向回复，例如，通过向 GitHub 问题添加响应或向 Trello 卡添加日期。</span><span class="sxs-lookup"><span data-stu-id="64087-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="64087-202">注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-202">Considerations</span></span>

- <span data-ttu-id="64087-203">发布连接器消息的系统不知道邮件的发布对象或接收者：不会披露有关收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="64087-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="64087-204"> (Microsoft 是实际收件人，而不是租户;Microsoft 向 channel.) </span><span class="sxs-lookup"><span data-stu-id="64087-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="64087-205">将连接器消息发布至通道时，没有数据离开企业网络。</span><span class="sxs-lookup"><span data-stu-id="64087-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="64087-206">支持可操作消息的连接器 (REPLYTO_CONNECTOR_MESSAGE权限) 也看不到 IP 地址和引用服务器信息;此信息将发送到 Microsoft，然后路由到以前在连接器门户中向 Microsoft 注册的 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="64087-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="64087-207">每次为通道配置连接器时，会创建该连接器实例的唯一 URL。</span><span class="sxs-lookup"><span data-stu-id="64087-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="64087-208">如果删除该连接器实例，则无法再使用 URL。</span><span class="sxs-lookup"><span data-stu-id="64087-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="64087-209">连接器消息不能包含文件附件。</span><span class="sxs-lookup"><span data-stu-id="64087-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="64087-210">连接器实例 URL 应视为机密/机密：拥有该 URL 的任何人都可以发布，例如电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="64087-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="64087-211">因此，存在垃圾邮件或指向网络钓鱼或恶意软件网站的链接的风险。</span><span class="sxs-lookup"><span data-stu-id="64087-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="64087-212">如果发生这种情况，团队所有者可以删除连接器实例。</span><span class="sxs-lookup"><span data-stu-id="64087-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="64087-213">如果发送连接器消息的服务遭到入侵并开始发送垃圾邮件/钓鱼/恶意软件链接，租户管理员可以阻止创建新的连接器实例，Microsoft 可以集中阻止它们。</span><span class="sxs-lookup"><span data-stu-id="64087-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="64087-214">目前无法知道哪些连接器支持可操作消息 (REPLYTO_CONNECTOR_MESSAGE权限) 。</span><span class="sxs-lookup"><span data-stu-id="64087-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="64087-215">传出 Webhook</span><span class="sxs-lookup"><span data-stu-id="64087-215">Outgoing webhooks</span></span>

<span data-ttu-id="64087-216">*传出 Webhook* 由团队所有者或团队成员进行创建。</span><span class="sxs-lookup"><span data-stu-id="64087-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="64087-217">它们不是 Teams 应用的功能;为了完整，包含此信息。</span><span class="sxs-lookup"><span data-stu-id="64087-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64087-218">所需权限</span><span class="sxs-lookup"><span data-stu-id="64087-218">Required permissions</span></span>

<span data-ttu-id="64087-219">RECEIVE_MESSAGE，REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="64087-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="64087-220">可以接收来自用户的消息并回复他们。</span><span class="sxs-lookup"><span data-stu-id="64087-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64087-221">可选权限</span><span class="sxs-lookup"><span data-stu-id="64087-221">Optional permissions</span></span>

<span data-ttu-id="64087-222">无</span><span class="sxs-lookup"><span data-stu-id="64087-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="64087-223">注意事项</span><span class="sxs-lookup"><span data-stu-id="64087-223">Considerations</span></span>

- <span data-ttu-id="64087-224">传出 Webhook 类似于机器人，但权限较少。</span><span class="sxs-lookup"><span data-stu-id="64087-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="64087-225">必须明确提及它们，就像机器人一样。</span><span class="sxs-lookup"><span data-stu-id="64087-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="64087-226">注册传出 Webhook 时，会生成一个机密，该机密允许传出 Webhook 验证发送方是 Microsoft Teams 而不是恶意攻击者。</span><span class="sxs-lookup"><span data-stu-id="64087-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="64087-227">此机密应保留为机密;有权访问它的任何人都可以模拟 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="64087-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="64087-228">如果机密泄露，可以删除并重新创建传出 Webhook，并生成新的机密。</span><span class="sxs-lookup"><span data-stu-id="64087-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="64087-229">虽然可以创建不验证机密的传出 Webhook，但建议不要这样做。</span><span class="sxs-lookup"><span data-stu-id="64087-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="64087-230">除了接收和答复消息外，传出 Webhook 无法执行许多操作：它们无法主动发送消息，无法发送或接收文件，除了接收和答复消息之外，他们无法执行机器人可以执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="64087-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>