---
title: 保留附加到业务会议 Skype 的大型文件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 您可以将文件附加到业务会议，参与者可以再打开，并下载 Skype。 附加到 Skype 业务会议文件中的任何参与者都将其邮箱置于诉讼保留，有应用，Office 365 保留策略或将置于保持状态，与 Office 365 安全性电子数据展示事例关联邮箱的保留&amp;合规性中心。 此内容将保存到其邮箱中的参与者的可恢复的项目文件夹。
ms.openlocfilehash: e72a5e5ffa47ef3e451f4f4830e8cd6c524d70a7
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25436633"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="c21f6-105">保留附加到业务会议 Skype 的大型文件</span><span class="sxs-lookup"><span data-stu-id="c21f6-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="c21f6-106">您可以将文件附加到业务会议，参与者可以再打开，并下载 Skype。</span><span class="sxs-lookup"><span data-stu-id="c21f6-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="c21f6-107">附加到 Skype 业务会议文件中的任何参与者都将其邮箱置于诉讼保留，有应用，Office 365 保留策略或将置于保持状态，与 Office 365 安全性电子数据展示事例关联邮箱的保留&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="c21f6-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="c21f6-108">此内容将保存到其邮箱中的参与者的**可恢复的项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="c21f6-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="c21f6-109">在置于保持状态的邮箱中保留的文件编制索引和安全中运行内容搜索时因此可搜索&amp;合规性中心时搜索参与者的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c21f6-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="c21f6-110">但是，大于 30 MB 的附件是拆分为两个或多个较小的文件，保存为压缩 (.zip) 文件。</span><span class="sxs-lookup"><span data-stu-id="c21f6-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="c21f6-111">这些较小的文件的*内容*不编制索引以搜索，且不可能在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="c21f6-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="c21f6-112">但是，这些文件 （如文件的名称和作者） 的*元数据*搜索编制索引，并且可能会在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="c21f6-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c21f6-113">Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置会影响保留大型文件从 Skype 业务会议的功能。</span><span class="sxs-lookup"><span data-stu-id="c21f6-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="c21f6-114">MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。</span><span class="sxs-lookup"><span data-stu-id="c21f6-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="c21f6-115">但是，这些默认设置是太小，无法保留从 Skype 大于 30 MB 的业务会议的任何文件。</span><span class="sxs-lookup"><span data-stu-id="c21f6-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="c21f6-116">实际上，附加大于不会保留 23 MB 的文件。</span><span class="sxs-lookup"><span data-stu-id="c21f6-116">In fact, attached files larger than 23 MB will not be retained.</span></span> <span data-ttu-id="c21f6-117">这是因为 Exchange Online 使用 Base64 编码的邮件附件和其他二进制数据。</span><span class="sxs-lookup"><span data-stu-id="c21f6-117">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="c21f6-118">时编码一条消息，其大小大约 33%的增长。</span><span class="sxs-lookup"><span data-stu-id="c21f6-118">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="c21f6-119">因此，以确保大型文件从 Skype 业务会议将会保留，我们建议您 MaxReceiveSize 和 MaxSendSize 为 39 MB （即大约 33%以上的前面所述的 30 MB 大小限制） 增加值置于保持状态的用户。</span><span class="sxs-lookup"><span data-stu-id="c21f6-119">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="c21f6-120">否则，可能不会保留附加到业务会议 Skype 的大型文件。</span><span class="sxs-lookup"><span data-stu-id="c21f6-120">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="c21f6-121">有关 Exchange Online PowerShell 中使用**Set-mailbox MaxReceiveSize**和**Set-mailbox MaxSendSize**命令的详细信息，请参阅[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c21f6-121">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="c21f6-122">不是置于保持状态的邮箱不会保存任何会议数据。</span><span class="sxs-lookup"><span data-stu-id="c21f6-122">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="c21f6-123">例如，有三人参加会议中的两个参与者的邮箱的保留标记，会议数据保存到的邮箱的这些两个参与者，但不是到邮箱的第三个参与者，其邮箱位于不保留。</span><span class="sxs-lookup"><span data-stu-id="c21f6-123">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c21f6-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="c21f6-124">Related topics</span></span>
[<span data-ttu-id="c21f6-125">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="c21f6-125">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="c21f6-126">阻止点对点文件传输</span><span class="sxs-lookup"><span data-stu-id="c21f6-126">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="c21f6-127">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="c21f6-127">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="c21f6-128">设置您的组织中的会议策略</span><span class="sxs-lookup"><span data-stu-id="c21f6-128">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 