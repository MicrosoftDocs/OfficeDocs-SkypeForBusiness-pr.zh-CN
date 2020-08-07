---
title: 在 Microsoft 团队中管理大型团队-最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在 Microsoft 团队中管理大型团队以满足组织的需求的最佳做法。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582659"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft 团队中管理大型团队-最佳做法
======================================================

Microsoft 团队同样有效，可促进具有数十个成员的小型组与具有上千个成员的大型组之间的通信。 查看团队有关团队规模更新的[限制和规范](limits-specifications-teams.md)。 团队规模的增加导致了独特的管理和运营挑战。 本文介绍创建和管理数千个成员组成的大型团队的最佳做法。

## <a name="value-of-large-teams"></a>大型团队的价值

大型团队在启用以下协作方案方面非常有用：

- **部门范围的协作**：如果您的组织具有多个部门（如财务、运营、&D 等），则可以创建一个团队，其中包含特定部门中的所有成员。 现在，与部门相关的所有通信都可以在此团队中共享，从而促进来自成员的即时访问和参与。

- **员工资源组中的协作**：组织通常具有属于不同部门或工作组的共同兴趣的大型用户组。 例如，可以有一群人分享个人财务和投资的热情。 在大型组织中，通常很难连接。 若要为此类组开发社区，租户管理员可以创建一个大型团队，作为任何人都可以加入和利用的公共公司范围的资源组。 最终，这些社区将收集新成员和现有成员都可以享用的信息。

- **内部和外部成员之间的协作**：常用产品通常开发一个早期使用者社区，让他们积极尝试新产品版本并提供反馈。 早期使用者开发与产品组之间的关系，以帮助形成产品。 在这种情况下，租户管理员可以设置一个包含内部产品组和外部产品评估程序的大型团队，以促进丰富的产品开发过程。 这些团队还可以向一组选定的客户提供客户支持。

## <a name="create-teams-from-existing-groups"></a>从现有组创建团队

使用联系人组、安全组或 Office 组快速开始团队。 可以导入组以从 Office 组中创建团队或创建团队。

**导入团队以创建团队**：将多达3500个成员的组导入到团队时，团队会自动计算组中的成员总数。 这只是一次性导入，组中的未来更改不会自动在团队中更新。

**从大型 microsoft 365 组创建团队**：当您从大型 microsoft 365 组创建团队时，成员将自动成为 microsoft 365 组**和**团队的一部分。 将来，随着团队成员加入或离开 Microsoft 365 组，他们会自动添加或从团队中删除。

## <a name="create-channels-to-focus-discussions"></a>创建以讨论为重点的频道

你可以通过创建重点频道缩小组讨论范围。 请参阅[组织团队的最佳做法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制频道创建

如果允许任何团队成员创建频道，则该团队可以有渠道蔓延。 团队所有者应为 "**设置 > 成员权限**" 中的成员关闭频道创建、更新、删除和还原。 请参阅[团队和频道概述](teams-channels-overview.md)。

![显示 "管理控制台设置" 选项卡的 "成员权限" 部分的屏幕图像。](media/no-channel-creation.png ""管理控制台设置" 选项卡的 "成员权限" 部分的屏幕图像。"允许成员创建或删除频道" 选项处于未选中状态。")

## <a name="add-favorite-channels"></a>添加常用频道

为了加快新用户的参与和内容发现，你可以选择默认可供用户使用的常用频道。 在管理中心的 "**通道**" 窗格中，检查 "**成员显示**" 列下的频道。

![显示管理控制台的频道窗格的屏幕图像。](media/favorite-channels.png "显示管理员控制台的频道窗格的屏幕图像。将为成员选中 "显示" 部分频道。")

 有关详细信息，请参阅[创建您的第一个团队和频道](get-started-with-teams-create-your-first-teams-and-channels.md)。

## <a name="regulate-applications-and-bots-in-large-teams"></a>调节大型团队中的应用程序和机器人

为了防止添加分散的应用程序或 bot，团队所有者可以禁用、添加、删除和上载团队成员的应用和连接器。 在管理中心的 "**设置" > "成员权限**" 下，取消选中允许成员添加应用或连接器的三个选项。

![显示 "设置" 窗格的 "成员权限" 部分的屏幕图像。](media/disable-bots-connectors.png "显示 "设置" 窗格的 "成员权限" 部分的屏幕图像。"允许成员添加应用或连接器" 的选项未选中。")

请参阅[应用、bot、& 连接器](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>调节团队和频道提及

团队和频道提及可用于将整个团队的注意力吸引到某些频道发布。 在帖子中使用提及后，会向数以千计的团队成员发送通知。 如果通知太频繁，则团队成员可能会过载，并可能会向团队所有者发出投诉。 若要防止团队或频道提及，请通过取消选中 "团队**设置" > @mentions**窗格中的框来关闭成员的团队和频道提及。

![显示 "设置" 窗格中提及部分的屏幕图像。](media/no-at-mentions.png "显示 "设置" 窗格中提及部分的屏幕图像。未选中 "用于显示和授予成员对提及的访问权限" 选项。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>考虑在频道中设置审核

团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。 设置审核后，可以选择一个或多个团队成员作为审核员。 团队所有者默认为 "审阅者"。 有关详细信息，请参阅[设置和管理通道裁决](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相关主题

- [组织团队的最佳做法](best-practices-organizing.md)
- [创建组织范围的团队](create-an-org-wide-team.md)
