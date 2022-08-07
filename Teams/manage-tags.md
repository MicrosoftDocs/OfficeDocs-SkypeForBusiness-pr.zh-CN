---
title: 在 Microsoft Teams 中管理标记
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中的组织中使用标记。
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267947"
---
# <a name="manage-tags-in-microsoft-teams"></a>在 Microsoft Teams 中管理标记

## <a name="overview"></a>概述

Microsoft Teams 中的标记使用户能够快速轻松地与团队中的一部分人员进行连接。 可以创建和分配自定义标记，以便根据角色、项目、技能或位置等属性对人员进行分类。 或者，标记可以根据人员在 [Shifts 应用](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)中的日程安排和轮班信息自动分配给他们。 将标记添加到一个或多个团队成员后，可以由频道帖子中团队中的任何人在@mentions中使用该标记，或者仅通知分配了该聊天标记的人员

如前所述，Teams 中有两种类型的标记。

- **自定义标记**：团队所有者和团队成员 (如果为其启用了该功能，) 可以手动创建标记并向人员分配标记。 例如，“设计器”或“放射学家”标记将访问团队中的这些人员集，而无需键入他们的名字。
- **按班次标记**：使用此功能，在 Teams 的 [Shifts 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 中自动分配与其计划和班次组名称匹配的标记。 例如，“EngineerOnCall”标记将到达在聊天或频道帖子中使用标记时计划在 Shifts 中工作的所有工程师。 通过按班次标记，当用户需要快速中继信息时，Teams 会从知道轮班员工的姓名中获取猜测。

> [!NOTE]
> 专用频道或共享频道不支持标记。

## <a name="how-tags-work"></a>标记的工作原理

可以手动添加标记或自动分配给特定团队中的人员。 然后，可以在聊天的 **“To** ”行的@mentions或团队任何标准频道的帖子中使用它。 下面是有关如何在 Teams 中使用标记的一些示例：

- 商店经理向频道发布公告，通知所有收银员。
- 医院管理员向频道中的所有放射科医生发送消息。
- 营销经理开始与所有设计人员进行群聊。

在频道对话中@mentioned标记时，与标记关联的团队成员将收到通知，就像任何其他@mention一样。

## <a name="manage-custom-tags-for-your-organization"></a>管理组织的自定义标记

作为管理员，你可以控制如何在 Microsoft Teams 管理中心内跨组织使用标记。 请注意，不能使用 PowerShell 管理标记。

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Microsoft Teams 管理中心中标记设置的屏幕截图。":::

团队最多可以有 100 个标记，最多可以为 100 个团队成员分配一个标记，最多可以向单个用户分配 25 个标记。

### <a name="set-who-can-add-custom-tags"></a>设置谁可以添加自定义标记

默认情况下，团队所有者可以添加自定义标记。 可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭组织的标记。

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **Teams Teams** \> **设置**。

2. 在 **“标记**”下， **在“标记**”旁边，选择以下选项之一：

    - **团队所有者和成员**：允许团队所有者和成员管理标记。
    - **团队所有者**：允许团队所有者管理标记。
    - **已禁用**：关闭标记。

### <a name="configure-custom-tags-settings"></a>配置自定义标记设置

可以配置以下标记设置，以控制在整个组织中使用自定义标记的方式。

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **Teams Teams** \> **设置**。

2. 在 **“标记**”下，根据组织的需求设置以下内容。

    - **让团队所有者替代谁可以管理标记**：打开此设置时，团队所有者可以设置团队成员是否可以在团队中创建和管理标记， **并且通过设置管理标记** 的值是每个团队的默认值。 如果关闭此设置，则无法为每个团队更改设置来 **管理标记** 。
    - **建议的默认标记**：使用此标记添加一组默认标记。 最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。 团队所有者和成员 (为其启用功能) 可以使用这些建议、添加到这些建议或创建一组新的标记。
    - **允许创建自定义标记**：打开此设置，允许用户添加你设置的建议默认标记以外的标记。 如果关闭此设置，则用户只能使用建议的默认标记。 如果关闭此标记，请确保添加一个或多个默认标记。

## <a name="related-topics"></a>相关主题

[在 Teams 中使用标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中为组织管理排班应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts Help 文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
