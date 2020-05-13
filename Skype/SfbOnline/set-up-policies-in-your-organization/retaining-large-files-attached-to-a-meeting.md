---
title: 保留附加到 Skype for Business 会议的大型文件
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 你可以将文件附加到 Skype for business 会议，参与者可以打开并下载。 附加到 Skype for business 会议的文件将保留在任何参与者的邮箱中，其邮箱已应用于诉讼保留、已应用 Microsoft 365 或 Office 365 保留策略，或者置于与 Microsoft 365 合规中心中的电子数据展示事例相关联的保留。 此内容保存到参与者的邮箱中的 "可恢复项目" 文件夹。
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164071"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="6374a-105">保留附加到 Skype for Business 会议的大型文件</span><span class="sxs-lookup"><span data-stu-id="6374a-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="6374a-106">你可以将文件附加到 Skype for business 会议，参与者可以打开并下载。</span><span class="sxs-lookup"><span data-stu-id="6374a-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="6374a-107">附加到 Skype for business 会议的文件将保留在任何参与者的邮箱中，其邮箱已应用于诉讼保留、已应用 Microsoft 365 或 Office 365 保留策略，或者置于与 Microsoft 365 合规中心中的电子数据展示事例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="6374a-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="6374a-108">此内容保存到参与者的邮箱中的 "**可恢复项目**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6374a-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="6374a-109">在保留邮箱中保留的文件已编制索引，因此，当搜索参与者的邮箱时，在安全&amp;合规中心中运行内容搜索时，可以搜索这些文件。</span><span class="sxs-lookup"><span data-stu-id="6374a-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="6374a-110">但是，大于 30 MB 的附加文件将拆分为两个或更多较小的文件，并保存为压缩（.zip）文件。</span><span class="sxs-lookup"><span data-stu-id="6374a-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="6374a-111">这些较小文件的*内容*不是为搜索编制索引，并且可能不会在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="6374a-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="6374a-112">但是，这些文件的*元数据*（如文件名和作者）已为搜索编制了索引，并且可能会在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="6374a-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6374a-113">Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置可能会影响从 Skype for Business 会议中保留大型文件的功能。</span><span class="sxs-lookup"><span data-stu-id="6374a-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="6374a-114">MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。</span><span class="sxs-lookup"><span data-stu-id="6374a-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="6374a-115">但是，这些默认设置太小，无法保留大于 30 MB 的 Skype for Business 会议中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="6374a-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="6374a-116">这是因为 Exchange Online 使用邮件附件的 Base64 编码和其他二进制数据。</span><span class="sxs-lookup"><span data-stu-id="6374a-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="6374a-117">对邮件进行编码后，其大小会增加约33%。</span><span class="sxs-lookup"><span data-stu-id="6374a-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="6374a-118">因此，为了确保保留 Skype for Business 会议中的大型文件，我们建议你将 MaxReceiveSize 和 MaxSendSize 的值增加到 39 MB 33 （比之前所述的 30 MB 大小限制更大），以供处于保留状态的用户使用。</span><span class="sxs-lookup"><span data-stu-id="6374a-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="6374a-119">否则，附加到 Skype for Business 会议的大型文件可能不会保留。</span><span class="sxs-lookup"><span data-stu-id="6374a-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="6374a-120">有关在 Exchange Online PowerShell 中使用**设置邮箱 MaxReceiveSize**和**设置邮箱 MaxSendSize**命令的详细信息，请参阅[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。</span><span class="sxs-lookup"><span data-stu-id="6374a-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="6374a-121">未处于暂停状态的邮箱将不会保存任何会议数据。</span><span class="sxs-lookup"><span data-stu-id="6374a-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="6374a-122">例如，在一个三人的会议中，将两个参与者的邮箱标记为保留，则会将会议数据保存到这两个参与者的邮箱，但不会保存到其邮箱未保留的第三方参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="6374a-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6374a-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="6374a-123">Related topics</span></span>
[<span data-ttu-id="6374a-124">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="6374a-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="6374a-125">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="6374a-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6374a-126">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="6374a-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6374a-127">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="6374a-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 
