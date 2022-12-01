---
title: 在 Microsoft Teams 中管理频道策略
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
- chat-teams-channels-revamp
description: 了解如何在组织中使用和管理团队频道策略，以控制用户可以在团队和频道中执行的操作。
ms.openlocfilehash: 1223f191550675d5edd7b99a1cf9820fa14c9992
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198554"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理频道策略

作为管理员，你可以使用 Microsoft Teams 中的策略来控制组织中的用户可以在团队和频道中执行哪些操作。 例如，可以设置是允许用户创建专用频道还是共享频道。

可通过转到 Microsoft Teams 管理中心中的 **Teams** >  Teams **策略** 来管理团队策略。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

可以编辑全局策略，也可以创建并分配自定义策略。 编辑全局策略或分配策略后，更改可能需要 24 小时才能生效。

## <a name="channel-policies"></a>通道策略

以下策略适用于团队频道：

|策略|说明|
|:-----|:----------|
|**创建专用频道**|**启用** 时，团队所有者和成员可以创建专用频道。  (团队所有者可以控制成员是否可以在每个团队中创建专用频道。) |
|**创建共享频道**|**打开时**，团队所有者可以创建共享频道。 适用于你的组织的 Teams 应用也可在共享频道中使用。|
|**邀请外部用户加入共享频道**|**打开时**，共享频道的所有者和成员可以从已配置跨组织信任的组织邀请外部参与者。 组织的 Teams 策略适用于这些频道。|
|**加入外部共享频道**|**启用时**，用户可以参与已配置跨组织信任的其他组织创建的共享频道。 其他组织的 Teams 策略适用于这些频道。|

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams** > **Teams 策略**。
2. 单击“**添加**”。
3. 输入策略的名称和说明。

    ![团队策略设置的屏幕截图。](media/teams-policies.png)
4. 打开或关闭所需的设置，然后单击“ **保存**”。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

可以编辑全局策略或创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **Teams** > **Teams 策略**。
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 打开或关闭所需的设置，然后单击“ **保存**”。

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[管理 Teams 连接的站点和频道网站](/SharePoint/teams-connected-sites)

[Teams 中的专用频道](private-channels.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
