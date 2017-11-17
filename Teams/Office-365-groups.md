---
title: "Office 365 组和 Microsoft Teams | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 15989e5a846aa3bdf94f17218105d56336c8cfb9
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 组和 Microsoft Teams
=====================================

Office 365 组是 Office 365 中跨应用的成员身份服务。 从基本层面上来说，Office 365 组是 Azure Active Directory 中的一个对象，包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、Yammer 组、共享的 Exchange 邮箱资源、Planner、PowerBI 和 OneNote）的松散耦合。 你可以在组中添加或删除人员，就像 Active Directory 中的任何其他基于组的安全对象一样。

Office 365 管理员可以定义 Office 365 组、添加成员以及利用 Exchange 共享邮箱、SharePoint 文档库、Yammer 组等功能。有关组的详细信息，请访问：[了解 Office 365 组](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

<a name="how-office-365-groups-work"></a>Office 365 组工作方式
--------------------------

在 Microsoft Teams 中创建团队时，会在后台创建一个 Office 365 组、关联的 SharePoint 文档库、OneNote 笔记本以及与其他 Office 365 云应用的关联。 如果创建团队的用户是现有 Office 365 公用组或专用组的所有者，则该用户可以向组添加 Teams 功能。 这将创建一个默认的“常规”频道，聊天消息、文档、OneNote 及其他对象位于该频道中。 查看该频道的文档库将在团队中显示表示该频道的“常规”文件夹。 更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。

|||
|---------|---------|
|  ![注意图标。](media/Understand_Office_365_groups_and_Microsoft_Teams_image1.png) 注意    |删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。 从删除团队到在 Outlook 中生效大约需要 20 分钟。 从 Teams 客户端删除团队将从属于团队成员的所有用户的视图中立即删除该团队。 如果删除已启用了 Teams 功能的 Office 365 组的成员，可能会延迟大约一小时从已被删除的受影响用户的 Teams 客户端上视图中删除该团队。         |


<a name="group-membership"></a>组成员身份
----------------

根据你从其实施组成员身份的位置，你的用户将体验到不同的功能。 例如，如果你删除团队成员，则该成员也将从 Office 365 组中删除。 从组中删除成员将立即从 Teams 客户端中删除团队和频道。 如果从组中删除使用 Office 365 管理门户的用户，则该用户将不再有权访问其他协作项，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。 但是，该用户仍有权访问团队的聊天功能大约一小时。

对于 Teams 的“成员管理”，我们建议通过 Teams 客户端驱动添加/删除功能，以确保对其他相关云应用实施正确的级联访问控制。 此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。
