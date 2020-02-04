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
description: 你可以将文件附加到 Skype for business 会议，参与者可以打开并下载。 附加到 Skype for business 会议的文件将保留在任何参与者的邮箱中，其邮箱位于诉讼封存位置、已应用 Office 365 保留策略，或者置于与 Office 365 安全&amp;合规中心中的电子数据展示事例相关联的保留。 此内容保存到参与者的邮箱中的 "可恢复项目" 文件夹。
ms.openlocfilehash: fdd6786cb9b7e5535abee47eb1f0b538b6a22b45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706647"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到 Skype for Business 会议的大型文件

你可以将文件附加到 Skype for business 会议，参与者可以打开并下载。 附加到 Skype for business 会议的文件将保留在任何参与者的邮箱中，其邮箱位于诉讼封存位置、已应用 Office 365 保留策略，或者置于与 Office 365 安全&amp;合规中心中的电子数据展示事例相关联的保留。 此内容保存到参与者的邮箱中的 "**可恢复项目**" 文件夹。
  
在保留邮箱中保留的文件已编制索引，因此，当搜索参与者的邮箱时，在安全&amp;合规中心中运行内容搜索时，可以搜索这些文件。 但是，大于 30 MB 的附加文件将拆分为两个或更多较小的文件，并保存为压缩（.zip）文件。 这些较小文件的*内容*不是为搜索编制索引，并且可能不会在内容搜索中返回。 但是，这些文件的*元数据*（如文件名和作者）已为搜索编制了索引，并且可能会在内容搜索中返回。
  
> [!IMPORTANT]
> Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置可能会影响从 Skype for Business 会议中保留大型文件的功能。 MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。 但是，这些默认设置太小，无法保留大于 30 MB 的 Skype for Business 会议中的任何文件。 这是因为 Exchange Online 使用邮件附件的 Base64 编码和其他二进制数据。 对邮件进行编码后，其大小会增加约33%。 因此，为了确保保留 Skype for Business 会议中的大型文件，我们建议你将 MaxReceiveSize 和 MaxSendSize 的值增加到 39 MB （比之前所述的 30 MB 大小限制更大的33%）适用于处于保留状态的用户。 否则，附加到 Skype for Business 会议的大型文件可能不会保留。 有关在 Exchange Online PowerShell 中使用**设置邮箱 MaxReceiveSize**和**设置邮箱 MaxSendSize**命令的详细信息，请参阅[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未处于暂停状态的邮箱将不会保存任何会议数据。 例如，在一个三人的会议中，将两个参与者的邮箱标记为保留，则会将会议数据保存到这两个参与者的邮箱，但不会保存到其邮箱未保留的第三方参与者的邮箱中。
  
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)
  
  
 