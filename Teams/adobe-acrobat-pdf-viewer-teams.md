---
title: 在 Teams 中 Adobe Acrobat 作为默认 PDF 查看器
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
description: 了解如何将 Adobe Acrobat 设置为默认 PDF 查看器，以便在 Microsoft Teams 中查看和编辑 PDF 文件。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 88babd01496738825cbe655215532e311a32f541
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270877"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>在 Microsoft Teams 中 Adobe Acrobat 作为默认 PDF 查看器

> [!NOTE]
> Adobe Acrobat 作为 Microsoft Teams 中的默认 PDF 体验目前仅在公共预览版中提供。 若要使用此功能，管理员必须为其租户 [启用公共预览版](public-preview-doc-updates.md#enable-public-preview)，并确保最终用户将 Teams 客户端版本更改为公共预览版。

作为管理员，你可以将 Adobe Acrobat 设置为默认应用，以便在 Microsoft Teams 中查看和编辑 PDF 文件。 最终用户可以查看、搜索、注释和批注 PDF 文件，而无需 Adobe Acrobat 订阅或 Adobe ID。

若要将 Adobe Acrobat 应用配置为租户中 PDF 文件的默认处理程序，请完成以下先决条件步骤：

* [允许 Adobe Acrobat 应用](#allow-adobe-acrobat-app-in-your-tenant)。
* [安装 Adobe Acrobat 应用](#install-adobe-acrobat-app-for-all-users)。

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>允许租户使用 Adobe Acrobat 应用

在设置应用之前，请确保允许在租户中使用该应用，即明确允许 Adobe Acrobat 应用，且应用权限策略允许该应用。 若要将 Adobe Acrobat 设置为 PDF 文件的默认应用，请执行以下步骤：

1. 登录到 Teams 管理中心，然后转到 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 搜索 Adobe Acrobat 应用并将其选中。

1. 在“**权限**”选项卡中，选择“**审阅权限**”。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 管理中心中应用权限的屏幕截图。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. 选择“**接受**”。

## <a name="install-adobe-acrobat-app-for-all-users"></a>为所有用户安装 Adobe Acrobat 应用

若要为所有用户分配并使 Adobe Acrobat 应用可用，请执行以下步骤：

1. 在 Teams 管理中心，转到 **Teams 应用** > [**安装策略**](https://admin.teams.microsoft.com/policies/app-setup)。

1. 在“**管理策略**”选项卡下，选择“**全局（组织范围的默认值）**”，然后选择“**编辑**”。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 管理中心中 Adobe Acrobat 应用设置策略的屏幕截图。":::

1. 在“安装的应用”下，选择“**添加应用**”。

1. 搜索 **Adobe Acrobat**，选择应用名称旁边的“**添加**”，然后选择“**添加**”。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="显示如何为所有用户添加 Adobe Acrobat 应用的屏幕截图。" lightbox="media/add-adobe-acrobat-app.png":::

1. 选择“**保存**”。

选择保存后，Teams 将使用 Adobe Acrobat 应用作为 PDF 文件的默认文件处理程序。

如果要有选择地允许少数个人或组使用 Adobe Acrobat 应用，可以分配 [自定义应用权限策略](teams-app-permission-policies.md)。

了解有关此功能的以下信息：

* 设置策略后，通常需要 [几个小时](teams-app-setup-policies.md) 才能使应用可供用户使用。
* “查看 PDF 文件”作为选项卡固定在频道中，而在“分配”应用中的“查看 PDF 文件”继续由本机 Teams 体验提供支持。
* 作为 Teams 中默认 PDF 查看器的 Adobe Acrobat 仅适用于桌面版和 Web 客户端。 移动客户端不支持此功能。
* 用户需要 Adobe Acrobat 计划才能使用高级工具，例如导出 PDF、组织页面、合并文件、压缩 PDF 和保护 PDF。
* 若要卸载应用，最终用户可以从 Teams 客户端中删除该应用。 管理员可以使用安装策略删除 Adobe Acrobat 应用。
* 如果要阻止 Adobe Acrobat 应用，请将其从安装策略中删除。 这样会确保最终用户体验还原为使用本机 PDF 文件查看器。
* 在 Teams 桌面客户端中，如果在登录到 Adobe Acrobat 应用时遇到任何问题，请在浏览器中使用 Teams 登录。
