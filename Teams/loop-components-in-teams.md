---
title: 循环中组件Teams
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
description: 了解如何管理设备中的循环Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 175b7f4bf8d181ae7e66edb255bd32dd40bb2fa1
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518974"
---
# <a name="overview-of-loop-components-in-teams"></a>循环中组件Teams

通过聊天Teams组件提供了一种共同构思、创建和做出决策的新方式。 发送一个组件（如表格、任务列表或段落），其中聊天中的每个人都可以内联编辑并查看所做的更改。 

> [!Note]
> 循环组件是 [Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) 应用的第一项功能，可在 Teams。 

**一起更快地完成任务。** 对议程进行众源处理、跟踪组的操作项目或共同做笔记。 这些只是使用循环组件简化的一些方案。

**共享组件。** 在此版本中，你可以将循环组件共享到不同的聊天Teams中。 收件人可以从他们身在何处进行编辑，并即时查看更新，无论更改发生在何处。

**从聊天开始，从该聊天开始生成。** 从聊天Teams创建的每一个组件都会自动保存到聊天OneDrive。 因此，你可能会开始在聊天中协作，然后移动到文件，在这里，你具有更大的可视空间进行编辑，并可以添加任何喜欢的组件。

## <a name="clients-and-platforms"></a>客户端和平台

在 Teams、Mac Windows Linux、iOS 和 Android 上的应用上可用。

## <a name="loop-components-and-fluid-files"></a>循环组件和 .fluid 文件

在 Teams 中创建的循环组件由创建者的 OneDrive 中存储的 .fluid 文件OneDrive。 作为一个OneDrive意味着用户可以创建、发现和管理循环组件 (.fluid 文件) 与任何文档Office一样。 .fluid 文件可处理电子数据展示、审核、报告和法定保留等数据管理功能。

## <a name="how-are-fluid--files-stored"></a>如何存储 .fluid 文件？

.fluid 文件显示在 Office.com 和 OneDrive 上，例如"最近"和"建议"区域。 用户可以从 Office.com 和 OneDrive 搜索 .fluid 文件中的内容。 可以将 .fluid 文件从 OneDrive 还原到以前的OneDrive。 若要创建循环组件，聊天参与者必须具有OneDrive帐户。 如果没有有效的OneDrive帐户，聊天参与者仍可以协作处理由拥有有效帐户的其他用户创建OneDrive，但不能创建自己的组件。 

将 .fluid 文件从 OneDrive 移动到 SharePoint 网站将导致实时组件无法加载到聊天Teams中。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>如果文件的所有者离开了公司，会发生什么情况？

OneDrive策略适用于 .fluid 文件，就像应用于用户创建的其他内容一样。

## <a name="how-are-fluid-files-shared"></a>如何共享 .fluid 文件？

可以在聊天中插入循环组件Teams从一个聊天复制到另一个聊天。  (通道尚不支持循环组件。) 它们默认为组织的现有权限，但用户可以在发送之前更改权限，以确保每个人都具有访问权限。

在 Office.com 中从 Teams 聊天打开组件在窗口顶部提供共享功能，类似于为其他文档Office选项。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>如果 .fluid 文件损坏或损坏，该做什么？

版本历史记录允许查看和复制文件的先前版本。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>哪些应用可以打开和编辑 .fluid 文件？

.fluid 文件只能在浏览器（例如 Office.com）中作为链接打开，在聊天中作为循环Teams打开。 如果已下载，则它们不能再次打开，而无需先将其上载回OneDrive或SharePoint。

## <a name="known-issues"></a>已知问题

- 在 Android 上使用聊天时，Office 应用聊天中的Teams编辑。
- 如果租户默认文件权限设置为"特定 *人员" (* 则仅用户指定) ，并且发件人在创建组件时从权限对话框中的"特定人员"列表中删除某些用户，则这些用户可能仍有权访问内容。
- 将租户默认文件权限设置为"特定人员" (仅用户指定) ，将链接复制到实时组件并粘贴到另一个聊天中需要发件人使用权限对话框，并添加"特定人员"选项中的收件人以正确授予访问权限。
- 将租户默认文件权限设置为"特定人员" (仅用户指定) ，在包含 20 多个成员的群组聊天中创建实时组件需要发件人手动选择该组件的权限选项。
- 在搜索中搜索循环Teams将返回指向聊天 office.com 的链接，而不是聊天消息本身。
- 在联合聊天中禁用循环组件。
- B2B 来宾无法协作处理通过组织中人员链接与它们共享实时组件，除非租户设置外部访问选项以允许 B2B 来宾具有与租户成员相同的访问级别。 有关详细信息，请参阅 [配置 B2B 外部协作设置](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings)。
- 通道不支持循环Teams组件。
- 只有当文件移动到不同的库时，聊天中的循环组件才加载。 如果文件移动到不同的文件夹，则该文件将继续在聊天中加载。

## <a name="related-topics"></a>相关主题

[管理循环中的SharePoint](/sharepoint/manage-loop-components)
