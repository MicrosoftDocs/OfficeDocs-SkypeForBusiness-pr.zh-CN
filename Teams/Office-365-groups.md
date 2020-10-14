---
title: Microsoft 365 组和 Microsoft 团队
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
description: 了解 Microsoft 365 组和组成员如何与 Microsoft 团队一起工作。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456076"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 组和 Microsoft 团队

Microsoft 365 组是 Microsoft 365 中的跨应用程序成员身份服务。 在基本级别，Microsoft 365 组是 Azure Active Directory 中的一个对象，其中包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、共享 Exchange 邮箱、Planner 和 Power BI 工作区）的耦合。 您可以像对待 Active Directory 中任何其他基于组的安全对象一样，在组中添加或删除人员。

![显示 Microsoft 365 组和相关服务的图表](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

默认情况下，Microsoft 365 中的用户可以创建和管理组。 有关 Microsoft 365 组的详细信息，请参阅 [了解 microsoft 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 和 [MICROSOFT 365 for IT 设计师](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 版海报中的组。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 组如何与团队协作

创建团队时，将创建 Microsoft 365 组以管理团队成员身份。 组的相关服务（如 SharePoint 网站、Power BI 工作区等）同时创建。

创建团队的人员可以选择使用现有的 Microsoft 365 组（如果他们是该组的所有者）。 团队中的每个频道在文档库中都有一个单独的文件夹。 直接在文档库中创建文件夹不会在团队中创建频道。

在 Outlook 或 SharePoint 中创建 Microsoft 365 组时，组邮箱在 Outlook 中可见。 在团队中创建团队时，默认情况下，组邮箱处于隐藏状态。 你可以将 [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数配合使用，以使邮箱可见。

## <a name="group-membership"></a>组成员身份

如果删除团队的成员，也将从 Microsoft 365 组中删除这些成员。 从组中删除立即从团队客户端删除团队和频道。 如果您使用 Microsoft 365 管理中心从组中删除人员，他们将无法再访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，他们在大约两个小时内仍可访问团队的聊天功能。

作为管理团队成员的最佳做法，可从团队客户端添加和删除它们，以确保快速连接其他组所连接的工作负荷的权限更新。 如果你在团队客户端 (使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 添加或删除团队成员，则可能最多需要24小时才能在团队中反映更改。

## <a name="deleting-groups-and-teams"></a>删除组和团队

删除 Microsoft 365 组将删除持久 Outlook/OWA 对话和团队会议邀请的邮箱别名，并将 SharePoint 网站标记为 "删除"。 在团队中删除团队及其对 Outlook 的影响之间大约需要20分钟。 从团队客户端删除团队会将其从视图中立即删除为团队成员的所有人。 如果删除了已启用团队功能的 Microsoft 365 组的成员，则在从团队客户端视图中删除团队客户端的视图之前，可能会延迟大约两个小时。

有关组和团队结束生命周期选项的详细信息，请参阅  [组、团队和 Yammer 的生命周期选项结束](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) ，并 [在 Microsoft 团队中存档或删除团队](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)。

## <a name="related-topics"></a>相关主题

[Microsoft 团队 (视频) 基础 ](https://aka.ms/teams-foundations)

[还原已删除的组](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)