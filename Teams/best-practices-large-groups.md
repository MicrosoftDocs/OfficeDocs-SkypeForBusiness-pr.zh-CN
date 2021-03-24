---
title: 在 Microsoft Teams 中管理大型团队 - 最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在 Microsoft Teams 中管理大型团队的最佳实践，以满足组织的需求。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9dfecde14e47992588fa13e04aa652a069f7108b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092880"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft Teams 中管理大型团队 - 最佳做法
======================================================

Microsoft Teams 在促进具有数十个成员和具有数千个成员的大型组之间的通信方面同样有效。 有关 [团队大小更新，](limits-specifications-teams.md) 请查看 Teams 的限制和规范。 团队规模增加会导致独特的管理和运营挑战。 本文介绍创建和管理由数千个成员组成的大型团队的最佳实践。

## <a name="value-of-large-teams"></a>大型团队的价值

大型团队在启用以下协作方案方面非常有用：

- **部门范围的协作**：如果组织有多个部门（如财务、运营、R&D 等），可以创建一个包含特定部门所有成员的团队。 现在，可以在此团队中共享与部门相关的所有通信，这便于成员即时联系和参与。

- **员工资源组协作**：组织通常有一大群共同感兴趣的人员，这些人员属于不同的部门或工作组。 例如，可以有一组人对个人财务和投资有一种热情。 在大型组织中连接通常很难。 若要为此类组开发社区，租户管理员可以创建一个大型团队，充当公司范围内任何人都可以加入和利用的公共资源组。 最终，这些社区收集新成员和现有成员都可以享受的信息。

- **内部和外部成员之间的协作**：热门产品通常开发一个早期采用者社区，这些用户希望尝试新产品发布并提供反馈。 早期采用者与产品组发展关系，帮助塑造产品。 在这种情况下，租户管理员可以设置包括内部产品组和外部产品评估人员的大型团队，以简化丰富的产品开发过程。 这些团队还可以为一组选定客户提供客户支持。

## <a name="create-teams-from-existing-groups"></a>从现有组创建团队

使用联系人组、安全组或 Office 组快速启动团队。 可以导入组以创建团队，也可以从 Office 组创建团队。

**导入组以** 创建团队：将最多 3，500 个成员的组导入 Teams 时，Teams 会自动计算组中成员的总数。 这是一次导入，组的未来更改不会在 Teams 中自动更新。

**从大型 Microsoft 365** 组创建团队：从大型 Microsoft 365 组创建团队时，成员自动成为 Microsoft 365组和团队的一部分。 将来，当团队成员加入或离开 Microsoft 365 组时，将自动添加或删除他们。

## <a name="bulk-importexportremove-members-in-a-team"></a>批量导入/导出/删除团队中的成员

Azure 门户允许用户批量导入/导出/删除 Microsoft 365 组中的成员。 有关详细信息，请参阅批量 [导入组成员](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。

由于每个团队都由 Microsoft 365 组支持，因此可以使用 Azure 门户在对应于该团队的组中执行这些操作。 成员操作将在 24 小时内反映在团队中。

## <a name="create-channels-to-focus-discussions"></a>创建以讨论为重点的频道

您可以通过创建重点频道来缩小组讨论范围。 请参阅 [组织团队的最佳实践](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制通道创建

如果允许任何团队成员创建频道，该团队可以扩大频道。 团队所有者应在"设置"和"成员权限"中为成员关闭 **>、更新、删除和还原**。 请参阅 [团队和频道概述](teams-channels-overview.md)。

![显示管理员控制台"设置"选项卡的"成员权限"部分的屏幕图像。](media/no-channel-creation.png "显示管理员控制台"设置"选项卡上成员权限部分的图像。"允许成员创建或删除频道"选项未选中。")

## <a name="add-favorite-channels"></a>添加收藏频道

为了加速新的用户参与和内容发现，可以选择默认可供用户使用的收藏频道。 在 **管理中心的"** 频道"窗格中，检查"显示 **成员"列下的** 频道。

![显示管理控制台的通道窗格的屏幕图像。](media/favorite-channels.png "显示管理控制台的通道窗格的屏幕图像。某些频道将选中"针对成员显示"。")

 有关详细信息 [，请参阅创建你的第一个团队](get-started-with-teams-create-your-first-teams-and-channels.md) 和频道。

## <a name="regulate-applications-and-bots-in-large-teams"></a>管理大型团队中的应用程序和机器人

为了防止添加让人分心的应用程序或机器人，团队所有者可以禁用、添加、删除和上传团队成员的应用和连接器。 在管理 **中心的"设置**">"成员权限"下，取消选中允许成员添加应用或连接器的三个选项。

![显示"设置"窗格的"成员权限"部分的屏幕图像。](media/disable-bots-connectors.png "显示"设置"窗格的"成员权限"部分的屏幕图像。将取消选中允许成员添加应用或连接器的选项。")

请参阅 [应用、机器人&连接器](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>管理团队和频道提及

团队和频道提及可用于引起整个团队对某些频道帖子的注意。 在帖子中使用提及后，会向成千上万的团队成员发送通知。 如果通知过于频繁，则团队成员可能会过载，并可能向团队所有者投诉。 若要阻止团队或频道提及，请通过取消选中团队"设置"窗格中的框来为成员关闭团队 **> @mentions** 提及。

![屏幕图像，显示"设置"窗格的"提及"部分。](media/no-at-mentions.png "屏幕图像，显示"设置"窗格的"提及"部分。取消选中显示和向成员授予提及访问权限的选项。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>考虑在频道中设置审核

团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。 设置审核后，可以选择一个或多个团队成员作为审核员。 默认情况下，团队所有者是审阅人。 有关详细信息，请参阅 [设置和管理频道审核](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相关主题

- [组织 Teams 的最佳实践](best-practices-organizing.md)
- [创建组织范围的团队](create-an-org-wide-team.md)