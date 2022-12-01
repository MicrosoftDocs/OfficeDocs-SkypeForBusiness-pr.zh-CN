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
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1405464a3eb963d55c357b5fcc165c67a143e5e1
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198544"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams 中的循环组件概述

Teams 聊天中的循环组件提供了一种共同构思、创建和做出决策的新方法。 发送组件（如表格、任务列表或段落），聊天中的每个人都可以在其中进行内联编辑，并在进行更改时查看更改。 

> [!Note]
> 循环组件是 [Microsoft Loop 应用](https://www.microsoft.com/en-us/microsoft-loop)在 Teams 中可用的第一项功能。 

**共同更快地完成任务。** 对议程进行众包、跟踪组的操作项目或共同做笔记。 这些只是使用循环组件简化的几个方案。

**共享组件。** 在此版本中，可以将循环组件共享到不同的 Teams 聊天中。 收件人可以从任何位置进行编辑，并立即查看更新，无论更改是在何处进行的。

**从聊天开始，从那里生成。** 从 Teams 聊天创建的每个组件都会自动保存到 OneDrive 中的文件中。 因此，你可能会开始在聊天中协作，然后移动到 Office.com 上的文件，其中你有更大的视觉空间进行编辑，并且可以添加任意数量的组件。

有关 Teams 中循环组件的管理员设置的信息，请参阅 [在 SharePoint 中管理循环组件](/sharepoint/manage-loop-components)。

## <a name="clients-and-platforms"></a>客户端和平台

适用于 Windows、Mac、Linux、iOS 和 Android 上的 Teams 应用。

## <a name="loop-components-and-fluid-files"></a>循环组件和 .fluid 文件

在 Teams 中创建的循环组件由 .fluid (将在不久的将来更改为 .loop，) 文件存储在创建者的 OneDrive 中。 成为 OneDrive 中的文件意味着用户可以像任何 Office 文档一样轻松地创建、发现和管理循环组件 (.fluid 文件) 。 

## <a name="how-are-fluid-files-stored"></a>如何存储 .fluid 文件？

.fluid 文件显示在 Office.com 和 OneDrive 上，例如“最近”和“推荐”区域中。 用户可以从 Office.com 和 OneDrive 搜索 .fluid 文件中的内容。 .fluid 文件可以从 OneDrive 还原到以前的版本。 若要创建循环组件，聊天参与者必须具有 OneDrive 帐户。 如果没有有效的 OneDrive 帐户，聊天参与者可能仍能够协作处理由具有有效 OneDrive 帐户但无法创建自己的帐户的其他用户创建的组件。 

将 .fluid 文件从 OneDrive 移动到 SharePoint 网站将导致实时组件无法在 Teams 聊天中加载。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果文件的所有者离开公司，会发生什么情况？

OneDrive 保留策略适用于 .fluid 文件，就像对用户创建的其他内容一样。

## <a name="how-are-fluid-files-shared"></a>如何共享 .fluid 文件？

循环组件可以插入 Teams 聊天中，也可以从一个聊天复制到另一个聊天。 channels 中尚不支持 (循环组件。) 它们默认为组织的现有权限，但用户可以在发送之前更改权限，以确保每个人都有权访问。

在 Office.com 中打开 Teams 聊天中的组件提供窗口顶部的共享功能，类似于为其他 Office 文档提供的共享选项。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 文件损坏或损坏，该怎么办？

版本历史记录允许查看、还原或复制文件的早期版本。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些应用可以打开和编辑 .fluid 文件？

.fluid 文件只能在浏览器中作为链接（例如 Office.com）和 Teams 聊天中的循环组件打开。 如果已下载，则无法再次打开它们，而无需先将其上传回 OneDrive 或 SharePoint。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid 文件是否支持电子数据展示？

.fluid 文件是可发现的，但电子数据展示工作流支持有限。 目前，.fluid 文件存储在创建者的 OneDrive 中，可用于在电子数据展示 (Standard) 和电子数据展示 (Premium) 中搜索和收集。 但是，它们不会以预览形式呈现，并且现有工具不会使用用于审阅的导出格式。 若要查看导出的内容，请将其上传到任何 OneDrive。 如果需要，可以暂时禁用这些体验，如 [设置管理](/sharepoint/manage-loop-components#settings-management) 部分中所述。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>如果从管理开关禁用 Loop，用户体验会是什么？

如果按 [“设置管理”](/sharepoint/manage-loop-components#settings-management) 部分中所述禁用这些体验，将应用以下体验更改：

- Teams 消息传送中的创建/插入入口点将被隐藏。 用户将无法创建新的 .fluid 文件。
- 以前呈现为交互式循环组件的现有消息将改为呈现为超链接“循环组件”。 Teams 中不会显示任何交互式内容。
- 当最终用户单击“循环组件”超链接或浏览到 OneDrive for Business 中的 .fluid 文件并单击打开时，它将在单独的浏览器选项卡中打开该文件。最终用户仍可以编辑该文件。

## <a name="known-issues"></a>已知问题

- 将租户默认文件权限设置为 *“特定人员* ” (仅用户指定) 的人员时，将链接复制到循环组件并将其粘贴到另一个聊天中需要发件人使用权限对话框并在“特定人员”选项中添加收件人以正确授予访问权限。
- 如果租户默认文件权限设置为 *“特定人员* ” (只有用户指定的) ，则创建包含 20 个以上成员的群组聊天中的实时组件需要发件人手动选择组件的权限选项。
- 在 Teams 搜索中搜索循环组件将返回指向 office.com 中的组件的链接，而不是聊天消息本身。
- 循环组件在联合聊天中处于禁用状态。
- 来宾将无法协作处理通过公司共享链接与他们共享的实时组件。 将权限设置为 **人员当前在此聊天中** 与来宾共享组件。
- Teams 频道不支持循环组件。
- 仅当文件移动到不同的库时，聊天中的循环组件才会加载。 如果文件移动到其他文件夹，它将继续在聊天中加载。
