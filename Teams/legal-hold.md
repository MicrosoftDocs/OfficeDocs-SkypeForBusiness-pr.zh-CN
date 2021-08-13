---
title: 将 Microsoft Teams 用户或团队置于法定保留状态
author: markjjo
ms.author: markjjo
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
description: 了解如何使用安全性和合规性中心将 Microsoft Teams 用户或团队置于法定保留状态，以及了解根据数据要求哪些内容需要法定保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 714b96f4ba2ea49d158bcc360a6fa95814674f1551935db64a87fd684ed0010c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321314"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>将 Microsoft Teams 用户或团队置于法定保留状态

当存在合理的诉讼预期时，组织需要保留以电子方式 (ESI) 的信息，Teams与案例相关的聊天消息。 组织可能需要保留与特定主题或特定个人相关的所有消息。 本文介绍法定保留Microsoft Teams。 若要跨多个Microsoft 365内容，请参阅[创建电子数据展示保留](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds)。

> [!NOTE]
> 我们于 2020 年 2 月对专用频道启用法定保留。 私人频道聊天存储在用户邮箱中，而普通频道聊天存储在Teams组邮箱中。 如果用户邮箱已有法定保留，则保留策略现在将自动应用于存储在该邮箱中的专用频道邮件。 管理员无需执行进一步的操作来启用此功能。 还支持对在专用通道中共享的文件进行法定保留。

在Microsoft Teams内，整个团队或选定用户都可以被置于法定保留状态。 这样做将确保所有团队中交换的消息 (包括专用频道) 或这些人员交换的消息都由组织的合规性经理或管理员Teams发现。

> [!NOTE]
> 将用户置于保留状态并不会自动将组置于保留状态，反之亦然。
> 无法保留活动源中发送的通知。

在核心电子数据展示案例中将用户或团队置于法定保留状态：

1. 转到["Microsoft 365 合规中心"。](https://compliance.microsoft.com) 在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。

2. 转到 **电子数据展示**  >  **核心**，通过单击"创建案例 **"创建案例**。 创建案例后，打开它。
  
   ![Microsoft Teams"电子数据展示"选项卡，显示"创建案例"按钮。](media/LegalHold1.png)

   > [!NOTE]
   > 还可以将用户放在与案例关联的保留Advanced eDiscovery保留。 有关详细信息，请参阅在 Advanced eDiscovery[中管理保留](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。

3. 转到顶部 **菜单上的"** 保留"选项卡，然后单击 **"创建** "以创建保留。 保留用户或团队会保留这些用户或消息交换的所有消息。 在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。

   ![显示选中了"保留"选项卡和下方的"创建"按钮的图像。](media/LegalHold2.png)
    
    1. **将保留名称为**。 选择要创建的保留的描述性唯一名称。
  
       ![此屏幕截图显示"命名保留"选项卡，可在其中输入要创建的保留的名称和说明。](media/LegalHold3.png)

    1. **选择位置**。 选择要将保留应用于用户还是整个团队， (目前不能应用于单个频道) 。 注意：如果用户保持状态，其所有消息将被保留，包括他们在 1：1 聊天、1：多聊天或群组聊天中发送的任何消息，或者频道对话 (包括私人频道) 。
    ![在这里，我们提供了"创建新保留"的"选择位置"部分，您可以在其中决定要应用到的 M365 选项Microsoft Teams选项（包括 Microsoft Teams）。](media/LegalHold4.png)

    2. **创建查询**。 如果希望保留策略中具有更精细的粒度，可以自定义保留。 例如，您可以指定要查找的关键字，或者可以添加更多条件，需要满足这些条件才能使保留生效。
    
    3. **在创建保留之前** 查看设置。

创建法定保留后，可以搜索任何保留策略保留的内容。 有关详细信息，请参阅在[Teams 中执行电子数据展示调查](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 将用户或组置于保留状态时，将保留所有邮件副本。 例如，如果用户在频道中发布消息，然后修改了消息，在保留方案中，消息的两个副本将保留。 如果不就地保留法定保留，则仅保留最新邮件。

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>要保留法定保留的内容位置，以保留Teams内容

作为有用的指南，可以使用下表来了解哪些内容位置 (例如邮箱或网站) ，以保留不同类型的 Teams 内容。

|使用场景  |内容位置  |
|---------|---------|
|Teams 1：1 (聊天、1：N 群组聊天和私人频道对话等用户聊天)      |用户邮箱。         |
|Teams频道聊天 (专用频道除外)     |用于团队的组邮箱。         |
|Teams文件内容 (，例如 Wiki 内容和文件)      |SharePoint团队使用的网站。         |
|Teams专用频道文件     |专用SharePoint专用频道的专用站点。     |
|用户的私人内容     |用户的帐户OneDrive for Business帐户。         |
|聊天中的卡片内容|用于 1：1 聊天、1：N 群组聊天以及私人频道对话或群组邮箱的用户邮箱，用于频道消息中的卡片内容。 有关详细信息，请参阅创建电子数据展示保留中的"保留卡内容 ["部分](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。
||||

> [!NOTE]
> 若要在专用通道中保留通信，需要将用户邮箱 ( 专用通道用户) 置于保留状态，使用电子数据展示工具进行搜索时，应在该用户的邮箱中搜索。 如前面所述，私人频道聊天存储在用户邮箱中，而不是存储在团队的组邮箱中。

若要进一步阅读本主题，了解Teams区域，Microsoft 365电子数据展示事例[：保留内容位置](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。
