---
title: 团队 PowerShell 概述
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用用于管理 Microsoft 团队的 PowerShell 控件，包括 PowerShell cmdlet 的结构。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c74f27af718b10aa033c51d4b42d1a3d15bcbc1b
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690948"
---
# <a name="teams-powershell-overview"></a>团队 PowerShell 概述

Microsoft 团队拥有一组丰富的工具，可供 IT 管理员通过 Microsoft 团队管理中心、PowerShell 控件和图形 Api 管理产品。 本指南介绍我们如何构建我们的 PowerShell cmdlet 以供 IT 管理员使用，并提供了指向更多文档的指针。 请注意，不同的团队管理员角色具有访问不同 cmdlet 的权限。 有关详细信息，请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。

## <a name="which-modules-do-you-need-to-use"></a>需要使用哪些模块？

用于管理团队的 PowerShell 控件位于两个不同的 PowerShell 模块中： 
- [Microsoft 团队 powershell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)：团队 powershell 模块包含创建和管理团队所需的所有 cmdlet。  
- [Skype for Business powershell 模块](https://www.microsoft.com/download/details.aspx?id=39366)： skype For business powershell 模块包含用于管理策略、配置和其他团队工具的 cmdlet。 

PowerShell 控件的参考文档将告诉你你正在调查的 cmdlet 所在的模块。 （最终，将组合两个模块。）

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以执行哪些操作？

已阅读[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)，了解不同管理员角色可以利用的 PowerShell cmdlet。

## <a name="creating-and-managing-teams-via-powershell"></a>通过 PowerShell 创建和管理团队

用于创建和管理团队的 cmdlet 位于[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。 

团队由 Microsoft 365 组支持，因此当你创建团队时，将创建一个组。 提供了一组 cmdlet，用于在核心团队及其设置（ ``new-team`` 、 ``get-team`` 、 ``set-team`` ）、管理团队用户（、）以及 ``add-teamuser`` ``remove-teamuser`` 用于管理团队频道（ ``new-teamchannel`` 、）的 cmdlet ``remove-teamchannel`` 之间进行操作。 所有这些 cmdlet 都可以作为最终用户运行，但它们仅适用于您拥有或属于其成员的团队。 如果你是全局管理员或团队服务管理员，你将能够针对组织中的所有团队执行操作。

> Microsoft 团队 PowerShell 模块 cmdlet 中使用的**GroupId**与 Exchange PowerShell 模块中返回的**Identity**属性相同 ``Get-UnifiedGroup`` 。

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>预览和一般可用的 Microsoft 团队 PowerShell 模块之间的差异

发布了我们的 PowerShell 模块的通用版本后，仅在 beta 模块中保留几个 cmdlet，如下表所述。

| Cmdlet | 预览中的可用 | 1.0 中提供 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | 是 | 是 |
| Connect-MicrosoftTeams | 是 | 是 |
| 断开连接-MicrosoftTeams | 是 | 是 |
| 获取团队 | 是 | 是 |
| TeamChannel | 是 | 是 |
| TeamFunSettings | 仅限1.0 发布之前 | 否 |
| TeamGuestSettings | 仅限1.0 发布之前 | 否 |
| TeamHelp | 是 | 是 |
| TeamMemberSettings | 仅限1.0 发布之前 | 否 |
| TeamMessagingSettings | 仅限1.0 发布之前 | 否 |
| TeamUser | 是 | 是 |
| 新团队 | 是 | 是 |
| 新-TeamChannel | 是 | 是 |
| 删除-团队 | 是 | 是 |
| Remove-TeamChannel | 是 | 是 |
| Remove-TeamUser | 是 | 是 |
| 集-团队 | 是 | 是 |
| Set-TeamChannel | 是 | 是 |
| Set-TeamFunSettings | 仅限1.0 发布之前 | 否 |
| Set-TeamGuestSettings | 仅限1.0 发布之前 | 否 |
| Set-TeamMemberSettings | 仅限1.0 发布之前 | 否 |
| Set-TeamMessagingSettings | 仅限1.0 发布之前 | 否 |
| Set-TeamPicture | 是 | 无、计划内 |


## <a name="managing-policies-via-powershell"></a>通过 PowerShell 管理策略

使用[Skype For business cmdlet 模块](https://www.microsoft.com/download/details.aspx?id=39366)中的 cmdlet 管理单个用户的策略。

> [!NOTE]
> 一旦连接到 Skype for Business Online，cmdlet 将在你的 PowerShell 会话中可用。 有关详细信息，请参阅[管理 Microsoft 365 或 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。 

策略是一组可对单个用户进行精确应用的设置。 每个策略类型都有自己的一组用于创建、查看、删除和更新策略的 cmdlet，然后将这些策略分配给用户。 常规结构是：

- 获取命令（例如 ``Get-CsTeamsMeetingPolicy`` ）：返回可供您在组织中分配的策略文档，由 Microsoft 创建以供您使用的策略和您创建的自定义策略。
   > 如果您只想查找您在组织中创建的自定义策略，则可以使用 ``-Filter "tag:*"`` 。

- 新命令（例如 ``New-CsTeamsMeetingPolicy`` ）：让你可以为你的组织创建新策略，这些策略随后可分配给你的组织中的用户。 并非所有策略都支持创建自定义策略。 通常，这是为了确保您在组织中使用的策略具有受支持的设置组合。

- SET 命令（例如 ``Set-CsTeamsMeetingPolicy`` ）：允许你在给定策略上设置特定值。 某些策略没有可用的 set 命令，或者包含无法在策略中自定义的参数。 每个 PowerShell 说明将调用无法自定义的参数。 
   > 若要编辑默认情况下将分配给您的组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。

- 删除命令（例如 ``Remove-CsTeamsMeetingPolicy`` ）：你可以使用此 cmdlet 删除已在租户中创建的自定义策略。 如果您删除的自定义策略已分配给您的组织中的至少一个用户，该用户将回退到全局策略。
   > 你不能真正删除你的组织中的全局策略，但是如果你想要将组织中的全局策略重置为 Microsoft 提供的默认设置，则可以运行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- "授予" 命令（例如 ``Grant-CsTeamsMeetingPolicy`` ）：允许您向特定用户分配策略。
   > 若要删除自定义策略分配并使用户回退到组织中的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 并非所有策略都允许创建自定义策略，某些策略具有你无法自定义的设置（因此你可以查看设置，但不能在和期间设置自定义值 ``set-`` ``new-`` ）。 如果参数不可供客户使用，特定 cmdlet 的文档将会调用。

常用参数：

- **标识**：对于 ``Get-`` 、 ``Set-`` 、 ``New-`` 和， ``Remove-`` **identity**参数将始终引用特定策略实例。 对于 ``Grant`` ， **Identity**参数引用要对其应用策略的特定用户对象。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>通过 PowerShell 管理配置

用于管理您的配置的 cmdlet 位于[Skype For business cmdlet 模块](https://www.microsoft.com/download/details.aspx?id=39366)中。

配置是在服务中维护的不能在用户级别指定的设置的存储桶。 设置始终在整个组织中应用。 您的全局配置是您的组织中唯一有效的配置。 每种配置类型均带有两个主要 cmdlet：

- ``Get-Cs<ConfigurationName>``（例如 ``Get-CsTeamsClientConfiguration`` ）： 

- SET 命令（例如 ``Set-CsTeamsClientConfiguration`` ）：在该类型的配置中设置属性。 指定要修改的参数。
   > 你可以通过以下两种方式之一引用你正在修改的配置：通过指定**全局标识**或通过运行进行修改 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="other-powershell-tools"></a>其他 PowerShell 工具

有关如何使用用于管理 Microsoft 团队和 Skype for business 的所有 PowerShell 控件的详细说明，包括每个策略中的设置的详细说明，请参阅[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和[Skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="learn-more"></a>了解详细信息

- [Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)
