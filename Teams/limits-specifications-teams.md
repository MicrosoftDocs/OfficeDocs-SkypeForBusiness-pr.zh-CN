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
ms.openlocfilehash: 5fbf2efa3ad1d77300138a57336b4254ea788e84
ms.sourcegitcommit: 242561bfc12504614633539ca696b91dfc890b92
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52328504"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="50f29-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="50f29-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="50f29-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="50f29-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="50f29-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="50f29-105">Teams and channels</span></span>

|<span data-ttu-id="50f29-106">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-106">Feature</span></span>    | <span data-ttu-id="50f29-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="50f29-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="50f29-108">Number of teams a user can create</span></span> | <span data-ttu-id="50f29-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="50f29-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="50f29-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="50f29-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="50f29-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="50f29-111">1,000&sup2;</span></span>|
|<span data-ttu-id="50f29-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-112">Number of members in a team</span></span> | <span data-ttu-id="50f29-113">25,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-113">25,000<sup>6</sup></span></span>     |
|<span data-ttu-id="50f29-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="50f29-114">Number of owners per team</span></span> | <span data-ttu-id="50f29-115">100</span><span class="sxs-lookup"><span data-stu-id="50f29-115">100</span></span>   |
|<span data-ttu-id="50f29-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="50f29-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="50f29-117">5&sup2;</span><span class="sxs-lookup"><span data-stu-id="50f29-117">5&sup2;</span></span>     |
|<span data-ttu-id="50f29-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="50f29-119">10,000</span><span class="sxs-lookup"><span data-stu-id="50f29-119">10,000</span></span>       |
|<span data-ttu-id="50f29-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="50f29-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="50f29-121">500,000</span><span class="sxs-lookup"><span data-stu-id="50f29-121">500,000</span></span>   |
|<span data-ttu-id="50f29-122">Microsoft 365 或 Office 365 组织可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="50f29-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="50f29-123">500,000&sup3;</span><span class="sxs-lookup"><span data-stu-id="50f29-123">500,000&sup3;</span></span>     |
|<span data-ttu-id="50f29-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="50f29-124">Number of channels per team</span></span>    | <span data-ttu-id="50f29-125">200（包括已删除的频道）<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-125">200 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="50f29-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="50f29-126">Number of Private channels per team</span></span>    |<span data-ttu-id="50f29-127">30（包括已删除的频道）<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-127">30 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="50f29-128">专用频道中的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="50f29-129">250</span><span class="sxs-lookup"><span data-stu-id="50f29-129">250</span></span>|
|<span data-ttu-id="50f29-130">可导入到团队中的通讯组列表、安全组或 Office 365 组的最大大小</span><span class="sxs-lookup"><span data-stu-id="50f29-130">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="50f29-131">3,500</span><span class="sxs-lookup"><span data-stu-id="50f29-131">3,500</span></span>|
|<span data-ttu-id="50f29-132">Office 365 组中最多可以有多少名成员以转换为团队</span><span class="sxs-lookup"><span data-stu-id="50f29-132">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="50f29-133">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-133">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="50f29-134">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="50f29-134">Channel conversation post size</span></span> | <span data-ttu-id="50f29-135">每个帖子约 28 KB<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-135">Approximately 28 KB per post<sup>5</sup></span></span> |

<span data-ttu-id="50f29-p101"><sup>1</sup> Azure Active Directory 中的目录对象均计入此限额。与使用[应用程序权限](/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="50f29-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).</span></span>

<span data-ttu-id="50f29-138"><sup>2</sup> 此限制包含已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="50f29-138"><sup>2</sup> This limit includes archived teams.</span></span> 

<span data-ttu-id="50f29-139"><sup>3</sup> 若要进一步增加团队数量，必须联系 Microsoft 支持人员，并请求进一步增加租户中的 Azure Active Directory 对象数量。</span><span class="sxs-lookup"><span data-stu-id="50f29-139"><sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant.</span></span> <span data-ttu-id="50f29-140">仅针对真实生产方案进行了增加。</span><span class="sxs-lookup"><span data-stu-id="50f29-140">Increase is only made for real-life production scenarios.</span></span>

<span data-ttu-id="50f29-141"><sup>4</sup> 30 天内可还原已删除的频道。</span><span class="sxs-lookup"><span data-stu-id="50f29-141"><sup>4</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="50f29-142">在这 30 天内，已删除的频道仍然计入每个团队 200 个频道或 30 个专用频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="50f29-142">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="50f29-143">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队的限额内。</span><span class="sxs-lookup"><span data-stu-id="50f29-143">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="50f29-144"><sup>5</sup> 28 KB 是近似限制，因为它包括邮件本身（文本、图像链接等）、@提及、连接线数目以及反应。</span><span class="sxs-lookup"><span data-stu-id="50f29-144"><sup>5</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="50f29-145"><sup>GCC</sup> 6 个工作组可容纳 25，000 名成员，但 GCCH/DoD 中的团队仅能容纳 2，500 个成员。</span><span class="sxs-lookup"><span data-stu-id="50f29-145"><sup>6</sup> Teams in GCC can accommodate 25,000 members but teams in GCCH/DoD can only accommodate 2,500 members.</span></span> <span data-ttu-id="50f29-146">进一步请注意，拥有 10，000 多个成员的团队/频道提及将被阻止。</span><span class="sxs-lookup"><span data-stu-id="50f29-146">Further note that teams/channel mentions are blocked in teams with over 10,000 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="50f29-147">消息传递</span><span class="sxs-lookup"><span data-stu-id="50f29-147">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="50f29-148">聊天</span><span class="sxs-lookup"><span data-stu-id="50f29-148">Chat</span></span>

<span data-ttu-id="50f29-p105">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="50f29-p105">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="50f29-155">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="50f29-155">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="50f29-156">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-156">Feature</span></span>  | <span data-ttu-id="50f29-157">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-157">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="50f29-158">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-158">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="50f29-159">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-159">250<sup>2</sup></span></span> |
|<span data-ttu-id="50f29-160">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="50f29-160">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="50f29-161">20</span><span class="sxs-lookup"><span data-stu-id="50f29-161">20</span></span> |
|<span data-ttu-id="50f29-162">文件附件数<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-162">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="50f29-163">10</span><span class="sxs-lookup"><span data-stu-id="50f29-163">10</span></span>     |
|<span data-ttu-id="50f29-164">聊天大小</span><span class="sxs-lookup"><span data-stu-id="50f29-164">Chat size</span></span> | <span data-ttu-id="50f29-165">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-165">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="50f29-p106"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。当专用组聊天包含超过 20 个成员时，还将删除“设置发送选项”按钮 (!)。</span><span class="sxs-lookup"><span data-stu-id="50f29-p106"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="50f29-168"><sup>2</sup> 一次仅有 200 个成员可添加到群组聊天。</span><span class="sxs-lookup"><span data-stu-id="50f29-168"><sup>2</sup> Only 200 members at a time can be added to a group chat.</span></span> <span data-ttu-id="50f29-169">[请参阅本文了解详细信息](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。</span><span class="sxs-lookup"><span data-stu-id="50f29-169">[See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="50f29-170"><sup>3</sup> 如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="50f29-170"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="50f29-171"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="50f29-171"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="50f29-172">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="50f29-172">Emailing a channel</span></span>

 <span data-ttu-id="50f29-p108">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="50f29-p108">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="50f29-176">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-176">Feature</span></span>  | <span data-ttu-id="50f29-177">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-177">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="50f29-178">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="50f29-178">Message size<sup>1<sup></span></span> | <span data-ttu-id="50f29-179">24 KB</span><span class="sxs-lookup"><span data-stu-id="50f29-179">24 KB</span></span> |
|<span data-ttu-id="50f29-180">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-180">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="50f29-181">20</span><span class="sxs-lookup"><span data-stu-id="50f29-181">20</span></span>     |
|<span data-ttu-id="50f29-182">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="50f29-182">Size of each file attachment</span></span> | <span data-ttu-id="50f29-183">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="50f29-183">Less than 10 MB</span></span> |
|<span data-ttu-id="50f29-184">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-184">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="50f29-185">50</span><span class="sxs-lookup"><span data-stu-id="50f29-185">50</span></span>   |

<span data-ttu-id="50f29-186"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="50f29-186"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="50f29-187"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="50f29-187"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="50f29-188">有关详细信息，请参阅 [Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="50f29-188">For more information, see [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="50f29-p109">所有 Microsoft 365 和 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。Office GCC/GCCH/DOD 组织无法在 Teams 中通过电子邮件发送频道。</span><span class="sxs-lookup"><span data-stu-id="50f29-p109">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="50f29-191">频道名称</span><span class="sxs-lookup"><span data-stu-id="50f29-191">Channel names</span></span>

<span data-ttu-id="50f29-192">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="50f29-192">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="50f29-193">类型</span><span class="sxs-lookup"><span data-stu-id="50f29-193">Type</span></span>|<span data-ttu-id="50f29-194">示例</span><span class="sxs-lookup"><span data-stu-id="50f29-194">Example</span></span>|
|---------|---------|
|<span data-ttu-id="50f29-195">字符</span><span class="sxs-lookup"><span data-stu-id="50f29-195">Characters</span></span>     | <span data-ttu-id="50f29-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span><span class="sxs-lookup"><span data-stu-id="50f29-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span></span>        |
|<span data-ttu-id="50f29-198">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="50f29-198">Characters in these ranges</span></span>    | <span data-ttu-id="50f29-199">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="50f29-199">0 to 1F</span></span><br><span data-ttu-id="50f29-200">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="50f29-200">80 to 9F</span></span>        |
|<span data-ttu-id="50f29-201">字词</span><span class="sxs-lookup"><span data-stu-id="50f29-201">Words</span></span>     | <span data-ttu-id="50f29-202">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="50f29-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="50f29-203">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="50f29-203">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="50f29-204">会议和通话</span><span class="sxs-lookup"><span data-stu-id="50f29-204">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50f29-205">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="50f29-205">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="50f29-206">**若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：</span><span class="sxs-lookup"><span data-stu-id="50f29-206">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="50f29-207">可为多达20,000名与会者提供活动支持</span><span class="sxs-lookup"><span data-stu-id="50f29-207">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="50f29-208">一个租户可同时举办50场活动</span><span class="sxs-lookup"><span data-stu-id="50f29-208">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="50f29-209">每次广播的活动持续时间为16小时</span><span class="sxs-lookup"><span data-stu-id="50f29-209">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="50f29-p111">此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="50f29-p111">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="50f29-213">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-213">Feature</span></span>     | <span data-ttu-id="50f29-214">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="50f29-215">会议中的人数（可聊天和通话）</span><span class="sxs-lookup"><span data-stu-id="50f29-215">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="50f29-216">1000，包括 GCC，但还不包括 GCCH 或 DoD。</span><span class="sxs-lookup"><span data-stu-id="50f29-216">1000, includes GCC but not yet for GCCH or DoD.</span></span> <span data-ttu-id="50f29-217">“**仅供查看**”允许最多 20，000 名仅收听的参与者加入组织者拥有 E3/E5/A3/A5 SKU 以及政府版（GCC、GCC High 和 DoD）许可证。</span><span class="sxs-lookup"><span data-stu-id="50f29-217">**View-only** allows for up to 20,000 listen-only participants to join a meeting in which the organizer has a license for E3/E5/A3/A5 SKU, as well as, Government (GCC, GCC High, DoD).</span></span> <span data-ttu-id="50f29-218">了解关于[仅供查看体验](view-only-meeting-experience.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="50f29-218">Learn more about the [View-only experience](view-only-meeting-experience.md).</span></span>|
|<span data-ttu-id="50f29-219">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="50f29-219">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="50f29-220">20</span><span class="sxs-lookup"><span data-stu-id="50f29-220">20</span></span> |
|<span data-ttu-id="50f29-221">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="50f29-221">Max PowerPoint File Size</span></span> | <span data-ttu-id="50f29-222">2GB</span><span class="sxs-lookup"><span data-stu-id="50f29-222">2GB</span></span>|
|<span data-ttu-id="50f29-223">Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="50f29-223">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="50f29-224">20 天</span><span class="sxs-lookup"><span data-stu-id="50f29-224">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="50f29-225">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="50f29-225">Meeting expiration</span></span>

> [!NOTE]
> <span data-ttu-id="50f29-p113">会议 URL 永远不会停止工作。过期仅涉及任何 PSTN 拨入号码和/或基础会议策略和设置。</span><span class="sxs-lookup"><span data-stu-id="50f29-p113">A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers and/or underlying meeting policies and settings.</span></span>

|<span data-ttu-id="50f29-228">会议类型</span><span class="sxs-lookup"><span data-stu-id="50f29-228">Meeting type</span></span>  |<span data-ttu-id="50f29-229">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="50f29-229">Meeting expires after this much time</span></span>  |<span data-ttu-id="50f29-230">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="50f29-230">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="50f29-231">立即开会</span><span class="sxs-lookup"><span data-stu-id="50f29-231">Meet now</span></span>     |<span data-ttu-id="50f29-232">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="50f29-232">Start time + 8 hours</span></span>         |<span data-ttu-id="50f29-233">不适用</span><span class="sxs-lookup"><span data-stu-id="50f29-233">N/A</span></span>         |
|<span data-ttu-id="50f29-234">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="50f29-234">Regular with no end time</span></span>     |<span data-ttu-id="50f29-235">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-235">Start time + 60 days</span></span>         | <span data-ttu-id="50f29-236">60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-236">60 days</span></span>        |
|<span data-ttu-id="50f29-237">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="50f29-237">Regular with end time</span></span>     |<span data-ttu-id="50f29-238">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-238">End time + 60 days</span></span>         |<span data-ttu-id="50f29-239">60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-239">60 days</span></span>         |
|<span data-ttu-id="50f29-240">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="50f29-240">Recurring with no end time</span></span>     |<span data-ttu-id="50f29-241">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-241">Start time + 60 days</span></span>         |<span data-ttu-id="50f29-242">60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-242">60 days</span></span>         |
|<span data-ttu-id="50f29-243">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="50f29-243">Recurring with end time</span></span>     |<span data-ttu-id="50f29-244">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-244">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="50f29-245">60 天</span><span class="sxs-lookup"><span data-stu-id="50f29-245">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="50f29-246">Microsoft Teams 会议的时间限制为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="50f29-246">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="50f29-247">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="50f29-247">Teams Live Events</span></span>

|<span data-ttu-id="50f29-248">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-248">Feature</span></span>     | <span data-ttu-id="50f29-249">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-249">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="50f29-250">受众规模</span><span class="sxs-lookup"><span data-stu-id="50f29-250">Audience size</span></span> | <span data-ttu-id="50f29-251">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="50f29-251">10,000 attendees</span></span> |
|<span data-ttu-id="50f29-252">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="50f29-252">Duration of event</span></span> | <span data-ttu-id="50f29-253">4 小时</span><span class="sxs-lookup"><span data-stu-id="50f29-253">4 hours</span></span> |
|<span data-ttu-id="50f29-254">Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50f29-254">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="50f29-255">15</span><span class="sxs-lookup"><span data-stu-id="50f29-255">15</span></span> |

<span data-ttu-id="50f29-p114"><sup>1</sup> 可根据需要安排许多实时事件，但每次只能运行 15 个。一旦制造者加入实时事件，即被视为正在运行。尝试加入第 16 个实时事件的制造者将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="50f29-p114"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="50f29-p115">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另请参阅[安排 Teams 实时事件](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="50f29-p115">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50f29-261">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="50f29-261">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="50f29-262">**若要继续支持客户的需求，直至2021年6月30日，我们将扩展现场活动的临时增加限额，包括**：</span><span class="sxs-lookup"><span data-stu-id="50f29-262">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="50f29-263">可为多达20,000名与会者提供活动支持</span><span class="sxs-lookup"><span data-stu-id="50f29-263">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="50f29-264">一个租户可同时举办50场活动</span><span class="sxs-lookup"><span data-stu-id="50f29-264">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="50f29-265">每次广播的活动持续时间为16小时</span><span class="sxs-lookup"><span data-stu-id="50f29-265">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="50f29-p116">此外，可通过 Microsoft 365 辅助计划规划最多 100,000 名与会者的实时活动。团队将评估每个请求，并共同确定可能可用的选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="50f29-p116">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="50f29-269">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="50f29-269">Presence in Outlook</span></span>

<span data-ttu-id="50f29-p117">Outlook 2013 桌面应用及更高版本支持 Outlook 中的 Teams 状态。若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="50f29-p117">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="50f29-272">存储</span><span class="sxs-lookup"><span data-stu-id="50f29-272">Storage</span></span>

<span data-ttu-id="50f29-p118">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="50f29-p118">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="50f29-275">每个[专用频道](./private-channels.md)都拥有自己的 SharePoint 网站（以前称为“网站集”）。</span><span class="sxs-lookup"><span data-stu-id="50f29-275">Each [private channel](./private-channels.md) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="50f29-p119">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="50f29-p119">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="50f29-p120">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="50f29-p120">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="50f29-p121">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="50f29-p121">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="50f29-282">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-282">Feature</span></span>                 |<span data-ttu-id="50f29-283">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="50f29-283">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="50f29-284">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="50f29-284">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="50f29-285">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="50f29-285">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="50f29-286">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="50f29-286">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="50f29-287">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="50f29-287">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="50f29-288">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="50f29-288">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="50f29-289">存储空间</span><span class="sxs-lookup"><span data-stu-id="50f29-289">Storage</span></span>                 |<span data-ttu-id="50f29-290">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="50f29-290">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="50f29-291">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="50f29-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="50f29-292">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="50f29-292">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="50f29-293">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="50f29-293">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="50f29-294">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="50f29-294">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="50f29-295">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="50f29-295">1 TB per organization</span></span>           |
|<span data-ttu-id="50f29-296">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="50f29-296">Storage for Teams Files</span></span> |<span data-ttu-id="50f29-297">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="50f29-298">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="50f29-299">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-299">Up to 25 TB per site or group</span></span> |<span data-ttu-id="50f29-300">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-300">Up to 25 TB per site or group</span></span> |<span data-ttu-id="50f29-301">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-301">Up to 25 TB per site or group</span></span> |<span data-ttu-id="50f29-302">每个网站或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="50f29-302">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="50f29-303">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="50f29-303">File upload limit  (per file)</span></span>    |<span data-ttu-id="50f29-304">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-304">100 GB</span></span>    |<span data-ttu-id="50f29-305">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-305">100 GB</span></span>    |<span data-ttu-id="50f29-306">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-306">100 GB</span></span>    |<span data-ttu-id="50f29-307">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-307">100 GB</span></span>    |<span data-ttu-id="50f29-308">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-308">100 GB</span></span>    |<span data-ttu-id="50f29-309">100 GB</span><span class="sxs-lookup"><span data-stu-id="50f29-309">100 GB</span></span>    |

<span data-ttu-id="50f29-310">频道由 SharePoint Online 网站（以前称为“网站集”）中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="50f29-310">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="50f29-311">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="50f29-311">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="50f29-312">课堂团队</span><span class="sxs-lookup"><span data-stu-id="50f29-312">Class teams</span></span>

<span data-ttu-id="50f29-p122">Microsoft Teams 教育版提供了专为独特教育场景设计的模板，如课堂教学。有关团队类型的详细信息（包括课堂团队），可在“[在 Microsoft Teams 中选择团队类型进行协作](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)”中找到。</span><span class="sxs-lookup"><span data-stu-id="50f29-p122">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="50f29-315">课堂团队是一种模板类型，其中包含附加应用，且具有单独限制团队成员数量的功能。</span><span class="sxs-lookup"><span data-stu-id="50f29-315">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="50f29-316">使用课堂团队需要 [Office 365 教育版许可证](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="50f29-316">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="50f29-317">下表列出了课堂团队的限制：</span><span class="sxs-lookup"><span data-stu-id="50f29-317">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="50f29-318">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-318">Feature</span></span>  |<span data-ttu-id="50f29-319">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-319">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="50f29-320">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-320">Number of members in a team</span></span>    | <span data-ttu-id="50f29-321">请参阅本文的[“团队和频道”](#teams-and-channels)部分</span><span class="sxs-lookup"><span data-stu-id="50f29-321">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="50f29-322">课堂团队中使用“作业”的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-322">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="50f29-323">200</span><span class="sxs-lookup"><span data-stu-id="50f29-323">200</span></span>        |
|<span data-ttu-id="50f29-324">课堂团队中使用“OneNote 课堂笔记本”的成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-324">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="50f29-325">200</span><span class="sxs-lookup"><span data-stu-id="50f29-325">200</span></span>         |

<span data-ttu-id="50f29-p123">课堂团队可以支持超过 200 位成员。但是，如果你计划在你的团队中使用“作业”应用或“课堂笔记本”应用，则需要保留低于最大限制的成员数。</span><span class="sxs-lookup"><span data-stu-id="50f29-p123">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="50f29-328">标记</span><span class="sxs-lookup"><span data-stu-id="50f29-328">Tags</span></span>

|<span data-ttu-id="50f29-329">功能</span><span class="sxs-lookup"><span data-stu-id="50f29-329">Feature</span></span>  |<span data-ttu-id="50f29-330">最大限制</span><span class="sxs-lookup"><span data-stu-id="50f29-330">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="50f29-331">每个团队的标记数</span><span class="sxs-lookup"><span data-stu-id="50f29-331">Number of tags per team</span></span>    | <span data-ttu-id="50f29-332">100</span><span class="sxs-lookup"><span data-stu-id="50f29-332">100</span></span>        |
|<span data-ttu-id="50f29-333">每个团队建议的默认标记数</span><span class="sxs-lookup"><span data-stu-id="50f29-333">Number of suggested default tags per team</span></span>    | <span data-ttu-id="50f29-334">25</span><span class="sxs-lookup"><span data-stu-id="50f29-334">25</span></span>        |
|<span data-ttu-id="50f29-335">分配有标记的团队成员数</span><span class="sxs-lookup"><span data-stu-id="50f29-335">Number of team members assign to a tag</span></span>    |<span data-ttu-id="50f29-336">100</span><span class="sxs-lookup"><span data-stu-id="50f29-336">100</span></span>         |
|<span data-ttu-id="50f29-337">分配给每个团队每个用户的标记数</span><span class="sxs-lookup"><span data-stu-id="50f29-337">Number of tags assigned to a user per team</span></span>    |<span data-ttu-id="50f29-338">25</span><span class="sxs-lookup"><span data-stu-id="50f29-338">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="50f29-339">联系人</span><span class="sxs-lookup"><span data-stu-id="50f29-339">Contacts</span></span>

<span data-ttu-id="50f29-340">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="50f29-340">Teams uses these contacts:</span></span>

- <span data-ttu-id="50f29-341">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="50f29-341">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="50f29-342">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="50f29-342">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="50f29-343">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="50f29-343">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="50f29-344">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="50f29-344">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="50f29-345">浏览器</span><span class="sxs-lookup"><span data-stu-id="50f29-345">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="50f29-346">操作系统</span><span class="sxs-lookup"><span data-stu-id="50f29-346">Operating systems</span></span>

<span data-ttu-id="50f29-347">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="50f29-347">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
