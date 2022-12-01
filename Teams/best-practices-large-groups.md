---
title: 在 Microsoft Teams 中管理大型团队 - 最佳做法
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在 Microsoft Teams 中管理大型团队以满足组织需求的最佳做法。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199074"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft Teams 中管理大型团队 - 最佳做法

Microsoft Teams 在促进具有数十名成员的小组和具有数千名成员的大型组之间的通信方面同样有效。 有关团队大小的更新 [，请查看 Teams 的限制和规范](limits-specifications-teams.md) 。 团队规模的增加会导致独特的管理和运营挑战。 本文介绍创建和管理由数千名成员组成的大型团队的最佳做法。

## <a name="value-of-large-teams"></a>大型团队的价值

大型团队在实现以下协作方案方面非常有用：

- **部门范围的协作**：如果你的组织有多个部门，如财务、运营、R&D 等，则可以创建一个包含特定部门中所有成员的单个团队。 现在，与某个部门相关的所有通信都可以在此团队中共享，从而促进成员的即时接触和参与。

- **员工资源组中的协作**：组织通常拥有属于不同部门或工作组的大型具有共同利益的人员组。 例如，可能有一群人对个人理财和投资有着共同的热情。 在大型组织中通常很难连接。 若要为此类组开发社区，租户管理员可以创建一个大型团队，充当公共公司范围的资源组，任何人都可以加入和利用该资源组。 最终，这些社区收集新成员和现有成员都可以享受的信息。

- **内部和外部成员之间的协作**：热门产品通常开发一个早期采用者社区，他们渴望尝试新产品版本并提供反馈。 早期采用者与产品组建立关系，以帮助塑造产品。 在这种情况下，租户管理员可以设置一个大型团队，其中包括内部产品组和外部产品评估程序，以促进丰富的产品开发过程。 这些团队还可以向一组选定客户提供客户支持。

## <a name="create-teams-from-existing-groups"></a>从现有组创建团队

使用联系人组、安全组或 Office 组快速启动团队。 可以导入组以创建团队或从 Office 组创建团队。

**导入组以组建团队**：将具有最多 3，500 个成员的组导入 Teams 时，Teams 会自动计算组中成员的总数。 这只是一次性导入，组中的将来更改不会在 Teams 中自动更新。

**从大型 Microsoft 365 组创建团队：从大型Microsoft 365** 组创建团队时，成员将自动成为Microsoft 365 组 **和** 团队的一部分。 将来，当团队成员加入或离开Microsoft 365 组时，会自动在团队中添加或删除他们。

## <a name="bulk-importexportremove-members-in-a-team"></a>批量导入/导出/删除团队中的成员

Azure 门户允许用户批量导入/导出/删除Microsoft 365 组中的成员。 有关详细信息，请参阅 [批量导入组成员](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。

由于每个团队都由 Microsoft 365 组提供支持，因此可以使用 Azure 门户在与团队对应的组中执行这些操作。 成员操作将在 24 小时内反映在团队中。

## <a name="create-channels-to-focus-discussions"></a>创建以讨论为重点的频道

可以通过创建重点频道来缩小小组讨论范围。 请参阅 [组织团队的最佳做法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制通道创建

如果允许任何团队成员创建频道，该团队可能会有频道扩展。 团队所有者应在 **“设置”中** 关闭成员的频道创建、更新、删除和还原>成员权限。 请参阅 [团队和频道概述](teams-channels-overview.md)。

![显示管理控制台“设置”选项卡的成员权限部分的屏幕图像。](media/no-channel-creation.png "管理控制台“设置”选项卡的成员权限部分的屏幕图像。未选中“允许成员创建或删除通道”选项。")

## <a name="add-favorite-channels"></a>添加收藏频道

为了加快新的用户参与度和内容发现速度，可以选择默认可供用户使用的收藏频道。 在管理中心的“ **频道** ”窗格中，检查“ **显示成员** ”列下的频道。

![显示管理控制台的频道窗格的屏幕图像。](media/favorite-channels.png "显示管理控制台频道窗格的屏幕图像。某些频道会选中“成员的显示”。")

 有关详细信息 [，请参阅创建第一个团队和频道](get-started-with-teams-create-your-first-teams-and-channels.md) 。

## <a name="regulate-applications-and-bots-in-large-teams"></a>规范大型团队中的应用程序和机器人

为了防止添加分散注意力的应用程序或机器人，团队所有者可以为团队成员禁用、添加、删除和上传应用和连接器。 在管理中心 **的“设置>成员权限”** 下，取消选中允许成员添加应用或连接器的三个选项。

![显示“设置”窗格的“成员权限”部分的屏幕图像。](media/disable-bots-connectors.png "显示“设置”窗格的“成员权限”部分的屏幕图像。未选中用于允许成员添加应用或连接器的选项。")

请参阅 [Teams 应用概述](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>规范团队和频道提及

团队和频道提及可用于将整个团队的注意力吸引到某些频道帖子上。 在帖子中使用提及后，会向成千上万的团队成员发送通知。 如果通知过于频繁，则团队成员可能会过载，并可能向团队所有者投诉。 若要防止团队或频道提及，请取消选中团队 **设置> @mentions** 窗格中的框，关闭成员的团队和频道提及。

![显示“设置”窗格的“提及”部分的屏幕图像。](media/no-at-mentions.png "显示“设置”窗格的“提及”部分的屏幕图像。未选中用于显示和授予成员访问提及权限的选项。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>考虑在频道中设置审核

团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。 设置审核后，可以选择一个或多个团队成员作为审核员。 默认情况下，团队所有者是审阅者。 有关详细信息，请参阅 [设置和管理频道审查](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相关主题

- [组织 Teams 的最佳做法](best-practices-organizing.md)
- [创建组织范围的团队](create-an-org-wide-team.md)