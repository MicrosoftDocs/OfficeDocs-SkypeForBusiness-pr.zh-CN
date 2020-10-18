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
ms.openlocfilehash: ae0583225de5eabfd6cad77895859f9c7159276f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508079"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="f2863-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="f2863-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="f2863-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="f2863-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="f2863-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="f2863-105">Teams and channels</span></span>

|<span data-ttu-id="f2863-106">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-106">Feature</span></span>    | <span data-ttu-id="f2863-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="f2863-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="f2863-108">Number of teams a user can create</span></span> | <span data-ttu-id="f2863-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="f2863-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="f2863-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="f2863-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="f2863-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="f2863-111">1,000&sup2;</span></span>|
|<span data-ttu-id="f2863-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-112">Number of members in a team</span></span> | <span data-ttu-id="f2863-113">10,000</span><span class="sxs-lookup"><span data-stu-id="f2863-113">10,000</span></span>       |
|<span data-ttu-id="f2863-114">每个团队的所有者数</span><span class="sxs-lookup"><span data-stu-id="f2863-114">Number of owners per team</span></span> | <span data-ttu-id="f2863-115">100</span><span class="sxs-lookup"><span data-stu-id="f2863-115">100</span></span>   |
|<span data-ttu-id="f2863-116">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="f2863-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="f2863-117">5</span><span class="sxs-lookup"><span data-stu-id="f2863-117">5</span></span>     |
|<span data-ttu-id="f2863-118">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="f2863-119">5,000</span><span class="sxs-lookup"><span data-stu-id="f2863-119">5,000</span></span>       |
|<span data-ttu-id="f2863-120">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="f2863-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="f2863-121">500,000</span><span class="sxs-lookup"><span data-stu-id="f2863-121">500,000</span></span>   |
|<span data-ttu-id="f2863-122">Microsoft 365 或 Office 365 组织可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="f2863-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="f2863-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="f2863-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="f2863-124">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="f2863-124">Number of channels per team</span></span>    | <span data-ttu-id="f2863-125">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="f2863-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="f2863-126">各团队专用频道数</span><span class="sxs-lookup"><span data-stu-id="f2863-126">Number of Private channels per team</span></span>    |<span data-ttu-id="f2863-127">30</span><span class="sxs-lookup"><span data-stu-id="f2863-127">30</span></span>| <span data-ttu-id="f2863-128">（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="f2863-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="f2863-129">专用频道中的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="f2863-130">250</span><span class="sxs-lookup"><span data-stu-id="f2863-130">250</span></span>|
|<span data-ttu-id="f2863-131">Office 365 组中最多可以有多少名成员以转换为团队</span><span class="sxs-lookup"><span data-stu-id="f2863-131">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="f2863-132">10,000</span><span class="sxs-lookup"><span data-stu-id="f2863-132">10,000</span></span>|
|<span data-ttu-id="f2863-133">频道对话文章大小</span><span class="sxs-lookup"><span data-stu-id="f2863-133">Channel conversation post size</span></span> | <span data-ttu-id="f2863-134">每篇文章约 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-134">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="f2863-135"><sup>1</sup> Azure Active Directory 中的目录对象均计入此限额。</span><span class="sxs-lookup"><span data-stu-id="f2863-135"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="f2863-136">如同使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="f2863-136">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="f2863-137"><sup>2</sup> 此限制涵盖已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="f2863-137"><sup>2</sup> This limit includes archived teams.</span></span> <span data-ttu-id="f2863-138">若要超出最大限制，你必须联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="f2863-138">To go beyond the maximum limit, you must contact Microsoft support.</span></span>

<span data-ttu-id="f2863-139"><sup>3</sup> 已删除的频道可在删除后 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="f2863-139"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="f2863-140">在这 30 天内，已删除的频道仍然计入每个团队 200 个频道或 30 个专用频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="f2863-140">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="f2863-141">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队的限额内。</span><span class="sxs-lookup"><span data-stu-id="f2863-141">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="f2863-142"><sup>4</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及、连接器数量和回应。</span><span class="sxs-lookup"><span data-stu-id="f2863-142"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="f2863-143">消息传递</span><span class="sxs-lookup"><span data-stu-id="f2863-143">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="f2863-144">聊天</span><span class="sxs-lookup"><span data-stu-id="f2863-144">Chat</span></span>

<span data-ttu-id="f2863-145">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="f2863-145">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="f2863-146">原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f2863-146">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="f2863-147">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="f2863-147">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="f2863-148">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。</span><span class="sxs-lookup"><span data-stu-id="f2863-148">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="f2863-149">但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f2863-149">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="f2863-150">（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="f2863-150">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="f2863-151">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="f2863-151">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="f2863-152">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-152">Feature</span></span>  | <span data-ttu-id="f2863-153">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-153">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f2863-154">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-154">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="f2863-155">250</span><span class="sxs-lookup"><span data-stu-id="f2863-155">250</span></span> |
|<span data-ttu-id="f2863-156">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="f2863-156">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="f2863-157">20</span><span class="sxs-lookup"><span data-stu-id="f2863-157">20</span></span> |
|<span data-ttu-id="f2863-158">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-158">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="f2863-159">10</span><span class="sxs-lookup"><span data-stu-id="f2863-159">10</span></span>     |
|<span data-ttu-id="f2863-160">聊天大小</span><span class="sxs-lookup"><span data-stu-id="f2863-160">Chat size</span></span> | <span data-ttu-id="f2863-161">每篇文章约 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-161">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="f2863-162"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。</span><span class="sxs-lookup"><span data-stu-id="f2863-162"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="f2863-163">当专用组聊天包含超过 20 个成员时，还将删除“设置发送选项”按钮 (!)。</span><span class="sxs-lookup"><span data-stu-id="f2863-163">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="f2863-164"><sup>2</sup>如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="f2863-164"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="f2863-165"><sup>3</sup> 28 KB 是一个近似限制，因为它包含消息本身（文本和图像链接等）、@提及和回应。</span><span class="sxs-lookup"><span data-stu-id="f2863-165"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="f2863-166">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="f2863-166">Emailing a channel</span></span>

 <span data-ttu-id="f2863-167">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f2863-167">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="f2863-168">如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。</span><span class="sxs-lookup"><span data-stu-id="f2863-168">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="f2863-169">下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="f2863-169">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="f2863-170">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-170">Feature</span></span>  | <span data-ttu-id="f2863-171">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-171">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f2863-172">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="f2863-172">Message size<sup>1<sup></span></span> | <span data-ttu-id="f2863-173">24 KB</span><span class="sxs-lookup"><span data-stu-id="f2863-173">24 KB</span></span> |
|<span data-ttu-id="f2863-174">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-174">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="f2863-175">20</span><span class="sxs-lookup"><span data-stu-id="f2863-175">20</span></span>     |
|<span data-ttu-id="f2863-176">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="f2863-176">Size of each file attachment</span></span> | <span data-ttu-id="f2863-177">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="f2863-177">Less than 10 MB</span></span> |
|<span data-ttu-id="f2863-178">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-178">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="f2863-179">50</span><span class="sxs-lookup"><span data-stu-id="f2863-179">50</span></span>   |

<span data-ttu-id="f2863-180"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f2863-180"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="f2863-181"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="f2863-181"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="f2863-182">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="f2863-182">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="f2863-183">所有 Microsoft 365 和 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。</span><span class="sxs-lookup"><span data-stu-id="f2863-183">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span> <span data-ttu-id="f2863-184">Office GCC/GCCH/DOD 组织无法在 Teams 中通过电子邮件发送频道。</span><span class="sxs-lookup"><span data-stu-id="f2863-184">Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>



## <a name="channel-names"></a><span data-ttu-id="f2863-185">频道名称</span><span class="sxs-lookup"><span data-stu-id="f2863-185">Channel names</span></span>

<span data-ttu-id="f2863-186">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="f2863-186">Channel names can't contain the following characters or words.</span></span>

|<span data-ttu-id="f2863-187">类型</span><span class="sxs-lookup"><span data-stu-id="f2863-187">Type</span></span>|<span data-ttu-id="f2863-188">示例</span><span class="sxs-lookup"><span data-stu-id="f2863-188">Example</span></span>|
|---------|---------|
|<span data-ttu-id="f2863-189">字符</span><span class="sxs-lookup"><span data-stu-id="f2863-189">Characters</span></span>     | <span data-ttu-id="f2863-190">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="f2863-190">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="f2863-191">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="f2863-191">&#124; ' " , .</span></span>        |
|<span data-ttu-id="f2863-192">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="f2863-192">Characters in these ranges</span></span>    | <span data-ttu-id="f2863-193">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="f2863-193">0 to 1F</span></span><br><span data-ttu-id="f2863-194">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="f2863-194">80 to 9F</span></span>        |
|<span data-ttu-id="f2863-195">字词</span><span class="sxs-lookup"><span data-stu-id="f2863-195">Words</span></span>     | <span data-ttu-id="f2863-196">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="f2863-196">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="f2863-197">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="f2863-197">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="f2863-198">会议和通话</span><span class="sxs-lookup"><span data-stu-id="f2863-198">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2863-199">**Microsoft 365 直播活动提升人数上限**</span><span class="sxs-lookup"><span data-stu-id="f2863-199">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="f2863-200">**为帮助支持我们的客户，从 2021 年 1 月 1 日起，我们将为 Teams、Stream 和 Yammer 中托管的直播活动扩展临时人数上限，包括**：</span><span class="sxs-lookup"><span data-stu-id="f2863-200">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="f2863-201">每场活动最多可容纳 2 万名参考者</span><span class="sxs-lookup"><span data-stu-id="f2863-201">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="f2863-202">每个 Teams 租户最多可同时举行 50 场活动</span><span class="sxs-lookup"><span data-stu-id="f2863-202">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="f2863-203">每次直播最多持续 16 个小时</span><span class="sxs-lookup"><span data-stu-id="f2863-203">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="f2863-204">此外，可通过 Microsoft 365 辅助计划来安排最多有 10 万名参与者的直播活动。</span><span class="sxs-lookup"><span data-stu-id="f2863-204">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="f2863-205">团队将评估每个请求，并与共同确定可能的选项。</span><span class="sxs-lookup"><span data-stu-id="f2863-205">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="f2863-206">[了解详细信息](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="f2863-206">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="f2863-207">**2021 年 1 月 1 日之后，需要提高上述人数上限的客户将需要购买[高级通信附加产品](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="f2863-207">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="f2863-208">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-208">Feature</span></span>     | <span data-ttu-id="f2863-209">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-209">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="f2863-210">会议中的人数（可聊天和通话）</span><span class="sxs-lookup"><span data-stu-id="f2863-210">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="f2863-211">300</span><span class="sxs-lookup"><span data-stu-id="f2863-211">300</span></span> |
|<span data-ttu-id="f2863-212">通过视频或音频通话聊天的人员数</span><span class="sxs-lookup"><span data-stu-id="f2863-212">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="f2863-213">20</span><span class="sxs-lookup"><span data-stu-id="f2863-213">20</span></span> |
|<span data-ttu-id="f2863-214">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="f2863-214">Max PowerPoint File Size</span></span> | <span data-ttu-id="f2863-215">2GB</span><span class="sxs-lookup"><span data-stu-id="f2863-215">2GB</span></span>|
|<span data-ttu-id="f2863-216">Teams 保留了不会上传到 Microsoft Stream 且可供本地下载的[会议记录](cloud-recording.md)</span><span class="sxs-lookup"><span data-stu-id="f2863-216">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="f2863-217">20 天</span><span class="sxs-lookup"><span data-stu-id="f2863-217">20 days</span></span> |

>[!Note]
> <span data-ttu-id="f2863-218">将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](tmr-meeting-recording-change.md) 将是一种分阶段的方法。</span><span class="sxs-lookup"><span data-stu-id="f2863-218">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="f2863-219">在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月你必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。</span><span class="sxs-lookup"><span data-stu-id="f2863-219">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="f2863-220">会议过期时间</span><span class="sxs-lookup"><span data-stu-id="f2863-220">Meeting expiration</span></span>

|<span data-ttu-id="f2863-221">会议类型</span><span class="sxs-lookup"><span data-stu-id="f2863-221">Meeting type</span></span>  |<span data-ttu-id="f2863-222">会议将在此时间后过期</span><span class="sxs-lookup"><span data-stu-id="f2863-222">Meeting expires after this much time</span></span>  |<span data-ttu-id="f2863-223">每次发起或更新会议时，过期时间都延长此时间</span><span class="sxs-lookup"><span data-stu-id="f2863-223">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f2863-224">立即开会</span><span class="sxs-lookup"><span data-stu-id="f2863-224">Meet now</span></span>     |<span data-ttu-id="f2863-225">开始时间 + 8 小时</span><span class="sxs-lookup"><span data-stu-id="f2863-225">Start time + 8 hours</span></span>         |<span data-ttu-id="f2863-226">不适用</span><span class="sxs-lookup"><span data-stu-id="f2863-226">N/A</span></span>         |
|<span data-ttu-id="f2863-227">常规，无结束时间</span><span class="sxs-lookup"><span data-stu-id="f2863-227">Regular with no end time</span></span>     |<span data-ttu-id="f2863-228">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-228">Start time + 60 days</span></span>         | <span data-ttu-id="f2863-229">60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-229">60 days</span></span>        |
|<span data-ttu-id="f2863-230">常规，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="f2863-230">Regular with end time</span></span>     |<span data-ttu-id="f2863-231">结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-231">End time + 60 days</span></span>         |<span data-ttu-id="f2863-232">60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-232">60 days</span></span>         |
|<span data-ttu-id="f2863-233">定期，无结束时间</span><span class="sxs-lookup"><span data-stu-id="f2863-233">Recurring with no end time</span></span>     |<span data-ttu-id="f2863-234">开始时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-234">Start time + 60 days</span></span>         |<span data-ttu-id="f2863-235">60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-235">60 days</span></span>         |
|<span data-ttu-id="f2863-236">定期，设有结束时间</span><span class="sxs-lookup"><span data-stu-id="f2863-236">Recurring with end time</span></span>     |<span data-ttu-id="f2863-237">上次会议的结束时间 + 60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-237">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="f2863-238">60 天</span><span class="sxs-lookup"><span data-stu-id="f2863-238">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="f2863-239">Microsoft Teams 会议的时间限制为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="f2863-239">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="f2863-240">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="f2863-240">Teams live events</span></span>

|<span data-ttu-id="f2863-241">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-241">Feature</span></span>     | <span data-ttu-id="f2863-242">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-242">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="f2863-243">受众规模</span><span class="sxs-lookup"><span data-stu-id="f2863-243">Audience size</span></span> | <span data-ttu-id="f2863-244">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="f2863-244">10,000 attendees</span></span> |
|<span data-ttu-id="f2863-245">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="f2863-245">Duration of event</span></span> | <span data-ttu-id="f2863-246">4 小时</span><span class="sxs-lookup"><span data-stu-id="f2863-246">4 hours</span></span> |
|<span data-ttu-id="f2863-247">Microsoft 365 或 Office 365 组织中运行的并发实时事件数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f2863-247">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="f2863-248">15</span><span class="sxs-lookup"><span data-stu-id="f2863-248">15</span></span> |

<span data-ttu-id="f2863-249"><sup>1</sup> 可以根据需要安排许多实时事件，但每次只能运行 15 个。</span><span class="sxs-lookup"><span data-stu-id="f2863-249"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="f2863-250">一旦制造者加入实时事件，即被视为正在运行。</span><span class="sxs-lookup"><span data-stu-id="f2863-250">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="f2863-251">尝试加入第 16 个实时事件的制造者将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f2863-251">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="f2863-252">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="f2863-252">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2863-253">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="f2863-253">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="f2863-254">为帮助客户满足快速变化的沟通需求，Microsoft 365 直播活动将暂时对 Teams 中托管的活动提高默认人数上限，直到 2021 年 1 月 1 日。</span><span class="sxs-lookup"><span data-stu-id="f2863-254">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="f2863-255">参与者限制：事件最多可以支持 20000 名参与者</span><span class="sxs-lookup"><span data-stu-id="f2863-255">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="f2863-256">并发事件：同一租户可以同时托管 50 件事件</span><span class="sxs-lookup"><span data-stu-id="f2863-256">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="f2863-257">事件持续时间：每个播报的事件持续时间增加到 16 小时</span><span class="sxs-lookup"><span data-stu-id="f2863-257">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="f2863-258">此外，可通过 Microsoft 直播活动辅助计划来安排最多有 10 万名参与者的直播活动。</span><span class="sxs-lookup"><span data-stu-id="f2863-258">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="f2863-259">[了解详细信息](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="f2863-259">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="f2863-260">**2021 年 1 月 1 日之后，需要提高上述人数上限的客户将需要购买[高级通信附加产品](teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="f2863-260">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="f2863-261">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="f2863-261">Presence in Outlook</span></span>

<span data-ttu-id="f2863-262">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="f2863-262">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="f2863-263">若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="f2863-263">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="f2863-264">存储空间</span><span class="sxs-lookup"><span data-stu-id="f2863-264">Storage</span></span>

<span data-ttu-id="f2863-265">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="f2863-265">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="f2863-266">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="f2863-266">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f2863-267">每个[私人频道](https://docs.microsoft.com/microsoftteams/private-channels)都拥有自己的 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="f2863-267">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="f2863-268">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="f2863-268">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="f2863-269">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="f2863-269">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="f2863-270">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="f2863-270">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="f2863-271">（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="f2863-271">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="f2863-272">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。</span><span class="sxs-lookup"><span data-stu-id="f2863-272">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="f2863-273">下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="f2863-273">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="f2863-274">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-274">Feature</span></span>                 |<span data-ttu-id="f2863-275">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="f2863-275">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="f2863-276">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="f2863-276">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="f2863-277">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="f2863-277">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="f2863-278">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="f2863-278">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="f2863-279">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f2863-279">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="f2863-280">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="f2863-280">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="f2863-281">存储空间</span><span class="sxs-lookup"><span data-stu-id="f2863-281">Storage</span></span>                 |<span data-ttu-id="f2863-282">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="f2863-282">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f2863-283">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="f2863-283">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f2863-284">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="f2863-284">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="f2863-285">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="f2863-285">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="f2863-286">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="f2863-286">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f2863-287">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="f2863-287">1 TB per organization</span></span>           |
|<span data-ttu-id="f2863-288">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="f2863-288">Storage for Teams Files</span></span> |<span data-ttu-id="f2863-289">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-289">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f2863-290">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-290">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f2863-291">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-291">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f2863-292">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-292">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f2863-293">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-293">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f2863-294">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="f2863-294">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="f2863-295">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="f2863-295">File upload limit  (per file)</span></span>    |<span data-ttu-id="f2863-296">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-296">100 GB</span></span>    |<span data-ttu-id="f2863-297">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-297">100 GB</span></span>    |<span data-ttu-id="f2863-298">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-298">100 GB</span></span>    |<span data-ttu-id="f2863-299">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-299">100 GB</span></span>    |<span data-ttu-id="f2863-300">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-300">100 GB</span></span>    |<span data-ttu-id="f2863-301">100 GB</span><span class="sxs-lookup"><span data-stu-id="f2863-301">100 GB</span></span>    |

<span data-ttu-id="f2863-302">频道由 SharePoint Online 网站集中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="f2863-302">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="f2863-303">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="f2863-303">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="f2863-304">课堂团队</span><span class="sxs-lookup"><span data-stu-id="f2863-304">Class teams</span></span>

<span data-ttu-id="f2863-305">Microsoft Teams 教育版提供了专为独特教育场景设计的模板，如课堂教学。</span><span class="sxs-lookup"><span data-stu-id="f2863-305">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="f2863-306">有关团队类型的详细信息（包括课堂团队），可在“[在 Microsoft Teams 中选择团队类型进行协作](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)”中找到。</span><span class="sxs-lookup"><span data-stu-id="f2863-306">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="f2863-307">课堂团队是一种模板类型，其中包含附加应用，且具有单独限制团队成员数量的功能。</span><span class="sxs-lookup"><span data-stu-id="f2863-307">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="f2863-308">使用课堂团队需要 [Office 365 教育版许可证](https://www.microsoft.com/education/products/office)。</span><span class="sxs-lookup"><span data-stu-id="f2863-308">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="f2863-309">下表列出了课堂团队的限制：</span><span class="sxs-lookup"><span data-stu-id="f2863-309">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="f2863-310">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-310">Feature</span></span>  |<span data-ttu-id="f2863-311">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-311">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f2863-312">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-312">Number of members in a team</span></span>    | <span data-ttu-id="f2863-313">请参阅本文的[“团队和频道”](#teams-and-channels)部分</span><span class="sxs-lookup"><span data-stu-id="f2863-313">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="f2863-314">课堂团队中使用“作业”的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-314">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="f2863-315">200</span><span class="sxs-lookup"><span data-stu-id="f2863-315">200</span></span>        |
|<span data-ttu-id="f2863-316">课堂团队中使用“OneNote 课堂笔记本”的成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-316">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="f2863-317">200</span><span class="sxs-lookup"><span data-stu-id="f2863-317">200</span></span>         |

<span data-ttu-id="f2863-318">课堂团队可以支持超过 200 位成员。</span><span class="sxs-lookup"><span data-stu-id="f2863-318">A class team can support more than 200 members.</span></span> <span data-ttu-id="f2863-319">但是，如果你计划在你的团队中使用“作业”应用或“课堂笔记本”应用，则需要保留低于最大限制的成员数。</span><span class="sxs-lookup"><span data-stu-id="f2863-319">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="f2863-320">标记</span><span class="sxs-lookup"><span data-stu-id="f2863-320">Tags</span></span>

|<span data-ttu-id="f2863-321">功能</span><span class="sxs-lookup"><span data-stu-id="f2863-321">Feature</span></span>  |<span data-ttu-id="f2863-322">最大限制</span><span class="sxs-lookup"><span data-stu-id="f2863-322">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="f2863-323">每个团队的标记数</span><span class="sxs-lookup"><span data-stu-id="f2863-323">Number of tags per team</span></span>    | <span data-ttu-id="f2863-324">100</span><span class="sxs-lookup"><span data-stu-id="f2863-324">100</span></span>        |
|<span data-ttu-id="f2863-325">每个团队建议的默认标记数</span><span class="sxs-lookup"><span data-stu-id="f2863-325">Number of suggested default tags per team</span></span>    | <span data-ttu-id="f2863-326">25</span><span class="sxs-lookup"><span data-stu-id="f2863-326">25</span></span>        |
|<span data-ttu-id="f2863-327">分配有标记的团队成员数</span><span class="sxs-lookup"><span data-stu-id="f2863-327">Number of team members assign to a tag</span></span>    |<span data-ttu-id="f2863-328">100</span><span class="sxs-lookup"><span data-stu-id="f2863-328">100</span></span>         |
|<span data-ttu-id="f2863-329">分配给用户的标记数</span><span class="sxs-lookup"><span data-stu-id="f2863-329">Number of tags assigned to a user</span></span>    |<span data-ttu-id="f2863-330">25</span><span class="sxs-lookup"><span data-stu-id="f2863-330">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="f2863-331">联系人</span><span class="sxs-lookup"><span data-stu-id="f2863-331">Contacts</span></span>

<span data-ttu-id="f2863-332">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="f2863-332">Teams uses these contacts:</span></span>

- <span data-ttu-id="f2863-333">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="f2863-333">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="f2863-334">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="f2863-334">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="f2863-335">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="f2863-335">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="f2863-336">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="f2863-336">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="f2863-337">浏览器</span><span class="sxs-lookup"><span data-stu-id="f2863-337">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="f2863-338">操作系统</span><span class="sxs-lookup"><span data-stu-id="f2863-338">Operating systems</span></span>

<span data-ttu-id="f2863-339">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="f2863-339">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
