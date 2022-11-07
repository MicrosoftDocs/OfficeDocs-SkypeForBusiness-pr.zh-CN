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
description: 了解如何在 Microsoft Teams 中管理组织中的标记使用方式。
ms.openlocfilehash: 56a2daf53c362accec8059b11fba400547a7b6ff
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869557"
---
# <a name="manage-tags-in-microsoft-teams"></a>在 Microsoft Teams 中管理标记

Microsoft Teams 中的标记允许用户快速轻松地与团队中的一部分人员联系。 可以创建和分配自定义标记，以便根据角色、项目、技能或位置等属性对人员进行分类。 或者，可以根据排 [班应用中](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6)的日程安排和排班信息自动将标记分配给人员。 将标记添加到一个或多个团队成员后，团队中的任何人在频道帖子中都可以在@mentions，以仅通知已分配该聊天标记的人员。

如果你是团队所有者，并且想要管理团队中的标记，请参阅 [在 Teams 中使用标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

如前所述，Teams 中有两种类型的标记。

- **自定义标记**：团队所有者和团队成员 (，如果他们具有) 可以手动创建标记并将其分配给人员的权限。 例如，“Designer”或“放射科医生”标记将到达团队中的这些人员集，而无需键入其姓名。
- **按班次标记**：使用此功能，系统会自动为人员分配与其在 Teams 中的排 [班应用中](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) 与其日程安排和班次组名称匹配的标记。 例如，“EngineerOnCall”标记将到达在聊天或频道帖子中使用标记时安排在班次中工作的所有工程师。 通过逐班标记，当用户需要快速传递信息时，Teams 无需猜测轮班员工的姓名。

> [!NOTE]
> 专用或共享频道不支持标记。

## <a name="how-tags-work"></a>标记的工作原理

标记可以手动添加 (自定义标记) ，或者通过在排班应用中设置排班) 自动分配给特定团队 (的人员。 然后，可以在聊天中的“ **To** ”行@mentions或团队任何标准频道上的帖子中使用该标记。 下面是如何在 Teams 中使用标记的一些示例：

- 商店经理将公告发布到频道，以通知所有收银员。
- 医院管理员在频道中向所有放射科医生发送消息。
- 营销经理开始与所有设计人员的群组聊天。
- 护士向所有待命心脏病专家发送消息。
- 系统工程师将公告发布到频道，以通知所有轮班现场工程师。

在频道对话中@mentioned标记时，与该标记关联的团队成员将收到通知，就像任何其他@mention一样。

## <a name="manage-tags-for-your-organization"></a>管理组织的标记

作为管理员，可以在 Microsoft Teams 管理中心控制整个组织中的标记使用方式。 请注意，不能使用 PowerShell 来管理标记。

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Microsoft Teams 管理中心中的标记设置的屏幕截图。":::

一个团队最多可以有 100 个标记，最多可以将 200 个团队成员分配到一个标记，同一团队中最多可以有 25 个标记分配给单个用户。

### <a name="set-who-can-manage-tags"></a>设置谁可以管理标记

默认情况下，团队所有者可以创建、编辑和删除标记。 可以更改 **“谁可以管理标记** ”设置以允许团队所有者和团队成员管理标记，也可以关闭组织的标记。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击“ **Teams** \> **Teams 设置**”。

2. 在 **“标记”** 下的“ **谁可以管理标记**”旁边，选择以下选项之一：

    - **团队所有者和成员**：允许团队所有者和成员管理标记。
    - **团队所有者**：允许团队所有者管理标记。
    - **未启用**：关闭标记。

### <a name="configure-tagging-settings"></a>配置标记设置

可以配置以下标记设置，以控制如何在组织中使用标记。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击“ **Teams** \> **Teams 设置**”。

2. 在 **“标记”** 下，根据组织的需要设置以下内容。

    - **团队所有者可以更改谁可以管理标记**：启用此设置时，团队所有者可以设置团队成员是否可以在团队中创建和管理标记，并且“ **谁可以管理标记”** 设置的值是每个团队的默认值。 如果关闭此设置，则无法更改每个团队 **的“谁可以管理标记** ”设置。
    - **建议的标记**：使用此标记可添加一组默认标记。 最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。 团队所有者和成员 (是否为他们启用了此功能) 可以使用这些建议、向其添加或创建新的标记集。
    - **自定义标记**：启用此设置可让用户添加除你设置的建议默认标记以外的标记。 如果此功能处于关闭状态，则用户只能使用建议的默认标记。 如果关闭此功能，请确保添加一个或多个默认标记。
    - **排班应用可以应用标记**：启用此设置，使排班应用能够自动向轮班人员实时分配标记。 这些标记将与排班中的用户计划和组名称匹配。 通知仅发送给在聊天或频道帖子中使用标记时轮班的人员。

## <a name="related-topics"></a>相关主题

[管理排班应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[排班帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
