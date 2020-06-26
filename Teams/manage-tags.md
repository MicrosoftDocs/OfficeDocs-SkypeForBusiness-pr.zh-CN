---
title: 管理 Microsoft 团队中的标记
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
ms.openlocfilehash: b19613268384831aaaa2608fc183b62fdc1b0445
ms.sourcegitcommit: 0979fae58ecd713f8317ed99caae015b5cc2c8e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44877933"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft 团队中的标记

Microsoft 团队中的标记使用户能够与团队中的一部分人员进行通信。 可将标记添加到一个或多个团队成员，以便轻松地与用户的正确子集连接。 团队所有者和成员（如果为其启用了该功能）可以向某个人员添加一个或多个标记。 然后，这些标记可在频道发布中由团队的任何人 @mentions，或者仅与分配了该标记的人员开始对话。

> [!NOTE]
> 专用频道尚不支持标记。 在美国政府社区云（GCC）、GCC 高或国防（DoD）组织中尚不提供标记。

## <a name="how-tags-work"></a>标记的工作方式

可以向特定团队中的人员添加标记。 添加标记后，可以在聊天中的 @mentions 或团队的任何标准频道中使用。 下面是如何在团队中使用标记的一些示例：

- 商店经理希望向频道发布公告并通知所有出纳。
- 组产品经理希望向频道中的所有产品经理发送消息。
- 医院管理员想要向频道中的所有 radiologists 发送一封邮件。
- 市场营销经理希望开始与所有设计人员进行群组聊天。

当标记在频道对话中 @mentioned 时，与该标记相关联的团队成员将收到通知，就像任何其他 @mention 一样。

若要了解详细信息，请参阅[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

## <a name="manage-tags-for-your-organization"></a>管理你的组织的标记

作为管理员，你可以控制哪些人可以添加标签，以及如何在 Microsoft 团队管理中心中跨你的组织使用标记。

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

一个团队最多可以有100个标记，最多可以向100个团队成员分配一个标记，并且可以将最多25个标记分配给单个用户。 

### <a name="set-who-can-add-tags"></a>设置可以添加标记的人员

默认情况下，团队所有者可以添加标记。 你可以更改此设置以允许团队所有者和团队成员添加标记，也可以关闭你的组织的标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。
2. 在 "**标记**" 下，在 "**标记已启用**" 旁边，选择下列选项之一：

    - **团队所有者和成员**：允许团队所有者和成员添加标记。
    - **团队所有者**：允许团队所有者添加标记。
    - **已禁用**：关闭标记。

### <a name="configure-tags-settings"></a>配置标签设置

你可以配置以下标记设置以控制如何在组织中使用标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。
2. 在 "**标记**" 下，根据组织的需要设置以下各项。

    - **团队所有者可以覆盖可以应用标记的人员**：当启用此功能时，团队所有者可以允许或禁止成员在团队设置中添加标记。
    - **成员可以添加其他标记**：如果允许团队成员添加标记，请启用此设置，让团队成员添加除了所设置的建议默认标记以外的其他标记。 如果关闭此功能，团队成员只能使用默认标记。
    - **建议的默认标记**：使用此项添加一组默认标记。 您最多可以添加25个标签，每个标签最多可以包含25个字符。 团队所有者和成员（如果为其启用了该功能）可以使用这些建议、添加到这些建议或创建新的标记集。

## <a name="manage-tags-settings-for-a-team"></a>管理团队的标记设置

如果已打开**团队所有者可以覆盖**Microsoft 团队管理中心中可以应用 "标记" 设置的人员，团队所有者可以设置成员是否可以在团队级别添加标记。 若要执行此操作，请在团队的 "**设置**" 选项卡上，转到 "**标记**"，然后选择可以添加标记的人员。

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用标记

### <a name="add-tags"></a>添加标记

若要创建和分配标记，请选择应用左侧的 "**团队**"，然后在列表中找到您的团队。 选择 "**更多选项**"，然后选择 "**管理标记**"。

在此处，你可以创建标记并将其分配给团队中的人员。

![如何在团队客户端应用标记的屏幕截图 ](media/manage-tags-teams.png)

### <a name="delete-tags"></a>删除标记

删除与标记相关联的所有团队成员，标记将被删除。

## <a name="related-topics"></a>相关主题

[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)
