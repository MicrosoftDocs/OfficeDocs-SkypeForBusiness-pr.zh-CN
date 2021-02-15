---
title: 在 Microsoft Teams 中创建自定义团队模板
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中创建自定义团队模板。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f22b2c53ab6f3c3c90e1720313c135c2106b1a49
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196526"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>在 Microsoft Teams 中创建自定义团队模板

**EDU 客户尚不支持自定义模板。**

自定义团队模板是一个预定义的团队结构，包含一组频道、选项卡和应用。 可以开发一个模板来帮助你快速创建正确的协作空间。 自定义团队模板使用首选设置。  

若要开始，请：

1. 登录到 Teams 管理中心。

2. 在左侧导航栏中，展开 **Teams**  >  **团队模板**。

3. 单击“**添加**”。

![突出显示"添加"的"团队模板"对话框的图像。](media/team-templates-new.png)

4. 在"**团队模板"** 部分中，选择 **"创建全新的模板"。**

5. 在"**模板设置"** 部分中，完成以下字段，然后单击"下 **一步"：**
    - 模板名称
    - 模板简短和长说明
    - 区域设置可见性  

!["团队模板设置命名"对话框的图像。](media/template-add-a-name.png)

6. 在 **频道、选项卡和应用** 部分中，添加团队所需的任何频道和应用。

    1. 在"**频道"部分中**，单击"**添加"。**
    2. 在" **添加"** 对话框中，为频道命名。
    3. 添加说明。
    4. 确定是否默认应显示频道。
    5. 搜索要添加到通道的应用名称。
    6. 完成后 **单击"** 应用"。

![团队模板频道、选项卡和应用屏幕的图像。](media/template-channels-tabs-apps.png)

8. 完成后 **单击** "提交"。

新模板显示在"团队 **模板"** 列表中。 该模板可用于在 Teams 中创建团队。

> [!Note]
> 团队用户最多可能需要 24 小时才能在库中查看自定义模板。

## <a name="known-issues"></a>已知问题 

**问题**：如果已基于包含其他自定义选项卡的自定义模板创建了团队，则可能会看到空白选项卡，以用于自定义选项卡应用。 默认选项卡 (如帖子、文件和 **Wiki** ) 按预期显示。

**解决方案**：如果已基于包含其他自定义选项卡的自定义模板创建了团队，则可能会看到空白选项卡，以用于自定义选项卡应用。 默认选项卡 (如帖子、文件和 Wiki) 按预期显示。

若要解决此问题，请删除自定义选项卡，并使用相同的应用添加新选项卡。 如果您没有权限删除自定义选项卡并添加新选项卡，请联系团队所有者，让他们这样做。

我们目前正在为将来从自定义模板创建的团队开发修补程序。

## <a name="related-topics"></a>相关主题

- [管理中心中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)
