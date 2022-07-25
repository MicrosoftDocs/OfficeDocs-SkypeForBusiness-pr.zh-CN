---
title: Adobe Acrobat 作为 Teams 中的默认 PDF 查看器
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: 了解如何将 Adobe Acrobat 设置为默认的 PDF 查看器，以便在 Microsoft Teams 中查看和编辑 PDF 文件。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002333"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat 作为 Teams 中的默认 PDF 查看器

> [!NOTE]
> Adobe Acrobat 作为 Teams 中的默认 PDF 体验目前仅在公共预览版中提供。 在使用此功能之前，为租户[启用公共预览](public-preview-doc-updates.md#enable-public-preview)版。 确保最终用户将 Teams 客户端版本更改为公共预览版，以体验 Adobe Acrobat 作为 Teams 中的 PDF 查看器。

作为管理员，可以将 Adobe Acrobat 设置为默认应用，以便在 Microsoft Teams 中查看和编辑 PDF 文件。 最终用户不需要 Adobe Acrobat 订阅或 Adobe ID 即可查看、搜索、注释和批注 PDF 文件。

## <a name="set-up-adobe-acrobat-app"></a>设置 Adobe Acrobat 应用

若要将 Adobe Acrobat 设置为默认应用以查看 PDF 文件，请执行以下步骤：

1. 登录到 Teams 管理中心并转到 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 搜索 Adobe Acrobat 应用，然后选择 **Adobe Acrobat** 应用。

   > [!NOTE]
   >
   > * 确保 Adobe Acrobat 应用状态设置为 **“允许**”。 否则，启用 **“允许** ”切换。
   > * 如果应用权限策略或组织范围的应用设置中存在阻止应用的任何现有管理员设置，请确保在 [应用权限策略](teams-app-permission-policies.md) 或 [组织范围的应用设置](teams-app-permission-policies.md)中允许应用。

1. 在“ **权限”** 选项卡中，选择 **“审阅”权限**。

1. 选择 **“接受**”。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 管理中心中应用权限的屏幕截图。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>为所有用户安装 Adobe Acrobat 应用

可以使用全局 (组织范围的默认) 策略来分配 Adobe Acrobat 应用并使其可供所有用户使用。 此步骤在 Teams 中触发一个信号，将应用设置为 PDF 文件的默认文件处理程序。 若要为所有用户分配 Adobe Acrobat 应用，请执行以下步骤：

1. 在 Teams 管理中心，转到 **Teams 应用** > [**设置策略**](https://admin.teams.microsoft.com/policies/app-setup)。

1. 在 **“管理策略** ”选项卡下，选择 **全局 (组织范围的默认)**，然后选择 **“编辑**”。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 管理中心中 Adobe Acrobat 应用的设置策略的屏幕截图。":::

1. 在“已安装的应用”下，选择 **“添加应用**”。

1. 搜索 **Adobe Acrobat**，选择应用名称旁边的 **“添加** ”，然后选择 **“添加**”。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="显示如何为所有用户添加 Adobe Acrobat 应用的屏幕截图。" lightbox="media/add-adobe-acrobat-app.png":::

1. 选择“**保存**”。

选择保存后，Adobe Acrobat 应用将配置为使用 Teams 从聊天、频道或文件应用打开 Adobe Acrobat 应用中的任何 PDF 文件。

如果希望有选择地允许几个特定个人或组使用 Adobe Acrobat 应用，则可以分配 [自定义应用权限策略](teams-app-permission-policies.md)。

了解有关此功能的以下信息：

* 设置策略后，应用通常需要 [几个小时](teams-app-setup-policies.md) 才能可供用户使用。
设置策略后，安装的应用在几个小时后可供用户使用。
* 查看固定在频道中的 PDF 文件作为选项卡，并在工作分配应用中查看 PDF 文件继续由本机 Teams 体验提供支持。
* 作为 Teams 中的默认 PDF 查看器的 Adobe Acrobat 仅适用于桌面和 Web 客户端。 移动客户端不支持此功能。
* 用户需要 Adobe Acrobat 计划才能使用高级工具，例如导出 PDF、组织页面、合并文件、压缩 PDF 和保护 PDF。

> [!NOTE]
> 在 Teams 桌面客户端中，如果在登录 Adobe Acrobat 应用时遇到任何问题，可以在浏览器中打开 Teams 并登录。 这是已知问题，将于 2022 年 9 月解决。

## <a name="faqs"></a>常见问题 解答

* 如何从 Teams 客户端中删除 Adobe Acrobat 应用？
  
  最终用户可以从 Teams 客户端卸载应用，管理员可以从安装策略中删除 Adobe Acrobat 应用。

* 管理员在将 Adobe Acrobat 应用设置为默认处理程序后，是否可以阻止它？
  
  是的，但在管理员阻止应用之前，请删除设置策略，以确保最终用户安全地恢复到 Teams 默认体验。
