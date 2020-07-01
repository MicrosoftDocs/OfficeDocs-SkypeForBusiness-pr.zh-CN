---
title: 管理 Microsoft 团队中的团队策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理组织中的团队策略，以控制用户可在团队和频道中执行的操作。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938141"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的团队策略

作为管理员，你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。 例如，你可以设置是否允许用户在搜索结果和团队库中发现专用团队以及是否允许用户创建专用频道。

通过转到**Teams**  >  Microsoft 团队管理中心中的团队**团队策略**管理团队策略。 你可以使用全局（组织范围默认）策略或创建并分配自定义策略。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。

你可以编辑全局策略，也可以创建并分配自定义策略。 编辑全局策略或分配策略后，可能需要几个小时才能使更改生效。

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。
2. 单击“添加”****。
3. 输入策略的名称和说明。

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. 选择所需的设置：

- **发现专用团队**（在私人预览版中）<a name="discoverteams"> </a> ：启用此设置可允许用户在搜索结果和团队库中发现个人团队。
- **创建专用通道**： <a name="createchannels"> </a>启用此设置可允许用户创建专用频道。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 打开或关闭所需设置，然后单击 "**保存**"。

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[在 Teams 中管理私人团队的发现](manage-discovery-of-private-teams.md)

[团队中的专用频道](private-channels.md)

[向团队中的用户分配策略](assign-policies.md)
