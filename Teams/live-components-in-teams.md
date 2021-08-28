---
title: 管理实时组件Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何在 Teams 中管理实时Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 031f49d79659e0d5af1152e054466255d208a146
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631456"
---
# <a name="manage-live-components-in-teams"></a>管理实时组件Teams

实时聊天Teams提供了一种共同构思、创建和做出决策的新方式。 发送一个组件（如表格、任务列表或段落），聊天中的每个人都可以在其中进行内联编辑并查看所做的更改。 这意味着，你可以从团队收集想法和反馈，同时召开更少的会议并最大程度地减少长聊天线程需求。

**一起更快地完成任务。** 对议程进行众源处理、跟踪组的操作项目或共同做笔记。 这些只是使用实时组件简化的一些方案。

**共享组件。** 在此版本中，你可以将实时组件共享到不同的聊天Teams中。 收件人可以从他们身在何处进行编辑，并且无论更改发生在何处，都可以立即查看更新。 在将来的版本中，实时组件Teams会议笔记和频道、Outlook，并最终在所有Microsoft 365支持。

**从聊天开始，从该聊天开始生成。** 从聊天Teams创建的每一个组件都会自动保存到聊天OneDrive。 因此，你可能会开始在聊天中协作，然后移动到文件，在这里，你具有更大的可视空间进行编辑，并可以添加任何喜欢的组件。

## <a name="clients-and-platforms"></a>客户端和平台

在 Teams、Mac、Linux、iOS Windows Android 上的应用上可用。

从 9 月初开始，将在全球提供实时组件。 在 9 月底，它可用于 政府社区云 Mod (GCC) 。

## <a name="settings-management"></a>设置管理

实时组件是使用Microsoft Fluid Framework套件Microsoft 365组件构建的，并且从 SharePoint Online 而不是从 Teams 管理中心进行控制。

需要最新版本的 SharePoint Online [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)模块才能启用或禁用整个租户Office 365体验。 Microsoft Fluid Framework **目标发布租户**，默认为"打开"。 由于实时组件专为协作设计，因此，即使租户设置为默认仅查看其他文件类型，组件也始终以可编辑方式共享。 有关详细信息 **，请参阅** 设置旁边的"了解详细信息"链接。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework Online PowerShell cmdlet 检查SharePoint是否已启用

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 在不Fluid Framework的情况下运行 Get-SPOTenant cmdlet，检查是否已启用该 cmdlet。

3. 验证 IsFluidEnabled 的值 **是否为 true。**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework Online PowerShell cmdlet SharePoint启用配置 

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 使用 cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   在租户中应用更改需要一小段时间。 

此功能将在台式机、Mac、iOS Teams Windows Android 上提供。 启用后，用户将看到一个新选项，用于在这些客户端的消息撰写体验中插入实时组件。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework PowerShell cmdlet SharePoint禁用配置

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. 使用 Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false。 

   在租户中应用更改需要一小段时间。 

如果需要重新启用此功能，可以使用 SharePoint PowerShell Cmdlet。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>已知限制

- 重启应用后，将表或任务列表创建Teams可能需要一些时间。

- 当提及 @@) 符号时，其他 (聊天成员将收到电子邮件通知。  (活动源中Teams通知即将推出。) 

- 在搜索中搜索实时Teams将返回指向聊天 office.com 的链接，而不是聊天消息本身。

- 实时组件在联合聊天中禁用，并且使用 Azure B2B 通过来宾帐户启用常规聊天。

- 虽然可以在频道和其他应用Teams共享组件Microsoft 365，但收件人此时可在大多数位置获取链接。 计划进行内联编辑，以在将来提供更多体验。

## <a name="storage-of-fluid-files"></a>存储 `.fluid` 文件

**`.fluid`如何存储？**

在 Teams 中创建实时组件受创建者的 `.fluid` OneDrive for Business。 成为文档中OneDrive for Business意味着用户可以像创建任何文档 (一样) 、发现和管理实时Office `.fluid` 组件。

用户可以从 `.fluid` Office.com 和 OneDrive for Business 搜索文件内容。
`.fluid` 文件使用电子数据展示、审核、报告和法定保留等数据管理功能。

`.fluid`文件现在将显示在 Office.com 和 OneDrive for Business 上，例如"最近"和"推荐"区域。
`.fluid`可以将文件从 OneDrive for Business 还原到以前的OneDrive for Business。

聊天参与者必须具有一个OneDrive帐户，以创建实时组件。 如果没有有效的OneDrive帐户，聊天参与者仍可以协作处理由具有有效帐户的其他用户创建的组件，但不能OneDrive创建自己的组件。

[将](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) `.fluid` 文件从OneDrive移动到SharePoint将导致实时组件无法加载到聊天Teams中。

**如果文件的所有者离开了公司，会发生什么情况？**

[OneDrive策略](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)应用于文件，就像它们应用于 `.fluid` 用户创建的其他内容一样。

**如何 `.fluid` 共享文件？**

可以在聊天中插入实时Teams，或者从一个聊天复制到另一个聊天。  (频道尚不支持实时组件。) 它们默认为租户的现有权限，但用户可以在发送之前更改权限，以确保每个人都具有访问权限。

在 Office Teams.com 中Teams聊天打开组件在窗口顶部提供共享功能，类似于为其他文档Office选项。

**如果文件 `.fluid` 损坏或损坏，该做什么？**

版本历史记录允许查看和复制文件的先前版本。

**哪些应用可以打开和编辑 `.fluid` 文件？**

`.fluid`文件只能在浏览器（如 Office.com）中作为链接打开，在聊天中Teams组件。 如果已下载，则它们不能再次打开，而无需先将其上载回 OneDrive for Business 或 SharePoint Online。
