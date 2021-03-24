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
description: 你可以将文件附加到 Skype for Business 会议，然后参与者可以打开和下载。 附加到 Skype for Business 会议的文件将保留在邮箱中，这些参与者的邮箱被置于诉讼保留状态，应用了 Microsoft 365 或 Office 365 保留策略，或者被置于与 Microsoft 365 合规中心电子数据展示案例关联的保留中。 此内容将保存到参与者邮箱中的"可恢复项目"文件夹。
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100568"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="13173-105">保留附加到 Skype for Business 会议的大型文件</span><span class="sxs-lookup"><span data-stu-id="13173-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="13173-106">你可以将文件附加到 Skype for Business 会议，然后参与者可以打开和下载。</span><span class="sxs-lookup"><span data-stu-id="13173-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="13173-107">附加到 Skype for Business 会议的文件将保留在邮箱中，这些参与者的邮箱被置于诉讼保留状态，应用了 Microsoft 365 或 Office 365 保留策略，或者被置于与 Microsoft 365 合规中心电子数据展示案例关联的保留中。</span><span class="sxs-lookup"><span data-stu-id="13173-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="13173-108">此内容将保存到参与者邮箱 **中的"** 可恢复项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="13173-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="13173-109">保留邮箱中保留的文件会编制索引，因此在搜索参与者的邮箱时在安全合规中心运行内容搜索时可以 &amp; 搜索这些文件。</span><span class="sxs-lookup"><span data-stu-id="13173-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="13173-110">但是，大于 30 MB 的附加文件将拆分为两个或多个较小的文件，并另存为 (.zip) 文件。</span><span class="sxs-lookup"><span data-stu-id="13173-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="13173-111">*这些* 较小文件的内容不会为搜索编制索引，并且可能不会在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="13173-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="13173-112">但是， *这些文件*  的元数据 (例如文件名和作者) 进行索引搜索，并可能在内容搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="13173-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="13173-113">Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置可能会影响从 Skype for Business 会议保留大型文件的能力。</span><span class="sxs-lookup"><span data-stu-id="13173-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="13173-114">MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。</span><span class="sxs-lookup"><span data-stu-id="13173-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="13173-115">但是，这些默认设置太小，无法保留 Skype for Business 会议的任何大于 30 MB 的文件。</span><span class="sxs-lookup"><span data-stu-id="13173-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="13173-116">这是因为 Exchange Online 使用邮件附件和其他二进制数据的 Base64 编码。</span><span class="sxs-lookup"><span data-stu-id="13173-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="13173-117">对消息进行编码时，其大小大约增加 33%。</span><span class="sxs-lookup"><span data-stu-id="13173-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="13173-118">因此，为了确保保留 Skype for Business 会议中的大型文件，建议将 MaxReceiveSize 和 MaxSendSize 的值增大到 39 MB (这大约比之前为被暂停的用户解释的) 30 MB 大小限制大 33%。</span><span class="sxs-lookup"><span data-stu-id="13173-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="13173-119">否则，附加到 Skype for Business 会议的大型文件可能不会保留。</span><span class="sxs-lookup"><span data-stu-id="13173-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="13173-120">有关在 Exchange Online PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令详细信息，请参阅 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。</span><span class="sxs-lookup"><span data-stu-id="13173-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="13173-121">未保持的邮箱不会保存任何会议数据。</span><span class="sxs-lookup"><span data-stu-id="13173-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="13173-122">例如，在一个三人会议（其中两个参与者的邮箱标记为保留）中，会议数据将保存到这两个参与者的邮箱，而不是保存到其邮箱未保留的第三个参与者的邮箱。</span><span class="sxs-lookup"><span data-stu-id="13173-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="13173-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="13173-123">Related topics</span></span>
[<span data-ttu-id="13173-124">创建自定义外部访问策略</span><span class="sxs-lookup"><span data-stu-id="13173-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="13173-125">阻止点到点文件传输</span><span class="sxs-lookup"><span data-stu-id="13173-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="13173-126">为你的组织设置客户端策略</span><span class="sxs-lookup"><span data-stu-id="13173-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="13173-127">在组织中设置会议策略</span><span class="sxs-lookup"><span data-stu-id="13173-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
