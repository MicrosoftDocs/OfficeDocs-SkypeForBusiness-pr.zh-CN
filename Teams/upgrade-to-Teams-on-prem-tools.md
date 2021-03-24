---
title: 用于从 Skype for Business 本地部署升级到 Teams 的工具
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams 的工具
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097498"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>适用于 IT 管理员的升级到 Teams &mdash; 的工具

本文介绍从 Skype for Business 升级到 Teams 的工具。 

在开始升级之前，Microsoft 建议以下文章介绍重要的升级概念和共存行为：

- [Teams 和 Skype for Business 共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>用于管理升级的工具

无论选择哪种升级方法，对于已有 Skype for Business Online 的用户，你使用 [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)管理到 Teams 的转换，它控制用户的共存模式。 对于在 Skype for Business Server 中拥有本地帐户的用户，还可使用 将其 `Move-CsUser` [移动到云 。](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  有关每个模式详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

> [!NOTE]
> 如果你当前正在使用 Skype for Business Online 连接器管理服务，则需要移动到 Teams PowerShell 模块并更新现有的 PowerShell 脚本。 有关详细信息 [，请参阅从 Skype for Business Online 连接器移动到 Teams PowerShell](teams-powershell-move-from-sfbo.md) 模块。

无论你是使用 Skype for Business 模式执行选择功能转换，还是只是从默认群岛配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 都是已拥有 Skype for Business Online 的用户的主要工具。 与 Teams 中的其他任何策略一样，可以直接将 TeamsUpgradePolicy 分配给用户。 还可以将策略设置为租户范围的默认值。 向用户分配的任何作业优先于租户默认设置。  可以在 Teams 管理控制台和 PowerShell 中管理策略。

还可以将 TeamsUpgradePolicy 的任何模式（TeamsOnly 模式除外）分配给本地 Skype for Business 中的用户。 **TeamsOnly 模式只能分配给** 已位于 Skype for Business Online 中的用户。 这是因为只有在用户位于 Skype for Business Online 中时，才能与 Skype for Business 用户和联合身份验证以及 Microsoft 365 电话系统功能进行互操作。 此外，如果你有 Skype for Business 本地部署 (，则不能将 **TeamsOnly** 模式分配为租户范围默认值。如果存在指向 Office 365 之外位置的 lyncdiscover DNS 记录，则检测到此模式。

在本地拥有 Skype for Business 帐户的用户[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)必须联机 (移动到 Skype for Business Online 或直接移动到 Teams) （使用 Skype for Business 本地工具集的 Move-CsUser）。 这些用户可以通过 1 或 2 个步骤移动到 TeamsOnly：

-   1 步：在 Move-CsUser 中指定 -MoveToTeams 开关。 这需要具有 CU8 或更高版本的 Skype for Business Server 2019 或 Skype for Business Server 2015。

-   2 个步骤：运行 Move-CsUser 后，使用 TeamsUpgradePolicy 向用户授予 TeamsOnly 模式。

与其他策略不同，在 Microsoft 365 或 Office 365 中无法创建新的 TeamsUpgradePolicy 实例。 所有现有实例都内置于服务中。   (请注意，模式是 TeamsUpgradePolicy 中的一个属性，而不是策略实例的名称。) 在某些（但并非所有）情况下，策略实例的名称与模式相同。 具体而言，若要将 TeamsOnly 模式分配给用户，需要向该用户授予 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 若要查看所有实例的列表，可以运行以下命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要将联机用户升级到 TeamsOnly 模式，请分配"UpgradeToTeams"实例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要将本地 Skype for Business 用户升级到 TeamsOnly 模式，请使用Move-CsUser工具集：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要更改租户中所有用户的模式，但具有按用户显式授予权限的用户除外 (优先) ，请运行以下命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果有任何用户拥有本地 Skype for Business 帐户，则不能在租户级别分配 TeamsOnly 模式。 必须使用 Move-CsUser 将这些用户单独移动到云。


## <a name="using-notifications-in-skype-for-business-clients"></a>在 Skype for Business 客户端中使用通知

管理员可以选择在 Skype for Business 客户端中提供最终用户通知，以通知用户他们即将升级到 Teams，如下图所示。 例如，在管理员计划将一组用户升级到 TeamsOnly 模式之前一周，管理员可能需要为该组用户启用这些通知。 这些通知是使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 实例启用的。  对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。  对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

如果你的用户在 Skype for Business Online 中，只需分配与用户模式相同的策略实例，但使用 NotifySfbUsers=true。 

如果用户位于本地 Skype for Business Server 中，则需要使用本地工具集，并且需要 Skype for Business Server 2019 或 CU8 for Skype for Business Server 2015。 对于本地 Skype for Business Server 中的用户，将遵守 TeamsUpgradePolicy 联机实例中的 mode 属性，但不使用 NotifySfbUsers 属性。 如果需要通知，则必须创建 TeamsUpgradePolicy 本地实例来控制客户端行为。 

在本地 PowerShell 窗口中，使用 NotifySfbUsers=true 创建 TeamsUpgradePolicy 的新实例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

然后，使用相同的本地 PowerShell 窗口，将新策略分配给所需的用户：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>会议迁移

当用户迁移到 TeamsOnly 模式时，默认情况下，他们组织的现有 Skype for Business 会议将转换为 Teams。 可以选择在将 TeamsOnly 模式分配给用户时禁用默认行为。 将用户从本地移动时，会议必须迁移到云，以便使用联机用户帐户运行，但如果您未指定 -MoveToTeams，会议将迁移为 Skype for Business 会议，而不是转换为 Teams。 

在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。 如果要在租户级别分配 TeamsOnly 模式并迁移会议，可以使用 PowerShell 获取租户 (中的用户列表，例如，将 Get-CsOnlineUser 与所需的筛选器一同使用) 然后循环访问每个用户，以使用 Start-CsExMeetingMigration 触发会议迁移。 有关详细信息，请参阅[使用会议迁移服务 (MMS) 。 ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>相关链接

[共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)