---
title: 在 Microsoft Teams 中创建自定义团队模板
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中创建自定义团队模板。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c99fc2ebedac1372beff283ccbcf057c0bfdf78b
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198514"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>在 Microsoft Teams 中创建自定义团队模板

**EDU 客户尚不支持自定义模板。**

自定义团队模板是具有一组频道、选项卡和应用的预定义团队结构。 可以开发一个模板，帮助你快速创建正确的协作空间。 自定义团队模板使用首选设置。  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


若要开始使用，请：

1. 登录到 Teams 管理中心。

2. 在左侧导航中，展开 **“Teams** > **团队模板**”。

3. 选择“**添加**”。

    ![“团队模板”对话框的图像，其中突出显示了“添加”。](media/team-templates-new.png)

4. 在 **“团队模板** ”部分中，选择“ **创建全新的模板**”。

5. 在 **“模板设置”** 部分中，完成以下字段，然后选择“ **下一步**”：
    - 模板名称
    - 模板短说明和长说明
    - 区域设置可见性  

    ![“团队模板设置命名”对话框的图像。](media/template-add-a-name.png)

6. 在 **频道、选项卡和应用** 部分中，添加团队所需的任何频道和应用。

    1. 在“ **通道** ”部分中，选择“ **添加**”。
    2. 在 **“添加** ”对话框中，为通道命名。
    3. 添加说明。
    4. 确定是否应默认显示通道。
    5. 搜索要添加到通道的应用名称。
    6. 完成后，选择“ **应用** ”。

    ![团队模板频道、选项卡和应用屏幕的图像。](media/template-channels-tabs-apps.png)

8. 完成后，选择“ **提交** ”。

新模板将显示在 **“团队模板** ”列表中。 该模板可用于在 Teams 中创建团队。

> [!Note]
> 团队用户最长可能需要 24 小时才能在库中查看自定义模板更改。

## <a name="customizing-website-tab-apps"></a>自定义网站选项卡应用

> [!Note]
> 此功能处于早期预览阶段

你可能希望为自定义团队模板中的频道指定网站选项卡的 URL。 使用模板创建团队的最终用户将具有预设到指定网站 URL 的网站选项卡。

若要开始使用，请：

1. 创建新的团队模板或编辑现有团队模板。

2. 在“频道”部分中，添加新频道或选择现有频道，然后选择 **“编辑**”。

3. 在 **“为此模板添加应用** ”部分中，添加“网站”应用。

    ![为此模板选项添加应用。](media/add-an-app-template.png)

4. 选择编辑图标并输入所选的 URL。

    ![添加应用 URL。](media/add-url-app-template.png)

5. 为选项卡应用编辑选择 **“保存** ”，然后选择“ **应用** ”以保存更改。

## <a name="known-issues"></a>已知问题

**问题**：如果已从包含其他自定义选项卡的自定义模板创建团队，则可能会看到空白选项卡代替自定义选项卡应用。 默认选项卡 (（如 **帖子**、 **文件和** **Wiki**) ）将按预期显示。

**解决方案**：若要解决此问题，请删除自定义选项卡，并添加具有相同应用的新选项卡。 如果无权删除自定义选项卡并添加新选项卡，请联系团队所有者寻求帮助。

我们目前正在为从自定义模板创建的未来团队开发一个修补程序。

**问题**：在浏览器中使用 Teams 时，某些网站不支持在 Teams 选项卡中呈现。

![浏览器错误消息。](media/browser-error-message.png)

**解决方案**：如果无法查看网站选项卡的内容，则会重定向到在单独的网页中打开选项卡，或者在桌面应用中打开 Teams 来查看网站选项卡应用。

## <a name="related-topics"></a>相关主题

- [管理中心中的团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)
- [从现有团队创建模板](create-template-from-existing-team.md)
- [从现有团队模板创建团队模板](create-template-from-existing-template.md)
