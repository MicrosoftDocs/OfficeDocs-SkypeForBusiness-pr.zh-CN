---
title: Microsoft 365组和Microsoft Teams
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
description: 了解如何Microsoft 365组和组成员身份与Microsoft Teams。
ms.openlocfilehash: e74e2e8c11753fbf97ef1161e8443f57dbb6146d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631556"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365组和Microsoft Teams

Microsoft 365组是应用程序中的跨应用程序成员身份Microsoft 365。 在基本级别，Microsoft 365 组是 Azure Active Directory 中的对象，包含成员列表，并且与相关工作负荷（包括 SharePoint 团队网站、共享 Exchange 邮箱、Planner 和 Power BI 工作区）耦合。 可以像在 Active Directory 中任何其他基于组的安全对象一样向组添加或删除人员。

![显示组Microsoft 365相关服务的图表](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

默认情况下，Microsoft 365可以创建和管理组。 有关组Microsoft 365，请参阅了解 Microsoft 365[组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)和 Microsoft 365 [FOR IT 架构师海报中的](teams-architecture-solutions-posters.md#groups-in-microsoft-365)组。

## <a name="how-microsoft-365-groups-work-with-teams"></a>组Microsoft 365组如何使用Teams

创建团队时，Microsoft 365组来管理团队成员身份。 组的相关服务（例如SharePoint站点、Power BI工作区等）会同时创建。

创建团队的人可以选择使用现有Microsoft 365组（如果他们是该组的所有者）。 团队的每个频道在文档库中都有一个单独的文件夹。 直接在文档库中创建文件夹不会在团队中创建频道。

在Microsoft 365或Outlook SharePoint组时，组邮箱显示在Outlook。 在 Teams 创建团队时，组邮箱默认处于隐藏状态。 可以将 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数一起用于使邮箱可见。

## <a name="group-membership"></a>组成员身份

如果删除团队的成员，则他们Microsoft 365组中删除。 从组中删除会立即从客户端中删除团队Teams频道。 如果使用 Microsoft 365 管理中心 从组中删除人员，他们将不再有权访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享OneNote。 但是，他们仍可在大约两小时内访问团队的聊天功能。

作为管理团队成员的最佳实践，在 Teams 客户端中添加和删除这些成员，以确保快速更新其他组连接的工作负荷的权限。 如果使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 在 Teams 客户端 (外部添加或删除团队成员，则更改最多可能需要 24 小时才能反映在 Teams 中。

## <a name="deleting-groups-and-teams"></a>删除组和团队

删除Microsoft 365组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，并SharePoint网站进行删除。 删除团队及其对团队的影响大约需要 20 Outlook。 从客户端中删除团队Teams团队将立即将其从视图中删除，所有团队成员都查看该团队。 如果删除已启用 Teams 功能的 Microsoft 365 组的成员，则对于已删除的受影响人员，在 Teams 客户端中将团队从视图中删除之前，可能会存在大约两小时的延迟。

有关组和团队生命周期结束选项的详细信息，请参阅组、团队和团队的生命周期结束选项[Yammer存档或删除](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)[Microsoft Teams。](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>相关主题

[视频Microsoft Teams (的基础) ](https://aka.ms/teams-foundations)

[还原已删除的组](/microsoft-365/admin/create-groups/restore-deleted-group)