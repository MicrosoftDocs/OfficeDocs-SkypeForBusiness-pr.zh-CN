---
title: 保留附加到Skype for Business会议的大型文件
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 可以将文件附加到Skype for Business会议，然后参与者可以打开并下载这些文件。 附加到Skype for Business会议的文件将保留在任何参与者的邮箱中，其邮箱置于诉讼保留中、应用了Microsoft 365或Office 365保留策略，或被置于与 Microsoft Purview 合规性门户中的电子数据展示案例相关联的保留中。 此内容保存到参与者邮箱中的“可恢复邮件”文件夹。
ms.openlocfilehash: 35792e3415d3def0b8ac45ab39e9dec65f2f7725
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922433"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到Skype for Business会议的大型文件

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

可以将文件附加到Skype for Business会议，然后参与者可以打开并下载这些文件。 附加到Skype for Business会议的文件将保留在任何参与者的邮箱中，其邮箱置于诉讼保留中、应用了Microsoft 365或Office 365保留策略，或被置于与 Microsoft Purview 合规性门户中的电子数据展示案例相关联的保留中。 此内容保存到参与者邮箱中的 **“可恢复邮件** ”文件夹。
  
保留在邮箱中保留的文件会编制索引，因此在搜索参与者的邮箱时，可以在安全 &amp; 合规中心运行内容搜索时进行搜索。 但是，大于 30 MB 的附加文件将拆分为两个或多个较小的文件，并保存为压缩的 (.zip) 文件。 这些较小的文件  *的内容*  不会为搜索编制索引，并且可能不会在内容搜索中返回。 但是，这些文件 (的 *元数据*  （例如文件名和作者) ）会为搜索编制索引，并且可能会在内容搜索中返回。
  
> [!IMPORTANT]
> Exchange Online邮箱的 MaxReceiveSize 和 MaxSendSize 设置可能会影响从Skype for Business会议中保留大型文件的功能。 MaxReceiveSize 和 MaxSendSize 的默认设置分别为 36 MB 和 35 MB。 但是，这些默认设置太小，无法保留大于 30 MB 的Skype for Business会议中的任何文件。 这是因为Exchange Online使用消息附件和其他二进制数据的 Base64 编码。 编码消息时，其大小将增加约 33%。 因此，为了确保保留Skype for Business会议中的大型文件，我们建议将 MaxReceiveSize 和 MaxSendSize 的值增加到 39 MB (，这比先前为被搁置的用户) 解释的 30 MB 大小限制大约 33%。 否则，可能无法保留附加到Skype for Business会议的大型文件。 有关在 Exchange Online PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令的详细信息，请参 [阅 Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保留的邮箱将不会保存任何会议数据。 例如，在一个三人会议中，两个参与者的邮箱被标记为保留，会议数据保存在这两个参与者的邮箱中，但不保存到第三个参与者的邮箱，其邮箱未被搁置。
  
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)
  
  
