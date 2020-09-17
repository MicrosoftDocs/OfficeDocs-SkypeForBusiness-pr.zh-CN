---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940625"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>面向 IT 管理员的团队升级工具 &mdash;

本文介绍了用于升级到团队的工具。 本文是针对 IT 管理员介绍升级概念和实现的第三个。  

- [概述](upgrade-to-teams-on-prem-overview.md)
- [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)
-  (本文中**用于管理升级的工具**) 
- [具有 Skype for business 内部部署的组织的其他注意事项](upgrade-to-teams-on-prem-considerations.md)
- [实现升级](upgrade-to-teams-on-prem-implement.md)
- [ (PSTN) 注意事项的公共交换电话网络](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>用于管理升级的工具

无论选择哪种升级方法，都可以使用 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)（用于控制用户的共存模式）管理到 TeamsOnly 的切换。 有关每种模式的详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

无论是使用 Skype for Business 模式执行选择功能过渡，还是只从默认孤岛配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 是主要工具。 与团队中的任何其他策略一样，你可以将 TeamsUpgradePolicy 直接分配给用户。 您也可以将策略设置为租户范围内的默认设置。 对用户的任何分配都优先于租户默认设置。  你可以在团队管理控制台和 PowerShell 中管理该策略。

你可以将用户的任何模式分配给用户，无论用户是托管在 Skype for Business Online 还是在本地， **除了只能将 TeamsOnly 模式分配给已驻留在 skype for Business online 中的用户**。 这是因为使用 Skype for Business 用户和联盟以及 Microsoft 365 Phone 系统功能的互操作仅在用户托管在 Skype for business Online 中时才可以使用。

具有 Skype for business 帐户的 Skype for business 帐户的用户 [必须在线 (移动](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 到 skype For business online 或直接与团队) 使用 Skype for business 内部部署工具单中的 "移动 move-csuser"。 这些用户可以通过1个或2个步骤移到 TeamsOnly：

-   1步：在 Move-csuser 中指定-MoveToTeams 开关。 这需要具有 CU8 或更高版本的 Skype for business Server 2019 或 Skype for business Server 2015。

-   2个步骤：运行移动 Move-csuser 后，使用 TeamsUpgradePolicy 向用户授予 TeamsOnly 模式。

与其他策略不同，不能在 Microsoft 365 或 Office 365 中创建新的 TeamsUpgradePolicy 实例。 所有现有实例都内置在该服务中。   (注意，mode 是 TeamsUpgradePolicy 内的一个属性，而不是策略实例的名称。 ) 在某些-但不是所有情况下，策略实例的名称与模式相同。 特别是，若要为用户分配 TeamsOnly 模式，请将 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例授予该用户。 若要查看所有实例的列表，可以运行以下命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要将联机用户升级到 TeamsOnly 模式，请分配 "UpgradeToTeams" 实例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要将内部部署的 Skype for business 用户升级到 TeamsOnly 模式，请在本地工具集中使用移动 Move-csuser：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

若要为租户中的所有用户更改模式，但具有明确的每用户授权 (的模式优先) ，请运行以下命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果你拥有本地 Skype for Business 帐户的任何用户，则不能在租户级别分配 TeamsOnly 模式，除非你将其他模式显式分配给具有本地 Skype for Business 帐户的所有用户。


## <a name="using-notifications-in-skype-for-business-clients"></a>在 Skype for Business 客户端中使用通知

管理员可以选择在 Skype for Business 客户端中提供最终用户通知，以通知用户即将升级到团队，如下图所示。 例如，管理员计划将一组用户升级到 TeamsOnly 模式之前的一周，管理员可能希望为该组用户启用这些通知。 使用 NotifySfbUsers = true 的 TeamsUpgradePolicy 实例启用这些通知。  对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。  对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

如果你的用户托管在 Skype for Business Online 中，只需分配与用户具有相同模式的策略实例，但 NotifySfbUsers = true。 

如果你的用户托管在本地 Skype for business 服务器中，你需要使用本地工具集，你需要使用 skype for business server 2019 或 CU8 for Skype for business Server 2015。 对于驻留在本地 Skype for business 服务器中的用户，将接受 TeamsUpgradePolicy 的 online 实例的 mode 属性，但 NotifySfbUsers 属性不是。 如果需要通知，必须创建 TeamsUpgradePolicy 的本地实例以控制客户端行为。 

在本地 PowerShell 窗口中，使用 NotifySfbUsers = true 创建 TeamsUpgradePolicy 的新实例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

然后，使用相同的本地 PowerShell 窗口，将该新策略分配给所需的用户：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>会议迁移

当用户迁移到 TeamsOnly 模式时，默认情况下，他们组织的现有 Skype for Business 会议将被转换为团队。 你可以选择禁用向用户分配 TeamsOnly 模式时的默认行为。 从本地移动用户时，必须将会议迁移到云才能使用联机用户帐户运行，但如果未指定-MoveToTeams，则会议将作为 Skype for Business 会议进行迁移，而不是转换为团队。 

在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。 如果你想要在租户级别分配 TeamsOnly 模式和迁移会议，则可以使用 PowerShell 获取租户中的用户列表 (例如，将 CsOnlineUser 与) 需要的任何筛选器一起使用，然后遍历这些用户中的每个用户以使用启动-CsExMeetingMigration 触发会议迁移。 有关详细信息，请参阅 [使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。



## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

