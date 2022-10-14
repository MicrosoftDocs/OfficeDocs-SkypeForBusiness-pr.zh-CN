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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 06fc3d0bdf0e4741918e380d13acd1b7391bd6ef
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576398"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>在 Microsoft Teams 中管理大型团队 - 最佳做法

Microsoft Teams 在促进具有数十个成员的小型组和拥有数千个成员的大型组之间的通信方面同样有效。 有关团队规模的更新，请查看 [Teams 的限制和规范](limits-specifications-teams.md) 。 增加团队规模会导致独特的管理和运营挑战。 本文介绍创建和管理由数千名成员组成的大型团队的最佳做法。

## <a name="value-of-large-teams"></a>大型团队的价值

大型团队在启用以下协作方案方面非常有用：

- **部门范围内的协作**：如果你的组织具有多个部门，例如财务、运营、R&D 等，则可以创建一个包含特定部门中所有成员的单个团队。 现在，可以在此团队中共享与某个部门相关的所有通信，从而促进成员的即时联系和参与。

- **员工资源组中的协作**：组织通常有属于不同部门或工作组的有共同利益的大组人员。 例如，可能有一组人对个人理财和投资充满热情。 通常很难在大型组织中进行连接。 为了为此类组开发社区，租户管理员可以创建一个大型团队，作为公司范围内的公共资源组，任何人都可以加入并利用该团队。 最终，这些社区收集新成员和现有成员都可以享受的信息。

- **内部和外部成员之间的协作**：热门产品通常会发展一个早期采用者社区，他们渴望尝试新产品发布并提供反馈。 早期采用者与产品组建立关系，以帮助塑造产品。 在这种情况下，租户管理员可以设置一个大型团队，包括内部产品组和外部产品评估器，以促进丰富的产品开发过程。 这些团队还可以为一组选择的客户提供客户支持。

## <a name="create-teams-from-existing-groups"></a>从现有组创建团队

使用联系人组、安全组或 Office 组来启动团队。 可以导入组以创建团队或从 Office 组创建团队。

**导入组以组成团队**：将最多 3，500 个成员的组导入 Teams 时，Teams 会自动计算组中的成员总数。 这是一次性导入，将来在 Teams 中不会自动更新组中的更改。

**从大型 Microsoft 365 组创建团队**：从大型 Microsoft 365 组创建团队时，成员会自动成为 Microsoft 365 组 **和** 团队的一部分。 将来，当团队成员加入或离开 Microsoft 365 组时，他们将自动添加或从团队中删除。

## <a name="bulk-importexportremove-members-in-a-team"></a>批量导入/导出/删除团队中的成员

Azure 门户允许用户批量导入/导出/删除 Microsoft 365 组中的成员。 有关详细信息，请参阅 [“批量导入组成员](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)”。

由于每个团队都由 Microsoft 365 组提供支持，因此可以使用Azure 门户在与团队对应的组中执行这些操作。 成员操作将在 24 小时内反映在团队中。

## <a name="create-channels-to-focus-discussions"></a>创建以讨论为重点的频道

可以通过创建重点频道来缩小组讨论的范围。 请参阅 [有关组织团队的最佳做法](best-practices-organizing.md)。

## <a name="restrict-channel-creation"></a>限制通道创建

如果允许任何团队成员创建频道，该团队可以进行频道扩张。 团队所有者应关闭“设置”中成员的通道创建、更新、删除和还原 **>成员权限**。 请参阅 [团队和频道概述](teams-channels-overview.md)。

![显示管理控制台“设置”选项卡的成员权限部分的屏幕图像。](media/no-channel-creation.png "管理员控制台“设置”选项卡的成员权限部分的屏幕图像。允许成员创建或删除通道选项不受选中。")

## <a name="add-favorite-channels"></a>添加收藏频道

为了加快新的用户参与度和内容发现速度，可以选择默认情况下可供用户使用的收藏频道。 在管理中心的 **“频道** ”窗格中，检查 **“显示成员** ”列下的通道。

![显示管理控制台的通道窗格的屏幕图像。](media/favorite-channels.png "显示管理控制台的通道窗格的屏幕图像。为成员检查某些频道是否显示。")

 有关详细信息，请参阅 [“创建第一个团队和频道](get-started-with-teams-create-your-first-teams-and-channels.md) ”。

## <a name="regulate-applications-and-bots-in-large-teams"></a>在大型团队中管理应用程序和机器人

为了防止添加分散注意力的应用程序或机器人，团队所有者可以禁用、添加、删除和上传团队成员的应用和连接器。 在“ **设置”>成员权限** 下的管理中心中，取消选中允许成员添加应用或连接器的三个选项。

![显示“设置”窗格的“成员权限”部分的屏幕图像。](media/disable-bots-connectors.png "显示“设置”窗格的“成员权限”部分的屏幕图像。允许成员添加应用或连接器的选项不受选中。")

请参阅 [Teams 应用概述](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="regulate-team-and-channel-mentions"></a>规范团队和频道提及

团队和频道提及可用于吸引整个团队对某些频道帖子的关注。 在帖子中使用提及后，会向成千上万的团队成员发送通知。 如果通知过于频繁，团队成员可能会重载，并可能向团队所有者投诉。 若要防止提及团队或频道，请取消选中团队 **设置> @mentions** 窗格中的框，关闭对成员的团队和频道提及。

![显示“设置”窗格的“提及”部分的屏幕图像。](media/no-at-mentions.png "显示“设置”窗格的“提及”部分的屏幕图像。未选中显示和授予成员访问提及权限的选项。")

## <a name="consider-setting-up-moderation-in-your-channels"></a>考虑在频道中设置审核

团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。 设置审核后，可以选择一个或多个团队成员作为审核员。 默认情况下，团队所有者是审查者。 有关详细信息，请参阅 [设置和管理通道审查](manage-channel-moderation-in-teams.md)。

## <a name="related-topics"></a>相关主题

- [组织 Teams 的最佳做法](best-practices-organizing.md)
- [创建组织范围的团队](create-an-org-wide-team.md)