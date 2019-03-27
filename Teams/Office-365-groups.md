---
title: Office 365 组和 Microsoft 团队
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
description: 了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a456e0777d354585eddf3676f2fdcae56ae9485
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890091"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 组和 Microsoft 团队
=====================================

> [!Tip]
> 观看下面的会话，若要了解与 Azure Active Directory (Azure AD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)

Office 365 组是 Office 365 中跨应用的成员身份服务。 基本级别 Office 365 组是在 Azure Active Directory 中具有成员和松散耦合到相关工作负荷，包括 SharePoint 工作组网站，Yammer 组的列表的对象共享 Exchange 邮箱资源，计划程序、 Power BI 和 OneNote。 您可以添加或删除到组的人员，就像在 Active Directory 中的任何其他基于组的安全对象。

Office 365 管理员可以定义一个 Office 365 组、 添加成员，以及受益功能，如 Exchange 共享邮箱、 SharePoint 文档库、 Yammer 组等。 有关 Office 365 组的详细信息，请参阅[了解 Office 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

<a name="how-office-365-groups-work"></a>Office 365 组的工作方式
--------------------------

后端创建一个团队，时，您正在创建 Office 365 组关联的 SharePoint 文档库和 OneNote 笔记本，以及其他 Office 365 云应用程序的关系。 如果创建团队的人是现有 Office 365 公共或专用组的所有者，他们可以向组添加团队功能，如果小于 5000 人员和从不已添加到团队。 这将创建一个默认**常规**频道的聊天消息、 文档、 OneNote 和其他对象驻留。 查看该频道的文档库将揭示代表团队中的通道的**一般**文件夹。 更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。

> [!NOTE]
> 根据客户反馈，由于 Microsoft 团队在创建团队生成的新 Office 365 组将不再显示在 Outlook 中默认情况下。 对于要继续在 Outlook 中显示这些组的现有行为的客户，将其可以启用 Outlook 体验的组提供 Exchange Online PowerShell cmdlet。 组创建通过 Outlook 和更高版本启用团队将继续要显示在 Outlook 和团队。 此更新将逐步执行跨 Outlook 和团队滚月。

> [!NOTE]
> 删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。 计大约 20 分钟团队的删除操作之间 Outlook 受到影响。 删除团队来自团队客户端会将其立即从视图的所有用户的工作组成员。 如果删除了具有团队功能在其上启用 Office 365 组的成员，可能有约为两个小时，团队删除从视图中已删除的受影响人员的团队客户端之前的延迟。
>
>阅读[此](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)有关还原已删除 Office 365 组信息。

<a name="group-membership"></a>组成员身份
----------------

组特性和功能为您的用户取决于其中驱动器中的组成员身份。 例如，如果您删除的工作组成员，请删除这些空格从 Office 365 组。 从组中删除立即删除工作组和通道来自团队客户端。 如果从使用 Office 365 管理中心组中删除联系人，将不再拥有对其他协作方面的访问 SharePoint Online 的文档库，如 Yammer 组或共享的 OneNote。 但是，他们仍将约为两个小时内有权团队的聊天功能。

管理团队成员的最佳做法是，添加和删除工作组客户端以确保正确的级联访问控件其他相关的云应用程序应用的成员。 此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。 如果您执行添加或删除外部团队客户端的工作组成员 (通过使用 Office 365 管理中心的 Azure AD 或 Exchange Online PowerShell)，可能需要更改可以反映在工作组达两个小时。
