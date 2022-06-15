---
title: Teams中的Loop组件概述
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
description: 了解如何在Teams中管理Loop组件。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088578"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams中的Loop组件概述

Teams聊天中的Loop组件提供了一种一起构想、创建和决策的新方法。 发送组件（如表、任务列表或段落），其中聊天中的每个人都可以内联编辑并查看所做的更改。 

> [!Note]
> Loop组件是[Microsoft Loop应用在Teams](https://www.microsoft.com/en-us/microsoft-loop)中可用的第一项功能。 

**一起更快地完成任务。** 为议程众源，跟踪组的操作项目，或集体做笔记。 这些只是Loop组件更易于使用的一些方案。

**共享组件。** 在此版本中，可以将Loop组件共享到不同的Teams聊天中。 无论在何处进行更改，收件人都可以从任何位置进行编辑，并立即查看更新。

**"开始"菜单聊天中，从那里生成。** 从聊天Teams创建的每个组件都会自动保存到OneDrive中的文件。 因此，你可以开始在聊天中协作，然后移动到文件，在该文件中，你具有更大的可编辑视觉空间，并且可以添加任意数量的组件。

有关Teams中Loop组件的管理员设置的信息，请参阅[SharePoint中的管理Loop组件](/sharepoint/manage-loop-components)。

## <a name="clients-and-platforms"></a>客户端和平台

可在 Windows、Mac、Linux、iOS 和 Android 上的Teams应用上使用。

## <a name="loop-components-and-fluid-files"></a>Loop组件和 .fluid 文件

在Teams中创建的Loop组件由存储在创建者OneDrive中的 .fluid 文件提供支持。 作为OneDrive中的文件意味着用户可以像任何Office文档一样轻松地创建、发现和管理 (.fluid 文件) Loop组件。 

## <a name="how-are-fluid--files-stored"></a>如何存储 .fluid 文件？

.fluid 文件显示在 Office.com 和OneDrive上，例如“最近”和“推荐”区域。 用户可以从 Office.com 和 OneDrive 搜索 .fluid 文件中的内容。 .fluid 文件可以从OneDrive还原到以前的版本。 若要创建Loop组件，聊天参与者必须具有OneDrive帐户。 如果没有有效的OneDrive帐户，聊天参与者可能仍能够协作处理由具有有效OneDrive帐户但无法创建自己的帐户的其他用户创建的组件。 

将 .fluid 文件从OneDrive移动到SharePoint站点将导致实时组件无法加载Teams聊天。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果文件所有者离开公司，会发生什么情况？

OneDrive保留策略适用于 .fluid 文件，就像它们适用于用户创建的其他内容一样。

## <a name="how-are-fluid-files-shared"></a>如何共享 .fluid 文件？

Loop组件可以插入Teams聊天中，也可以从一个聊天复制到另一个聊天中。 频道尚不支持 (Loop组件。) 它们默认为组织的现有权限，但用户可以在发送之前更改权限，以确保每个人都具有访问权限。

在 Office.com 中打开Teams聊天中的组件可在窗口顶部提供共享功能，类似于为其他Office文档提供的共享选项。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 文件损坏或损坏，该怎么办？

使用版本历史记录可以查看和复制文件的早期版本。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些应用可以打开和编辑 .fluid 文件？

.fluid 文件只能作为浏览器中的链接（如 Office.com）打开，并作为Teams聊天中的Loop组件打开。 如果已下载，则无法在不先将它们上传到OneDrive或SharePoint的情况下再次打开它们。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid 文件是否支持电子数据展示？

.fluid 文件是可发现的，但电子数据展示工作流支持有限。 目前，.fluid 文件存储在创建者的OneDrive中，可用于在电子数据展示 (标准) 和电子数据展示 (高级版) 中进行搜索和收集。 但是，它们不会以预览版呈现，并且现有工具无法使用导出格式供审阅。 若要查看导出的内容，请将其上传到任何OneDrive。 如果需要，可以根据[设置管理](/sharepoint/manage-loop-components#settings-management)部分中所述暂时禁用这些体验。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>如果从管理开关禁用Loop，用户体验会是什么？

如果按照[设置管理](/sharepoint/manage-loop-components#settings-management)部分中所述禁用这些体验，将应用以下体验更改：

- 将隐藏Teams消息传送中的创建/插入入口点。 用户将无法创建新的 .fluid 文件。
- 以前作为交互式Loop组件呈现的现有消息将改为呈现为超链接“Loop组件”。 Teams中不会显示交互式内容。
- 当最终用户单击“Loop组件”超链接或浏览到OneDrive for Business中的 .fluid 文件并单击打开时，它将在单独的浏览器选项卡中打开该文件，但最终用户将无法编辑该文件。

## <a name="known-issues"></a>已知问题

- 在Android上使用Teams时，无法通过Office 应用编辑聊天中的Loop组件。
- 如果将租户默认文件权限设置为 *特定人员* (用户指定) 的人员，并且发件人在创建组件时从权限对话框的 *“特定人员* ”列表中删除某些用户，则这些用户可能仍然有权访问该内容。
- 将租户默认文件权限设置为 *特定人员* (仅用户指定的人员) ，将链接复制到实时组件并粘贴到另一个聊天中，则要求发件人使用权限对话框，并在“特定人员”选项中添加收件人以正确授予访问权限。
- 将租户默认文件权限设置为 *特定人员* (用户指定) 的人员时，在包含 20 多个成员的群聊中创建实时组件将要求发件人手动选择组件的权限选项。
- 在Teams搜索中搜索Loop组件将返回指向 office.com 中的组件的链接，而不是聊天消息本身的链接。
- 在联合聊天中禁用Loop组件。
- B2B 来宾将无法协作处理通过公司共享链接与他们共享的实时组件。 将权限设置为 **当前在此聊天中的人员** ，以便与 B2B 来宾共享组件。
- Teams通道不支持Loop组件。
- 仅当文件移动到不同的库时，聊天中的Loop组件才会加载。 如果将文件移动到不同的文件夹，则它将继续在聊天中加载。
