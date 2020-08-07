---
title: Microsoft Teams 的限制和规范
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 1aeee07b9c9f25c459366d7bf5f062c731c12f66
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581989"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="cf5a6-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="cf5a6-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="cf5a6-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="cf5a6-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="cf5a6-105">Teams and channels</span></span>

|<span data-ttu-id="cf5a6-106">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-106">Feature</span></span>    | <span data-ttu-id="cf5a6-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="cf5a6-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-108">Number of teams a user can create</span></span> | <span data-ttu-id="cf5a6-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="cf5a6-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="cf5a6-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="cf5a6-111">1,000</span><span class="sxs-lookup"><span data-stu-id="cf5a6-111">1,000</span></span>|
|<span data-ttu-id="cf5a6-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-112">Number of members in a team</span></span> | <span data-ttu-id="cf5a6-113">10,000</span><span class="sxs-lookup"><span data-stu-id="cf5a6-113">10,000</span></span>       |
|<span data-ttu-id="cf5a6-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-114">Number of owners per team</span></span> | <span data-ttu-id="cf5a6-115">100</span><span class="sxs-lookup"><span data-stu-id="cf5a6-115">100</span></span>   |
|<span data-ttu-id="cf5a6-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="cf5a6-117">5</span><span class="sxs-lookup"><span data-stu-id="cf5a6-117">5</span></span>     |
|<span data-ttu-id="cf5a6-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="cf5a6-119">5,000</span><span class="sxs-lookup"><span data-stu-id="cf5a6-119">5,000</span></span>       |
|<span data-ttu-id="cf5a6-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="cf5a6-121">500,000</span><span class="sxs-lookup"><span data-stu-id="cf5a6-121">500,000</span></span>   |
|<span data-ttu-id="cf5a6-122">Microsoft 365 或 Office 365 组织可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="cf5a6-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="cf5a6-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="cf5a6-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-124">Number of channels per team</span></span>    | <span data-ttu-id="cf5a6-125">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="cf5a6-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="cf5a6-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-126">Number of Private channels per team</span></span>    |<span data-ttu-id="cf5a6-127">30</span><span class="sxs-lookup"><span data-stu-id="cf5a6-127">30</span></span>|
|<span data-ttu-id="cf5a6-128">专用频道中的成员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="cf5a6-129">250</span><span class="sxs-lookup"><span data-stu-id="cf5a6-129">250</span></span>|
|<span data-ttu-id="cf5a6-130">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="cf5a6-130">Channel conversation post size</span></span> | <span data-ttu-id="cf5a6-131">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-131">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="cf5a6-132"><sup>1</sup> Azure Active Directory 中的目录对象均计入此限额。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-132"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="cf5a6-133">如同使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-133">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="cf5a6-134"><sup>2</sup> 此限制涵盖已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-134"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="cf5a6-135"><sup>3</sup> 已删除的频道可在删除后 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-135"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="cf5a6-136">在该等 30 天，已删除的频道仍然计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-136">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="cf5a6-137">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-137">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="cf5a6-138"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及、连接器数量和回应。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-138"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="cf5a6-139">消息传递</span><span class="sxs-lookup"><span data-stu-id="cf5a6-139">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="cf5a6-140">聊天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-140">Chat</span></span>

<span data-ttu-id="cf5a6-141">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-141">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="cf5a6-142">原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-142">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="cf5a6-143">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-143">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="cf5a6-144">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-144">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="cf5a6-145">但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-145">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="cf5a6-146">（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="cf5a6-146">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="cf5a6-147">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-147">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="cf5a6-148">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-148">Feature</span></span>  | <span data-ttu-id="cf5a6-149">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-149">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="cf5a6-150">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-150">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="cf5a6-151">250</span><span class="sxs-lookup"><span data-stu-id="cf5a6-151">250</span></span><br><br><span data-ttu-id="cf5a6-152">**注意：** 对于 Teams 政府版（GCC、GCC 高、DoD），该限制仍然为 100。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-152">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 100.</span></span> <span data-ttu-id="cf5a6-153">政府云限制从 100 增加到 250 时，我们会更新此文章。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-153">We'll update this article when the government cloud limit increases from 100 to 250.</span></span>    |
|<span data-ttu-id="cf5a6-154">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="cf5a6-155">20</span><span class="sxs-lookup"><span data-stu-id="cf5a6-155">20</span></span> |
|<span data-ttu-id="cf5a6-156">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="cf5a6-157">10</span><span class="sxs-lookup"><span data-stu-id="cf5a6-157">10</span></span>     |
|<span data-ttu-id="cf5a6-158">聊天大小</span><span class="sxs-lookup"><span data-stu-id="cf5a6-158">Chat size</span></span> | <span data-ttu-id="cf5a6-159">每篇文章约 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="cf5a6-160"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="cf5a6-161">当专用组聊天包含超过 20 个成员时，还将删除“设置发送选项”按钮 (!)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="cf5a6-162"><sup>2</sup>如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="cf5a6-163"><sup>3</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="cf5a6-164">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="cf5a6-164">Emailing a channel</span></span>

 <span data-ttu-id="cf5a6-165">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="cf5a6-166">如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="cf5a6-167">下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="cf5a6-168">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-168">Feature</span></span>  | <span data-ttu-id="cf5a6-169">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="cf5a6-170">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="cf5a6-171">24 KB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-171">24 KB</span></span> |
|<span data-ttu-id="cf5a6-172">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="cf5a6-173">20</span><span class="sxs-lookup"><span data-stu-id="cf5a6-173">20</span></span>     |
|<span data-ttu-id="cf5a6-174">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="cf5a6-174">Size of each file attachment</span></span> | <span data-ttu-id="cf5a6-175">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-175">Less than 10 MB</span></span> |
|<span data-ttu-id="cf5a6-176">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="cf5a6-177">50</span><span class="sxs-lookup"><span data-stu-id="cf5a6-177">50</span></span>   |

<span data-ttu-id="cf5a6-178"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="cf5a6-179"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="cf5a6-180">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="cf5a6-181">所有 Microsoft 365 和 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="cf5a6-182">频道名称</span><span class="sxs-lookup"><span data-stu-id="cf5a6-182">Channel names</span></span>

<span data-ttu-id="cf5a6-183">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="cf5a6-184">字符</span><span class="sxs-lookup"><span data-stu-id="cf5a6-184">Characters</span></span>     | <span data-ttu-id="cf5a6-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="cf5a6-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="cf5a6-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="cf5a6-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="cf5a6-187">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="cf5a6-187">Characters in these ranges</span></span>    | <span data-ttu-id="cf5a6-188">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="cf5a6-188">0 to 1F</span></span><br><span data-ttu-id="cf5a6-189">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="cf5a6-189">80 to 9F</span></span>        |
|<span data-ttu-id="cf5a6-190">字词</span><span class="sxs-lookup"><span data-stu-id="cf5a6-190">Words</span></span>     | <span data-ttu-id="cf5a6-191">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="cf5a6-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="cf5a6-192">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="cf5a6-193">会议和通话</span><span class="sxs-lookup"><span data-stu-id="cf5a6-193">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf5a6-194">四月时，[我们已宣布](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-in-microsoft-teams-april-2020/ba-p/1347929)将为 Microsoft 365 实时事件启用临时默认限制增加，以帮助更好地支持客户，直至 7 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-194">In April, [we announced](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-in-microsoft-teams-april-2020/ba-p/1347929) that temporary default limit increases would be enabled for Microsoft 365 live events to help better support customers, through July 1st.</span></span> <span data-ttu-id="cf5a6-195">为继续满足客户需求，我们会将此临时默认限制延长至 2020 年 10 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-195">To continue meeting the needs of customers, we will extend the temporary default limits until October 1, 2020.</span></span> <span data-ttu-id="cf5a6-196">Teams、Stream 和 Yammer 中举办的实时事件将继续临时支持最多有 20000 人参与、最长达 16 个小时和有最多 50 个事件同时发生的事件。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-196">Live events hosted in Teams, Stream, and Yammer will continue to temporarily support events for up to 20,000 attendees, 16 hours in length, and 50 events happening simultaneously.</span></span> <span data-ttu-id="cf5a6-197">此外，通过 [Microsoft 实时事件协助计划](https://resources.techcommunity.microsoft.com/live-events/assistance/)，客户可以按计划在 Stream 中举办最多 100,000 人参加的实时事件。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-197">Additionally, customers can host a live event in Stream for up to 100,000 attendees when planned though the [Microsoft live events assistance program](https://resources.techcommunity.microsoft.com/live-events/assistance/).</span></span>

|<span data-ttu-id="cf5a6-198">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-198">Feature</span></span>     | <span data-ttu-id="cf5a6-199">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-199">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="cf5a6-200">会议中的人数（可聊天和通话）</span><span class="sxs-lookup"><span data-stu-id="cf5a6-200">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="cf5a6-201">300</span><span class="sxs-lookup"><span data-stu-id="cf5a6-201">300</span></span> |
|<span data-ttu-id="cf5a6-202">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-202">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="cf5a6-203">20</span><span class="sxs-lookup"><span data-stu-id="cf5a6-203">20</span></span> |
|<span data-ttu-id="cf5a6-204">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="cf5a6-204">Max PowerPoint File Size</span></span> | <span data-ttu-id="cf5a6-205">2GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-205">2GB</span></span>|
|<span data-ttu-id="cf5a6-206">Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="cf5a6-206">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="cf5a6-207">20 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-207">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="cf5a6-208">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-208">Meeting expiration</span></span>

|<span data-ttu-id="cf5a6-209">会议类型</span><span class="sxs-lookup"><span data-stu-id="cf5a6-209">Meeting type</span></span>  |<span data-ttu-id="cf5a6-210">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="cf5a6-210">Meeting expires after this much time</span></span>  |<span data-ttu-id="cf5a6-211">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-211">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cf5a6-212">立即开会</span><span class="sxs-lookup"><span data-stu-id="cf5a6-212">Meet now</span></span>     |<span data-ttu-id="cf5a6-213">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="cf5a6-213">Start time + 8 hours</span></span>         |<span data-ttu-id="cf5a6-214">不适用</span><span class="sxs-lookup"><span data-stu-id="cf5a6-214">N/A</span></span>         |
|<span data-ttu-id="cf5a6-215">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-215">Regular with no end time</span></span>     |<span data-ttu-id="cf5a6-216">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-216">Start time + 60 days</span></span>         | <span data-ttu-id="cf5a6-217">60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-217">60 days</span></span>        |
|<span data-ttu-id="cf5a6-218">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-218">Regular with end time</span></span>     |<span data-ttu-id="cf5a6-219">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-219">End time + 60 days</span></span>         |<span data-ttu-id="cf5a6-220">60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-220">60 days</span></span>         |
|<span data-ttu-id="cf5a6-221">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-221">Recurring with no end time</span></span>     |<span data-ttu-id="cf5a6-222">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-222">Start time + 60 days</span></span>         |<span data-ttu-id="cf5a6-223">60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-223">60 days</span></span>         |
|<span data-ttu-id="cf5a6-224">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-224">Recurring with end time</span></span>     |<span data-ttu-id="cf5a6-225">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-225">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="cf5a6-226">60 天</span><span class="sxs-lookup"><span data-stu-id="cf5a6-226">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="cf5a6-227">Microsoft Teams 会议的时间限制为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-227">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="cf5a6-228">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="cf5a6-228">Teams live events</span></span>

|<span data-ttu-id="cf5a6-229">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-229">Feature</span></span>     | <span data-ttu-id="cf5a6-230">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-230">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="cf5a6-231">受众规模</span><span class="sxs-lookup"><span data-stu-id="cf5a6-231">Audience size</span></span> | <span data-ttu-id="cf5a6-232">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="cf5a6-232">10,000 attendees</span></span> |
|<span data-ttu-id="cf5a6-233">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-233">Duration of event</span></span> | <span data-ttu-id="cf5a6-234">4 小时</span><span class="sxs-lookup"><span data-stu-id="cf5a6-234">4 hours</span></span> |
|<span data-ttu-id="cf5a6-235">Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cf5a6-235">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="cf5a6-236">15</span><span class="sxs-lookup"><span data-stu-id="cf5a6-236">15</span></span> |

<span data-ttu-id="cf5a6-237"><sup>1</sup> 可以根据需要安排许多实时事件，但每次只能运行 15 个。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-237"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="cf5a6-238">一旦制造者加入实时事件，即被视为正在运行。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-238">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="cf5a6-239">尝试加入第 16 个实时事件的制造者将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-239">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="cf5a6-240">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-240">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf5a6-241">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="cf5a6-241">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="cf5a6-242">为帮助客户满足快速变化的沟通需求，Microsoft 365 直播活动将暂时对 Teams 中托管的直播活动提高默认限制，直到 2020 年 10 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-242">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until October 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="cf5a6-243">即将推出以下数量增长：</span><span class="sxs-lookup"><span data-stu-id="cf5a6-243">The following increases are being rolled out:</span></span>
>
> - <span data-ttu-id="cf5a6-244">参与者限制：事件最多可以支持 20000 名参与者</span><span class="sxs-lookup"><span data-stu-id="cf5a6-244">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="cf5a6-245">并发事件：同一租户可以同时托管 50 件事件</span><span class="sxs-lookup"><span data-stu-id="cf5a6-245">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="cf5a6-246">事件持续时间：每个播报的事件持续时间增加到 16 小时</span><span class="sxs-lookup"><span data-stu-id="cf5a6-246">Event duration: event length has been increased to 16 hours per broadcast</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="cf5a6-247">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="cf5a6-247">Presence in Outlook</span></span>

<span data-ttu-id="cf5a6-248">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-248">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="cf5a6-249">若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-249">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="cf5a6-250">存储空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-250">Storage</span></span>

<span data-ttu-id="cf5a6-251">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-251">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="cf5a6-252">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-252">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cf5a6-253">每个[私人频道](https://docs.microsoft.com/microsoftteams/private-channels)都拥有自己的 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-253">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="cf5a6-254">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-254">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="cf5a6-255">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-255">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="cf5a6-256">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-256">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="cf5a6-257">（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="cf5a6-257">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="cf5a6-258">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-258">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="cf5a6-259">下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-259">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="cf5a6-260">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-260">Feature</span></span>                 |<span data-ttu-id="cf5a6-261">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="cf5a6-261">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="cf5a6-262">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="cf5a6-262">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="cf5a6-263">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="cf5a6-263">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="cf5a6-264">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="cf5a6-264">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="cf5a6-265">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="cf5a6-265">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="cf5a6-266">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="cf5a6-266">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="cf5a6-267">存储空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-267">Storage</span></span>                 |<span data-ttu-id="cf5a6-268">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-268">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="cf5a6-269">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-269">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="cf5a6-270">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-270">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="cf5a6-271">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-271">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="cf5a6-272">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-272">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="cf5a6-273">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-273">1 TB per organization</span></span>           |
|<span data-ttu-id="cf5a6-274">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-274">Storage for Teams Files</span></span> |<span data-ttu-id="cf5a6-275">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-275">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="cf5a6-276">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-276">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="cf5a6-277">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-277">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="cf5a6-278">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-278">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="cf5a6-279">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-279">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="cf5a6-280">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="cf5a6-280">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="cf5a6-281">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="cf5a6-281">File upload limit  (per file)</span></span>    |<span data-ttu-id="cf5a6-282">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-282">100 GB</span></span>    |<span data-ttu-id="cf5a6-283">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-283">100 GB</span></span>    |<span data-ttu-id="cf5a6-284">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-284">100 GB</span></span>    |<span data-ttu-id="cf5a6-285">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-285">100 GB</span></span>    |<span data-ttu-id="cf5a6-286">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-286">100 GB</span></span>    |<span data-ttu-id="cf5a6-287">100 GB</span><span class="sxs-lookup"><span data-stu-id="cf5a6-287">100 GB</span></span>    |

<span data-ttu-id="cf5a6-288">频道由 SharePoint Online 网站集中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-288">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="cf5a6-289">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-289">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="cf5a6-290">标记</span><span class="sxs-lookup"><span data-stu-id="cf5a6-290">Tags</span></span>

|<span data-ttu-id="cf5a6-291">功能</span><span class="sxs-lookup"><span data-stu-id="cf5a6-291">Feature</span></span>  |<span data-ttu-id="cf5a6-292">最大限制</span><span class="sxs-lookup"><span data-stu-id="cf5a6-292">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="cf5a6-293">每个团队的标记数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-293">Number of tags per team</span></span>    | <span data-ttu-id="cf5a6-294">100</span><span class="sxs-lookup"><span data-stu-id="cf5a6-294">100</span></span>        |
|<span data-ttu-id="cf5a6-295">每个团队建议的默认标记数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-295">Number of suggested default tags per team</span></span>    | <span data-ttu-id="cf5a6-296">25</span><span class="sxs-lookup"><span data-stu-id="cf5a6-296">25</span></span>        |
|<span data-ttu-id="cf5a6-297">分配有标记的团队成员数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-297">Number of team members assign to a tag</span></span>    |<span data-ttu-id="cf5a6-298">100</span><span class="sxs-lookup"><span data-stu-id="cf5a6-298">100</span></span>         |
|<span data-ttu-id="cf5a6-299">分配给用户的标记数</span><span class="sxs-lookup"><span data-stu-id="cf5a6-299">Number of tags assigned to a user</span></span>    |<span data-ttu-id="cf5a6-300">25</span><span class="sxs-lookup"><span data-stu-id="cf5a6-300">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="cf5a6-301">联系人</span><span class="sxs-lookup"><span data-stu-id="cf5a6-301">Contacts</span></span>

<span data-ttu-id="cf5a6-302">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="cf5a6-302">Teams uses these contacts:</span></span>

- <span data-ttu-id="cf5a6-303">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="cf5a6-303">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="cf5a6-304">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="cf5a6-304">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="cf5a6-305">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-305">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="cf5a6-306">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-306">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="cf5a6-307">浏览器</span><span class="sxs-lookup"><span data-stu-id="cf5a6-307">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="cf5a6-308">操作系统</span><span class="sxs-lookup"><span data-stu-id="cf5a6-308">Operating systems</span></span>

<span data-ttu-id="cf5a6-309">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="cf5a6-309">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
