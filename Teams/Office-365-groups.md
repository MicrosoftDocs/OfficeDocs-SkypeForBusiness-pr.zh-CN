---
title: Office 365 组和 Microsoft 团队
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: 了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a0daed292ccccb85c5231242161c75e8cb60949c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136492"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 组和 Microsoft 团队
=====================================

> [!Tip]
> 观看以下会话，了解团队如何与 Azure Active Directory （Azure AD）、Office 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队的基础](https://aka.ms/teams-foundations)

Office 365 组是 Office 365 中跨应用的成员身份服务。 在基本级别，Office 365 组是 Azure Active Directory 中的一个对象，其中包含一组成员以及与相关工作负荷之间的松散耦合（包括 SharePoint 团队网站、Yammer 组、共享 Exchange 邮箱资源、Planner、Power BI 和 OneNote）。 您可以像对待 Active Directory 中任何其他基于组的安全对象一样，在组中添加或删除人员。

Office 365 管理员可以定义 Office 365 组、添加成员和受益于诸如 Exchange 共享邮箱、SharePoint 文档库、Yammer 组等功能。 有关 Office 365 组的详细信息，请参阅[了解 office 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

不要错过[Microsoft 365 FOR IT 设计师](teams-architecture-solutions-posters.md#groups-in-microsoft-365)的海报组。

<a name="how-office-365-groups-work"></a>Office 365 组的工作原理
--------------------------

创建团队时，在后端，你正在创建 Office 365 组以及关联的 SharePoint 文档库和 OneNote 笔记本，以及与其他 Office 365 云应用程序的关联。 如果创建团队的人员是现有 Office 365 公共组或专用组的所有者，则他们可以向组添加团队功能（如果它的人员少于5000人），并且尚未添加到团队。 这将创建一个默认**常规**频道，其中聊天消息、文档、OneNote 和其他对象驻留在该频道中。 查看频道的文档库将显示代表团队中的频道的**常规**文件夹。 更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。

> [!NOTE]
> 根据客户反馈，由于在 Microsoft 团队中创建团队而生成的新 Office 365 组在 Outlook 中不再显示，因此默认情况下，Outlook 将不再显示在 Outlook 中。 对于希望继续在 Outlook 中显示这些组的现有行为的客户，将提供 Exchange Online PowerShell cmdlet，该 cmdlet 可为 Outlook 体验启用组。 通过 Outlook 创建的组在 "Outlook 和团队" 中启用后，团队将继续显示。 此更新将在未来几个月内逐步推出到 Outlook 和团队。

> [!NOTE]
> 删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。 在团队中删除团队及其对 Outlook 的影响之间大约需要20分钟。 从团队客户端删除团队会将其从视图中立即删除为团队成员的所有人。 如果删除了已启用团队功能的 Office 365 组的成员，则在从团队客户端视图中删除团队客户端的视图之前，可能会延迟大约两个小时。
>
>有关还原已删除的 Office 365 组的信息，请阅读[此](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)信息。

<a name="group-membership"></a>组成员身份
----------------

您的用户的组功能和功能取决于您从哪里推动组成员身份。 例如，如果删除团队的成员，则也会从 Office 365 组中删除这些成员。 从组中删除立即从团队客户端删除团队和频道。 如果您使用 Microsoft 365 管理中心从组中删除人员，他们将无法再访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，他们在大约两个小时内仍可访问团队的聊天功能。

作为管理团队成员的最佳做法，在团队客户端添加和删除成员以确保应用对其他从属云应用程序的正确的级联访问控制。 此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。 如果你在团队客户端外部添加或删除团队成员（使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell），则可能需要长达两个小时才能在团队中反映更改。
