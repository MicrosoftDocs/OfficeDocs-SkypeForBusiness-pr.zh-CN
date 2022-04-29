---
title: Microsoft 365 组和Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 了解Microsoft 365组和组成员身份如何与Microsoft Teams配合使用。
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125427"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 组和Microsoft Teams

Microsoft 365 组是Microsoft 365中的跨应用程序成员身份服务。 在基本级别，Microsoft 365组是Azure Active Directory中的一个对象，其中包含成员列表和与相关工作负荷（包括SharePoint团队网站、共享Exchange邮箱、Planner 和OneNote笔记本）的耦合。 可以将人员添加或删除到组，就像在 Active Directory 中添加或删除任何其他基于组的安全对象一样。

![显示Microsoft 365 组和相关服务的示意图。](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

默认情况下，Microsoft 365中的用户可以创建和管理组。 For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 组如何使用Teams

创建团队时，会创建一个Microsoft 365组来管理团队成员身份。 同时创建组的相关服务，例如SharePoint网站、邮箱等。

创建团队的人员可以选择使用现有Microsoft 365组（如果他们是该组的所有者）。 团队中的每个频道在文档库中都有一个单独的文件夹。 直接在文档库中创建文件夹不会在团队中创建通道。

在Outlook或SharePoint中创建Microsoft 365组时，组邮箱在Outlook中可见。 在Teams中创建团队时，组邮箱默认处于隐藏状态。 可以将 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数配合使用，使邮箱可见。

## <a name="group-membership"></a>组成员身份

如果删除团队成员，也会将其从Microsoft 365组中删除。 从组中删除会立即从Teams客户端中删除团队和频道。 如果使用Microsoft 365 管理中心从组中删除人员，他们将不再有权访问其他协作方面，例如SharePoint联机文档库、Yammer组或共享OneNote。 但是，他们仍然可以访问团队的聊天功能大约两个小时。

作为管理团队成员的最佳做法，请从Teams客户端添加和删除这些成员，以确保为其他组连接的工作负载快速进行权限更新。 如果使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 在Teams客户端 (外部添加或删除团队成员，则最长可能需要 24 小时才能在Teams中反映更改。

## <a name="deleting-groups-and-teams"></a>删除组和团队

删除Microsoft 365组将删除用于持久Outlook/OWA 对话和Teams会议邀请的邮箱别名，并标记要删除的SharePoint网站。 团队的删除及其对Outlook的影响大约需要 20 分钟。 从Teams客户端中删除团队会立即将其从视图中删除给所有团队成员。 如果删除已对其启用了Teams功能的Microsoft 365组的成员，则可能会延迟大约两个小时，才能将团队从Teams客户端的视图中删除，以便删除受影响的人员。

有关组和团队生命周期结束选项的详细信息，请参阅[组、团队和Yammer的生命周期结束选项，](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)并在[Microsoft Teams中存档或删除团队](./archive-or-delete-a-team.md)。

## <a name="related-topics"></a>相关主题

[Microsoft Teams (视频) 的基础](https://aka.ms/teams-foundations)

[还原已删除的组](/microsoft-365/admin/create-groups/restore-deleted-group)
