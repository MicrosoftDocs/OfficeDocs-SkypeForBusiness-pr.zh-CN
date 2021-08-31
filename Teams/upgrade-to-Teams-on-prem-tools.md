---
title: 用于从本地Teams升级到 Skype for Business 的工具
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 用于从 Skype for Business 升级到 Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729301"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>适用于 IT 管理员Teams &mdash; 升级工具

本文介绍用于从 Teams 升级到 Skype for Business。 

在开始升级之前，Microsoft 建议以下文章介绍重要的升级概念和共存行为：

- [Teams 和 Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>用于管理升级的工具

无论选择哪种升级方法，对于已有 Skype for Business Online 的用户，可以使用[TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)管理到 TeamsOnly 的转换，它控制用户的共存模式。 对于在云中具有本地帐户Skype for Business Server，还可使用 `Move-CsUser` 将其[移动到云](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有关每个模式详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。

> [!NOTE]
> 如果当前正在使用 Skype for Business Online 连接器来管理服务，则需要移动到 powerShell Teams并更新现有的 PowerShell 脚本。 有关详细信息[，请参阅](teams-powershell-move-from-sfbo.md)从 Skype for Business Online 连接器Teams PowerShell 模块。

无论你是使用新模式执行Skype for Business转换，还是只是从默认的 Islands 配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 都是主要工具。与 Teams策略一样，可以直接将 TeamsUpgradePolicy 分配给用户。 还可以将策略设置为租户范围的默认值。 向用户分配的任何作业优先于租户默认设置。  可以在管理控制台和 PowerShell Teams管理策略。

可以将 TeamsUpgradePolicy 的任何模式（TeamsOnly 模式除外）分配给本地Skype for Business用户。 相反，只能为托管在云中的用户分配 TeamsOnly 模式。 **只能将 TeamsOnly** 模式分配给已托管在云中的用户，因为只有该用户位于 Skype for Business Online 中，才能与 Skype for Business 用户以及 Microsoft 365 电话系统 功能进行互操作和联合。  此外，如果具有 Skype for Business 本地部署 (，则不能将 **TeamsOnly** 模式分配为租户范围的默认值 (该部署通过 lyncdiscover DNS 记录（指向 Office 365 外的位置）检测到。 有关详细信息，请参阅[禁用混合配置以完成迁移到"仅Teams"。](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)

在本地Skype for Business帐户的用户必须使用本地工具Teams工具Move-CsUser帐户[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)Skype for Business仅模式。 

与其他策略不同，不可在 Microsoft 365 或 Office 365 中创建新的 TeamsUpgradePolicy 实例。 所有现有实例都内置于服务中。   (请注意，模式是 TeamsUpgradePolicy 中的一个属性，而不是策略实例的名称。) 在某些（但并非所有）情况下，策略实例的名称与模式相同。 具体而言，若要将 TeamsOnly 模式分配给用户，需要向该用户授予 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 若要查看所有实例的列表，可以运行以下命令：

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

若要将联机用户升级到 TeamsOnly 模式，请分配"UpgradeToTeams"实例： 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

若要将本地用户Skype for Business TeamsOnly 模式，请使用Move-CsUser工具集：

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

若要更改租户中所有用户的模式，但具有按用户显式授予权限的用户除外 (优先) ，请运行以下命令：

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>如果有任何用户在本地Skype for Business帐户，则不能在租户级别分配 TeamsOnly 模式。 必须使用 Move-CsUser 将这些Teams移动到"仅"模式。


## <a name="using-notifications-in-skype-for-business-clients"></a>在客户端Skype for Business通知

管理员可以选择在客户端中提供最终用户Skype for Business通知用户他们即将升级到 Teams，如下图所示。 例如，在管理员计划将一组用户升级到 TeamsOnly 模式之前一周，管理员可能需要为该组用户启用这些通知。 这些通知是使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 实例启用的。  对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。  对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。 

![显示通知的图表。](media/teams-upgrade-sfb-with-notifications.png)

如果用户在 Skype for Business Online 中，只需分配与用户模式相同的策略实例，但使用 NotifySfbUsers=true。 

如果用户位于 Skype for Business Server 本地，则需要使用本地工具集，并且需要 Skype for Business Server 2019 或 CU8 Skype for Business Server 2015。 对于本地 Skype for Business Server中的用户，将遵守 TeamsUpgradePolicy 联机实例中的 mode 属性，但不使用 NotifySfbUsers 属性。 如果需要通知，则必须创建 TeamsUpgradePolicy 本地实例来控制客户端行为。 

在本地 PowerShell 窗口中，使用 NotifySfbUsers=true 创建 TeamsUpgradePolicy 的新实例：

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

然后，使用相同的本地 PowerShell 窗口将新策略分配给所需的用户：

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>会议迁移

当用户迁移到 TeamsOnly 模式时，默认情况下，他们Skype for Business的现有会议将转换为Teams。 可以选择在将 TeamsOnly 模式分配给用户时禁用默认行为。 将用户从本地移动时，必须将会议迁移到云，以便使用联机用户帐户运行，但如果您未指定 -MoveToTeams，会议将迁移为 Skype for Business 会议，而不是转换为 Teams。 

在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。 如果要在租户级别分配 TeamsOnly 模式并迁移会议，可以使用 PowerShell 获取租户 (中的用户列表，例如，将 Get-CsOnlineUser 与所需的筛选器一起使用) 然后循环访问每个用户，以使用 Start-CsExMeetingMigration 触发会议迁移。 有关详细信息，请参阅[使用会议迁移服务 (MMS) 。 ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>相关链接

[共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
