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
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034489"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft 团队中的标记

> [!NOTE]
> 尚未在 Microsoft 团队管理中心中看到此功能？ 当前正在推出此功能，可能在贵组织中还不可用。 若要保持在即将到来的团队功能上，请查看[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

Microsoft 团队中的标记使用户能够与团队中的一部分人员进行通信。 可将标记添加到一个或多个团队成员，以便轻松地与用户的正确子集连接。 团队所有者和成员（如果为其启用了该功能）可以向某个人员添加一个或多个标记。 然后，可在频道发布 @mentions 由团队中的任何人使用，以便仅与分配了该标记的人员进行通信。

> [!NOTE]
> 专用频道尚不支持标记。

## <a name="how-tags-work"></a>标记的工作方式

可以向特定团队中的人员添加标记。 添加标记后，可以在团队的任何标准频道 @mentions 中使用。 下面是如何在团队中使用标记的一些示例：

- 商店经理希望向频道发布公告并通知所有出纳。
- 组产品经理希望向频道中的所有产品经理发送消息。
- 医院管理员想要向频道中的所有 radiologists 发送一封邮件。

若要了解详细信息，请参阅[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

## <a name="manage-tags-for-your-organization"></a>管理你的组织的标记

作为管理员，你可以控制哪些人可以添加标签，以及如何在 Microsoft 团队管理中心中跨你的组织使用标记。

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>设置可以添加标记的人员

默认情况下，团队所有者可以添加标记。 你可以更改此设置以允许团队所有者和团队成员添加标记，也可以关闭你的组织的标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置** > "**团队设置**。
2. 在 "**标记**" 下，在 "**标记已启用**" 旁边，选择下列选项之一：

    - **团队所有者和成员**：允许团队所有者和成员添加标记。
    - **团队所有者**：允许团队所有者添加标记。
    - **已禁用**：关闭标记。

### <a name="configure-tags-settings"></a>配置标签设置

你可以配置以下标记设置以控制如何在组织中使用标记。

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置** > "**团队设置**。
2. 在 "**标记**" 下，根据组织的需要设置以下各项。

    - **团队所有者可以覆盖可以应用标记的人员**：当启用此功能时，团队所有者可以允许或禁止成员在团队设置中添加标记。
    - **成员可以添加其他标记**：如果允许团队成员添加标记，请启用此设置，让团队成员添加除了所设置的建议默认标记以外的其他标记。 如果关闭此功能，团队成员只能使用默认标记。
    - **建议的默认标记**：使用此项添加一组默认标记。 您最多可以添加25个标签，每个标签最多可以包含25个字符。 团队所有者和成员（如果为其启用了该功能）可以使用这些建议、添加到这些建议或创建新的标记集。

## <a name="manage-tags-settings-for-a-team"></a>管理团队的标记设置

如果已打开**团队所有者可以覆盖**Microsoft 团队管理中心中可以应用 "标记" 设置的人员，团队所有者可以设置成员是否可以在团队级别添加标记。 若要执行此操作，请在团队的 "**设置**" 选项卡上，转到 "**标记**"，然后选择可以添加标记的人员。

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>在团队中添加标记

在团队中，团队的 "管理团队" 页面的 "**成员**" 选项卡包括 "**标记**" 列。 团队所有者和成员（如果为其启用了该功能）可以单击成员旁边的 "**管理标记**"，以查看该成员的建议标记列表，并将标记添加到列表中。

![如何在团队客户端应用标记的屏幕截图 ](media/manage-tags-teams.png) 
