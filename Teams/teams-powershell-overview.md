---
title: Teams PowerShell 概览
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: article
ms.service: msteams
description: 了解如何使用 PowerShell 控件来管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 477aa468cf057bd5f1a042acd5aff9772e8244f0
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442426"
---
# <a name="teams-powershell-overview"></a>Teams PowerShell 概览

Microsoft 团队具有一组丰富的 IT 管理员可以管理通过 Microsoft 团队 & Business Admin Center、 PowerShell 控件和图形 Api 的 Skype 产品的工具。 本指南介绍了我们如何构建 IT 管理员可以使用，我们 PowerShell cmdlet，并提供指向更多文档。 请注意不同工作组管理员角色有权访问不同的 cmdlet。 有关详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。

## <a name="which-modules-do-you-need-to-use"></a>您需要使用哪些模块？

管理团队的 PowerShell 控件是两个不同的 PowerShell 模块中： 
- [Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.5)（公共预览）： 团队 PowerShell 模块包含您需要创建和管理团队的所有 cmdlet。  
- [业务 PowerShell 模块的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366): Skype for Business PowerShell 模块包含 cmdlet 来管理策略、 配置和其他团队工具。 

PowerShell 控件的参考文档会告诉您哪些模块包含正在研究 cmdlet。 （最终，两个模块将合并。）

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以做什么？

阅读[使用的 Microsoft 团队管理角色，来管理工作组](using-admin-roles.md)了解哪些 PowerShell cmdlet 管理不同角色都将能够利用。

## <a name="creating-and-managing-teams-via-powershell"></a>创建和管理团队通过 PowerShell 自定义

用于创建和管理团队的 cmdlet 是在[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3)中。 

团队有后盾 O365 组，因此何时创建工作组，创建一个组。 有一组的操作系统上核心团队和其设置为提供的 cmdlet (``new-team``， ``get-team``， ``set-teamfunsettings``， ``set-teammessagingsettings``， ``set-teamguestsettings``， ``set-teammembersettings``)，管理团队用户 (``add-teamuser``， ``remove-teamuser``)，以及用于管理团队的通道 cmdlet (``new-teamchannel``, ``remove-teamchannel``). 所有这些 cmdlet 可以为最终用户运行，但其将仅参与团队拥有或的成员。 如果您是全局管理员或团队服务管理员，您将能够在组织中的所有团队。

> 使用中的 Microsoft 团队 PowerShell 模块 cmdlet **GroupId**是返回的**Identity**属性相同``Get-UnifiedGroup``Exchange PowerShell 模块中。

## <a name="managing-policies-via-powershell"></a>管理通过 PowerShell 自定义策略

用于管理策略的 cmdlet 是[Skype for Business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。

策略是可以应用于单个用户的粒度设置一组。 每个策略类型都有其自己的创建、 查看、 删除和更新策略本身，然后将这些策略分配给用户用于 cmdlet 集。 一般结构是：

- GET 命令 (例如， ``Get-CsTeamsMeetingPolicy``): 返回供您在您的组织，供您使用 Microsoft 创建的策略和已创建的自定义策略分配的策略文档。
   > 如果您想要查找只有您已在组织中创建自定义策略，则可以使用``-Filter "tag:*"``。

- 新命令 (例如， ``New-CsTeamsMeetingPolicy``): 允许您创建了然后可分配给您的组织中的用户的组织的新策略。 并非所有策略都支持创建的自定义策略。 通常，这是为了确保在组织中使用的策略设置的支持的组合。

- 设置命令 (例如， ``Set-CsTeamsMeetingPolicy``): 允许您在给定的策略设置特定的值。 一些策略没有设置命令可用，或包含不能自定义策略中的参数。 每个 PowerShell 说明将调用出哪些参数不能自定义。 
   > 若要编辑的策略，将默认情况下分配给组织中没有自定义策略分配的用户，请运行``Set-Cs<PolicyName> -Identity Global``。

- 删除命令 (例如， ``Remove-CsTeamsMeetingPolicy``): 您可以使用此 cmdlet 删除您的租户中已创建的自定义策略。 如果您删除已分配给您的组织中的至少一个用户的自定义策略，该用户将回退到全局策略。
   > 您无法实际删除全局策略，在您的组织，但如果您想要将您的组织中的全局策略重置为 Microsoft 提供的默认设置，则可以运行``Remove-Cs<PolicyName> -Identity Global``。

- 授予命令 (例如， ``Grant-CsTeamsMeetingPolicy``): 允许您将策略分配给特定用户。
   > 若要删除一个自定义策略分配并使用户回退到您的组织中的默认策略，请运行``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。

> [!TIP]
> 并非所有策略都允许要创建的自定义策略和一些策略具有不能自定义的设置 (使您可以查看的设置，但无法设置过程中的自定义值``set-``和``new-``)。 如果参数不是可供客户使用将调用的特定 cmdlet 的文档。

常见的参数：

- **标识**： 为``Get-``， ``Set-``， ``New-``，和``Remove-``， **Identity**参数将始终引用一个特定的策略实例。 为``Grant``， **Identity**参数指的是应用策略的特定用户对象。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>管理通过 PowerShell 自定义配置

用于管理您的配置的 cmdlet 是[Skype for Business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。

配置是存储桶的维护中不能在用户级别指定的服务的设置。 在整个组织始终应用设置。 全局配置是在组织中的唯一有效的配置。 每种配置类型附带的两个主要 cmdlet:

- 例如：``Get-Cs<ConfigurationName>``。 

- 设置命令 (例如， ``Set-CsTeamsClientConfiguration``): 该类型的配置中设置属性。 指定要修改的参数。
   > 您可以引用正在修改以下两种方式中的配置： 通过指定-**Identity 全局**，或通过运行``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``。

## <a name="other-powershell-tools"></a>其他 PowerShell 工具

您可以找到详细的说明如何管理 Microsoft 团队和 Skype 的业务需要，包括详细的说明中的[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和[Skype 的每个策略中的设置为使用所有 PowerShell 控件业务 cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="learn-more"></a>了解更多信息

- [Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype 的业务 cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)
