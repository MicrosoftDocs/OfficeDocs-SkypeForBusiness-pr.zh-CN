---
title: 使用 Microsoft Teams PowerShell 管理 Teams
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams PowerShell 管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756150"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 Microsoft Teams PowerShell 管理 Teams

本文演示如何使用 Microsoft Teams PowerShell 管理 Teams 和 Skype for Business。 

将本指南与 [Microsoft Teams cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 和 Skype for Business [cmdlet 参考结合使用](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 创建和管理团队

用于创建和管理团队的 cmdlet 在 Microsoft [Teams PowerShell 模块 中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。

Teams 由 Office 365 组支持，因此创建团队时，会创建一个组。 提供了一组 cmdlet 用于核心团队及其设置 （ (、、) 、管理团队用户 (、) ）以及用于管理团队 (、) 的频道的 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` cmdlet。 所有这些 cmdlet 都可以作为最终用户运行，但它们只能在你拥有或成员的团队中运行。 如果你是全局管理员或 Teams 服务管理员，你将能够对组织的所有团队采取行动。

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Microsoft Teams PowerShell 模块 cmdlet 中使用的 **GroupId** 与Exchange PowerShell 模块中返回的 ``Get-UnifiedGroup`` Identity 属性相同。

## <a name="manage-policies-via-powershell"></a>通过 PowerShell 管理策略

> [!NOTE]
> - Skype for Business Online 连接器正在整合到 Teams PowerShell 中。 它目前以公共预览版提供。 随后，适用于 Teams 的 Skype for Business Online cmdlet 将在 Teams PowerShell 模块中本机提供。 安装步骤可在安装 [Teams PowerShell](teams-powershell-install.md) 一文获得。
>
> - 连接到 Skype for Business Online 后，这些 cmdlet 将在 PowerShell 会话中可用。 有关详细信息，请参阅使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)管理 Skype for Business Online。

在 Skype for Business cmdlet 模块 中查找用于管理策略[的 cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

策略是一组设置，可以精细地应用于单个用户。 每个策略类型都有其自己的一组 cmdlet，用于创建、查看、删除和更新策略本身，然后将这些策略分配给用户。 一般结构为：

- **GET** (例如，) ：返回可供你在组织中分配的策略文档，包括 Microsoft 创建供你使用的策略以及你创建的自定义策略。 ``Get-CsTeamsMeetingPolicy``
   - 若要仅查找在组织中创建的自定义策略，请使用 ``-Filter "tag:*"`` 。

- **新** (例如，) ：为组织创建新策略 ``New-CsTeamsMeetingPolicy`` 以分配给组织的用户。 并非所有策略都支持创建自定义策略。 通常，这是为了确保在组织中使用的策略具有受支持的设置组合。

- **SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy`` ，) ：在给定策略上设置特定值。 某些策略没有可用的 SET 命令，或者包含在策略中无法自定义的参数。 PowerShell 说明告知无法自定义哪些参数。 
   - 若要编辑默认情况下将分配给组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **删除** (，例如) ：删除已在租户 ``Remove-CsTeamsMeetingPolicy`` 中创建的自定义策略。 如果删除已分配给组织中至少一个用户的自定义策略，该用户将回退到全局策略。
   - 实际上无法删除组织的全局策略，但如果要将组织中全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT** 命令 (例如 ``Grant-CsTeamsMeetingPolicy`` ，) ：向特定用户分配策略。
   - 若要删除自定义策略分配，并让用户回退到组织的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 并非所有策略都允许创建自定义策略，并且某些策略具有无法自定义 (因此可以查看设置，但无法设置自定义值期间和 ``set-`` ``new-``) 。 每个 cmdlet 的文档会指出参数是否可供客户使用。

常见参数：

- **标识**： ``Get-`` 对于 ``Set-`` 、、 ``New-`` 和 ``Remove-`` **，Identity** 参数将始终引用特定的策略实例。 对于 ``Grant`` **，Identity** 参数是指要应用策略的特定用户对象。

## <a name="manage-configurations-via-powershell"></a>通过 PowerShell 管理配置

在 Skype for Business cmdlet 模块 中查找用于管理配置的[cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

配置是服务中维护的设置存储桶，无法以用户级别指定。 设置始终应用于整个组织。 全局配置是组织中唯一有效的配置。 每个配置类型附带两个主要 cmdlet：

- ``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：

- SET (例如 ``Set-CsTeamsClientConfiguration`` ，) ：设置该类型的配置中的属性。 指定要修改的参数。
   > 可以通过以下两种方式之一引用要修改的配置：通过指定 -**Identity Global** 或运行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以执行哪些功能？

请阅读 [使用 Microsoft Teams 管理员角色管理 Teams，](using-admin-roles.md) 了解哪些管理员角色可以运行每个 PowerShell cmdlet。

## <a name="related-topics"></a>相关主题

[安装 Teams PowerShell](teams-powershell-install.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Teams cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Teams 管理员角色管理 Teams](using-admin-roles.md)
