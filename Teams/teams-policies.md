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
ms.openlocfilehash: 727bb8b133d5119cd396c79561dde453281206f0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432264"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>管理频道策略Microsoft Teams

作为管理员，可以使用团队策略Microsoft Teams控制组织中用户可在团队和频道中执行哪些操作。 例如，可以设置是否允许用户创建专用通道。

若要管理团队策略，Teams Teams  >  **管理中心Microsoft Teams** 策略。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。

可以编辑全局策略，也可以创建和分配自定义策略。 编辑全局策略或分配策略后，可能需要几个小时更改才能生效。

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在管理中心左侧导航Microsoft Teams，转到 **"Teams Teams**  >  **策略"。**
2. 单击“**添加**”。
3. 输入策略的名称和说明。

    ![团队策略设置的屏幕截图。](media/teams-policies.png)
4. 打开或关闭 **"创建专用频道**<a name="createchannels"></a>"，具体取决于是否要允许用户创建专用频道。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

可以编辑全局策略或创建的任何自定义策略。

1. 在管理中心左侧导航Microsoft Teams，转到 **"Teams Teams**  >  **策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 打开或关闭想要的设置，然后单击"保存 **"。**

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相关主题

[管理Teams连接的站点和频道网站](/SharePoint/teams-connected-sites)

[专用频道Teams](private-channels.md)

[向 Teams 中的用户分配策略](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
