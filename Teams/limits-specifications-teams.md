---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/10/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: 了解适用于 Microsoft 团队的限制、规范和其他要求。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30e3a9de6a832753b8480733528a0db44f4f143b
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857403"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="00ca3-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="00ca3-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="00ca3-104">本文介绍适用于团队的一些限制、规范和其他要求。</span><span class="sxs-lookup"><span data-stu-id="00ca3-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="00ca3-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="00ca3-105">Teams and channels</span></span> 

|<span data-ttu-id="00ca3-106">功能</span><span class="sxs-lookup"><span data-stu-id="00ca3-106">Feature</span></span>    | <span data-ttu-id="00ca3-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="00ca3-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="00ca3-108">用户可以创建的团队数</span><span class="sxs-lookup"><span data-stu-id="00ca3-108">Number of teams a user can create</span></span> | <span data-ttu-id="00ca3-109">受250对象限制的限制&sup1;</span><span class="sxs-lookup"><span data-stu-id="00ca3-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="00ca3-110">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="00ca3-110">Number of members in a team</span></span> | <span data-ttu-id="00ca3-111">5,000</span><span class="sxs-lookup"><span data-stu-id="00ca3-111">5,000</span></span>       |
|<span data-ttu-id="00ca3-112">租户中允许的组织范围内的团队数</span><span class="sxs-lookup"><span data-stu-id="00ca3-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="00ca3-113">5</span><span class="sxs-lookup"><span data-stu-id="00ca3-113">5</span></span>     |
|<span data-ttu-id="00ca3-114">[组织范围团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="00ca3-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="00ca3-115">5,000</span><span class="sxs-lookup"><span data-stu-id="00ca3-115">5,000</span></span>       |
|<span data-ttu-id="00ca3-116">全局管理员可以创建的团队数</span><span class="sxs-lookup"><span data-stu-id="00ca3-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="00ca3-117">500000</span><span class="sxs-lookup"><span data-stu-id="00ca3-117">500,000</span></span>   |
|<span data-ttu-id="00ca3-118">Office 365 租户可以拥有的团队数</span><span class="sxs-lookup"><span data-stu-id="00ca3-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="00ca3-119">500000&sup2;</span><span class="sxs-lookup"><span data-stu-id="00ca3-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="00ca3-120">每个团队的频道数</span><span class="sxs-lookup"><span data-stu-id="00ca3-120">Number of channels per team</span></span>    | <span data-ttu-id="00ca3-121">200 (包括删除的频道) &sup3;</span><span class="sxs-lookup"><span data-stu-id="00ca3-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="00ca3-122">&sup1;Azure Active Directory 中的任何目录对象都将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="00ca3-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="00ca3-123">全局管理员不受此限制限制, 与使用[应用程序权限](https://docs.microsoft.com/graph/permissions-reference)调用 Microsoft Graph 的应用一样。</span><span class="sxs-lookup"><span data-stu-id="00ca3-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="00ca3-124">&sup2;此限制包括已存档的团队。</span><span class="sxs-lookup"><span data-stu-id="00ca3-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="00ca3-125">&sup3; 删除的频道可以在30天内恢复。</span><span class="sxs-lookup"><span data-stu-id="00ca3-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="00ca3-126">在30天内, 已删除的频道将继续按每个团队限额的200频道计入。</span><span class="sxs-lookup"><span data-stu-id="00ca3-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="00ca3-127">30天后, 删除的频道及其内容将被永久删除, 频道不再按每个团队的每个团队限额的200频道计数。</span><span class="sxs-lookup"><span data-stu-id="00ca3-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="00ca3-128">会议和通话</span><span class="sxs-lookup"><span data-stu-id="00ca3-128">Meetings and calls</span></span> 

|<span data-ttu-id="00ca3-129">功能</span><span class="sxs-lookup"><span data-stu-id="00ca3-129">Feature</span></span>     | <span data-ttu-id="00ca3-130">最大限制</span><span class="sxs-lookup"><span data-stu-id="00ca3-130">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="00ca3-131">会议中的人员数</span><span class="sxs-lookup"><span data-stu-id="00ca3-131">Number of people in a meeting</span></span>  | <span data-ttu-id="00ca3-132">250</span><span class="sxs-lookup"><span data-stu-id="00ca3-132">250</span></span>    |

## <a name="storage"></a><span data-ttu-id="00ca3-133">Storage</span><span class="sxs-lookup"><span data-stu-id="00ca3-133">Storage</span></span>

<span data-ttu-id="00ca3-134">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="00ca3-134">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="00ca3-135">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="00ca3-135">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="00ca3-136">如果你的租户中未启用 SharePoint Online, Microsoft 团队用户将无法始终共享团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="00ca3-136">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="00ca3-137">私人聊天中的用户也无法共享文件, 因为 OneDrive for business (绑定到 SharePoint 许可证) 是该功能所必需的。</span><span class="sxs-lookup"><span data-stu-id="00ca3-137">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="00ca3-138">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="00ca3-138">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="00ca3-139">(有关详细信息, 请参阅[SharePoint Online 和 OneDrive For Business 如何与 Microsoft 团队交互](sharepoint-onedrive-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="00ca3-139">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="00ca3-140">由于团队运行于 SharePoint Online 后端进行文件共享, 因此 SharePoint 限制适用于团队中的 "文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="00ca3-140">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="00ca3-141">下面是 SharePoint Online 适用的存储空间限制。</span><span class="sxs-lookup"><span data-stu-id="00ca3-141">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="00ca3-142">功能</span><span class="sxs-lookup"><span data-stu-id="00ca3-142">Feature</span></span>                 |<span data-ttu-id="00ca3-143">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="00ca3-143">Office 365 Business Essentials</span></span>  |<span data-ttu-id="00ca3-144">Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="00ca3-144">Office 365 Business Premium</span></span>   |<span data-ttu-id="00ca3-145">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="00ca3-145">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="00ca3-146">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="00ca3-146">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="00ca3-147">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="00ca3-147">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="00ca3-148">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="00ca3-148">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="00ca3-149">Storage</span><span class="sxs-lookup"><span data-stu-id="00ca3-149">Storage</span></span>                 |<span data-ttu-id="00ca3-150">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-150">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="00ca3-151">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-151">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="00ca3-152">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-152">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="00ca3-153">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-153">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="00ca3-154">每个组织 1 TB 加上购买的每个许可证 10 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-154">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="00ca3-155">每个组织 1 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-155">1 TB per organization</span></span>           |
|<span data-ttu-id="00ca3-156">团队文件的存储空间</span><span class="sxs-lookup"><span data-stu-id="00ca3-156">Storage for Teams Files</span></span> |<span data-ttu-id="00ca3-157">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-157">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="00ca3-158">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-158">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="00ca3-159">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-159">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="00ca3-160">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-160">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="00ca3-161">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-161">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="00ca3-162">每个网站集或组最多 25 TB</span><span class="sxs-lookup"><span data-stu-id="00ca3-162">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="00ca3-163">文件上载限制 (每个文件)</span><span class="sxs-lookup"><span data-stu-id="00ca3-163">File upload limit  (per file)</span></span>    |<span data-ttu-id="00ca3-164">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-164">15 GB</span></span>    |<span data-ttu-id="00ca3-165">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-165">15 GB</span></span>    |<span data-ttu-id="00ca3-166">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-166">15 GB</span></span>    |<span data-ttu-id="00ca3-167">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-167">15 GB</span></span>    |<span data-ttu-id="00ca3-168">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-168">15 GB</span></span>    |<span data-ttu-id="00ca3-169">15 GB</span><span class="sxs-lookup"><span data-stu-id="00ca3-169">15 GB</span></span>    |

<span data-ttu-id="00ca3-170">频道由为团队创建的 SharePoint Online 网站集内的文件夹提供支持, 因此频道内的文件选项卡共享其所属团队的存储限制。</span><span class="sxs-lookup"><span data-stu-id="00ca3-170">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="00ca3-171">有关详细信息, 请参阅[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="00ca3-171">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="messaging"></a><span data-ttu-id="00ca3-172">消息</span><span class="sxs-lookup"><span data-stu-id="00ca3-172">Messaging</span></span>

<span data-ttu-id="00ca3-173">参与 Microsoft 团队中的聊天列表的对话的用户必须具有 Exchange Online (基于云的) 邮箱, 管理员才能搜索聊天对话。</span><span class="sxs-lookup"><span data-stu-id="00ca3-173">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="00ca3-174">这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="00ca3-174">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="00ca3-175">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="00ca3-175">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="00ca3-176">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="00ca3-176">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="00ca3-177">但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="00ca3-177">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="00ca3-178">(有关详细信息, 请参阅[Exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)。)</span><span class="sxs-lookup"><span data-stu-id="00ca3-178">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="00ca3-179">Microsoft 团队聊天功能适用于 Microsoft Exchange 后端, 因此你可以将 Exchange 邮件限制应用于 Microsoft 团队内的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="00ca3-179">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="00ca3-180">如果用户想要向团队中的频道发送电子邮件, 他们将使用频道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="00ca3-180">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="00ca3-181">一旦电子邮件是频道的一部分, 任何人都可以回复它以启动对话。</span><span class="sxs-lookup"><span data-stu-id="00ca3-181">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="00ca3-182">下面是向频道发送电子邮件的一些适用限制。</span><span class="sxs-lookup"><span data-stu-id="00ca3-182">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="00ca3-183">功能</span><span class="sxs-lookup"><span data-stu-id="00ca3-183">Feature</span></span>  | <span data-ttu-id="00ca3-184">最大限制</span><span class="sxs-lookup"><span data-stu-id="00ca3-184">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="00ca3-185">私人聊天中的用户数</span><span class="sxs-lookup"><span data-stu-id="00ca3-185">Number of people in a private chat</span></span>  | <span data-ttu-id="00ca3-186">100</span><span class="sxs-lookup"><span data-stu-id="00ca3-186">100</span></span>    |
|<span data-ttu-id="00ca3-187">邮件大小&dagger;</span><span class="sxs-lookup"><span data-stu-id="00ca3-187">Message size &dagger;</span></span>  |<span data-ttu-id="00ca3-188">25 KB</span><span class="sxs-lookup"><span data-stu-id="00ca3-188">25 KB</span></span>   |
|<span data-ttu-id="00ca3-189">文件附件数&Dagger;</span><span class="sxs-lookup"><span data-stu-id="00ca3-189">Number of file attachments &Dagger;</span></span>  |<span data-ttu-id="00ca3-190">10</span><span class="sxs-lookup"><span data-stu-id="00ca3-190">10</span></span>     |
|<span data-ttu-id="00ca3-191">内联图像的数量&Dagger;</span><span class="sxs-lookup"><span data-stu-id="00ca3-191">Number of inline images &Dagger;</span></span> |<span data-ttu-id="00ca3-192">50</span><span class="sxs-lookup"><span data-stu-id="00ca3-192">50</span></span>   |

<span data-ttu-id="00ca3-193">&dagger;如果邮件超过此限制, 将生成预览消息, 要求用户从提供的链接查看/下载原始电子邮件。</span><span class="sxs-lookup"><span data-stu-id="00ca3-193">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="00ca3-194">&Dagger;如果附件或图像的数量超过此限制, 将不会处理邮件, 并且会将 NDR 电子邮件发送回发送错误的发件人。</span><span class="sxs-lookup"><span data-stu-id="00ca3-194">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR email will be sent back to the sender notifying them of the error.</span></span>

> [!NOTE]
> <span data-ttu-id="00ca3-195">邮件大小、文件附件和嵌入式图像限制在所有 Office 365 许可证中的大小相同。</span><span class="sxs-lookup"><span data-stu-id="00ca3-195">The message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

<span data-ttu-id="00ca3-196">有关详细信息, 请参阅[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="00ca3-196">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

## <a name="browsers"></a><span data-ttu-id="00ca3-197">上级</span><span class="sxs-lookup"><span data-stu-id="00ca3-197">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="00ca3-198">操作系统</span><span class="sxs-lookup"><span data-stu-id="00ca3-198">Operating systems</span></span>

<span data-ttu-id="00ca3-199">有关操作系统要求的信息, 请参阅[获取 Microsoft 团队客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="00ca3-199">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
