---
title: 在 Microsoft Teams 中管理标记
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
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中管理标记在组织的使用方式。
ms.openlocfilehash: e5222a820a3a721c3692b0cdb272d1c4f3aaea6d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145849"
---
# <a name="manage-tags-in-microsoft-teams"></a>在 Microsoft Teams 中管理标记

> [!NOTE]
> 本文讨论的功能之一（ **按 Shift** 标记）正在推出。如果你是管理员，可以在 [Microsoft 365](https://portal.office.com/adminportal/home) 管理中心内的消息中心 (了解此功能何时针对你的区域) 。 若要随时了解即将推出的 Teams 功能，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="overview"></a>概述

Microsoft Teams 中的标记允许用户快速轻松地与团队中的一部分人员联系。 可以创建和分配自定义标记，以便根据属性（例如角色、项目、技能或位置）对人员进行分类。 或者，标记可以基于其日程安排自动分配给人员，并且 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 应用中的班次信息 (即将推出) 。 将标记添加到一个或多个团队成员后，团队中任何在频道帖子中的人都可以在 @mentions 中使用标记，或者仅与分配了该标记的人开始对话。

如前所述，Teams 中有两种类型的标记。

- **自定义标记**：团队所有者和 (如果为其启用了该功能，) 手动创建标记并将其分配给人员。 例如，"Designer"或"Radi一"标记将到达团队中的这些人员集，而无需键入其姓名。
- **按班次标记**：使用此功能，系统会自动为用户分配与 Teams 中的 Shifts 应用中其日程安排和 [排班组名称匹配的](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 标记。 例如，在聊天或频道帖子使用标记时，"EngineerOnCall"标记将到达在 Shifts 中安排工作的所有工程师。 使用按轮班标记时，当用户需要快速中继信息时，Teams 无需知道轮班员工的姓名，因此无需猜测。 通过将主要员工管理系统（如 JDA、Kronos 和 AMiON）与 Teams 中的 Shifts 集成，也可以支持按班次进行标记。 若要详细了解如何设置此功能，请参阅"按 Shift[设置标记"。](#set-up-tagging-by-shift)

> [!NOTE]
> 专用通道尚不支持标记。 标记将推出到美国政府社区云 (GCC) 。 标记在 GCC High 或国防部 (DoD) 不可用。 

## <a name="how-tags-work"></a>标记工作

可以手动添加标记或自动将标记分配给特定团队中的人员。 然后，它可以在聊天@mentions的"至"行上或在团队的任何标准频道上的帖子中使用。 下面是在 Teams 中如何使用标记的一些示例：

- 商店经理向频道发布通知，通知所有收银员。
- 医院管理员向频道的所有辐射人员发送消息。
- 营销经理开始与所有设计人员进行群组聊天。
- 一名医生向所有通话医生发送消息。 （即将推出）
- 系统工程师向频道发布公告，通知所有轮班现场工程师。 （即将推出）

当标记在@mentioned对话中时，与标记关联的团队成员将收到通知，就像任何其他@mention。

## <a name="manage-custom-tags-for-your-organization"></a>管理组织的自定义标记

作为管理员，可以在 Microsoft Teams 管理中心控制整个组织的标记使用方式。 目前，无法通过 PowerShell 管理标记。

![Microsoft Teams 管理中心中标记设置的屏幕截图](media/manage-tags-admin-settings.png)

一个团队可以有多达 100 个标记，最多 100 个团队成员可以分配到一个标记，最多 25 个标记可以分配给单个用户。 

### <a name="set-who-can-add-custom-tags"></a>设置谁可以添加自定义标记

默认情况下，团队所有者可以添加自定义标记。 您可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭组织的标记。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"组织范围的** 设置  >  **Teams 设置"。**
2. 在 **"标记**" **下，选择** 以下选项之一作为"标记管理者"：

    - **团队所有者和成员**：允许团队所有者和成员管理标记。
    - **团队所有者**：允许团队所有者管理标记。
    - **已禁用**：关闭标记。

### <a name="configure-custom-tags-settings"></a>配置自定义标记设置

可以配置以下标记设置来控制如何在组织中使用自定义标记。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"组织范围的** 设置  >  **Teams 设置"。**
2. 在 **"标记**"下，根据组织的需要设置以下内容。

    - 让团队所有者替代谁可以管理标记：启用此设置时，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，而"标记"的值通过设置为每个团队的默认值进行管理。 如果关闭此设置，则不能按团队 **通过设置** 管理标记。
    - **建议的默认标记**：用于添加一组默认标记。 最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。 如果为 (启用该功能，团队所有者和成员) 可以使用这些建议、将其添加到建议或创建一组新的标记。
    - **允许创建自定义标记**：启用此设置，以允许用户添加您设置的建议默认标记外的其他标记。 如果此选项已关闭，则用户只能使用建议的默认标记。 如果将其关闭，请确保添加一个或多个默认标记。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理团队的自定义标记设置

如果启用"允许团队所有者 **替代谁可以** 管理 Microsoft Teams 管理中心中的标记设置"，团队所有者可以设置成员是否可以在团队级别添加标记。 为此，在团队的"设置"选项卡上，转到"标记"，然后选择可以添加标记的人。

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用标记

下面将了解如何添加自定义标记，以及如何在 Teams (中的 Shifts 应用时通过 shift) 设置标记。 若要了解有关详细信息，请查看"使用[Teams 中的标记"。](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

### <a name="create-and-assign-custom-tags"></a>创建和分配自定义标记

若要创建和分配自定义标记，请选择应用左侧的 **Teams，** 然后在列表中查找你的团队。 选择 **" 1 个"更多选项**，然后选择"**管理标记"。** 在这里，你可以创建标记并将其分配给团队中的人员。

![如何在 Teams 客户端中应用标记的屏幕截图 ](media/manage-tags-teams.png)

若要删除标记，请选择 **该标记旁边的 10** 个"更多"选项，然后选择"**删除标记"。**

### <a name="set-up-tagging-by-shift"></a>按 Shift 设置标记

1. 在 Teams 中，转到 [Shifts 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 创建 [班次组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，并基于角色等属性命名。 例如，EngineerOnCall。 班次组名称将是标记的名称。
3. [通过向团队成员](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 分配排班来填写日程安排。 完成后，在 Shifts 应用的右上角，选择"与 **团队共享"。**
4. 等待 15 分钟，让计划的排班填充标记服务。
5. 在 Teams 中你使用标记的任何位置使用标记。

按 Shift 标记可让用户实时联系轮班人员。 通知仅发送给使用标记开始聊天或频道帖子时轮班的人。

## <a name="related-topics"></a>相关主题

[在 Teams 中使用标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中为组织管理排班应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
