---
title: Microsoft 365 组和 Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 了解 Microsoft 365 组和组成员身份如何与 Microsoft Teams 一起工作。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105238"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 组和 Microsoft Teams

Microsoft 365 组是 Microsoft 365 中的跨应用程序成员身份服务。 在基本级别，Microsoft 365 组是 Azure Active Directory 中的对象，包含成员列表，并与相关工作负荷（包括 SharePoint 团队网站、共享 Exchange 邮箱、Planner 和 Power BI 工作区）耦合。 可以添加或删除组人员，就像在 Active Directory 中添加或删除任何其他基于组的安全对象一样。

![显示 Microsoft 365 组和相关服务的示意图](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

默认情况下，Microsoft 365 中的用户可以创建和管理组。 有关 Microsoft 365 组的信息，请参阅了解 [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 组和 [Microsoft 365 for IT 架构师](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 中的组海报。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 组如何与 Teams 协作

创建团队时，将创建 Microsoft 365 组来管理团队成员身份。 组的相关服务（如 SharePoint 网站、Power BI 工作区等）是同时创建的。

创建团队的人可以选择使用现有 Microsoft 365 组（如果他们是该组的所有者）。 团队的每个频道在文档库中都有一个单独的文件夹。 直接在文档库中创建文件夹不会在团队中创建频道。

在 Outlook 或 SharePoint 中创建 Microsoft 365 组时，组邮箱在 Outlook 中可见。 在 Teams 中创建团队时，组邮箱默认处于隐藏状态。 可以将 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数一起用于使邮箱可见。

## <a name="group-membership"></a>组成员身份

如果删除团队的成员，他们将被从 Microsoft 365 组中删除。 从组中删除会立即从 Teams 客户端中删除团队和频道。 如果使用 Microsoft 365 管理中心从组中删除人员，他们将不再有权访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，他们仍可在大约两小时内访问团队的聊天功能。

作为管理团队成员的最佳实践，在 Teams 客户端中添加和删除他们，以确保快速更新其他组连接的工作负荷的权限。 如果使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 在 Teams 客户端 (外部添加或删除团队成员，则更改最多可能需要 24 小时才能反映在 Teams 中。

## <a name="deleting-groups-and-teams"></a>删除组和团队

删除 Microsoft 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，并标记要删除的 SharePoint 网站。 删除团队与删除团队对 Outlook 的影响之间大约需要 20 分钟。 从 Teams 客户端中删除团队会立即将其从查看中删除，所有团队成员都查看。 如果删除已启用 Teams 功能的 Microsoft 365 组的成员，则对于已删除的受影响人员，在 Teams 客户端中将团队从视图中删除之前，可能会延迟大约两小时。

有关组和团队生命周期结束选项的详细信息，请参阅组、  [团队和 Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 的生命周期结束选项以及存档或删除 [Microsoft Teams](./archive-or-delete-a-team.md)中的团队。

## <a name="related-topics"></a>相关主题

[Microsoft Teams (视频) ](https://aka.ms/teams-foundations)

[还原已删除的组](/microsoft-365/admin/create-groups/restore-deleted-group)