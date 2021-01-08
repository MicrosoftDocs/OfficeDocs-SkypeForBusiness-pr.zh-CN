---
title: Microsoft Teams 的限制和规范
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 本文介绍了适用于 Microsoft Teams 的限制、规范和其他要求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b64042a318e6967523e80e62d1cca429bc7f7e88
ms.sourcegitcommit: f1f3b5220c4b411f2001fbdcbe25ae7c14b94df6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49776843"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="0f12a-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="0f12a-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="0f12a-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="0f12a-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="0f12a-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="0f12a-105">Teams and channels</span></span>

|<span data-ttu-id="0f12a-106">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-106">Feature</span></span>    | <span data-ttu-id="0f12a-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="0f12a-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="0f12a-108">Number of teams a user can create</span></span> | <span data-ttu-id="0f12a-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="0f12a-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="0f12a-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="0f12a-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="0f12a-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="0f12a-111">1,000&sup2;</span></span>|
|<span data-ttu-id="0f12a-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-112">Number of members in a team</span></span> | <span data-ttu-id="0f12a-113">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-113">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="0f12a-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="0f12a-114">Number of owners per team</span></span> | <span data-ttu-id="0f12a-115">100</span><span class="sxs-lookup"><span data-stu-id="0f12a-115">100</span></span>   |
|<span data-ttu-id="0f12a-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="0f12a-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="0f12a-117">5</span><span class="sxs-lookup"><span data-stu-id="0f12a-117">5</span></span>     |
|<span data-ttu-id="0f12a-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="0f12a-119">5,000</span><span class="sxs-lookup"><span data-stu-id="0f12a-119">5,000</span></span>       |
|<span data-ttu-id="0f12a-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="0f12a-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="0f12a-121">500,000</span><span class="sxs-lookup"><span data-stu-id="0f12a-121">500,000</span></span>   |
|<span data-ttu-id="0f12a-122">Microsoft 365 或 Office 365 组织可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="0f12a-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="0f12a-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="0f12a-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="0f12a-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="0f12a-124">Number of channels per team</span></span>    | <span data-ttu-id="0f12a-125">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="0f12a-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="0f12a-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="0f12a-126">Number of Private channels per team</span></span>    |<span data-ttu-id="0f12a-127">30</span><span class="sxs-lookup"><span data-stu-id="0f12a-127">30</span></span>| <span data-ttu-id="0f12a-128">（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="0f12a-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="0f12a-129">专用频道中的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="0f12a-130">250</span><span class="sxs-lookup"><span data-stu-id="0f12a-130">250</span></span>|
|<span data-ttu-id="0f12a-131">可导入到团队中的通讯组列表、安全组或 Office 365 组的最大大小</span><span class="sxs-lookup"><span data-stu-id="0f12a-131">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="0f12a-132">3,500</span><span class="sxs-lookup"><span data-stu-id="0f12a-132">3,500</span></span>|
|<span data-ttu-id="0f12a-133">Office 365 组中最多可以有多少名成员以转换为团队</span><span class="sxs-lookup"><span data-stu-id="0f12a-133">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="0f12a-134">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-134">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="0f12a-135">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="0f12a-135">Channel conversation post size</span></span> | <span data-ttu-id="0f12a-136">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-136">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="0f12a-p101"><sup>1</sup> Azure Active Directory 中的目录对象均计入此限额。与使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="0f12a-139"><sup>2</sup> 此限制包含已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="0f12a-139"><sup>2</sup> This limit includes archived teams.</span></span> <span data-ttu-id="0f12a-140">若要超出 Microsoft 365 或 Office 365 组织可拥有的最大团队数量，必须联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="0f12a-140">To go beyond the maximum number of teams a Microsoft 365 or Office 365 organization can have, you must contact Microsoft support.</span></span>

<span data-ttu-id="0f12a-p103"><sup>3</sup> 已删除的频道可在删除后 30 天内还原。在这 30 天内，已删除的频道仍然计入每个团队 200 个频道或 30 个专用频道的限额内。30 天后，已删除的频道及其内容将被永久删除，此频道也不再计入每个团队的限额内。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p103"><sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="0f12a-144"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及、连接器数量和回应。</span><span class="sxs-lookup"><span data-stu-id="0f12a-144"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="0f12a-145"><sup>5</sup> GCC 的 团队中仅可容纳 5000 名成员，而 GCCH/DoD 的团队只能容纳 2500 名成员。</span><span class="sxs-lookup"><span data-stu-id="0f12a-145"><sup>5</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="0f12a-146">消息传递</span><span class="sxs-lookup"><span data-stu-id="0f12a-146">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="0f12a-147">聊天</span><span class="sxs-lookup"><span data-stu-id="0f12a-147">Chat</span></span>

<span data-ttu-id="0f12a-p104">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="0f12a-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="0f12a-154">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="0f12a-154">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="0f12a-155">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-155">Feature</span></span>  | <span data-ttu-id="0f12a-156">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-156">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0f12a-157">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-157">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="0f12a-158">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-158">250<sup>2</sup></span></span> |
|<span data-ttu-id="0f12a-159">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-159">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="0f12a-160">20</span><span class="sxs-lookup"><span data-stu-id="0f12a-160">20</span></span> |
|<span data-ttu-id="0f12a-161">文件附件数<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-161">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="0f12a-162">10</span><span class="sxs-lookup"><span data-stu-id="0f12a-162">10</span></span>     |
|<span data-ttu-id="0f12a-163">聊天大小</span><span class="sxs-lookup"><span data-stu-id="0f12a-163">Chat size</span></span> | <span data-ttu-id="0f12a-164">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-164">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="0f12a-p105"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。当专用组聊天包含超过 20 个成员时，还将删除“设置发送选项”按钮 (!)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="0f12a-167"><sup>2</sup> 一次仅有 200 个成员可添加到群组聊天。</span><span class="sxs-lookup"><span data-stu-id="0f12a-167"><sup>2</sup> Only 200 members at a time can be added to a group chat.</span></span> <span data-ttu-id="0f12a-168">[请参阅本文了解详细信息](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-168">[See this article for more information](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="0f12a-169"><sup>3</sup> 如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="0f12a-169"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="0f12a-170"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="0f12a-170"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="0f12a-171">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="0f12a-171">Emailing a channel</span></span>

 <span data-ttu-id="0f12a-p107">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p107">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="0f12a-175">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-175">Feature</span></span>  | <span data-ttu-id="0f12a-176">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-176">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0f12a-177">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-177">Message size<sup>1<sup></span></span> | <span data-ttu-id="0f12a-178">24 KB</span><span class="sxs-lookup"><span data-stu-id="0f12a-178">24 KB</span></span> |
|<span data-ttu-id="0f12a-179">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-179">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="0f12a-180">20</span><span class="sxs-lookup"><span data-stu-id="0f12a-180">20</span></span>     |
|<span data-ttu-id="0f12a-181">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="0f12a-181">Size of each file attachment</span></span> | <span data-ttu-id="0f12a-182">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="0f12a-182">Less than 10 MB</span></span> |
|<span data-ttu-id="0f12a-183">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-183">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="0f12a-184">50</span><span class="sxs-lookup"><span data-stu-id="0f12a-184">50</span></span>   |

<span data-ttu-id="0f12a-185"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0f12a-185"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="0f12a-186"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="0f12a-186"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="0f12a-187">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-187">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="0f12a-p108">所有 Microsoft 365 和 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。Office GCC/GCCH/DOD 组织无法在 Teams 中通过电子邮件发送频道。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p108">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="0f12a-190">频道名称</span><span class="sxs-lookup"><span data-stu-id="0f12a-190">Channel names</span></span>

<span data-ttu-id="0f12a-191">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="0f12a-191">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="0f12a-192">类型</span><span class="sxs-lookup"><span data-stu-id="0f12a-192">Type</span></span>|<span data-ttu-id="0f12a-193">示例</span><span class="sxs-lookup"><span data-stu-id="0f12a-193">Example</span></span>|
|---------|---------|
|<span data-ttu-id="0f12a-194">字符</span><span class="sxs-lookup"><span data-stu-id="0f12a-194">Characters</span></span>     | <span data-ttu-id="0f12a-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="0f12a-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span></span>        |
|<span data-ttu-id="0f12a-197">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="0f12a-197">Characters in these ranges</span></span>    | <span data-ttu-id="0f12a-198">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="0f12a-198">0 to 1F</span></span><br><span data-ttu-id="0f12a-199">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="0f12a-199">80 to 9F</span></span>        |
|<span data-ttu-id="0f12a-200">字词</span><span class="sxs-lookup"><span data-stu-id="0f12a-200">Words</span></span>     | <span data-ttu-id="0f12a-201">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="0f12a-201">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="0f12a-202">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="0f12a-202">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="0f12a-203">会议和通话</span><span class="sxs-lookup"><span data-stu-id="0f12a-203">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f12a-204">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="0f12a-204">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="0f12a-205">**若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：</span><span class="sxs-lookup"><span data-stu-id="0f12a-205">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="0f12a-206">可为多达20,000名与会者提供活动支持</span><span class="sxs-lookup"><span data-stu-id="0f12a-206">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="0f12a-207">一个租户可同时举办50场活动</span><span class="sxs-lookup"><span data-stu-id="0f12a-207">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="0f12a-208">每次广播的活动持续时间为16小时</span><span class="sxs-lookup"><span data-stu-id="0f12a-208">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="0f12a-p110">此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p110">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="0f12a-212">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-212">Feature</span></span>     | <span data-ttu-id="0f12a-213">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-213">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="0f12a-214">会议中的人数（可聊天和通话）</span><span class="sxs-lookup"><span data-stu-id="0f12a-214">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="0f12a-215">300</span><span class="sxs-lookup"><span data-stu-id="0f12a-215">300</span></span> |
|<span data-ttu-id="0f12a-216">从聊天选项卡启动的视频或音频呼叫中的人员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-216">Number of people in a video or audio call started from the chat tab</span></span> | <span data-ttu-id="0f12a-217">20</span><span class="sxs-lookup"><span data-stu-id="0f12a-217">20</span></span> |
|<span data-ttu-id="0f12a-218">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="0f12a-218">Max PowerPoint File Size</span></span> | <span data-ttu-id="0f12a-219">2 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-219">2 GB</span></span>|
|<span data-ttu-id="0f12a-220">Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="0f12a-220">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="0f12a-221">20 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-221">20 days</span></span> |

>[!Note]
> <span data-ttu-id="0f12a-p111">从使用 Microsoft Stream 到[使用 OneDrive for Business 和 SharePoint for meeting 进行会议录制](tmr-meeting-recording-change.md)的改变将是分阶段进行的。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p111">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="0f12a-224">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-224">Meeting expiration</span></span>

|<span data-ttu-id="0f12a-225">会议类型</span><span class="sxs-lookup"><span data-stu-id="0f12a-225">Meeting type</span></span>  |<span data-ttu-id="0f12a-226">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="0f12a-226">Meeting expires after this much time</span></span>  |<span data-ttu-id="0f12a-227">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-227">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0f12a-228">立即开会</span><span class="sxs-lookup"><span data-stu-id="0f12a-228">Meet now</span></span>     |<span data-ttu-id="0f12a-229">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="0f12a-229">Start time + 8 hours</span></span>         |<span data-ttu-id="0f12a-230">不适用</span><span class="sxs-lookup"><span data-stu-id="0f12a-230">N/A</span></span>         |
|<span data-ttu-id="0f12a-231">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-231">Regular with no end time</span></span>     |<span data-ttu-id="0f12a-232">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-232">Start time + 60 days</span></span>         | <span data-ttu-id="0f12a-233">60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-233">60 days</span></span>        |
|<span data-ttu-id="0f12a-234">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-234">Regular with end time</span></span>     |<span data-ttu-id="0f12a-235">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-235">End time + 60 days</span></span>         |<span data-ttu-id="0f12a-236">60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-236">60 days</span></span>         |
|<span data-ttu-id="0f12a-237">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-237">Recurring with no end time</span></span>     |<span data-ttu-id="0f12a-238">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-238">Start time + 60 days</span></span>         |<span data-ttu-id="0f12a-239">60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-239">60 days</span></span>         |
|<span data-ttu-id="0f12a-240">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-240">Recurring with end time</span></span>     |<span data-ttu-id="0f12a-241">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-241">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="0f12a-242">60 天</span><span class="sxs-lookup"><span data-stu-id="0f12a-242">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="0f12a-243">Microsoft Teams 会议的时间限制为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="0f12a-243">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="0f12a-244">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="0f12a-244">Teams Live Events</span></span>

|<span data-ttu-id="0f12a-245">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-245">Feature</span></span>     | <span data-ttu-id="0f12a-246">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-246">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="0f12a-247">受众规模</span><span class="sxs-lookup"><span data-stu-id="0f12a-247">Audience size</span></span> | <span data-ttu-id="0f12a-248">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="0f12a-248">10,000 attendees</span></span> |
|<span data-ttu-id="0f12a-249">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="0f12a-249">Duration of event</span></span> | <span data-ttu-id="0f12a-250">4 小时</span><span class="sxs-lookup"><span data-stu-id="0f12a-250">4 hours</span></span> |
|<span data-ttu-id="0f12a-251">Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0f12a-251">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="0f12a-252">15</span><span class="sxs-lookup"><span data-stu-id="0f12a-252">15</span></span> |

<span data-ttu-id="0f12a-p112"><sup>1</sup> 可根据需要安排许多实时事件，但每次只能运行 15 个。一旦制造者加入实时事件，即被视为正在运行。尝试加入第 16 个实时事件的制造者将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p112"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="0f12a-p113">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另请参阅[安排 Teams 实时事件](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p113">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f12a-258">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="0f12a-258">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="0f12a-259">**若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：</span><span class="sxs-lookup"><span data-stu-id="0f12a-259">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="0f12a-260">可为多达20,000名与会者提供活动支持</span><span class="sxs-lookup"><span data-stu-id="0f12a-260">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="0f12a-261">一个租户可同时举办50场活动</span><span class="sxs-lookup"><span data-stu-id="0f12a-261">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="0f12a-262">每次广播的活动持续时间为16小时</span><span class="sxs-lookup"><span data-stu-id="0f12a-262">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="0f12a-p114">此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p114">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="0f12a-266">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="0f12a-266">Presence in Outlook</span></span>

<span data-ttu-id="0f12a-p115">Outlook 2013 桌面应用及更高版本支持 Outlook 中的 Teams 状态。若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p115">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="0f12a-269">存储</span><span class="sxs-lookup"><span data-stu-id="0f12a-269">Storage</span></span>

<span data-ttu-id="0f12a-p116">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p116">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0f12a-272">每个[专用频道](https://docs.microsoft.com/microsoftteams/private-channels)都拥有自己的 SharePoint 网站（以前称为“网站集”）。</span><span class="sxs-lookup"><span data-stu-id="0f12a-272">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="0f12a-p117">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p117">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="0f12a-p118">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="0f12a-p118">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="0f12a-p119">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p119">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="0f12a-279">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-279">Feature</span></span>                 |<span data-ttu-id="0f12a-280">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="0f12a-280">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="0f12a-281">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="0f12a-281">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="0f12a-282">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="0f12a-282">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="0f12a-283">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="0f12a-283">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="0f12a-284">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="0f12a-284">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="0f12a-285">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="0f12a-285">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="0f12a-286">存储空间</span><span class="sxs-lookup"><span data-stu-id="0f12a-286">Storage</span></span>                 |<span data-ttu-id="0f12a-287">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="0f12a-287">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0f12a-288">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="0f12a-288">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0f12a-289">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="0f12a-289">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="0f12a-290">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="0f12a-290">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="0f12a-291">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="0f12a-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0f12a-292">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="0f12a-292">1 TB per organization</span></span>           |
|<span data-ttu-id="0f12a-293">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="0f12a-293">Storage for Teams Files</span></span> |<span data-ttu-id="0f12a-294">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-294">Up to 25 TB per site or group</span></span> |<span data-ttu-id="0f12a-295">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-295">Up to 25 TB per site or group</span></span> |<span data-ttu-id="0f12a-296">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-296">Up to 25 TB per site or group</span></span> |<span data-ttu-id="0f12a-297">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="0f12a-298">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="0f12a-299">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="0f12a-299">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="0f12a-300">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="0f12a-300">File upload limit  (per file)</span></span>    |<span data-ttu-id="0f12a-301">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-301">100 GB</span></span>    |<span data-ttu-id="0f12a-302">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-302">100 GB</span></span>    |<span data-ttu-id="0f12a-303">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-303">100 GB</span></span>    |<span data-ttu-id="0f12a-304">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-304">100 GB</span></span>    |<span data-ttu-id="0f12a-305">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-305">100 GB</span></span>    |<span data-ttu-id="0f12a-306">100 GB</span><span class="sxs-lookup"><span data-stu-id="0f12a-306">100 GB</span></span>    |

<span data-ttu-id="0f12a-307">频道由 SharePoint Online 网站（以前称为“网站集”）中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="0f12a-307">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="0f12a-308">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-308">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="0f12a-309">课堂团队</span><span class="sxs-lookup"><span data-stu-id="0f12a-309">Class teams</span></span>

<span data-ttu-id="0f12a-p120">Microsoft Teams 教育版提供了专为独特教育场景设计的模板，如课堂教学。有关团队类型的详细信息（包括课堂团队），可在“[在 Microsoft Teams 中选择团队类型进行协作](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)”中找到。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p120">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="0f12a-312">课堂团队是一种模板类型，其中包含附加应用，且具有单独限制团队成员数量的功能。</span><span class="sxs-lookup"><span data-stu-id="0f12a-312">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="0f12a-313">使用课堂团队需要 [Office 365 教育版许可证](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-313">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="0f12a-314">下表列出了课堂团队的限制：</span><span class="sxs-lookup"><span data-stu-id="0f12a-314">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="0f12a-315">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-315">Feature</span></span>  |<span data-ttu-id="0f12a-316">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-316">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0f12a-317">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-317">Number of members in a team</span></span>    | <span data-ttu-id="0f12a-318">请参阅本文的[“团队和频道”](#teams-and-channels)部分</span><span class="sxs-lookup"><span data-stu-id="0f12a-318">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="0f12a-319">课堂团队中使用“作业”的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-319">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="0f12a-320">200</span><span class="sxs-lookup"><span data-stu-id="0f12a-320">200</span></span>        |
|<span data-ttu-id="0f12a-321">课堂团队中使用“OneNote 课堂笔记本”的成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-321">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="0f12a-322">200</span><span class="sxs-lookup"><span data-stu-id="0f12a-322">200</span></span>         |

<span data-ttu-id="0f12a-p121">课堂团队可以支持超过 200 位成员。但是，如果你计划在你的团队中使用“作业”应用或“课堂笔记本”应用，则需要保留低于最大限制的成员数。</span><span class="sxs-lookup"><span data-stu-id="0f12a-p121">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="0f12a-325">标记</span><span class="sxs-lookup"><span data-stu-id="0f12a-325">Tags</span></span>

|<span data-ttu-id="0f12a-326">功能</span><span class="sxs-lookup"><span data-stu-id="0f12a-326">Feature</span></span>  |<span data-ttu-id="0f12a-327">最大限制</span><span class="sxs-lookup"><span data-stu-id="0f12a-327">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0f12a-328">每个团队的标记数</span><span class="sxs-lookup"><span data-stu-id="0f12a-328">Number of tags per team</span></span>    | <span data-ttu-id="0f12a-329">100</span><span class="sxs-lookup"><span data-stu-id="0f12a-329">100</span></span>        |
|<span data-ttu-id="0f12a-330">每个团队建议的默认标记数</span><span class="sxs-lookup"><span data-stu-id="0f12a-330">Number of suggested default tags per team</span></span>    | <span data-ttu-id="0f12a-331">25</span><span class="sxs-lookup"><span data-stu-id="0f12a-331">25</span></span>        |
|<span data-ttu-id="0f12a-332">分配有标记的团队成员数</span><span class="sxs-lookup"><span data-stu-id="0f12a-332">Number of team members assign to a tag</span></span>    |<span data-ttu-id="0f12a-333">100</span><span class="sxs-lookup"><span data-stu-id="0f12a-333">100</span></span>         |
|<span data-ttu-id="0f12a-334">分配给用户的标记数</span><span class="sxs-lookup"><span data-stu-id="0f12a-334">Number of tags assigned to a user</span></span>    |<span data-ttu-id="0f12a-335">25</span><span class="sxs-lookup"><span data-stu-id="0f12a-335">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="0f12a-336">联系人</span><span class="sxs-lookup"><span data-stu-id="0f12a-336">Contacts</span></span>

<span data-ttu-id="0f12a-337">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="0f12a-337">Teams uses these contacts:</span></span>

- <span data-ttu-id="0f12a-338">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="0f12a-338">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="0f12a-339">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="0f12a-339">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="0f12a-340">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="0f12a-340">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="0f12a-341">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="0f12a-341">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="0f12a-342">浏览器</span><span class="sxs-lookup"><span data-stu-id="0f12a-342">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="0f12a-343">操作系统</span><span class="sxs-lookup"><span data-stu-id="0f12a-343">Operating systems</span></span>

<span data-ttu-id="0f12a-344">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="0f12a-344">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
