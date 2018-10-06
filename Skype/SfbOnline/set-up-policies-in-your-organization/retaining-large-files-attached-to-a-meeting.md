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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到业务会议 Skype 的大型文件

您可以将文件附加到业务会议，参与者可以再打开，并下载 Skype。 附加到 Skype 业务会议文件中的任何参与者都将其邮箱置于诉讼保留，有应用，Office 365 保留策略或将置于保持状态，与 Office 365 安全性电子数据展示事例关联邮箱的保留&amp;合规性中心。 此内容将保存到其邮箱中的参与者的**可恢复的项目**文件夹。
  
在置于保持状态的邮箱中保留的文件编制索引和安全中运行内容搜索时因此可搜索&amp;合规性中心时搜索参与者的邮箱。 但是，大于 30 MB 的附件是拆分为两个或多个较小的文件，保存为压缩 (.zip) 文件。 这些较小的文件的*内容*不编制索引以搜索，且不可能在内容搜索中返回。 但是，这些文件 （如文件的名称和作者） 的*元数据*搜索编制索引，并且可能会在内容搜索中返回。
  
> [!IMPORTANT]
> Exchange Online 邮箱的 MaxReceiveSize 和 MaxSendSize 设置会影响保留大型文件从 Skype 业务会议的功能。 MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。 但是，这些默认设置是太小，无法保留从 Skype 大于 30 MB 的业务会议的任何文件。 实际上，附加大于不会保留 23 MB 的文件。 这是因为 Exchange Online 使用 Base64 编码的邮件附件和其他二进制数据。 时编码一条消息，其大小大约 33%的增长。 因此，以确保大型文件从 Skype 业务会议将会保留，我们建议您 MaxReceiveSize 和 MaxSendSize 为 39 MB （即大约 33%以上的前面所述的 30 MB 大小限制） 增加值置于保持状态的用户。 否则，可能不会保留附加到业务会议 Skype 的大型文件。 有关 Exchange Online PowerShell 中使用**Set-mailbox MaxReceiveSize**和**Set-mailbox MaxSendSize**命令的详细信息，请参阅[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
不是置于保持状态的邮箱不会保存任何会议数据。 例如，有三人参加会议中的两个参与者的邮箱的保留标记，会议数据保存到的邮箱的这些两个参与者，但不是到邮箱的第三个参与者，其邮箱位于不保留。
  
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点对点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)
  
  
 