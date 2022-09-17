---
title: Teams 中的循环组件概述
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Teams 中管理循环组件。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e0b9c5a7ffef07a1d9245d2b1266a071b4ee0c2
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795051"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams 中的循环组件概述

Teams 聊天中的循环组件提供了一种一种一起构想、创建和做出决策的新方法。 发送组件（如表、任务列表或段落），其中聊天中的每个人都可以内联编辑并查看所做的更改。 

> [!Note]
> 循环组件是 [Microsoft Loop 应用](https://www.microsoft.com/en-us/microsoft-loop)在 Teams 中可用的第一项功能。 

**一起更快地完成任务。** 为议程众源，跟踪组的操作项目，或集体做笔记。 这些只是循环组件更易于使用的一些方案。

**共享组件。** 在此版本中，可以将循环组件共享到不同的 Teams 聊天中。 无论在何处进行更改，收件人都可以从任何位置进行编辑，并立即查看更新。

**从聊天开始，从那里生成。** 从 Teams 聊天创建的每个组件都会自动保存到 OneDrive 中的文件。 因此，你可以在聊天中开始协作，然后在 Office.com 上移动到文件，在其中，你有更大的可视空间进行编辑，并且可以添加任意数量的组件。

有关 Teams 中循环组件的管理员设置的信息，请参阅 [SharePoint 中的 Manage 循环组件](/sharepoint/manage-loop-components)。

## <a name="clients-and-platforms"></a>客户端和平台

在 Windows、Mac、Linux、iOS 和 Android 上的 Teams 应用上可用。

## <a name="loop-components-and-fluid-files"></a>循环组件和 .fluid 文件

在 Teams 中创建的循环组件由 .fluid (提供支持，在不久的将来，) 存储在创建者的 OneDrive 中的文件将更改为 .loop。 作为 OneDrive 中的文件意味着用户可以像任何 Office 文档一样轻松地创建、发现和管理循环组件 (.fluid 文件) 。 

## <a name="how-are-fluid-files-stored"></a>如何存储 .fluid 文件？

.fluid 文件显示在 Office.com 和 OneDrive 上，如“最近”和“推荐”区域。 用户可以从 Office.com 和 OneDrive 搜索 .fluid 文件中的内容。 .fluid 文件可以从 OneDrive 还原到以前的版本。 若要创建循环组件，聊天参与者必须具有 OneDrive 帐户。 如果没有有效的 OneDrive 帐户，聊天参与者可能仍能够协作处理由其他用户创建的组件，这些用户具有有效的 OneDrive 帐户，但无法创建自己的帐户。 

将 .fluid 文件从 OneDrive 移到 SharePoint 网站将导致实时组件无法在 Teams 聊天中加载。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果文件所有者离开公司，会发生什么情况？

OneDrive 保留策略适用于 .fluid 文件，就像它们适用于用户创建的其他内容一样。

## <a name="how-are-fluid-files-shared"></a>如何共享 .fluid 文件？

循环组件可以在 Teams 聊天中插入，也可以从一个聊天复制到另一个聊天。  (循环组件尚不受频道支持。) 它们默认为组织的现有权限，但用户可以在发送之前更改权限，以确保每个人都有权访问。

在 Office.com 中打开 Teams 聊天中的组件可在窗口顶部提供共享功能，类似于为其他 Office 文档提供的共享选项。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 文件损坏或损坏，该怎么办？

使用版本历史记录，可以查看、还原或复制以前版本的文件。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些应用可以打开和编辑 .fluid 文件？

.fluid 文件只能作为浏览器中的链接（例如 Office.com 和 Teams 聊天中的循环组件）打开。 如果已下载，则无法在不先将它们上传到 OneDrive 或 SharePoint 的情况下再次打开它们。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid 文件是否支持电子数据展示？

.fluid 文件是可发现的，但电子数据展示工作流支持有限。 目前，.fluid 文件存储在创建者的 OneDrive 中，可用于在电子数据展示 (标准) 和电子数据展示 (高级) 中进行搜索和收集。 但是，它们不会以预览版呈现，并且现有工具无法使用导出格式供审阅。 若要查看导出的内容，请将其上传到任何 OneDrive。 如果需要，可以根据 [“设置管理”](/sharepoint/manage-loop-components#settings-management) 部分中所述暂时禁用这些体验。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>如果从管理员开关禁用循环，用户体验会是什么？

如果按照 [“设置管理”](/sharepoint/manage-loop-components#settings-management) 部分中所述禁用这些体验，将应用以下体验更改：

- Teams 消息传送中的创建/插入入口点将被隐藏。 用户将无法创建新的 .fluid 文件。
- 以前作为交互式循环组件呈现的现有消息将改为呈现为超链接“循环组件”。 Teams 中不会显示交互式内容。
- 当最终用户单击“循环组件”超链接或浏览到OneDrive for Business中的 .fluid 文件并单击打开时，它将在单独的浏览器选项卡中打开该文件。最终用户仍可编辑该文件。

## <a name="known-issues"></a>已知问题

- 将租户默认文件权限设置为 *特定人员* (仅用户指定) 的人员，将链接复制到循环组件并将其粘贴到另一个聊天中需要发件人使用权限对话框，并在“特定人员”选项中添加收件人以正确授予访问权限。
- 将租户默认文件权限设置为 *特定人员* (用户指定) 的人员时，在包含 20 多个成员的群聊中创建实时组件将要求发件人手动选择组件的权限选项。
- 在 Teams 搜索中搜索循环组件将返回指向 office.com 中的组件的链接，而不是聊天消息本身的链接。
- 联合聊天中禁用循环组件。
- 来宾将无法协作处理通过公司共享链接与他们共享的实时组件。 设置 **当前在此聊天中人员** 的权限，以便与来宾共享组件。
- Teams 频道不支持循环组件。
- 仅当文件移动到不同的库时，聊天中的循环组件才会加载。 如果将文件移动到不同的文件夹，则它将继续在聊天中加载。
