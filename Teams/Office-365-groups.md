---
title: Microsoft 365 组和 Microsoft 团队
ms.reviewer: Kyle Blevins
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: 在本文中，你将了解 Microsoft 365 组和组成员如何与 Microsoft 团队一起工作。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a44adb84cb6669bb96bd617fb52ea9b5fdceb7af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581123"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 组和 Microsoft 团队
=====================================

> [!Tip]
> 观看以下会话，了解团队如何与 Azure Active Directory (Azure AD) 、Microsoft 365 组、Exchange、SharePoint 和 OneDrive for business 进行交互： [Microsoft 团队的基础](https://aka.ms/teams-foundations)

Microsoft 365 组是 Office 365 中的跨应用程序成员身份服务。 在基本级别，Microsoft 365 组是 Azure Active Directory 中的一个对象，其中包含一组成员以及与相关工作负荷之间的松散耦合（包括 SharePoint 团队网站、Yammer 组、共享 Exchange 邮箱资源、Planner、Power BI 和 OneNote）。 您可以像对待 Active Directory 中任何其他基于组的安全对象一样，在组中添加或删除人员。

Office 365 管理员可以定义 Microsoft 365 组、添加成员和受益于诸如 Exchange 共享邮箱、SharePoint 文档库、Yammer 组等功能。 有关 Microsoft 365 组的详细信息，请参阅[了解 microsoft 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

不要错过[Microsoft 365 FOR IT 设计师](teams-architecture-solutions-posters.md#groups-in-microsoft-365)的海报组。

<a name="how-microsoft-365-groups-work"></a>Microsoft 365 组的工作原理
--------------------------

创建团队时，在后端，你正在创建 Microsoft 365 组以及关联的 SharePoint 文档库和 OneNote 笔记本，以及与其他 Office 365 云应用程序之间的关联。 如果创建团队的人员是现有 Office 365 公共组或专用组的所有者，则他们可以向组添加团队功能（如果它的人员少于5000人），并且尚未添加到团队。 这将创建一个默认**常规**频道，其中聊天消息、文档、OneNote 和其他对象驻留在该频道中。 查看频道的文档库将显示代表团队中的频道的**常规**文件夹。 更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。

> [!NOTE]
> 根据客户反馈，由于在 Microsoft 团队客户端中创建团队而生成的新 Microsoft 365 组在默认情况下将不再显示在 Outlook 中。 若要在 Outlook 中启用或禁用组的显示，请将[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 与**HiddenFromExchangeClientsEnabled**参数一起使用。 通过 Outlook 创建的组在 "Outlook 和团队" 中启用后，团队将继续显示。 

> [!NOTE]
> 删除 Microsoft 365 组将删除持久 Outlook/OWA 对话和团队会议邀请的邮箱别名，并将 SharePoint 网站标记为 "删除"。 在团队中删除团队及其对 Outlook 的影响之间大约需要20分钟。 从团队客户端删除团队会将其从视图中立即删除为团队成员的所有人。 如果删除了已启用团队功能的 Microsoft 365 组的成员，则在从团队客户端视图中删除团队客户端的视图之前，可能会延迟大约两个小时。
>
>请阅读[此](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)信息，了解有关还原已删除的 Microsoft 365 组的信息。

<a name="group-membership"></a>组成员身份
----------------

您的用户的组功能和功能取决于您从哪里推动组成员身份。 例如，如果删除团队的成员，则也会从 Microsoft 365 组中删除这些成员。 从组中删除立即从团队客户端删除团队和频道。 如果您使用 Microsoft 365 管理中心从组中删除人员，他们将无法再访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，他们在大约两个小时内仍可访问团队的聊天功能。

作为管理团队成员的最佳做法，在团队客户端添加和删除成员以确保应用对其他从属云应用程序的正确的级联访问控制。 此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。 如果你在团队客户端 (使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 添加或删除团队成员，则在某些情况下，可能需要长达 24 (小时才能在团队中反映更改) 。

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>在安排会议时将组添加为与会者的能力
----------------------------------------------------------

从五月2020开始，您现在可以邀请组加入计划会议，但有以下注意事项：
1. 从现有 Microsoft 365 组创建的所有现有 Microsoft 365 组和团队均可搜索，并可添加到会议。 但是，成员将根据其对组的订阅收到会议邀请。
2. 在 5 2018 月之前从头开始创建的团队也可以搜索，但由于其默认组订阅是 "仅答复您"，因此成员不会收到会议邀请。 这可以通过修改组设置在 Outlook 中进行更改
3. 在5月2018后从头开始创建的团队将不可搜索，并使用属性 "HiddenFromAddressListsEnabled" 隐藏。 这是管理员控制的设置，可由管理员进行修改。
