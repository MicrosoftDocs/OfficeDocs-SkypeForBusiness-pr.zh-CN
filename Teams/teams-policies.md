---
title: 在 Microsoft Teams 中管理团队策略
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 了解如何使用和管理组织中团队策略来控制用户可在团队和频道中执行哪些操作。
ms.openlocfilehash: a05aaf65418e46f7b631bac6f7d88d8bbdf4c806
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802362"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理团队策略

作为管理员，可以使用 Microsoft Teams 中的团队策略来控制组织中用户可以在团队和频道中执行哪些操作。 例如，可以设置是否允许用户创建专用通道。

通过访问 Microsoft Teams 管理中心中的 **Teams**  >  **Teams** 策略来管理团队策略。 可以使用全局策略 (组织范围内的默认) 策略，也可以创建和分配自定义策略。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。

可以编辑全局策略，也可以创建和分配自定义策略。 编辑全局策略或分配策略后，可能需要几个小时更改才能生效。

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams**  >  **策略**。
2. 单击“添加”。
3. 输入策略的名称和说明。

    ![Teams 策略设置的屏幕截图](media/teams-policies.png)
4. 打开或关闭"**创建专用**<a name="createchannels"></a>通道"，具体取决于是否要允许用户创建专用频道。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

可以编辑全局策略或创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams**  >  **策略**。
2. 单击策略名称左侧选择策略，然后单击"编辑 **"。**
3. 打开或关闭您需要的设置，然后单击"保存 **"。**

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[Teams 中的专用频道](private-channels.md)

[在 Teams 中向用户分配策略](assign-policies.md)

[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
