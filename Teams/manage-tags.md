---
title: 管理 Microsoft Teams 中的标记
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在组织内管理标记在 Microsoft Teams。
ms.openlocfilehash: e98c085dee7f91aebc6e34552217230384ba80b6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732521"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft Teams 中的标记

## <a name="overview"></a>概述

使用 Microsoft Teams 中的标记，用户可以快速轻松地与团队中的一部分人员进行连接。 可以创建和分配自定义标记，以便根据角色、项目、技能或位置等属性对人员进行分类。 或者，可以基于人员在 Shifts 应用中的日程安排和班次信息自动将标记 [分配给人员](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)。 将标记添加到一个或多个团队成员后，团队中任何在频道帖子中@mentions成员都可以在 @mentions 中使用标记，或者仅与分配了该标记的人开始对话。

如前所述，该标记有两种Teams。

- **自定义标记**：团队所有者和 (如果为其启用了该功能，则) 手动创建标记并将其分配给人员。 例如，"Designer"或"Radi一"标记将到达团队中的这些人员集，而无需键入其姓名。
- **按排班** 标记：使用此功能，将自动为人员分配与日程安排匹配的标记，在"班次"应用中自动分配Teams。 [](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 例如，在聊天或频道帖子中使用标记时，"EngineerOnCall"标记将到达在 Shifts 中计划工作的所有工程师。 使用按轮班Teams，当用户需要快速中继信息时，无需知道轮班员工的姓名， 通过将主要员工管理系统（例如 JDA、Kronos 和 AMiON）与工作团队中的 Shifts 集成，还可以支持按班次进行Teams。 若要详细了解如何设置此功能，请参阅按 shift [设置标记](#set-up-tagging-by-shift)。

> [!NOTE]
> 专用通道尚不支持标记。 在 DoD 组织的国防部 (中) 标记。 

## <a name="how-tags-work"></a>标记工作

可以手动添加标记或自动将标记分配给特定团队中的人员。 然后，它可以在聊天@mentions的"至"行上或在团队的任何标准频道上的帖子中使用。 下面是一些如何在应用中使用的标记Teams：

- 商店经理向频道发布公告以通知所有收银员。
- 医院管理员向频道中的所有辐射员发送消息。
- 营销经理开始与所有设计人员进行群组聊天。
- 一位护理员向所有通话卡员发送消息。 （即将推出）
- 系统工程师向频道发布公告，通知所有轮班现场工程师。 （即将推出）

当标记在@mentioned对话中时，与标记关联的团队成员将收到通知，就像任何其他@mention。

## <a name="manage-custom-tags-for-your-organization"></a>管理组织的自定义标记

作为管理员，你可以控制在管理中心内在整个组织中Microsoft Teams标记。 目前，无法通过 PowerShell 管理标记。

![管理中心中标记设置的Microsoft Teams屏幕截图。](media/manage-tags-admin-settings.png)

一个团队可以有多达 100 个标记，最多 100 个团队成员可以分配到一个标记，并且最多可以将 25 个标记分配给单个用户。 

### <a name="set-who-can-add-custom-tags"></a>设置谁可以添加自定义标记

默认情况下，团队所有者可以添加自定义标记。 您可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭组织的标记。

1. 在管理中心的左侧导航Microsoft Teams，单击"**组织范围的设置**"Teams  >  **设置"。**
2. 在 **"标记"** 下 **，在"标记由 管理"旁边**，选择以下选项之一：

    - **团队所有者和成员**：允许团队所有者和成员管理标记。
    - **团队所有者**：允许团队所有者管理标记。
    - **已禁用**：关闭标记。

### <a name="configure-custom-tags-settings"></a>配置自定义标记设置

可以配置以下标记设置来控制如何在组织中使用自定义标记。

1. 在管理中心的左侧导航Microsoft Teams，单击"**组织范围的设置**"Teams  >  **设置"。**
2. 在 **"标记**"下，根据组织的需求设置以下内容。

    - 让团队所有者替代谁可以管理标记：启用此设置时，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，并且"标记"的值通过设置进行管理是每个团队的默认值。 如果关闭此设置，则 **不能** 更改每个团队的"通过设置管理标记"。
    - **建议的默认标记**：用于添加一组默认标记。 最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。 如果为 (启用该功能，团队所有者和成员) 可以使用这些建议、向它们添加或创建一组新的标记。
    - **允许创建自定义标记**：启用此设置，以允许添加除你设置的建议默认标记外的其他标记。 如果此选项已关闭，则用户只能使用建议的默认标记。 如果关闭此功能，请确保添加一个或多个默认标记。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理团队的自定义标记设置

如果启用"允许团队所有者替代谁可以管理Microsoft Teams管理中心"设置，团队所有者可以设置成员是否可以在团队级别添加标记。 为此，在团队的设置选项卡上，转到"标记 **"，然后选择** 可以添加标记的人。

![团队级别的标记设置的屏幕截图。](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用标记

下面将了解如何添加自定义标记，以及如何在应用中使用 Shifts (Shifts 应用，通过 shift Teams) 。 若要了解有关详细信息，请查看使用[Teams 中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>创建和分配自定义标记

若要创建和分配自定义标记，请选择 **Teams** 左侧的标记，然后在列表中查找你的团队。 选择 **"""更多选项"，** 然后选择"**管理标记"。** 可在此处创建标记并将其分配给团队中的人员。

![如何在客户端 中应用标记的Teams屏幕截图。](media/manage-tags-teams.png)

若要删除标记，请选择 **标记旁边的"""更多选项**"，然后选择"删除 **标记"。**

### <a name="set-up-tagging-by-shift"></a>按 Shift 设置标记

按 shift 标记允许用户实时联系轮班人员。 Teams分配标记与计划匹配的用户，从 Shifts 应用转移组名称，从而启用动态的基于角色的消息传送。 通知仅发送给使用标记开始聊天或频道帖子时轮班的人。 

1. 在Teams，转到[Shifts 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 创建 [班次组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，并基于角色等属性命名。 例如，EngineerOnCall。 班次组名称将是标记的名称。
3. [通过向团队成员](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 分配班次来填写日程安排。 完成后，在 Shifts 应用的右上角，选择"**与团队共享"。**
4. 等待 15 分钟，让计划的排班填充标记服务。
5. 在任意位置使用标记，在 Teams。

## <a name="related-topics"></a>相关主题

[在 Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中为组织管理排班应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
