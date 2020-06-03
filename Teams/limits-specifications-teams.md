---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 本文介绍了适用于 Microsoft Teams 的限制、规范和其他要求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebdd3204be74e3f7b923d977e6de25c041c2038e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44512819"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="40300-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="40300-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="40300-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="40300-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="40300-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="40300-105">Teams and channels</span></span>

|<span data-ttu-id="40300-106">功能</span><span class="sxs-lookup"><span data-stu-id="40300-106">Feature</span></span>    | <span data-ttu-id="40300-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="40300-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="40300-108">Number of teams a user can create</span></span> | <span data-ttu-id="40300-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="40300-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="40300-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="40300-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="40300-111">1,000</span><span class="sxs-lookup"><span data-stu-id="40300-111">1,000</span></span>|
|<span data-ttu-id="40300-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="40300-112">Number of members in a team</span></span> | <span data-ttu-id="40300-113">10,000</span><span class="sxs-lookup"><span data-stu-id="40300-113">10,000</span></span>       |
|<span data-ttu-id="40300-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="40300-114">Number of owners per team</span></span> | <span data-ttu-id="40300-115">100</span><span class="sxs-lookup"><span data-stu-id="40300-115">100</span></span>   |
|<span data-ttu-id="40300-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="40300-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="40300-117">5</span><span class="sxs-lookup"><span data-stu-id="40300-117">5</span></span>     |
|<span data-ttu-id="40300-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="40300-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="40300-119">5,000</span><span class="sxs-lookup"><span data-stu-id="40300-119">5,000</span></span>       |
|<span data-ttu-id="40300-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="40300-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="40300-121">500,000</span><span class="sxs-lookup"><span data-stu-id="40300-121">500,000</span></span>   |
|<span data-ttu-id="40300-122">Office 365 组织可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="40300-122">Number of teams an Office 365 organization can have</span></span>    | <span data-ttu-id="40300-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="40300-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="40300-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="40300-124">Number of channels per team</span></span>    | <span data-ttu-id="40300-125">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="40300-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="40300-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="40300-126">Number of Private channels per team</span></span>    |<span data-ttu-id="40300-127">30</span><span class="sxs-lookup"><span data-stu-id="40300-127">30</span></span>|
|<span data-ttu-id="40300-128">专用频道中的成员数</span><span class="sxs-lookup"><span data-stu-id="40300-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="40300-129">250</span><span class="sxs-lookup"><span data-stu-id="40300-129">250</span></span>|
|<span data-ttu-id="40300-130">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="40300-130">Channel conversation post size</span></span> | <span data-ttu-id="40300-131">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="40300-131">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="40300-132">&sup1; Azure Active Directory 中的目录对象均计入此限额。</span><span class="sxs-lookup"><span data-stu-id="40300-132">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="40300-133">如同使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="40300-133">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="40300-134">&sup2; 此限制涵盖已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="40300-134">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="40300-135">&sup3; 已删除的频道可在删除后 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="40300-135">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="40300-136">在该等 30 天，已删除的频道仍然计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="40300-136">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="40300-137">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="40300-137">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="40300-138"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及、连接器数量和回应。</span><span class="sxs-lookup"><span data-stu-id="40300-138"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="40300-139">消息传递</span><span class="sxs-lookup"><span data-stu-id="40300-139">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="40300-140">聊天</span><span class="sxs-lookup"><span data-stu-id="40300-140">Chat</span></span>

<span data-ttu-id="40300-141">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="40300-141">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="40300-142">原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="40300-142">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="40300-143">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="40300-143">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="40300-144">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。</span><span class="sxs-lookup"><span data-stu-id="40300-144">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="40300-145">但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="40300-145">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="40300-146">（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="40300-146">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="40300-147">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="40300-147">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="40300-148">功能</span><span class="sxs-lookup"><span data-stu-id="40300-148">Feature</span></span>  | <span data-ttu-id="40300-149">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-149">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="40300-150">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="40300-150">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="40300-151">250</span><span class="sxs-lookup"><span data-stu-id="40300-151">250</span></span><br><br><span data-ttu-id="40300-152">**注意：** 对于 Teams 政府版（GCC、GCC 高、DoD），该限制仍然为 100。</span><span class="sxs-lookup"><span data-stu-id="40300-152">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 100.</span></span> <span data-ttu-id="40300-153">政府云限制从 100 增加到 250 时，我们会更新此文章。</span><span class="sxs-lookup"><span data-stu-id="40300-153">We'll update this article when the government cloud limit increases from 100 to 250.</span></span>    |
|<span data-ttu-id="40300-154">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="40300-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="40300-155">20</span><span class="sxs-lookup"><span data-stu-id="40300-155">20</span></span> |
|<span data-ttu-id="40300-156">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="40300-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="40300-157">10</span><span class="sxs-lookup"><span data-stu-id="40300-157">10</span></span>     |
|<span data-ttu-id="40300-158">聊天大小</span><span class="sxs-lookup"><span data-stu-id="40300-158">Chat size</span></span> | <span data-ttu-id="40300-159">每篇文章约 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="40300-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="40300-160"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。</span><span class="sxs-lookup"><span data-stu-id="40300-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="40300-161"><sup>2</sup>如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="40300-161"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="40300-162"><sup>3</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="40300-162"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="40300-163">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="40300-163">Emailing a channel</span></span>

 <span data-ttu-id="40300-164">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="40300-164">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="40300-165">如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。</span><span class="sxs-lookup"><span data-stu-id="40300-165">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="40300-166">下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="40300-166">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="40300-167">功能</span><span class="sxs-lookup"><span data-stu-id="40300-167">Feature</span></span>  | <span data-ttu-id="40300-168">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-168">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="40300-169">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="40300-169">Message size<sup>1<sup></span></span> | <span data-ttu-id="40300-170">24 KB</span><span class="sxs-lookup"><span data-stu-id="40300-170">24 KB</span></span> |
|<span data-ttu-id="40300-171">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="40300-171">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="40300-172">20</span><span class="sxs-lookup"><span data-stu-id="40300-172">20</span></span>     |
|<span data-ttu-id="40300-173">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="40300-173">Size of each file attachment</span></span> | <span data-ttu-id="40300-174">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="40300-174">Less than 10 MB</span></span> |
|<span data-ttu-id="40300-175">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="40300-175">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="40300-176">50</span><span class="sxs-lookup"><span data-stu-id="40300-176">50</span></span>   |

<span data-ttu-id="40300-177"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="40300-177"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="40300-178"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="40300-178"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="40300-179">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="40300-179">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="40300-180">所有 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。</span><span class="sxs-lookup"><span data-stu-id="40300-180">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="40300-181">频道名称</span><span class="sxs-lookup"><span data-stu-id="40300-181">Channel names</span></span>

<span data-ttu-id="40300-182">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="40300-182">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="40300-183">字符</span><span class="sxs-lookup"><span data-stu-id="40300-183">Characters</span></span>     | <span data-ttu-id="40300-184">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="40300-184">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="40300-185">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="40300-185">&#124; ' " ..</span></span>        |
|<span data-ttu-id="40300-186">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="40300-186">Characters in these ranges</span></span>    | <span data-ttu-id="40300-187">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="40300-187">0 to 1F</span></span><br><span data-ttu-id="40300-188">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="40300-188">80 to 9F</span></span>        |
|<span data-ttu-id="40300-189">字词</span><span class="sxs-lookup"><span data-stu-id="40300-189">Words</span></span>     | <span data-ttu-id="40300-190">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="40300-190">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="40300-191">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="40300-191">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="40300-192">会议和通话</span><span class="sxs-lookup"><span data-stu-id="40300-192">Meetings and calls</span></span>

|<span data-ttu-id="40300-193">功能</span><span class="sxs-lookup"><span data-stu-id="40300-193">Feature</span></span>     | <span data-ttu-id="40300-194">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-194">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="40300-195">会议中的人数（可聊天和通话）</span><span class="sxs-lookup"><span data-stu-id="40300-195">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="40300-196">250</span><span class="sxs-lookup"><span data-stu-id="40300-196">250</span></span>    |
|<span data-ttu-id="40300-197">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="40300-197">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="40300-198">20</span><span class="sxs-lookup"><span data-stu-id="40300-198">20</span></span> |
|<span data-ttu-id="40300-199">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="40300-199">Max PowerPoint File Size</span></span> | <span data-ttu-id="40300-200">2GB</span><span class="sxs-lookup"><span data-stu-id="40300-200">2GB</span></span>|
|<span data-ttu-id="40300-201">Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="40300-201">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="40300-202">20 天</span><span class="sxs-lookup"><span data-stu-id="40300-202">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="40300-203">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="40300-203">Meeting expiration</span></span>

|<span data-ttu-id="40300-204">会议类型</span><span class="sxs-lookup"><span data-stu-id="40300-204">Meeting type</span></span>  |<span data-ttu-id="40300-205">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="40300-205">Meeting expires after this much time</span></span>  |<span data-ttu-id="40300-206">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="40300-206">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="40300-207">立即开会</span><span class="sxs-lookup"><span data-stu-id="40300-207">Meet now</span></span>     |<span data-ttu-id="40300-208">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="40300-208">Start time + 8 hours</span></span>         |<span data-ttu-id="40300-209">不适用</span><span class="sxs-lookup"><span data-stu-id="40300-209">N/A</span></span>         |
|<span data-ttu-id="40300-210">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="40300-210">Regular with no end time</span></span>     |<span data-ttu-id="40300-211">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="40300-211">Start time + 60 days</span></span>         | <span data-ttu-id="40300-212">60 天</span><span class="sxs-lookup"><span data-stu-id="40300-212">60 days</span></span>        |
|<span data-ttu-id="40300-213">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="40300-213">Regular with end time</span></span>     |<span data-ttu-id="40300-214">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="40300-214">End time + 60 days</span></span>         |<span data-ttu-id="40300-215">60 天</span><span class="sxs-lookup"><span data-stu-id="40300-215">60 days</span></span>         |
|<span data-ttu-id="40300-216">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="40300-216">Recurring with no end time</span></span>     |<span data-ttu-id="40300-217">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="40300-217">Start time + 60 days</span></span>         |<span data-ttu-id="40300-218">60 天</span><span class="sxs-lookup"><span data-stu-id="40300-218">60 days</span></span>         |
|<span data-ttu-id="40300-219">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="40300-219">Recurring with end time</span></span>     |<span data-ttu-id="40300-220">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="40300-220">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="40300-221">60 天</span><span class="sxs-lookup"><span data-stu-id="40300-221">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="40300-222">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="40300-222">Teams live events</span></span>

|<span data-ttu-id="40300-223">功能</span><span class="sxs-lookup"><span data-stu-id="40300-223">Feature</span></span>     | <span data-ttu-id="40300-224">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-224">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="40300-225">受众规模</span><span class="sxs-lookup"><span data-stu-id="40300-225">Audience size</span></span> | <span data-ttu-id="40300-226">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="40300-226">10,000 attendees</span></span> |
|<span data-ttu-id="40300-227">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="40300-227">Duration of event</span></span> | <span data-ttu-id="40300-228">4 小时</span><span class="sxs-lookup"><span data-stu-id="40300-228">4 hours</span></span> |
|<span data-ttu-id="40300-229">Office 365 组织中运行的并发实时事件数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="40300-229">Concurrent live events running in an Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="40300-230">15</span><span class="sxs-lookup"><span data-stu-id="40300-230">15</span></span> |

<span data-ttu-id="40300-231"><sup>1</sup> 可以根据需要安排许多实时事件，但每次只能运行 15 个。</span><span class="sxs-lookup"><span data-stu-id="40300-231"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="40300-232">一旦制造者加入实时事件，即被视为正在运行。</span><span class="sxs-lookup"><span data-stu-id="40300-232">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="40300-233">尝试加入第 16 个实时事件的制造者将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="40300-233">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="40300-234">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="40300-234">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40300-235">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="40300-235">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="40300-236">为帮助客户满足快速变化的沟通需求，Microsoft 365 实时事件将暂时对 Teams 中托管的活动提高默认限制，直到 2020 年 7 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="40300-236">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="40300-237">2020 年 4 月底实施以下增加：</span><span class="sxs-lookup"><span data-stu-id="40300-237">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="40300-238">参与者限制：事件最多可以支持 20000 名参与者</span><span class="sxs-lookup"><span data-stu-id="40300-238">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="40300-239">并发事件：同一租户可以同时托管 50 件事件</span><span class="sxs-lookup"><span data-stu-id="40300-239">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="40300-240">事件持续时间：每个播报的事件持续时间增加到 16 小时</span><span class="sxs-lookup"><span data-stu-id="40300-240">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="40300-241">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="40300-241">Presence in Outlook</span></span>

<span data-ttu-id="40300-242">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="40300-242">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="40300-243">若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="40300-243">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="40300-244">存储空间</span><span class="sxs-lookup"><span data-stu-id="40300-244">Storage</span></span>

<span data-ttu-id="40300-245">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="40300-245">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="40300-246">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="40300-246">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="40300-247">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="40300-247">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="40300-248">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="40300-248">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="40300-249">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="40300-249">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="40300-250">（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="40300-250">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="40300-251">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。</span><span class="sxs-lookup"><span data-stu-id="40300-251">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="40300-252">下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="40300-252">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="40300-253">功能</span><span class="sxs-lookup"><span data-stu-id="40300-253">Feature</span></span>                 |<span data-ttu-id="40300-254">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="40300-254">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="40300-255">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="40300-255">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="40300-256">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="40300-256">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="40300-257">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="40300-257">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="40300-258">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="40300-258">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="40300-259">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="40300-259">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="40300-260">存储空间</span><span class="sxs-lookup"><span data-stu-id="40300-260">Storage</span></span>                 |<span data-ttu-id="40300-261">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="40300-261">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="40300-262">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="40300-262">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="40300-263">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="40300-263">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="40300-264">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="40300-264">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="40300-265">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="40300-265">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="40300-266">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="40300-266">1 TB per organization</span></span>           |
|<span data-ttu-id="40300-267">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="40300-267">Storage for Teams Files</span></span> |<span data-ttu-id="40300-268">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-268">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="40300-269">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-269">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="40300-270">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-270">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="40300-271">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-271">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="40300-272">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-272">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="40300-273">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="40300-273">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="40300-274">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="40300-274">File upload limit  (per file)</span></span>    |<span data-ttu-id="40300-275">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-275">15 GB</span></span>    |<span data-ttu-id="40300-276">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-276">15 GB</span></span>    |<span data-ttu-id="40300-277">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-277">15 GB</span></span>    |<span data-ttu-id="40300-278">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-278">15 GB</span></span>    |<span data-ttu-id="40300-279">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-279">15 GB</span></span>    |<span data-ttu-id="40300-280">15 GB</span><span class="sxs-lookup"><span data-stu-id="40300-280">15 GB</span></span>    |

<span data-ttu-id="40300-281">频道由 SharePoint Online 网站集中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="40300-281">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="40300-282">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="40300-282">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="40300-283">标记</span><span class="sxs-lookup"><span data-stu-id="40300-283">Tags</span></span>

|<span data-ttu-id="40300-284">功能</span><span class="sxs-lookup"><span data-stu-id="40300-284">Feature</span></span>  |<span data-ttu-id="40300-285">最大限制</span><span class="sxs-lookup"><span data-stu-id="40300-285">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="40300-286">每个团队的标记数</span><span class="sxs-lookup"><span data-stu-id="40300-286">Number of tags per team</span></span>    | <span data-ttu-id="40300-287">100</span><span class="sxs-lookup"><span data-stu-id="40300-287">100</span></span>        |
|<span data-ttu-id="40300-288">每个团队建议的默认标记数</span><span class="sxs-lookup"><span data-stu-id="40300-288">Number of suggested default tags per team</span></span>    | <span data-ttu-id="40300-289">25</span><span class="sxs-lookup"><span data-stu-id="40300-289">25</span></span>        |
|<span data-ttu-id="40300-290">分配有标记的团队成员数</span><span class="sxs-lookup"><span data-stu-id="40300-290">Number of team members assign to a tag</span></span>    |<span data-ttu-id="40300-291">100</span><span class="sxs-lookup"><span data-stu-id="40300-291">100</span></span>         |
|<span data-ttu-id="40300-292">分配给用户的标记数</span><span class="sxs-lookup"><span data-stu-id="40300-292">Number of tags assigned to a user</span></span>    |<span data-ttu-id="40300-293">25</span><span class="sxs-lookup"><span data-stu-id="40300-293">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="40300-294">联系人</span><span class="sxs-lookup"><span data-stu-id="40300-294">Contacts</span></span>

<span data-ttu-id="40300-295">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="40300-295">Teams uses these contacts:</span></span>

- <span data-ttu-id="40300-296">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="40300-296">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="40300-297">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="40300-297">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="40300-298">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="40300-298">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="40300-299">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="40300-299">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="40300-300">浏览器</span><span class="sxs-lookup"><span data-stu-id="40300-300">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="40300-301">操作系统</span><span class="sxs-lookup"><span data-stu-id="40300-301">Operating systems</span></span>

<span data-ttu-id="40300-302">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="40300-302">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
