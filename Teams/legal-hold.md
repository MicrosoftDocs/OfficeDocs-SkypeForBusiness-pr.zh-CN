---
title: 将 Microsoft Teams 用户或团队置于法定保留状态
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用Microsoft Purview 合规门户将 Microsoft Teams 用户或团队置于法定保留状态，并了解需要根据数据要求进行法定保留的内容。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc99518aa3580311c48966105ccc4b4ba6cf518
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808753"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>将 Microsoft Teams 用户或团队置于法定保留状态

如果存在合理的诉讼预期，则需要组织保留电子存储的信息 (ESI) ，包括与案件相关的 Teams 聊天消息。 组织可能需要保留与特定调查或特定人员相关的所有消息。 本文将讨论如何使用法定保留来保留 Microsoft Teams 中的内容。 若要在 Microsoft 365 中保留其他服务中的内容，请参阅 [创建电子数据展示保留](/microsoft-365/compliance/create-ediscovery-holds)。

> [!NOTE]
> 2020年2月，我们为私人渠道启用了法律保留。 专用频道聊天存储在用户邮箱中，而标准频道聊天存储在与父团队关联的邮箱中。 如果用户邮箱已有合法保留，则保留策略现在将自动应用于存储在该邮箱中的专用频道邮件。 管理员无需执行进一步操作即可启用此操作。 还支持合法保存在专用渠道中共享的文件。

在 Microsoft Teams 中，可以将整个团队或选择的用户置于法定保留状态。 这样做将确保组织合规性经理或 Teams 管理员可以发现这些团队中交换的所有消息 (包括个人) 和共享频道或由这些人员交换的消息。

> [!NOTE]
> 将用户置于保留状态并不会自动将组置于保留状态，反之亦然。
> 无法将活动源中发送的通知置于保留状态。

若要在电子数据展示 (标准) 案例中将用户或团队置于法定保留状态：

1. 转到[Microsoft Purview 合规门户](https://compliance.microsoft.com)。 创建新案例时，系统会显示将邮箱或网站置于保留状态的选项。

2. 单击“创建事例”转到 **电子数据展示** > **核心** 并创建 **事例**。 创建案例后，将其打开。
  
   ![已选择 Microsoft Teams 电子数据展示选项卡，其中显示了“创建事例”按钮。](media/LegalHold1.png)

   > [!NOTE]
   > 还可以将用户置于与电子数据展示 (高级) 案例关联的保留状态。 有关详细信息，请参阅 [电子数据展示 (高级) 中的管理保留 ](/microsoft-365/compliance/managing-holds)。

3. 转到顶部菜单上的 **“保留** ”选项卡，然后单击 **“创建** ”以创建保留。 将用户或团队置于保留状态会保留这些用户交换的所有消息。 创建新案例时，系统会显示将邮箱或网站置于保留状态的选项。

   ![显示所选“保留”选项卡的图像，以及下面的“创建”按钮。](media/LegalHold2.png)

   1. **为保留命名**。 为要创建的保留选择描述性且唯一的名称。
  
       ![此屏幕截图显示了“保留的名称”选项卡，可在其中输入要创建的保留的名称和说明。](media/LegalHold3.png)

   2. **选择位置**。 选择是希望将保留应用于用户还是整个团队 (目前无法在单个通道上应用保留) 。 如果用户处于保留状态，则保留其所有消息，包括 1：1 聊天、群聊和专用频道中的消息。 当父团队处于保留状态时，将保留标准频道和共享通道中的消息。

      ![选择要保留的数据位置。](media/LegalHold4.png)

   3. **创建查询**。 如果需要保留策略中的粒度更高，则可以自定义保留。 例如，可以指定要查找的关键字，也可以添加更多需要满足的条件才能使保留生效。

   4. 创建保留之前 **，请查看设置**。

创建保留后，可以搜索保留策略保留的内容。 有关详细信息，请参阅 [Teams 中的电子数据展示调查](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 当用户或组被搁置时，将保留消息的所有符合性副本。 例如，如果用户在频道中发布消息，然后修改消息，则会保留消息的两个副本。 如果没有保留，则仅保留最新消息。

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>要保留的内容位置以保留 Teams 内容

作为有用的指南，请使用下表了解要保留哪些内容位置 (，例如邮箱或网站) 保留以保留不同类型的 Teams 内容。

|使用场景  |内容位置  |
|---------|---------|
|用户的聊天消息 (例如 1：1 聊天、1：N 群聊和专用频道对话)      |用户邮箱         |
|标准频道和共享频道中的聊天消息    |与父团队关联的邮箱         |
|标准通道中的文件 (例如 Wiki 内容和文件)      |与父团队关联的 SharePoint 网站        |
|专用和共享通道中的文件     |与频道关联的专用 SharePoint 网站
|用户的专用内容     |用户的OneDrive for Business帐户       |
|聊天中的卡片内容|1：1 聊天、1：N 群聊和专用频道对话的用户邮箱：标准和共享频道邮件中卡片内容的父团队邮箱。 有关详细信息，请参阅“ [创建电子数据展示保留](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)”中的“保留卡片内容”部分。|
|||

> [!NOTE]
> 若要在专用频道中保留邮件内容，需要将专用频道成员的用户邮箱 () 保留。 使用电子数据展示工具搜索专用频道邮件时，必须搜索用户的邮箱。 如前所述，专用频道聊天存储在用户邮箱中，而不是存储在与父团队关联的组邮箱中。
