---
title: 保留大型商务会议 Skype 所附的文件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 您可以将文件附加到商务会议，哪些参与者然后可以打开并下载 Skype。 附加到 Skype 的用于业务会议的文件保留在其邮箱置于诉讼封存，有应用，Office 365 保留策略或保留与 eDiscovery 案例在 Office 365 安全关联上放置任何参与者的邮箱&amp;法规遵从性中心。 此内容将保存到他们的邮箱中的参与者的恢复项目文件夹。
ms.openlocfilehash: ddd4742b3e30ed09a7e538d40712577ab26edfda
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="4922b-105">保留大型商务会议 Skype 所附的文件</span><span class="sxs-lookup"><span data-stu-id="4922b-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="4922b-106">您可以将文件附加到商务会议，哪些参与者然后可以打开并下载 Skype。</span><span class="sxs-lookup"><span data-stu-id="4922b-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="4922b-107">附加到 Skype 的用于业务会议的文件保留在其邮箱置于诉讼封存，有应用，Office 365 保留策略或保留与 eDiscovery 案例在 Office 365 安全关联上放置任何参与者的邮箱&amp;法规遵从性中心。</span><span class="sxs-lookup"><span data-stu-id="4922b-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="4922b-108">此内容将保存到他们的邮箱中的参与者的**恢复项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="4922b-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="4922b-109">文件保留在邮箱中保留的已索引，并且因此可以安全运行内容搜索时搜索&amp;搜索参与者的邮箱时的法规遵从性中心。</span><span class="sxs-lookup"><span data-stu-id="4922b-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="4922b-110">不过，大于 39 MB 的附加的文件拆分为两个或多个较小的文件，另存为压缩 (.zip) 文件。</span><span class="sxs-lookup"><span data-stu-id="4922b-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="4922b-111">这些较小的文件的*内容*进行搜索，未被编入索引，可能不会在内容搜索返回。</span><span class="sxs-lookup"><span data-stu-id="4922b-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="4922b-112">但是，*元数据*（例如文件的名称和作者） 这些文件的索引进行搜索，并且可能会返回在内容的搜索。</span><span class="sxs-lookup"><span data-stu-id="4922b-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4922b-113">如果邮箱已满，或租户管理员已配置 MaxSendSize 39MB 比小，上载的数据不会在所有保留的文件。</span><span class="sxs-lookup"><span data-stu-id="4922b-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="4922b-114">默认的 MaxSendSize 为 150 MB，但是租户管理员可以配置 MaxSendSize 小为 1 MB。</span><span class="sxs-lookup"><span data-stu-id="4922b-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="4922b-115">未处于暂停状态的邮箱将不会保存任何会议数据。</span><span class="sxs-lookup"><span data-stu-id="4922b-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="4922b-116">例如，在中的三人会议这两个参与者的邮箱标记为保留、 会议数据保存那些两个参与者的邮箱，但不是到第三个参与者的邮箱，其邮箱不在保留。</span><span class="sxs-lookup"><span data-stu-id="4922b-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4922b-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="4922b-117">Related topics</span></span>
[<span data-ttu-id="4922b-118">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="4922b-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="4922b-119">块的点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="4922b-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4922b-120">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="4922b-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4922b-121">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="4922b-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 