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
ms.openlocfilehash: 103fa8b9602c4db1c5399a97a94613ac8e7b8621
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429378"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到业务会议 Skype 的大型文件

您可以将文件附加到业务会议，参与者可以再打开，并下载 Skype。 附加到 Skype 业务会议文件中的任何参与者都将其邮箱置于诉讼保留，有应用，Office 365 保留策略或将置于保持状态，与 Office 365 安全性电子数据展示事例关联邮箱的保留&amp;合规性中心。 此内容将保存到其邮箱中的参与者的**可恢复的项目**文件夹。
  
在置于保持状态的邮箱中保留的文件编制索引和安全中运行内容搜索时因此可搜索&amp;合规性中心时搜索参与者的邮箱。 但是，大于 30 MB 的附件是拆分为两个或多个较小的文件，保存为压缩 (.zip) 文件。 这些较小的文件的*内容*不编制索引以搜索，且不可能在内容搜索中返回。 但是，这些文件 （如文件的名称和作者） 的*元数据*编制索引的搜索，并且可能会在内容搜索返回。
  
> [!NOTE]
> 如果邮箱已满或租户管理员已配置 MaxSendSize 小于 30 MB，将不会在所有保留上载的文件数据。 默认 MaxSendSize 为 150 MB，但是租户管理员可以配置 MaxSendSize 为最小可为 1 MB。 
  
不是置于保持状态的邮箱不会保存任何会议数据。 例如，有三人参加会议中的两个参与者的邮箱的保留标记，会议数据保存到的邮箱的这些两个参与者，但不是到邮箱的第三个参与者，其邮箱位于不保留。
  
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点对点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)
  
  
 