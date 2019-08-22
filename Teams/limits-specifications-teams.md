---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: 了解适用于 Microsoft 团队的限制、规范和其他要求。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854c6beeccdae6286bc609a226a49b15de1114e6
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "36492999"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="dc6b6-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="dc6b6-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="dc6b6-104">本文介绍适用于团队的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="dc6b6-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="dc6b6-105">Teams and channels</span></span>

|<span data-ttu-id="dc6b6-106">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-106">Feature</span></span>    | <span data-ttu-id="dc6b6-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="dc6b6-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="dc6b6-108">用户可以创建的团队数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-108">Number of teams a user can create</span></span> | <span data-ttu-id="dc6b6-109">受250对象限制的限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="dc6b6-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="dc6b6-110">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-110">Number of members in a team</span></span> | <span data-ttu-id="dc6b6-111">5,000</span><span class="sxs-lookup"><span data-stu-id="dc6b6-111">5,000</span></span>       |
|<span data-ttu-id="dc6b6-112">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="dc6b6-113">5</span><span class="sxs-lookup"><span data-stu-id="dc6b6-113">5</span></span>     |
|<span data-ttu-id="dc6b6-114">[组织范围团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="dc6b6-115">5,000</span><span class="sxs-lookup"><span data-stu-id="dc6b6-115">5,000</span></span>       |
|<span data-ttu-id="dc6b6-116">全局管理员可以创建的团队数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="dc6b6-117">500000</span><span class="sxs-lookup"><span data-stu-id="dc6b6-117">500,000</span></span>   |
|<span data-ttu-id="dc6b6-118">Office 365 租户可以拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="dc6b6-119">500000&sup2;</span><span class="sxs-lookup"><span data-stu-id="dc6b6-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="dc6b6-120">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-120">Number of channels per team</span></span>    | <span data-ttu-id="dc6b6-121">200 (包括删除的频道) &sup3;</span><span class="sxs-lookup"><span data-stu-id="dc6b6-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="dc6b6-122">&sup1;Azure Active Directory 中的任何目录对象都将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="dc6b6-123">全局管理员不受此限制限制, 与使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="dc6b6-124">&sup2;此限制包括已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="dc6b6-125">&sup3; 删除的频道可以在30天内恢复。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="dc6b6-126">在30天内, 已删除的频道将继续按每个团队限额的200频道计入。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="dc6b6-127">30天后, 删除的频道及其内容将被永久删除, 频道不再按每个团队的每个团队限额的200频道计数。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="dc6b6-128">消息</span><span class="sxs-lookup"><span data-stu-id="dc6b6-128">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="dc6b6-129">聊天</span><span class="sxs-lookup"><span data-stu-id="dc6b6-129">Chat</span></span>

<span data-ttu-id="dc6b6-130">参与团队对话的用户在团队中必须具有 Exchange Online (基于云的) 邮箱, 管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-130">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="dc6b6-131">这是因为聊天列表中包含的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-131">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="dc6b6-132">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-132">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="dc6b6-133">例如, 在 Exchange 混合部署中, 具有本地邮箱的用户可能能够参与属于团队中的聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-133">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="dc6b6-134">但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-134">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="dc6b6-135">(有关详细信息, 请参阅[Exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="dc6b6-135">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="dc6b6-136">团队聊天适用于 Microsoft Exchange 后端, 因此 Exchange 消息限制适用于团队内的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-136">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="dc6b6-137">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-137">Feature</span></span>  | <span data-ttu-id="dc6b6-138">最大限制</span><span class="sxs-lookup"><span data-stu-id="dc6b6-138">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="dc6b6-139">私人聊天<sup>1</sup>中的用户数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-139">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="dc6b6-140">100</span><span class="sxs-lookup"><span data-stu-id="dc6b6-140">100</span></span>    |
|<span data-ttu-id="dc6b6-141">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dc6b6-141">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="dc6b6-142">10</span><span class="sxs-lookup"><span data-stu-id="dc6b6-142">10</span></span>     |

<span data-ttu-id="dc6b6-143"><sup>1</sup>如果您的聊天中有20多个用户, 则关闭以下聊天功能: Outlook 自动答复和团队状态消息;键入指示器;视频和音频通话;共享已读回执。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-143"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="dc6b6-144"><sup>2</sup>如果附件数超过此限制, 您将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-144"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="dc6b6-145">向频道发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="dc6b6-145">Emailing a channel</span></span>

 <span data-ttu-id="dc6b6-146">如果用户想要向团队中的频道发送电子邮件, 他们将使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-146">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="dc6b6-147">当电子邮件是频道的一部分时, 任何人都可以回复它以启动对话。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-147">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="dc6b6-148">下面是向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-148">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="dc6b6-149">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-149">Feature</span></span>  | <span data-ttu-id="dc6b6-150">最大限制</span><span class="sxs-lookup"><span data-stu-id="dc6b6-150">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="dc6b6-151">邮件大小<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="dc6b6-151">Message size<sup>1<sup></span></span> | <span data-ttu-id="dc6b6-152">24 KB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-152">24 KB</span></span> |
|<span data-ttu-id="dc6b6-153">文件附件数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dc6b6-153">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="dc6b6-154">名</span><span class="sxs-lookup"><span data-stu-id="dc6b6-154">20</span></span>     |
|<span data-ttu-id="dc6b6-155">每个文件附件的大小</span><span class="sxs-lookup"><span data-stu-id="dc6b6-155">Size of each file attachment</span></span> | <span data-ttu-id="dc6b6-156">小于 10 MB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-156">Less than 10 MB</span></span> |
|<span data-ttu-id="dc6b6-157">内联图像数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dc6b6-157">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="dc6b6-158">50</span><span class="sxs-lookup"><span data-stu-id="dc6b6-158">50</span></span>   |

<span data-ttu-id="dc6b6-159"><sup>1</sup>如果邮件超过此限制, 将生成预览邮件, 并要求用户从提供的链接下载和查看原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-159"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="dc6b6-160"><sup>2</sup>如果附件或图像的数量超过此限制, 您将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-160"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="dc6b6-161">有关详细信息, 请参阅[Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-161">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="dc6b6-162">邮件大小、文件附件和嵌入式图像限制在所有 Office 365 许可证中是相同的。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-162">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="dc6b6-163">频道名称</span><span class="sxs-lookup"><span data-stu-id="dc6b6-163">Channel names</span></span>

<span data-ttu-id="dc6b6-164">频道名称不能包含以下字符或字词。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-164">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="dc6b6-165">字符</span><span class="sxs-lookup"><span data-stu-id="dc6b6-165">Characters</span></span>     | <span data-ttu-id="dc6b6-166">~ #% & \* {} +/\:  < > ？</span><span class="sxs-lookup"><span data-stu-id="dc6b6-166">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="dc6b6-167">&#124; "" .。。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-167">&#124; ' " ..</span></span>        |
|<span data-ttu-id="dc6b6-168">这些区域中的字符数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-168">Characters in these ranges</span></span>    | <span data-ttu-id="dc6b6-169">0到1F</span><span class="sxs-lookup"><span data-stu-id="dc6b6-169">0 to 1F</span></span><br><span data-ttu-id="dc6b6-170">80到9F</span><span class="sxs-lookup"><span data-stu-id="dc6b6-170">80 to 9F</span></span>        |
|<span data-ttu-id="dc6b6-171">字</span><span class="sxs-lookup"><span data-stu-id="dc6b6-171">Words</span></span>     | <span data-ttu-id="dc6b6-172">forms、CON、CONIN $、CONOUT $、PRN、AUX、NUL、COM1 到 COM9、LPT9、、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="dc6b6-172">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="dc6b6-173">频道名称也不能以下划线 (_) 或句号 (.) 开头, 或以句点 (.) 结尾。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-173">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="dc6b6-174">会议和通话</span><span class="sxs-lookup"><span data-stu-id="dc6b6-174">Meetings and calls</span></span>

|<span data-ttu-id="dc6b6-175">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-175">Feature</span></span>     | <span data-ttu-id="dc6b6-176">最大限制</span><span class="sxs-lookup"><span data-stu-id="dc6b6-176">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="dc6b6-177">会议中的人员数</span><span class="sxs-lookup"><span data-stu-id="dc6b6-177">Number of people in a meeting</span></span>  | <span data-ttu-id="dc6b6-178">250</span><span class="sxs-lookup"><span data-stu-id="dc6b6-178">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="dc6b6-179">团队活动事件</span><span class="sxs-lookup"><span data-stu-id="dc6b6-179">Teams live events</span></span>

|<span data-ttu-id="dc6b6-180">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-180">Feature</span></span>     | <span data-ttu-id="dc6b6-181">最大限制</span><span class="sxs-lookup"><span data-stu-id="dc6b6-181">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="dc6b6-182">受众大小</span><span class="sxs-lookup"><span data-stu-id="dc6b6-182">Audience size</span></span> | <span data-ttu-id="dc6b6-183">10000与会者</span><span class="sxs-lookup"><span data-stu-id="dc6b6-183">10,000 attendees</span></span> |
|<span data-ttu-id="dc6b6-184">事件的持续时间</span><span class="sxs-lookup"><span data-stu-id="dc6b6-184">Duration of event</span></span> | <span data-ttu-id="dc6b6-185">4小时</span><span class="sxs-lookup"><span data-stu-id="dc6b6-185">4 hours</span></span> |
|<span data-ttu-id="dc6b6-186">Office 365 租户中的并发实时事件</span><span class="sxs-lookup"><span data-stu-id="dc6b6-186">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="dc6b6-187">岁</span><span class="sxs-lookup"><span data-stu-id="dc6b6-187">15</span></span> |

<span data-ttu-id="dc6b6-188">有关实时事件和团队实时事件与 Skype 会议直播比较的详细信息, 请转到[团队实时事件和 Skype 会议](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)直播。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-188">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="dc6b6-189">Storage</span><span class="sxs-lookup"><span data-stu-id="dc6b6-189">Storage</span></span>

<span data-ttu-id="dc6b6-190">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-190">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="dc6b6-191">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-191">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="dc6b6-192">如果你的租户中未启用 SharePoint Online, Microsoft 团队用户将无法始终共享团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-192">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="dc6b6-193">私人聊天中的用户也无法共享文件, 因为 OneDrive for business (绑定到 SharePoint 许可证) 是该功能所必需的。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-193">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="dc6b6-194">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-194">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="dc6b6-195">(有关详细信息, 请参阅[SharePoint Online 和 OneDrive For Business 如何与 Microsoft 团队交互](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="dc6b6-195">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="dc6b6-196">由于团队运行于 SharePoint Online 后端进行文件共享, 因此 SharePoint 限制适用于团队中的 "文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-196">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="dc6b6-197">下面是 SharePoint Online 适用的存储空间限制。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-197">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="dc6b6-198">功能</span><span class="sxs-lookup"><span data-stu-id="dc6b6-198">Feature</span></span>                 |<span data-ttu-id="dc6b6-199">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="dc6b6-199">Office 365 Business Essentials</span></span>  |<span data-ttu-id="dc6b6-200">Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="dc6b6-200">Office 365 Business Premium</span></span>   |<span data-ttu-id="dc6b6-201">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="dc6b6-201">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="dc6b6-202">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="dc6b6-202">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="dc6b6-203">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="dc6b6-203">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="dc6b6-204">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="dc6b6-204">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="dc6b6-205">Storage</span><span class="sxs-lookup"><span data-stu-id="dc6b6-205">Storage</span></span>                 |<span data-ttu-id="dc6b6-206">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-206">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="dc6b6-207">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-207">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="dc6b6-208">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-208">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="dc6b6-209">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-209">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="dc6b6-210">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-210">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="dc6b6-211">每个组织 1 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-211">1 TB per organization</span></span>           |
|<span data-ttu-id="dc6b6-212">团队文件的存储空间</span><span class="sxs-lookup"><span data-stu-id="dc6b6-212">Storage for Teams Files</span></span> |<span data-ttu-id="dc6b6-213">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-213">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="dc6b6-214">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-214">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="dc6b6-215">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-215">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="dc6b6-216">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-216">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="dc6b6-217">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-217">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="dc6b6-218">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-218">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="dc6b6-219">文件上载限制 (每个文件)</span><span class="sxs-lookup"><span data-stu-id="dc6b6-219">File upload limit  (per file)</span></span>    |<span data-ttu-id="dc6b6-220">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-220">15 GB</span></span>    |<span data-ttu-id="dc6b6-221">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-221">15 GB</span></span>    |<span data-ttu-id="dc6b6-222">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-222">15 GB</span></span>    |<span data-ttu-id="dc6b6-223">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-223">15 GB</span></span>    |<span data-ttu-id="dc6b6-224">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-224">15 GB</span></span>    |<span data-ttu-id="dc6b6-225">15 GB</span><span class="sxs-lookup"><span data-stu-id="dc6b6-225">15 GB</span></span>    |

<span data-ttu-id="dc6b6-226">频道由为团队创建的 SharePoint Online 网站集内的文件夹提供支持, 因此频道内的文件选项卡共享其所属团队的存储限制。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-226">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="dc6b6-227">有关详细信息, 请参阅[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-227">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="dc6b6-228">联系人</span><span class="sxs-lookup"><span data-stu-id="dc6b6-228">Contacts</span></span>

<span data-ttu-id="dc6b6-229">团队使用以下联系人:</span><span class="sxs-lookup"><span data-stu-id="dc6b6-229">Teams uses these contacts:</span></span>

- <span data-ttu-id="dc6b6-230">您的组织的 Active Directory 中的联系人</span><span class="sxs-lookup"><span data-stu-id="dc6b6-230">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="dc6b6-231">添加到用户的 Outlook 默认文件夹的联系人</span><span class="sxs-lookup"><span data-stu-id="dc6b6-231">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="dc6b6-232">团队用户可以与组织的 active directory 中的任何人进行通信, 并可以通过**聊天** > **联系人**或**呼叫** > 将组织的 Active directory 中的任何人添加为联系人和联系人列表。**联系人**。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-232">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="dc6b6-233">团队用户也可以通过**呼叫** > **联系人**将不在组织的 Active Directory 中的人员添加为联系人。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-233">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="dc6b6-234">上级</span><span class="sxs-lookup"><span data-stu-id="dc6b6-234">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="dc6b6-235">操作系统</span><span class="sxs-lookup"><span data-stu-id="dc6b6-235">Operating systems</span></span>

<span data-ttu-id="dc6b6-236">有关操作系统要求的信息, 请参阅[获取 Microsoft 团队客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="dc6b6-236">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
