---
title: 管理频道策略Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
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
description: 了解如何使用和管理组织中团队频道策略来控制用户可在团队和频道中执行哪些操作。
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711776"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>管理频道策略Microsoft Teams

作为管理员，可以使用团队Microsoft Teams中的策略来控制组织中用户可以在团队和频道中执行哪些操作。 例如，可以设置是允许用户创建专用通道还是共享通道。

若要管理团队策略，**Teams** >  **Teams管理中心Microsoft Teams** 策略。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

可以编辑全局策略，也可以创建和分配自定义策略。 编辑全局策略或分配策略后，更改可能需要 24 小时才能生效。

## <a name="channel-policies"></a>通道策略

以下策略适用于团队频道：

|策略|说明|
|:-----|:----------|
|**创建专用频道**|打开 **时**，团队所有者和成员可以创建专用频道。  (团队所有者可以控制成员是否可在每个团队中创建专用频道。) |
|**创建共享通道**|打开 **时**，团队所有者可以创建共享频道。 Teams组织可用的应用也在共享频道中可用。|
|**邀请外部用户加入共享频道**|启用 **时**，共享频道的所有者和成员可以从已配置跨组织信任的组织邀请外部参与者。 Teams组织的策略适用于这些渠道。|
|**加入外部共享频道**|**打开时**，用户可以参与其他组织创建的共享频道，其中已配置了跨组织信任。 Teams组织的策略适用于这些通道。|

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在管理中心左侧导航Microsoft Teams **，转到"** > Teams **Teams策略"**。
2. 单击“**添加**”。
3. 输入策略的名称和说明。

    ![团队策略设置的屏幕截图。](media/teams-policies.png)
4. 打开或关闭想要的设置，然后单击"保存 **"**。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心左侧导航Microsoft Teams **，转到"** > Teams **Teams策略"**。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 打开或关闭想要的设置，然后单击"保存 **"**。

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[管理Teams连接的站点和频道网站](/SharePoint/teams-connected-sites)

[专用频道Teams](private-channels.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
