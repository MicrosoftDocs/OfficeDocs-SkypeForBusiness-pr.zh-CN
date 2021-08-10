---
title: 管理实时组件Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
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
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305014"
---
# <a name="manage-live-components-in-teams"></a>管理实时组件Teams

聊天中的实时Teams提供了一种共同构想、创建和做出决策的新增方式。 发送组件（如表、任务列表或段落）。聊天中的每个人都可以内联编辑并查看所做的更改。 这意味着你可以收集团队的想法和反馈，同时举行更少的会议并最大限度地减少对长聊天线程的需要。

**一起更快地完成任务。** 众目成群地提供议程、跟踪组的操作项或共同做笔记。 这些只是使用实时组件更轻松的一些方案。

**共享组件。** 在此版本中，你可以将实时组件共享到不同的Teams聊天中。 收件人可以从他们身在何处进行编辑，并且无论在何处进行更改，都可以立即查看更新。 在将来的版本中，live components will be supported in Teams meeting notes and channels， Outlook， and eventually across all Microsoft 365 applications.

**从聊天开始，从聊天开始构建。** 从聊天Teams创建的每一个组件都会自动保存到OneDrive。 因此，您可能开始在聊天中协作，然后移动到文件，您具有更大的可视空间进行编辑，并可以添加您喜欢的多少组件。

## <a name="clients-and-platforms"></a>客户端和平台

适用于 Teams、Windows、Linux、iOS 和 Android 上的应用。

从 9 月开始，实时组件将在全球可用。 9 月底，政府社区云 Mod (GCC) 。

## <a name="settings-management"></a>设置管理

实时组件是使用跨 Microsoft Fluid Framework 套件Microsoft 365组件构建的，SharePoint Online 而不是 Teams 管理中心进行控制。

你需要最新版本的 SharePoint Online [PowerShell 模块](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)才能启用或禁用整个 Office 365 体验。 Microsoft Fluid Framework目标发布租户的默认值为 **ON。** 因为实时组件专为协作设计，所以组件始终由其他人作为可编辑的共享，即使对于其他文件类型，你的租户设置为默认为仅查看。 有关详细信息 **，请参阅** 设置旁边的"了解详细信息"链接。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework Online PowerShell Cmdlet 检查SharePoint是否已启用

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 通过运行不带Fluid Framework参数的 Get-SPOTenant cmdlet 来检查是否已启用该 cmdlet。

3. 验证 IsFluidEnabled 的值是否 **为 true。**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework Online PowerShell cmdlet 启用SharePoint Cmdlet 

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. 使用 cmdlet 启用流畅Set-SPOTenant -IsFluidEnabled $true 
   
   更改将在短时间内应用到整个租赁。 

此功能将在桌面、Teams Windows、iOS、Android 上提供。 启用后，用户将看到一个新选项，用于在这些客户端的邮件撰写体验中插入实时组件。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>通过 Fluid Framework Online SharePoint Cmdlet 禁用配置

1. [连接 SharePoint Online PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. 使用 Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false。 

   更改将在短时间内应用到整个租赁。 

如果需要重新启用此功能，可以使用 SharePoint Online PowerShell Cmdlet。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>已知限制

- 重新启动应用后，将表或任务列表创建为第一Teams可能需要一些时间。

- 当使用 at (@) 符号提及时，其他聊天成员将收到电子邮件通知。  (活动源中即将Teams"提及"通知。) 

- 搜索活动组件Teams搜索将返回指向 office.com 中的组件的链接，而不是聊天消息本身。

- 在联合聊天中禁用实时组件，并启用使用 Azure B2B 的来宾帐户进行常规聊天。

- 虽然可以在其他Teams和其他应用Microsoft 365组件，但收件人此时可在大多数位置获取链接。 内联编辑计划在将来提供更多体验。

## <a name="storage-of-fluid-files"></a>存储 `.fluid` 文件

**如何 `.fluid` 存储？**

在 Teams 中创建实时组件受存储在创建者的 `.fluid` OneDrive for Business。 成为用户OneDrive for Business意味着用户可以创建、发现和管理实时组件， (文件) 任何文档Office `.fluid` 组件。

用户可以从 `.fluid` Office.com 和 OneDrive for Business 中搜索文件内容。
`.fluid` 文件与数据治理功能（如电子数据展示、审核、报告和法定保留）一起工作。

`.fluid`文件现在将显示在 Office.com 和 OneDrive for Business，如"最近"和"推荐"区域。
`.fluid`可以将文件从 OneDrive for Business 还原到OneDrive for Business。

聊天参与者必须具有一OneDrive帐户来创建实时组件。 如果没有有效的 OneDrive 帐户，聊天参与者仍可以协作处理由具有有效 OneDrive 帐户但无法创建自己的帐户的其他用户创建的组件。

[将](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) `.fluid` 文件从OneDrive网站SharePoint将导致活动组件无法加载到Teams聊天中。

**如果文件所有者离开公司，会发生什么情况？**

[OneDrive策略应用于](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)文件，就像它们应用于用户创建 `.fluid` 的其他内容一样。

**如何 `.fluid` 共享文件？**

实时组件可以插入到聊天Teams或从一个聊天复制到另一个聊天。  (频道尚不支持 Live 组件。) 它们默认为租户的现有权限，但用户可以在发送前更改权限，以确保每个人都具有访问权限。

在 Office Teams.com Teams聊天中打开组件可提供窗口顶部的共享功能，类似于为其他 Office 文档提供的共享选项。

**如果文件 `.fluid` 已损坏，如何操作？**

版本历史记录允许你查看和复制以前版本的文件。

**哪些应用可以打开和编辑 `.fluid` 文件？**

`.fluid`文件只能在浏览器（如 Office.com）中作为链接打开，在聊天中Teams组件。 如果已下载，则如果未先将其上载回 OneDrive for Business 或 SharePoint Online，则无法再次打开它们。
