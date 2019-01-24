---
title: Microsoft Teams 的限制和规范
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: 了解这些限制、 规格和适用于 Microsoft 团队的其他要求。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 957d1d3b708d0d35c2743b9382af3ad12aba6632
ms.sourcegitcommit: 38f225d59929a08923e801f334fea7b3d28f537d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "29454573"
---
<a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="f852a-103">Microsoft Teams 的限制和规范</span><span class="sxs-lookup"><span data-stu-id="f852a-103">Limits and specifications for Microsoft Teams</span></span>
=============================================

<span data-ttu-id="f852a-104">本文介绍一些限制、 规格和适用于 Microsoft 团队的其他要求。</span><span class="sxs-lookup"><span data-stu-id="f852a-104">This article describes some of the limits, specifications, and other requirements that apply to Microsoft Teams.</span></span> 

<a name="teams-and-channels"></a><span data-ttu-id="f852a-105">团队和频道</span><span class="sxs-lookup"><span data-stu-id="f852a-105">Teams and channels</span></span> 
------------------

|<span data-ttu-id="f852a-106">功能</span><span class="sxs-lookup"><span data-stu-id="f852a-106">Feature</span></span>    | <span data-ttu-id="f852a-107">最大限制</span><span class="sxs-lookup"><span data-stu-id="f852a-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="f852a-108">用户可创建的团队数量</span><span class="sxs-lookup"><span data-stu-id="f852a-108">Number of teams a user can create</span></span> | <span data-ttu-id="f852a-109">受到 250 对象 limit&sup1;</span><span class="sxs-lookup"><span data-stu-id="f852a-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="f852a-110">团队中的成员数</span><span class="sxs-lookup"><span data-stu-id="f852a-110">Number of members in a team</span></span> | <span data-ttu-id="f852a-111">$2,500</span><span class="sxs-lookup"><span data-stu-id="f852a-111">2,500</span></span>       |
|<span data-ttu-id="f852a-112">[组织范围团队](create-an-org-wide-team.md)中的成员数</span><span class="sxs-lookup"><span data-stu-id="f852a-112">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="f852a-113">$2,500</span><span class="sxs-lookup"><span data-stu-id="f852a-113">2,500</span></span>       |
|<span data-ttu-id="f852a-114">全局管理员可以创建的团队数量</span><span class="sxs-lookup"><span data-stu-id="f852a-114">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="f852a-115">500,000 个</span><span class="sxs-lookup"><span data-stu-id="f852a-115">500,000</span></span>   |
|<span data-ttu-id="f852a-116">Office 365 租户可以具有的团队数量</span><span class="sxs-lookup"><span data-stu-id="f852a-116">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="f852a-117">500,000 个</span><span class="sxs-lookup"><span data-stu-id="f852a-117">500,000</span></span>     |
|<span data-ttu-id="f852a-118">每个工作组的通道数</span><span class="sxs-lookup"><span data-stu-id="f852a-118">Number of channels per team</span></span>    | <span data-ttu-id="f852a-119">200 （包括已删除的通道）</span><span class="sxs-lookup"><span data-stu-id="f852a-119">200 (includes deleted channels)</span></span>         |

<span data-ttu-id="f852a-120">&sup1;Azure Active Directory 中的任何目录对象计算达到此限制。</span><span class="sxs-lookup"><span data-stu-id="f852a-120">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span>

<a name="meetings-and-calls"></a><span data-ttu-id="f852a-121">会议和呼叫</span><span class="sxs-lookup"><span data-stu-id="f852a-121">Meetings and calls</span></span> 
------------------

|<span data-ttu-id="f852a-122">功能</span><span class="sxs-lookup"><span data-stu-id="f852a-122">Feature</span></span>     | <span data-ttu-id="f852a-123">最大限制</span><span class="sxs-lookup"><span data-stu-id="f852a-123">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="f852a-124">在会议中的人员数量</span><span class="sxs-lookup"><span data-stu-id="f852a-124">Number of people in a meeting</span></span>  | <span data-ttu-id="f852a-125">250</span><span class="sxs-lookup"><span data-stu-id="f852a-125">250</span></span>    |
|<span data-ttu-id="f852a-126">私人聊天中的人数</span><span class="sxs-lookup"><span data-stu-id="f852a-126">Number of people in a private chat</span></span>  | <span data-ttu-id="f852a-127">50%</span><span class="sxs-lookup"><span data-stu-id="f852a-127">50</span></span>    |

> [!IMPORTANT]
> <span data-ttu-id="f852a-128">默认情况下 AllowChannelMeetingScheduling 和 AllowPrivateMeetingScheduling 不包含种带内设置相对于 TeamsMeetingPolicy 如网亭工作者不会安排团队会议的功能。</span><span class="sxs-lookup"><span data-stu-id="f852a-128">Kiosk workers will not have the ability to schedule Teams Meetings, as by default, AllowChannelMeetingScheduling and AllowPrivateMeetingScheduling are not included with inband provisioning in respect to the TeamsMeetingPolicy.</span></span> <span data-ttu-id="f852a-129">这仅适用于网亭工作者。</span><span class="sxs-lookup"><span data-stu-id="f852a-129">This only applies to Kiosk workers.</span></span> 

<a name="storage"></a><span data-ttu-id="f852a-130"> 存储</span><span class="sxs-lookup"><span data-stu-id="f852a-130">Storage</span></span>
-------

<span data-ttu-id="f852a-131">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="f852a-131">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="f852a-132">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="f852a-132">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="f852a-133">如果你的租户中未启用 SharePoint Online，则 Microsoft Teams 用户不是总能够在团队中共享文件。</span><span class="sxs-lookup"><span data-stu-id="f852a-133">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="f852a-134">此外，由于该功能需要 OneDrive for Business（它与 SharePoint 许可证关联），因此私人聊天中的用户无法共享文件。</span><span class="sxs-lookup"><span data-stu-id="f852a-134">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="f852a-135">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="f852a-135">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="f852a-136">（有关详细信息，请参阅[如何 SharePoint Online 和 OneDrive for Business 交互的 Microsoft 团队](sharepoint-onedrive-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="f852a-136">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="f852a-137">工作组在文件共享的 SharePoint Online 后端上运行，因为 SharePoint 限制应用于工作组中文件部分。</span><span class="sxs-lookup"><span data-stu-id="f852a-137">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="f852a-138">以下是 SharePoint Online 的适用的存储限制。</span><span class="sxs-lookup"><span data-stu-id="f852a-138">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="f852a-139">功能</span><span class="sxs-lookup"><span data-stu-id="f852a-139">Feature</span></span>                 |<span data-ttu-id="f852a-140">Office 365 商业协作版</span><span class="sxs-lookup"><span data-stu-id="f852a-140">Office 365 Business Essentials</span></span>  |<span data-ttu-id="f852a-141">Office 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="f852a-141">Office 365 Business Premium</span></span>   |<span data-ttu-id="f852a-142">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="f852a-142">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="f852a-143">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="f852a-143">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="f852a-144">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f852a-144">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="f852a-145">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="f852a-145">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="f852a-146"> 存储</span><span class="sxs-lookup"><span data-stu-id="f852a-146">Storage</span></span>                 |<span data-ttu-id="f852a-147">1 TB 每个组织以及每个许可证购买 10 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-147">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f852a-148">1 TB 每个组织以及每个许可证购买 10 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-148">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f852a-149">1 TB 每个组织以及每个许可证购买 10 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-149">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="f852a-150">1 TB 每个组织以及每个许可证购买 10 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-150">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="f852a-151">1 TB 每个组织以及每个许可证购买 10 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-151">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="f852a-152">每个组织的 1 TB</span><span class="sxs-lookup"><span data-stu-id="f852a-152">1 TB per organization</span></span>           |
|<span data-ttu-id="f852a-153">团队文件存储</span><span class="sxs-lookup"><span data-stu-id="f852a-153">Storage for Teams Files</span></span> |<span data-ttu-id="f852a-154">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-154">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f852a-155">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-155">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f852a-156">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-156">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f852a-157">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-157">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f852a-158">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-158">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="f852a-159">最多 25 TB 每个网站集或组</span><span class="sxs-lookup"><span data-stu-id="f852a-159">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="f852a-160">文件上载限制</span><span class="sxs-lookup"><span data-stu-id="f852a-160">File upload limit</span></span>       |<span data-ttu-id="f852a-161">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-161">15 GB</span></span>    |<span data-ttu-id="f852a-162">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-162">15 GB</span></span>    |<span data-ttu-id="f852a-163">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-163">15 GB</span></span>    |<span data-ttu-id="f852a-164">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-164">15 GB</span></span>    |<span data-ttu-id="f852a-165">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-165">15 GB</span></span>    |<span data-ttu-id="f852a-166">15 GB</span><span class="sxs-lookup"><span data-stu-id="f852a-166">15 GB</span></span>    |

<span data-ttu-id="f852a-167">团队中的每个文件选项卡上 SharePoint Online 的后端，运行，因此以上的存储限制适用于团队中每个通道。</span><span class="sxs-lookup"><span data-stu-id="f852a-167">Each Files tab in Teams runs on a SharePoint Online backend, so the storage limits above apply to each Channel within a Team.</span></span>

<span data-ttu-id="f852a-168">有关详细信息，请参阅[SharePoint Online 的限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。</span><span class="sxs-lookup"><span data-stu-id="f852a-168">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

<a name="messaging"></a><span data-ttu-id="f852a-169">消息</span><span class="sxs-lookup"><span data-stu-id="f852a-169">Messaging</span></span>
---------

<span data-ttu-id="f852a-170">参与对话的一部分的 Microsoft 团队中的聊天列表中的用户必须拥有管理员可以搜索聊天 Exchange Online （基于云的） 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f852a-170">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="f852a-171">这是因为属于聊天列表的对话存储在聊天参与者的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f852a-171">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="f852a-172">如果聊天参与者没有 Exchange Online 邮箱，管理员将无法搜索聊天对话，也无法将聊天对话中的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="f852a-172">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="f852a-173">例如，在 Exchange 混合部署中，具有本地邮箱的用户也许能参与属于 Microsoft Teams 中聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="f852a-173">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="f852a-174">但是，在这种情况下，由于用户没有基于云的邮箱，这些对话中的内容不可搜索，也不可置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="f852a-174">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="f852a-175">（有关详细信息，请参阅[如何 Exchange 和 Microsoft 团队进行交互](exchange-teams-interact.md)。）</span><span class="sxs-lookup"><span data-stu-id="f852a-175">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="f852a-176">Microsoft 团队聊天函数处理 Microsoft Exchange 后端，以便您可以将应用 Exchange 邮件限制内的 Microsoft 团队的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="f852a-176">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="f852a-177">如果用户希望电子邮件发送给团队中的通道，他们使用的通道电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f852a-177">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="f852a-178">一旦电子邮件通道的一部分，任何人都可以对其开始对话进行答复。</span><span class="sxs-lookup"><span data-stu-id="f852a-178">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="f852a-179">下面是一些到通道发送电子邮件的适用限制。</span><span class="sxs-lookup"><span data-stu-id="f852a-179">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="f852a-180">功能</span><span class="sxs-lookup"><span data-stu-id="f852a-180">Feature</span></span>  |<span data-ttu-id="f852a-181">Office 365 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="f852a-181">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="f852a-182">Office 365 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="f852a-182">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="f852a-183">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f852a-183">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="f852a-184">Office 365 企业版 F1</span><span class="sxs-lookup"><span data-stu-id="f852a-184">Office 365 Enterprise F1</span></span>  |
|---------|---------|---------|---------|---------|
|<span data-ttu-id="f852a-185">邮件大小限制&dagger;</span><span class="sxs-lookup"><span data-stu-id="f852a-185">Message size limit &dagger;</span></span>  |<span data-ttu-id="f852a-186">25 KB</span><span class="sxs-lookup"><span data-stu-id="f852a-186">25 KB</span></span>   |<span data-ttu-id="f852a-187">25 KB</span><span class="sxs-lookup"><span data-stu-id="f852a-187">25 KB</span></span>   |<span data-ttu-id="f852a-188">25 KB</span><span class="sxs-lookup"><span data-stu-id="f852a-188">25 KB</span></span>   |<span data-ttu-id="f852a-189">25 KB</span><span class="sxs-lookup"><span data-stu-id="f852a-189">25 KB</span></span>   |
|<span data-ttu-id="f852a-190">文件附件限制&Dagger;</span><span class="sxs-lookup"><span data-stu-id="f852a-190">File attachments limit &Dagger;</span></span>  |<span data-ttu-id="f852a-191"> 10</span><span class="sxs-lookup"><span data-stu-id="f852a-191">10</span></span>     |<span data-ttu-id="f852a-192"> 10</span><span class="sxs-lookup"><span data-stu-id="f852a-192">10</span></span>     |<span data-ttu-id="f852a-193"> 10</span><span class="sxs-lookup"><span data-stu-id="f852a-193">10</span></span>     |<span data-ttu-id="f852a-194"> 10</span><span class="sxs-lookup"><span data-stu-id="f852a-194">10</span></span>    |
|<span data-ttu-id="f852a-195">内嵌图像限制&Dagger;</span><span class="sxs-lookup"><span data-stu-id="f852a-195">Inline images limit &Dagger;</span></span> |<span data-ttu-id="f852a-196">50%</span><span class="sxs-lookup"><span data-stu-id="f852a-196">50</span></span>   |<span data-ttu-id="f852a-197">50%</span><span class="sxs-lookup"><span data-stu-id="f852a-197">50</span></span>   |<span data-ttu-id="f852a-198">50%</span><span class="sxs-lookup"><span data-stu-id="f852a-198">50</span></span>   |<span data-ttu-id="f852a-199">50%</span><span class="sxs-lookup"><span data-stu-id="f852a-199">50</span></span>   |

<span data-ttu-id="f852a-200">&dagger;如果邮件超过此限制，生成预览消息，并要求用户要查看/下载原始电子邮件从提供的链接。</span><span class="sxs-lookup"><span data-stu-id="f852a-200">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="f852a-201">&Dagger;如果附件或图像的数目超过此限制，将不会处理邮件和 NDR 电子邮件将发送回发件人通知他们的错误。</span><span class="sxs-lookup"><span data-stu-id="f852a-201">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR e-mail will be sent back to the sender notifying them of the error.</span></span>

<span data-ttu-id="f852a-202">有关详细信息，请参阅[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f852a-202">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

<a name="browsers"></a><span data-ttu-id="f852a-203"> 浏览器</span><span class="sxs-lookup"><span data-stu-id="f852a-203">Browsers</span></span> 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a><span data-ttu-id="f852a-204">操作系统</span><span class="sxs-lookup"><span data-stu-id="f852a-204">Operating systems</span></span>
-----------------

<span data-ttu-id="f852a-205">有关操作系统要求的信息，请参阅[获取 Microsoft 团队的客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="f852a-205">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>


