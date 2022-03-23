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
description: 了解如何使用 Microsoft Teams将用户或团队法定保留Microsoft 365 合规中心并基于数据要求了解需要法定保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711556"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>将 Microsoft Teams 用户或团队置于法定保留状态

当存在合理的诉讼预期时，组织需要保留以电子方式存储的信息 (ESI) ，Teams与案例相关的聊天消息。 组织可能需要保留与特定调查或特定人员相关的所有邮件。 本文将讨论如何使用法定保留来保留Microsoft Teams。 若要保留其他服务中的内容Microsoft 365[，请参阅创建电子数据展示保留](/microsoft-365/compliance/create-ediscovery-holds)。

> [!NOTE]
> 我们于 2020 年 2 月对专用频道启用法定保留。 私人频道聊天存储在用户邮箱中，而标准频道聊天存储在与父团队关联的邮箱中。 如果用户邮箱已有法定保留，则保留策略现在将自动应用于存储在该邮箱中的专用频道邮件。 管理员无需执行进一步的操作来启用此功能。 还支持对在专用通道中共享的文件进行法定保留。

在Microsoft Teams，整个团队或选定用户都可以被置于法定保留状态。 这样做会确保那些团队中交换的所有消息 (包括专用和共享频道) 或者由这些人员交换的消息都由组织的合规性经理或管理员Teams发现。

> [!NOTE]
> 将用户置于保留状态并不会自动将组置于保留状态，反之亦然。
> 无法保留活动源中发送的通知。

在核心电子数据展示案例中将用户或团队置于法定保留状态：

1. 转到[Microsoft 365 合规中心。](https://compliance.microsoft.com) 创建新案例时，将看到将邮箱或网站置于保留状态的选项。

2. 转到 **电子数据展示** > **分数** ，通过单击"创建案例 **"创建案例**。 创建案例后，打开它。
  
   ![Microsoft Teams"电子数据展示"选项卡，显示"创建案例"按钮。](media/LegalHold1.png)

   > [!NOTE]
   > 还可以将用户放在与案例关联的保留Advanced eDiscovery保留。 有关详细信息，请参阅[管理 Advanced eDiscovery 中的保留](/microsoft-365/compliance/managing-holds)。

3. 转到顶部菜单 **上的"** 保留"选项卡，然后单击 **"创建** "以创建保留。 保留用户或团队会保留这些用户交换的所有消息。 创建新案例时，将看到将邮箱或网站置于保留状态的选项。

   ![显示选中了"保留"选项卡和下方的"创建"按钮的图像。](media/LegalHold2.png)

   1. **为保留命名**。 选择要创建的保留的描述性唯一名称。
  
       ![此屏幕截图显示"命名保留"选项卡，可在其中输入要创建的保留的名称和说明。](media/LegalHold3.png)

   2. **选择位置**。 选择是希望保留应用于用户还是整个团队 (目前无法对单个频道应用保留) 。 如果用户保持保留状态，则保留其所有消息，包括 1 对 1 聊天、群组聊天和专用频道中的消息。 当父团队处于保留状态时，将保留标准和共享频道中的消息。

      ![选择要保留的数据位置。](media/LegalHold4.png)

   3. **创建查询**。 如果希望保留策略中具有更精细的粒度，可以自定义保留。 例如，您可以指定要查找的关键字，或者可以添加更多条件，需要满足这些条件才能使保留生效。

   4. **在创建保留之前** 查看设置。

创建保留后，可以搜索保留策略保留的内容。 有关详细信息，请参阅[在 Teams 中执行电子数据展示Teams](eDiscovery-investigation.md)。

> [!IMPORTANT]
> 将用户或组置于保留状态时，将保留消息的所有符合性副本。 例如，如果用户在频道中发布消息并修改消息，则消息的两个副本将保留。 如果不保留，则仅保留最新消息。

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>要保留的内容位置以保留Teams内容

作为有用的指南，请使用下表来了解 (保留哪些内容位置，例如) 或网站，以保留不同类型的Teams内容。

|使用场景  |内容位置  |
|---------|---------|
|用户的聊天消息 (例如，1：1 聊天、1：N 群组聊天和私人频道)      |用户邮箱         |
|标准和共享通道中的聊天消息    |与父团队关联的邮箱         |
|标准频道中的文件 (例如 Wiki 内容和文件)      |SharePoint父团队关联的网站        |
|专用频道和共享频道中的文件     |与SharePoint关联的专用网站
|用户的私人内容     |用户的帐户OneDrive for Business帐户       |
|聊天中的卡片内容|用于 1：1 聊天、1：N 群组聊天和私人频道对话的用户邮箱;标准频道和共享频道消息中卡片内容的父团队邮箱。 有关详细信息，请参阅创建电子数据展示保留中的" [保留卡内容"部分](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。|
|||

> [!NOTE]
> 若要在专用频道中保留邮件内容，你需要将用户邮箱 (专用频道的成员中) 保留。 使用电子数据展示工具搜索私人频道邮件时，必须搜索用户的邮箱。 如前面所述，私人频道聊天存储在用户邮箱中，而不是存储在与父团队关联的组邮箱中。
