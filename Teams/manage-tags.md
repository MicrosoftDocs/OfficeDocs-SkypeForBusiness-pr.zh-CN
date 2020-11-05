---
title: 管理 Microsoft 团队中的标记
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队中管理组织中如何使用标记。
ms.openlocfilehash: 718a2401aa8e015a6dec2b6a4c6116a567aaf82d
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919054"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft 团队中的标记

> [!NOTE]
> 本文中讨论的功能之一是 " **按班次标记** "，尚未发布。 已宣布，即将推出。 如果您是管理员，则可以在 ([Microsoft 365 管理中心](https://portal.office.com/adminportal/home) ") 中的" 邮件中心 "中看到此功能的发布时间。 若要保持在即将到来的团队功能上，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="overview"></a>概述

Microsoft 团队中的标记使用户可以快速轻松地与团队中的一部分人员连接。 你可以创建和分配自定义标记，以便根据属性（如角色、项目、技能或位置）对人员进行分类。 或者，可以根据其日程安排将标记自动分配给人员，并在 " [倒班" 应用](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 中将信息移动 (即将推出) 。 将标记添加到一个或多个团队成员后，可在频道发布中由团队中的任何人使用 @mentions 或开始与分配了该标记的人员进行对话。

正如前面所述，团队中有两种类型的标记。

- **自定义标记** ：团队所有者和团队成员 (如果为其启用了功能) 可以手动创建标签并将其分配给人员。 例如，"设计者" 或 "Radiologist" 标记将与团队中的用户组联系，而无需键入他们的姓名。
- 通过 " (即将推出") 中 **的 "添加标签** "：使用此功能，将自动向人员分配与团队中的 [倒班应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)中的计划和班次组名称相匹配的标记。 例如，当在聊天或频道发布中使用标记时，"EngineerOnCall" 标记将达到安排的所有工程师的工作时间。 使用 "按 shift 进行标记"，当用户需要快速中继信息时，团队将不知道班次轮换人员的姓名。 通过 shift 进行标记还可以由主要劳动力管理系统（如 JDA、Kronos 和 AMiON）进行支持，方法是将其与团队中的倒班集成。 若要了解有关如何设置此功能的详细信息，请参阅 [通过 Shift 设置标记](#set-up-tagging-by-shift-coming-soon)。

> [!NOTE]
> 专用频道尚不支持标记。 在美国政府社区云 (GCC) 、GCC 高或国防 (DoD) 组织中尚不提供标记。 

## <a name="how-tags-work"></a>标记的工作方式

标记可手动添加或自动分配给特定团队中的人员。 然后，可以在 "收件人" 行上的 " **收件人** " 行中使用它，或在团队的任何标准频道中的帖子中 @mentions 使用它。 下面是如何在团队中使用标记的一些示例：

- 商店经理向频道发布公告以通知所有出纳。
- 医院管理员向频道中的所有 radiologists 发送一条消息。
- 市场营销经理开始与所有设计人员进行群组聊天。
- 护士将一封邮件发送给所有待命电话 cardiologists。 （即将推出）
- 系统工程师将公告发布到频道以通知所有现场活动工程师。 （即将推出）

当标记在频道对话中 @mentioned 时，与该标记相关联的团队成员将收到通知，就像任何其他 @mention 一样。

## <a name="manage-custom-tags-for-your-organization"></a>管理你的组织的自定义标记

作为管理员，你可以控制在 Microsoft 团队管理中心的组织内使用标记的方式。 目前，您无法使用 PowerShell 来管理标记。

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

一个团队最多可以有100个标记，最多可以向100个团队成员分配一个标记，并且可以将最多25个标记分配给单个用户。 

### <a name="set-who-can-add-custom-tags"></a>设置可添加自定义标记的人员

默认情况下，团队所有者可以添加自定义标记。 你可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭你的组织的标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 " **组织范围设置** "  >  **团队设置** 。
2. 在 **"标记"** 下的 "标记" 的 " **管理方式** " 下，选择下列选项之一：

    - **团队所有者和成员** ：允许团队所有者和成员管理标记。
    - **团队所有者** ：允许团队所有者管理标记。
    - **已禁用** ：关闭标记。

### <a name="configure-custom-tags-settings"></a>配置自定义标记设置

你可以配置以下标记设置以控制如何在组织中使用自定义标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 " **组织范围设置** "  >  **团队设置** 。
2. 在 " **标记** " 下，根据组织的需要设置以下各项。

    - **让团队所有者覆盖可以管理标记的人员** ：启用此设置后，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，并且 **通过设置管理标记** 的值是每个团队的默认值。 如果关闭此设置，则通过无法更改每个团队的设置 **来管理标记** 。
    - **建议的默认标记** ：使用此项添加一组默认标记。 您最多可以添加25个标签，每个标签最多可以包含25个字符。 团队所有者和成员 (如果为其启用了该功能) 可以使用这些建议、添加到它们或创建新的标记集。
    - **创建自定义标记** ：启用此设置可让用户添加除了所设置的建议默认标记以外的其他标记。 如果关闭此功能，则用户只能使用建议的默认标记。 如果关闭此功能，请确保添加一个或多个默认标记。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理团队的自定义标记设置

如果你在 Microsoft 团队管理中心中启用了 " **让团队所有者覆盖哪些人可以管理标记** " 设置，团队所有者可以设置成员是否可以在团队级别添加标记。 若要执行此操作，请在团队的 " **设置** " 选项卡上，转到 " **标记** "，然后选择可以添加标记的人员。

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用标记

下面介绍了如何添加自定义标记，以及如何在使用团队) 中的 "倒班" 应用时按 shift (设置标记。 若要了解详细信息，请参阅 [使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>创建和分配自定义标记

若要创建和分配自定义标记，请选择应用左侧的 " **团队** "，然后在列表中找到您的团队。 选择 **̇̇̇更多选项** ，然后选择 " **管理标记** "。 在此处，你可以创建标记并将其分配给团队中的人员。

![如何在团队客户端应用标记的屏幕截图 ](media/manage-tags-teams.png)

若要删除标记，请选择标记旁边的 **̇̇̇更多选项** ，然后选择 " **删除标记** "。

### <a name="set-up-tagging-by-shift-coming-soon"></a>通过 (即将推出的班次) 设置标记

1. 在 "团队" 中，转到 " [移动" 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 创建 [shift 组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 并将其命名为一个属性（如角色）。 例如，EngineerOnCall。 Shift 组名称将是该标记的名称。
3. 通过向团队成员分配倒班来[填写日程](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)。 完成后，在 "移动" 应用的右上角，选择 " **与团队共享** "。
4. 等待15分钟，安排的班次填充标记服务。
5. 在团队中使用标记的任意位置使用标记。

通过 shift 进行标记使你的用户能够实时联系到人员进行中的班次。 通知仅发送给在使用标记开始聊天或频道发布时具有班次的人员。

## <a name="related-topics"></a>相关主题

[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中为组织管理排班应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[班次帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
