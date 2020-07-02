---
title: 通过 Microsoft 团队 PowerShell 管理团队
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
description: 了解如何使用团队 PowerShell 管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944086"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>通过 Microsoft 团队 PowerShell 管理团队

本文介绍如何使用 Microsoft 团队 PowerShell 管理团队和 Skype for business。 

将本指南与[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和[Skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)结合使用。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 创建和管理团队

用于创建和管理团队的 cmdlet 位于[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。

团队受 Office 365 组支持，因此当您创建团队时，将创建一个组。 提供了一组 cmdlet，用于在核心团队及其设置（ ``new-team`` 、 ``get-team`` 、 ``set-team`` ）、管理团队用户（、）以及 ``add-teamuser`` ``remove-teamuser`` 用于管理团队频道（ ``new-teamchannel`` 、）的 cmdlet ``remove-teamchannel`` 之间进行操作。 所有这些 cmdlet 都可以作为最终用户运行，但它们仅适用于您拥有或属于其成员的团队。 如果你是全局管理员或团队服务管理员，你将能够针对组织中的所有团队执行操作。

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Microsoft 团队 PowerShell 模块 cmdlet 中使用的**GroupId**与 Exchange PowerShell 模块中返回的**Identity**属性相同 ``Get-UnifiedGroup`` 。

## <a name="manage-policies-via-powershell"></a>通过 PowerShell 管理策略

> [!NOTE]
> - Skype for Business Online 连接器将合并到团队 PowerShell 中。 它目前在公共预览版中可用。 在此期间，适用于团队的 Skype for Business Online cmdlet 将在团队 PowerShell 模块中本身提供。 安装步骤可在[安装团队 PowerShell](teams-powershell-install.md)文章中使用。
>
> - 一旦连接到 Skype for Business Online，cmdlet 将在你的 PowerShell 会话中可用。 有关详细信息，请参阅[管理 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

在[Skype For business cmdlet 模块](https://www.microsoft.com/download/details.aspx?id=39366)中查找用于管理策略的 cmdlet。

策略是一组可对单个用户进行精确应用的设置。 每个策略类型都有自己的一组用于创建、查看、删除和更新策略的 cmdlet，然后将这些策略分配给用户。 常规结构是：

- **GET**命令（例如 ``Get-CsTeamsMeetingPolicy`` ）：返回可供您在组织中分配的策略文档，包括 Microsoft 为您创建的策略以及您创建的自定义策略。
   - 若要仅查找您在组织中创建的自定义策略，请使用 ``-Filter "tag:*"`` 。

- **新**命令（例如 ``New-CsTeamsMeetingPolicy`` ）：为您的组织创建用于分配给组织中的用户的新策略。 并非所有策略都支持创建自定义策略。 通常，这是为了确保您在组织中使用的策略具有受支持的设置组合。

- **SET**命令（例如 ``Set-CsTeamsMeetingPolicy`` ）：在给定策略上设置特定值。 某些策略没有可用的 SET 命令，或者它们包含无法在策略中自定义的参数。 PowerShell 说明告诉你无法自定义哪些参数。 
   - 若要编辑默认情况下将分配给您的组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **删除**命令（例如 ``Remove-CsTeamsMeetingPolicy`` ）：删除在你的租户中创建的自定义策略。 如果您删除的自定义策略已分配给您的组织中的至少一个用户，该用户将回退到全局策略。
   - 你无法真正删除组织中的全局策略，但是如果你想要将组织中的全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- "**授予**" 命令（例如 ``Grant-CsTeamsMeetingPolicy`` ）：为特定用户分配策略。
   - 若要删除自定义策略分配并使用户回退到组织中的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 并非所有策略都允许创建自定义策略，某些策略具有你无法自定义的设置（因此你可以查看设置，但不能在和期间设置自定义值 ``set-`` ``new-`` ）。 每个 cmdlet 的文档都将调用用户是否可以使用参数。

常用参数：

- **标识**：对于 ``Get-`` 、 ``Set-`` 、 ``New-`` 和， ``Remove-`` **identity**参数将始终引用特定策略实例。 对于 ``Grant`` ， **Identity**参数引用要对其应用策略的特定用户对象。

## <a name="manage-configurations-via-powershell"></a>通过 PowerShell 管理配置

在[Skype For business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中查找用于管理配置的 cmdlet。

配置是在服务中维护的不能在用户级别指定的设置的存储桶。 设置始终在整个组织中应用。 您的全局配置是您的组织中唯一有效的配置。 每种配置类型均带有两个主要 cmdlet：

- ``Get-Cs<ConfigurationName>``（例如 ``Get-CsTeamsClientConfiguration`` ）：

- SET 命令（例如 ``Set-CsTeamsClientConfiguration`` ）：在该类型的配置中设置属性。 指定要修改的参数。
   > 你可以通过以下两种方式之一引用你正在修改的配置：通过指定**全局标识**或通过运行进行修改 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以执行哪些操作？

已阅读[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)，了解可以运行每个 PowerShell cmdlet 的管理员角色。

## <a name="related-topics"></a>相关主题

[安装团队 PowerShell](teams-powershell-install.md)

[团队 PowerShell 发行说明](teams-powershell-release-notes.md)

[团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Teams 管理员角色管理 Teams](using-admin-roles.md)