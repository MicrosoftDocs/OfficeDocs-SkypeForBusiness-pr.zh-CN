---
title: Office 365 组和 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: 了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 组和 Microsoft Teams
=====================================

Office 365 组是 Office 365 中跨应用的成员身份服务。 从基本层面上来说，Office 365 组是 Azure Active Directory 中的一个对象，包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、Yammer 组、共享的 Exchange 邮箱资源、Planner、PowerBI 和 OneNote）的松散耦合。 你可以在组中添加或删除人员，就像 Active Directory 中的任何其他基于组的安全对象一样。

Office 365 管理员可以定义 Office 365 组、添加成员以及利用 Exchange 共享邮箱、SharePoint 文档库、Yammer 组等功能。有关组的详细信息，请访问：[了解 Office 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

<a name="how-office-365-groups-work"></a>Office 365 组工作方式
--------------------------

在 Microsoft Teams 中创建团队时，会在后台创建一个 Office 365 组、关联的 SharePoint 文档库、OneNote 笔记本以及与其他 Office 365 云应用的关联。 如果创建团队的用户是现有 Office 365 公用组或专用组的所有者，则该用户可以向组添加 Teams 功能。 这将创建一个默认的“常规”频道，聊天消息、文档、OneNote 及其他对象位于该频道中。 查看该频道的文档库将在团队中显示表示该频道的“常规”文件夹。 更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。




> [!NOTE]
> 删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。 从删除团队到在 Outlook 中生效大约需要 20 分钟。 从 Teams 客户端删除团队将从属于团队成员的所有用户的视图中立即删除该团队。 如果删除已启用了 Teams 功能的 Office 365 组的成员，可能会延迟大约一小时从已被删除的受影响用户的 Teams 客户端上视图中删除该团队。

<a name="group-membership"></a>组成员身份
----------------

组功能和为您的用户的能力取决于驱动器中的组成员身份的地方。 例如，如果您删除一个团队的成员，他们会从 Office 365 组。 从组中删除成员将立即从 Teams 客户端中删除团队和频道。 如果从组中删除使用 Office 365 管理门户的用户，则该用户将不再有权访问其他协作项，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，该用户仍有权访问团队的聊天功能大约一小时。

最佳管理团队成员的做法： 添加和删除成员，从团队客户端，以确保与其他相关的云应用程序级联的正确访问控制应用。 此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。 不要添加或移除团队客户端之外的团队成员 (通过使用 Office 365 管理中心，Azure 的广告，或 Exchange 联机 PowerShell)，有时花费达一小时的更改将反映在工作组。
