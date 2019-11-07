---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: 了解适用于 Microsoft Teams 的限制、规范和其他要求。
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8de3a1b61d706ba2f85e83ec6290378d47cb20fe
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010515"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="463cc-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="463cc-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="463cc-104">本文介绍了适用于 Teams 的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="463cc-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="463cc-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="463cc-105">Teams and channels</span></span>

|<span data-ttu-id="463cc-106">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-106">Feature</span></span>    | <span data-ttu-id="463cc-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="463cc-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="463cc-108">用户可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="463cc-108">Number of teams a user can create</span></span> | <span data-ttu-id="463cc-109">限制为 250 个对象&sup1;</span><span class="sxs-lookup"><span data-stu-id="463cc-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="463cc-110">用户可以成为其成员的团队数</span><span class="sxs-lookup"><span data-stu-id="463cc-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="463cc-111">1,000</span><span class="sxs-lookup"><span data-stu-id="463cc-111">1,000</span></span>|
|<span data-ttu-id="463cc-112">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="463cc-112">Number of members in a team</span></span> | <span data-ttu-id="463cc-113">5,000</span><span class="sxs-lookup"><span data-stu-id="463cc-113">5,000</span></span>       |
|<span data-ttu-id="463cc-114">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="463cc-114">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="463cc-115">5</span><span class="sxs-lookup"><span data-stu-id="463cc-115">5</span></span>     |
|<span data-ttu-id="463cc-116">[组织范围内的团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="463cc-116">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="463cc-117">5,000</span><span class="sxs-lookup"><span data-stu-id="463cc-117">5,000</span></span>       |
|<span data-ttu-id="463cc-118">全局管理员可创建的团队数</span><span class="sxs-lookup"><span data-stu-id="463cc-118">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="463cc-119">500,000</span><span class="sxs-lookup"><span data-stu-id="463cc-119">500,000</span></span>   |
|<span data-ttu-id="463cc-120">Office 365 租户可拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="463cc-120">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="463cc-121">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="463cc-121">500,000&sup2;</span></span>     |
|<span data-ttu-id="463cc-122">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="463cc-122">Number of channels per team</span></span>    | <span data-ttu-id="463cc-123">200（包括已删除的频道）&sup3;</span><span class="sxs-lookup"><span data-stu-id="463cc-123">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="463cc-124">&sup1;Azure Active Directory 中的目录对象均计入此限额。</span><span class="sxs-lookup"><span data-stu-id="463cc-124">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="463cc-125">如同使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样，全局管理员不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="463cc-125">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="463cc-126">&sup2;此限制涵盖已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="463cc-126">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="463cc-127">&sup3;已删除的频道可在删除后 30 天内还原。</span><span class="sxs-lookup"><span data-stu-id="463cc-127">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="463cc-128">在该等 30 天，已删除的频道仍然计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="463cc-128">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="463cc-129">30 天后，已删除的频道及其内容将被永久删除，且此团队不再计入每个团队 200 个频道这一限额内。</span><span class="sxs-lookup"><span data-stu-id="463cc-129">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="463cc-130">消息传递</span><span class="sxs-lookup"><span data-stu-id="463cc-130">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="463cc-131">聊天</span><span class="sxs-lookup"><span data-stu-id="463cc-131">Chat</span></span>

<span data-ttu-id="463cc-132">参与 Teams 中聊天列表内的对话的用户必须具有 Exchange Online（基于云）邮箱，这样管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="463cc-132">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="463cc-133">原因是聊天列表包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="463cc-133">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="463cc-134">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="463cc-134">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="463cc-135">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与 Teams 中聊天列表包含的对话。</span><span class="sxs-lookup"><span data-stu-id="463cc-135">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="463cc-136">但在这种情况下，这些对话中的内容不可搜索且不可进行法定保留，因为用户不具备基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="463cc-136">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="463cc-137">（有关详细信息，请参阅 [Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="463cc-137">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="463cc-138">Teams 聊天适用于 Microsoft Exchange 后端，因此 Exchange 消息传递限制适用于 Teams 中的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="463cc-138">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="463cc-139">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-139">Feature</span></span>  | <span data-ttu-id="463cc-140">最大限制</span><span class="sxs-lookup"><span data-stu-id="463cc-140">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="463cc-141">私人聊天中的人员数<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="463cc-141">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="463cc-142">100</span><span class="sxs-lookup"><span data-stu-id="463cc-142">100</span></span>    |
|<span data-ttu-id="463cc-143">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="463cc-143">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="463cc-144">10</span><span class="sxs-lookup"><span data-stu-id="463cc-144">10</span></span>     |

<span data-ttu-id="463cc-145"><sup>1</sup>如果参与某次聊天的人数超过 20 人，则禁用以下聊天功能：Outlook 自动答复和 Teams 状态消息、键入指示器、视频和音频呼叫、共享、已读回执。</span><span class="sxs-lookup"><span data-stu-id="463cc-145"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="463cc-146"><sup>2</sup>如果附件数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="463cc-146"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="463cc-147">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="463cc-147">Emailing a channel</span></span>

 <span data-ttu-id="463cc-148">如果用户想要在 Teams 向频道发送电子邮件，可使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="463cc-148">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="463cc-149">如果电子邮件是频道的一部分，则任何人都可答复此邮件来发起对话。</span><span class="sxs-lookup"><span data-stu-id="463cc-149">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="463cc-150">下面是有关向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="463cc-150">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="463cc-151">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-151">Feature</span></span>  | <span data-ttu-id="463cc-152">最大限制</span><span class="sxs-lookup"><span data-stu-id="463cc-152">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="463cc-153">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="463cc-153">Message size<sup>1<sup></span></span> | <span data-ttu-id="463cc-154">24 KB</span><span class="sxs-lookup"><span data-stu-id="463cc-154">24 KB</span></span> |
|<span data-ttu-id="463cc-155">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="463cc-155">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="463cc-156">20</span><span class="sxs-lookup"><span data-stu-id="463cc-156">20</span></span>     |
|<span data-ttu-id="463cc-157">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="463cc-157">Size of each file attachment</span></span> | <span data-ttu-id="463cc-158">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="463cc-158">Less than 10 MB</span></span> |
|<span data-ttu-id="463cc-159">内嵌图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="463cc-159">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="463cc-160">50</span><span class="sxs-lookup"><span data-stu-id="463cc-160">50</span></span>   |

<span data-ttu-id="463cc-161"><sup>1</sup>如果邮件数超过此限制，则会生成一封预览邮件，并要求用户通过所提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="463cc-161"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="463cc-162"><sup>2</sup>如果附件或图像数超过此限制，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="463cc-162"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="463cc-163">有关详细信息，请参阅 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="463cc-163">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="463cc-164">所有 Office 365 许可证中的邮件大小、文件附件数和内嵌图像限制均相同。</span><span class="sxs-lookup"><span data-stu-id="463cc-164">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="463cc-165">频道名称</span><span class="sxs-lookup"><span data-stu-id="463cc-165">Channel names</span></span>

<span data-ttu-id="463cc-166">频道名称不得包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="463cc-166">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="463cc-167">字符</span><span class="sxs-lookup"><span data-stu-id="463cc-167">Characters</span></span>     | <span data-ttu-id="463cc-168">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="463cc-168">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="463cc-169">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="463cc-169">&#124; ' " ..</span></span>        |
|<span data-ttu-id="463cc-170">下述范围内的字符</span><span class="sxs-lookup"><span data-stu-id="463cc-170">Characters in these ranges</span></span>    | <span data-ttu-id="463cc-171">0 到 1F</span><span class="sxs-lookup"><span data-stu-id="463cc-171">0 to 1F</span></span><br><span data-ttu-id="463cc-172">80 到 9F</span><span class="sxs-lookup"><span data-stu-id="463cc-172">80 to 9F</span></span>        |
|<span data-ttu-id="463cc-173">字词</span><span class="sxs-lookup"><span data-stu-id="463cc-173">Words</span></span>     | <span data-ttu-id="463cc-174">forms、CON、CONIN$, CONOUT$、PRN、AUX、NUL、COM1 到 COM9、LPT1 到 LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="463cc-174">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="463cc-175">此外，频道名称不得以下划线 (_) 或句点 (.) 开头，也不得以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="463cc-175">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="463cc-176">会议和通话</span><span class="sxs-lookup"><span data-stu-id="463cc-176">Meetings and calls</span></span>

|<span data-ttu-id="463cc-177">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-177">Feature</span></span>     | <span data-ttu-id="463cc-178">最大限制</span><span class="sxs-lookup"><span data-stu-id="463cc-178">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="463cc-179">会议中的人员数</span><span class="sxs-lookup"><span data-stu-id="463cc-179">Number of people in a meeting</span></span>  | <span data-ttu-id="463cc-180">250</span><span class="sxs-lookup"><span data-stu-id="463cc-180">250</span></span>    |
|<span data-ttu-id="463cc-181">PowerPoint 文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="463cc-181">Max PowerPoint File Size</span></span> | <span data-ttu-id="463cc-182">2GB</span><span class="sxs-lookup"><span data-stu-id="463cc-182">2GB</span></span>|

## <a name="teams-live-events"></a><span data-ttu-id="463cc-183">Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="463cc-183">Teams live events</span></span>

|<span data-ttu-id="463cc-184">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-184">Feature</span></span>     | <span data-ttu-id="463cc-185">最大限制</span><span class="sxs-lookup"><span data-stu-id="463cc-185">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="463cc-186">受众规模</span><span class="sxs-lookup"><span data-stu-id="463cc-186">Audience size</span></span> | <span data-ttu-id="463cc-187">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="463cc-187">10,000 attendees</span></span> |
|<span data-ttu-id="463cc-188">事件持续时间</span><span class="sxs-lookup"><span data-stu-id="463cc-188">Duration of event</span></span> | <span data-ttu-id="463cc-189">4 小时</span><span class="sxs-lookup"><span data-stu-id="463cc-189">4 hours</span></span> |
|<span data-ttu-id="463cc-190">Office 365 租户中的并发实时事件数</span><span class="sxs-lookup"><span data-stu-id="463cc-190">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="463cc-191">15</span><span class="sxs-lookup"><span data-stu-id="463cc-191">15</span></span> |

<span data-ttu-id="463cc-192">要详细了解实时事件以及 Teams 实时事件与 Skype 会议直播之间的比较情况，请转到 [Teams 实时事件和 Skype 会议直播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。</span><span class="sxs-lookup"><span data-stu-id="463cc-192">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="463cc-193">Outlook 中的状态</span><span class="sxs-lookup"><span data-stu-id="463cc-193">Presence in Outlook</span></span>

<span data-ttu-id="463cc-194">Outlook 2013 桌面版及更高版本支持 Outlook 中的 Teams 状态。</span><span class="sxs-lookup"><span data-stu-id="463cc-194">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="463cc-195">若要详细了解 Teams 中的状态，请参阅 [Teams 中的用户状态](presence-admins.md)。</span><span class="sxs-lookup"><span data-stu-id="463cc-195">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="463cc-196">存储空间</span><span class="sxs-lookup"><span data-stu-id="463cc-196">Storage</span></span>

<span data-ttu-id="463cc-197">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="463cc-197">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="463cc-198">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="463cc-198">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="463cc-199">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户有时无法在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="463cc-199">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="463cc-200">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="463cc-200">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="463cc-201">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="463cc-201">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="463cc-202">（有关详细信息，请参阅 [SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="463cc-202">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="463cc-203">由于 Teams 运行在 SharePoint Online 后端上来实现文件共享，因此 SharePoint 限制适用于团队中的“文件”部分。</span><span class="sxs-lookup"><span data-stu-id="463cc-203">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="463cc-204">下面是一些适用于 SharePoint Online 的存储限制。</span><span class="sxs-lookup"><span data-stu-id="463cc-204">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="463cc-205">功能</span><span class="sxs-lookup"><span data-stu-id="463cc-205">Feature</span></span>                 |<span data-ttu-id="463cc-206">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="463cc-206">Office 365 Business Essentials</span></span>  |<span data-ttu-id="463cc-207">Help and training</span><span class="sxs-lookup"><span data-stu-id="463cc-207">Office 365 Business Premium</span></span>   |<span data-ttu-id="463cc-208">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="463cc-208">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="463cc-209">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="463cc-209">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="463cc-210">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="463cc-210">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="463cc-211">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="463cc-211">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="463cc-212">存储空间</span><span class="sxs-lookup"><span data-stu-id="463cc-212">Storage</span></span>                 |<span data-ttu-id="463cc-213">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="463cc-213">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="463cc-214">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="463cc-214">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="463cc-215">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="463cc-215">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="463cc-216">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="463cc-216">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="463cc-217">每个组织 1 TB 存储空间，外加每个许可证购买的 10 GB 空间。</span><span class="sxs-lookup"><span data-stu-id="463cc-217">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="463cc-218">每个组织 1 TB 空间</span><span class="sxs-lookup"><span data-stu-id="463cc-218">1 TB per organization</span></span>           |
|<span data-ttu-id="463cc-219">Teams 文件存储空间</span><span class="sxs-lookup"><span data-stu-id="463cc-219">Storage for Teams Files</span></span> |<span data-ttu-id="463cc-220">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-220">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="463cc-221">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-221">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="463cc-222">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-222">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="463cc-223">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-223">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="463cc-224">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-224">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="463cc-225">每个网站集或组最多 25 TB 的空间</span><span class="sxs-lookup"><span data-stu-id="463cc-225">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="463cc-226">文件上传限制（每个文件）</span><span class="sxs-lookup"><span data-stu-id="463cc-226">File upload limit  (per file)</span></span>    |<span data-ttu-id="463cc-227">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-227">15 GB</span></span>    |<span data-ttu-id="463cc-228">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-228">15 GB</span></span>    |<span data-ttu-id="463cc-229">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-229">15 GB</span></span>    |<span data-ttu-id="463cc-230">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-230">15 GB</span></span>    |<span data-ttu-id="463cc-231">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-231">15 GB</span></span>    |<span data-ttu-id="463cc-232">15 GB</span><span class="sxs-lookup"><span data-stu-id="463cc-232">15 GB</span></span>    |

<span data-ttu-id="463cc-233">频道由 SharePoint Online 网站集中专为团队创建的文件夹提供支持，因此频道中的文件选项卡共同享有其所属的团队的存储空间限额。</span><span class="sxs-lookup"><span data-stu-id="463cc-233">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="463cc-234">有关详细信息，请参阅 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="463cc-234">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="463cc-235">联系人</span><span class="sxs-lookup"><span data-stu-id="463cc-235">Contacts</span></span>

<span data-ttu-id="463cc-236">Teams 使用下述联系人：</span><span class="sxs-lookup"><span data-stu-id="463cc-236">Teams uses these contacts:</span></span>

- <span data-ttu-id="463cc-237">组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="463cc-237">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="463cc-238">添加到用户的 Outlook 默认文件夹中的联系人</span><span class="sxs-lookup"><span data-stu-id="463cc-238">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="463cc-239">Teams 用户可与你所在组织的 Active Directory 中的任何人通信，并且可通过转到“**聊天**” > “**联系人**”或“**呼叫**” > “**联系人**”，将你组织的 Active Directory 中的任何人添加为联系人或添加到期联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="463cc-239">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="463cc-240">通过转到“**聊天**” > “**联系人**”，Teams 用户还可将你组织的 Active Directory 中未包含的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="463cc-240">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="463cc-241">浏览器</span><span class="sxs-lookup"><span data-stu-id="463cc-241">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="463cc-242">操作系统</span><span class="sxs-lookup"><span data-stu-id="463cc-242">Operating systems</span></span>

<span data-ttu-id="463cc-243">要了解操作系统要求，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="463cc-243">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
