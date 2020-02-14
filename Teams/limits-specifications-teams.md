---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 了解适用于 Microsoft Teams 的限制、规范和其他要求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fd871f36c2261dd5ec243dbd8dbdd52a3a8e694
ms.sourcegitcommit: 93a8bd330c9a8ced81cd3eafb7b7236e9ed2066f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2020
ms.locfileid: "41962081"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="75a8e-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="75a8e-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="75a8e-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="75a8e-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="75a8e-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="75a8e-105">Teams and channels</span></span>

|<span data-ttu-id="75a8e-106">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-106">Feature</span></span>    | <span data-ttu-id="75a8e-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="75a8e-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="75a8e-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="75a8e-108">Number of teams a user can create</span></span> | <span data-ttu-id="75a8e-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="75a8e-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="75a8e-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="75a8e-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="75a8e-111">1,000</span><span class="sxs-lookup"><span data-stu-id="75a8e-111">1,000</span></span>|
|<span data-ttu-id="75a8e-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="75a8e-112">Number of members in a team</span></span> | <span data-ttu-id="75a8e-113">5,000</span><span class="sxs-lookup"><span data-stu-id="75a8e-113">5,000</span></span>       |
|<span data-ttu-id="75a8e-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="75a8e-114">Number of owners per team</span></span> | <span data-ttu-id="75a8e-115">100</span><span class="sxs-lookup"><span data-stu-id="75a8e-115">100</span></span>   |
|<span data-ttu-id="75a8e-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="75a8e-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="75a8e-117">5</span><span class="sxs-lookup"><span data-stu-id="75a8e-117">5</span></span>     |
|<span data-ttu-id="75a8e-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="75a8e-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="75a8e-119">5,000</span><span class="sxs-lookup"><span data-stu-id="75a8e-119">5,000</span></span>       |
|<span data-ttu-id="75a8e-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="75a8e-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="75a8e-121">500,000</span><span class="sxs-lookup"><span data-stu-id="75a8e-121">500,000</span></span>   |
|<span data-ttu-id="75a8e-122">Office 365 租户可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="75a8e-122">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="75a8e-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="75a8e-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="75a8e-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="75a8e-124">Number of channels per team</span></span>    | <span data-ttu-id="75a8e-125">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="75a8e-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="75a8e-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="75a8e-126">Number of Private channels per team</span></span>    |<span data-ttu-id="75a8e-127">30</span><span class="sxs-lookup"><span data-stu-id="75a8e-127">30</span></span>|
|<span data-ttu-id="75a8e-128">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="75a8e-128">Channel conversation post size</span></span> | <span data-ttu-id="75a8e-129">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-129">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="75a8e-130">&sup1; Azure Active Directory 中的目录对象均计入此限额。</span><span class="sxs-lookup"><span data-stu-id="75a8e-130">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="75a8e-131">如同使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="75a8e-131">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="75a8e-132">&sup2; 此限制涵盖已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="75a8e-132">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="75a8e-133">&sup3; 已删除的频道可在删除后 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="75a8e-133">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="75a8e-134">在该等 30 天，已删除的频道仍然计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="75a8e-134">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="75a8e-135">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="75a8e-135">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="75a8e-136"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及、连接器数量和回应。</span><span class="sxs-lookup"><span data-stu-id="75a8e-136"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="75a8e-137">消息传递</span><span class="sxs-lookup"><span data-stu-id="75a8e-137">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="75a8e-138">聊天</span><span class="sxs-lookup"><span data-stu-id="75a8e-138">Chat</span></span>

<span data-ttu-id="75a8e-139">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="75a8e-139">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="75a8e-140">原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="75a8e-140">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="75a8e-141">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="75a8e-141">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="75a8e-142">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。</span><span class="sxs-lookup"><span data-stu-id="75a8e-142">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="75a8e-143">但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="75a8e-143">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="75a8e-144">（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="75a8e-144">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="75a8e-145">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="75a8e-145">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="75a8e-146">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-146">Feature</span></span>  | <span data-ttu-id="75a8e-147">最大限制</span><span class="sxs-lookup"><span data-stu-id="75a8e-147">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="75a8e-148">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-148">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="75a8e-149">100</span><span class="sxs-lookup"><span data-stu-id="75a8e-149">100</span></span>    |
|<span data-ttu-id="75a8e-150">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-150">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="75a8e-151">10</span><span class="sxs-lookup"><span data-stu-id="75a8e-151">10</span></span>     |
|<span data-ttu-id="75a8e-152">聊天大小</span><span class="sxs-lookup"><span data-stu-id="75a8e-152">Chat size</span></span> | <span data-ttu-id="75a8e-153">每篇文章约 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-153">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="75a8e-154"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。</span><span class="sxs-lookup"><span data-stu-id="75a8e-154"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="75a8e-155"><sup>2</sup>如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="75a8e-155"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="75a8e-156"><sup>3</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="75a8e-156"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="75a8e-157">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="75a8e-157">Emailing a channel</span></span>

 <span data-ttu-id="75a8e-158">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="75a8e-158">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="75a8e-159">如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。</span><span class="sxs-lookup"><span data-stu-id="75a8e-159">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="75a8e-160">下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="75a8e-160">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="75a8e-161">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-161">Feature</span></span>  | <span data-ttu-id="75a8e-162">最大限制</span><span class="sxs-lookup"><span data-stu-id="75a8e-162">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="75a8e-163">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-163">Message size<sup>1<sup></span></span> | <span data-ttu-id="75a8e-164">24 KB</span><span class="sxs-lookup"><span data-stu-id="75a8e-164">24 KB</span></span> |
|<span data-ttu-id="75a8e-165">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-165">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="75a8e-166">20</span><span class="sxs-lookup"><span data-stu-id="75a8e-166">20</span></span>     |
|<span data-ttu-id="75a8e-167">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="75a8e-167">Size of each file attachment</span></span> | <span data-ttu-id="75a8e-168">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="75a8e-168">Less than 10 MB</span></span> |
|<span data-ttu-id="75a8e-169">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75a8e-169">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="75a8e-170">50</span><span class="sxs-lookup"><span data-stu-id="75a8e-170">50</span></span>   |

<span data-ttu-id="75a8e-171"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="75a8e-171"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="75a8e-172"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="75a8e-172"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="75a8e-173">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="75a8e-173">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="75a8e-174">所有 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。</span><span class="sxs-lookup"><span data-stu-id="75a8e-174">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="75a8e-175">频道名称</span><span class="sxs-lookup"><span data-stu-id="75a8e-175">Channel names</span></span>

<span data-ttu-id="75a8e-176">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="75a8e-176">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="75a8e-177">字符</span><span class="sxs-lookup"><span data-stu-id="75a8e-177">Characters</span></span>     | <span data-ttu-id="75a8e-178">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="75a8e-178">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="75a8e-179">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="75a8e-179">&#124; ' " ..</span></span>        |
|<span data-ttu-id="75a8e-180">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="75a8e-180">Characters in these ranges</span></span>    | <span data-ttu-id="75a8e-181">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="75a8e-181">0 to 1F</span></span><br><span data-ttu-id="75a8e-182">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="75a8e-182">80 to 9F</span></span>        |
|<span data-ttu-id="75a8e-183">字词</span><span class="sxs-lookup"><span data-stu-id="75a8e-183">Words</span></span>     | <span data-ttu-id="75a8e-184">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="75a8e-184">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="75a8e-185">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="75a8e-185">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="75a8e-186">会议和通话</span><span class="sxs-lookup"><span data-stu-id="75a8e-186">Meetings and calls</span></span>

|<span data-ttu-id="75a8e-187">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-187">Feature</span></span>     | <span data-ttu-id="75a8e-188">最大限制</span><span class="sxs-lookup"><span data-stu-id="75a8e-188">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="75a8e-189">会议中的人员数</span><span class="sxs-lookup"><span data-stu-id="75a8e-189">Number of people in a meeting</span></span>  | <span data-ttu-id="75a8e-190">250</span><span class="sxs-lookup"><span data-stu-id="75a8e-190">250</span></span>    |
|<span data-ttu-id="75a8e-191">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="75a8e-191">Max PowerPoint File Size</span></span> | <span data-ttu-id="75a8e-192">2GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-192">2GB</span></span>|

### <a name="meeting-expiration"></a><span data-ttu-id="75a8e-193">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-193">Meeting expiration</span></span>

|<span data-ttu-id="75a8e-194">会议类型</span><span class="sxs-lookup"><span data-stu-id="75a8e-194">Meeting type</span></span>  |<span data-ttu-id="75a8e-195">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="75a8e-195">Meeting expires after this much time</span></span>  |<span data-ttu-id="75a8e-196">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-196">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="75a8e-197">立即开会</span><span class="sxs-lookup"><span data-stu-id="75a8e-197">Meet now</span></span>     |<span data-ttu-id="75a8e-198">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="75a8e-198">Start time + 8 hours</span></span>         |<span data-ttu-id="75a8e-199">不适用</span><span class="sxs-lookup"><span data-stu-id="75a8e-199">N/A</span></span>         |
|<span data-ttu-id="75a8e-200">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-200">Regular with no end time</span></span>     |<span data-ttu-id="75a8e-201">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-201">Start time + 60 days</span></span>         | <span data-ttu-id="75a8e-202">60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-202">60 days</span></span>        |
|<span data-ttu-id="75a8e-203">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-203">Regular with end time</span></span>     |<span data-ttu-id="75a8e-204">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-204">End time + 60 days</span></span>         |<span data-ttu-id="75a8e-205">60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-205">60 days</span></span>         |
|<span data-ttu-id="75a8e-206">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-206">Recurring with no end time</span></span>     |<span data-ttu-id="75a8e-207">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-207">Start time + 60 days</span></span>         |<span data-ttu-id="75a8e-208">60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-208">60 days</span></span>         |
|<span data-ttu-id="75a8e-209">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-209">Recurring with end time</span></span>     |<span data-ttu-id="75a8e-210">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-210">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="75a8e-211">60 天</span><span class="sxs-lookup"><span data-stu-id="75a8e-211">60 days</span></span>         |



## <a name="teams-live-events"></a><span data-ttu-id="75a8e-212">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="75a8e-212">Teams live events</span></span>

|<span data-ttu-id="75a8e-213">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-213">Feature</span></span>     | <span data-ttu-id="75a8e-214">最大限制</span><span class="sxs-lookup"><span data-stu-id="75a8e-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="75a8e-215">受众规模</span><span class="sxs-lookup"><span data-stu-id="75a8e-215">Audience size</span></span> | <span data-ttu-id="75a8e-216">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="75a8e-216">10,000 attendees</span></span> |
|<span data-ttu-id="75a8e-217">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="75a8e-217">Duration of event</span></span> | <span data-ttu-id="75a8e-218">4 小时</span><span class="sxs-lookup"><span data-stu-id="75a8e-218">4 hours</span></span> |
|<span data-ttu-id="75a8e-219">Office 365 租户中的并发实时事件数</span><span class="sxs-lookup"><span data-stu-id="75a8e-219">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="75a8e-220">15</span><span class="sxs-lookup"><span data-stu-id="75a8e-220">15</span></span> |

<span data-ttu-id="75a8e-221">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="75a8e-221">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="75a8e-222">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="75a8e-222">Presence in Outlook</span></span>

<span data-ttu-id="75a8e-223">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="75a8e-223">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="75a8e-224">若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="75a8e-224">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="75a8e-225">存储空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-225">Storage</span></span>

<span data-ttu-id="75a8e-226">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="75a8e-226">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="75a8e-227">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="75a8e-227">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="75a8e-228">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="75a8e-228">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="75a8e-229">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="75a8e-229">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="75a8e-230">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="75a8e-230">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="75a8e-231">（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="75a8e-231">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="75a8e-232">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。</span><span class="sxs-lookup"><span data-stu-id="75a8e-232">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="75a8e-233">下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="75a8e-233">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="75a8e-234">功能</span><span class="sxs-lookup"><span data-stu-id="75a8e-234">Feature</span></span>                 |<span data-ttu-id="75a8e-235">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="75a8e-235">Office 365 Business Essentials</span></span>  |<span data-ttu-id="75a8e-236"> Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="75a8e-236">Office 365 Business Premium</span></span>   |<span data-ttu-id="75a8e-237">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="75a8e-237">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="75a8e-238">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="75a8e-238">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="75a8e-239">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="75a8e-239">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="75a8e-240">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="75a8e-240">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="75a8e-241">存储空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-241">Storage</span></span>                 |<span data-ttu-id="75a8e-242">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="75a8e-242">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="75a8e-243">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="75a8e-243">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="75a8e-244">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="75a8e-244">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="75a8e-245">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="75a8e-245">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="75a8e-246">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="75a8e-246">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="75a8e-247">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-247">1 TB per organization</span></span>           |
|<span data-ttu-id="75a8e-248">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-248">Storage for Teams Files</span></span> |<span data-ttu-id="75a8e-249">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-249">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="75a8e-250">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-250">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="75a8e-251">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-251">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="75a8e-252">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-252">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="75a8e-253">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-253">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="75a8e-254">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="75a8e-254">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="75a8e-255">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="75a8e-255">File upload limit  (per file)</span></span>    |<span data-ttu-id="75a8e-256">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-256">15 GB</span></span>    |<span data-ttu-id="75a8e-257">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-257">15 GB</span></span>    |<span data-ttu-id="75a8e-258">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-258">15 GB</span></span>    |<span data-ttu-id="75a8e-259">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-259">15 GB</span></span>    |<span data-ttu-id="75a8e-260">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-260">15 GB</span></span>    |<span data-ttu-id="75a8e-261">15 GB</span><span class="sxs-lookup"><span data-stu-id="75a8e-261">15 GB</span></span>    |

<span data-ttu-id="75a8e-262">频道由 SharePoint Online 网站集中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="75a8e-262">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="75a8e-263">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="75a8e-263">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="75a8e-264">联系人</span><span class="sxs-lookup"><span data-stu-id="75a8e-264">Contacts</span></span>

<span data-ttu-id="75a8e-265">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="75a8e-265">Teams uses these contacts:</span></span>

- <span data-ttu-id="75a8e-266">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="75a8e-266">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="75a8e-267">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="75a8e-267">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="75a8e-268">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="75a8e-268">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="75a8e-269">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="75a8e-269">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="75a8e-270">浏览器</span><span class="sxs-lookup"><span data-stu-id="75a8e-270">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="75a8e-271">操作系统</span><span class="sxs-lookup"><span data-stu-id="75a8e-271">Operating systems</span></span>

<span data-ttu-id="75a8e-272">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="75a8e-272">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
