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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到 Skype for Business 会议的大型文件

你可以将文件附加到 Skype for Business 会议，然后参与者可以打开和下载。 附加到 Skype for Business 会议的文件将保留在邮箱中，这些参与者的邮箱被置于诉讼保留状态，应用了 Microsoft 365 或 Office 365 保留策略，或者被置于与 Microsoft 365 合规中心电子数据展示案例关联的保留中。 此内容将保存到参与者邮箱 **中的"** 可恢复项目"文件夹。
  
保留邮箱中保留的文件会编制索引，因此在搜索参与者的邮箱时在安全合规中心运行内容搜索时可以 &amp; 搜索这些文件。 但是，大于 30 MB 的附加文件将拆分为两个或多个较小的文件，并另存为 (.zip) 文件。 *这些* 较小文件的内容不会为搜索编制索引，并且可能不会在内容搜索中返回。 但是， *这些文件*  的元数据 (例如文件名和作者) 进行索引搜索，并可能在内容搜索中返回。
  
> [!IMPORTANT]
> Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置可能会影响从 Skype for Business 会议保留大型文件的能力。 MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。 但是，这些默认设置太小，无法保留 Skype for Business 会议的任何大于 30 MB 的文件。 这是因为 Exchange Online 使用邮件附件和其他二进制数据的 Base64 编码。 对消息进行编码时，其大小大约增加 33%。 因此，为了确保保留 Skype for Business 会议中的大型文件，建议将 MaxReceiveSize 和 MaxSendSize 的值增大到 39 MB (这大约比之前为被暂停的用户解释的) 30 MB 大小限制大 33%。 否则，附加到 Skype for Business 会议的大型文件可能不会保留。 有关在 Exchange Online PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令详细信息，请参阅 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保持的邮箱不会保存任何会议数据。 例如，在一个三人会议（其中两个参与者的邮箱标记为保留）中，会议数据将保存到这两个参与者的邮箱，而不是保存到其邮箱未保留的第三个参与者的邮箱。
  
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)
  
  
