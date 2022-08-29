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
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396523"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 Microsoft Teams PowerShell 管理 Teams

本文介绍如何使用 Microsoft Teams PowerShell 管理 Teams 和Skype for Business。

将此指南与 [Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)和[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)结合使用。

若要在 Teams 管理中心管理 Teams，请参阅[使用 Azure Cloud Shell管理 Teams](#manage-teams-with-azure-cloud-shell)。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 创建和管理团队

用于创建和管理团队的 cmdlet 位于 [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。

Teams 由Office 365组提供支持，因此在创建团队时，将创建一个组。  (、) 、 ``set-team`` ``get-team``管理团队用户 (``new-team``、) ``remove-teamuser`` ``add-teamuser``以及用于管理团队 (、) 频道的 cmdlet，提供了一组 cmdlet，用于管理团队 (``new-teamchannel``的 ``remove-teamchannel`` 频道。 所有这些 cmdlet 都可以作为最终用户运行，但仅适用于你拥有或所属的团队。 如果你是全局管理员或 Teams 管理员，你将能够对组织中的所有团队采取行动。

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> Microsoft Teams PowerShell 模块 cmdlet 中使用的 **GroupId** 与 Exchange PowerShell 模块中返回的 ``Get-UnifiedGroup`` **Identity** 属性相同。

## <a name="manage-teams-with-azure-cloud-shell"></a>使用 Azure Cloud Shell管理 Teams

Cloud Shell是一个交互式、经过身份验证且可访问浏览器的 shell，可用于管理资源。 有关Cloud Shell的详细信息，请参阅 [Azure Cloud Shell](/azure/cloud-shell/overview)。

若要访问 Azure Cloud Shell并使用 PowerShell 管理 Teams，请登录 Teams 管理中心。

1. 选择右上角的Cloud Shell图标。

    ![带有Cloud Shell图标的 Teams 管理中心标头的屏幕截图。](media/cloud-shell-icon-select.png)

1. 出现提示时，选择 **PowerShell**。

    ![Azure Cloud Shell提示的屏幕截图。](media/cloud-shell.png)

1. 运行以下命令以启动 Teams PowerShell 会话：

    ```powershell
    Connect-MicrosoftTeams
    ```

完成这些步骤后，即可运行 Teams PowerShell 命令。

> [!IMPORTANT]
> 如果要使用 Cs* cmdlet，首先需要使用 ``Connect-MicrosoftTeams -UseDeviceAuthentication`` 该命令连接到 Teams。

## <a name="manage-policies-via-powershell"></a>通过 PowerShell 管理策略

> [!NOTE]
> - Skype for Business联机连接器正在合并到 Teams PowerShell 中。 它目前以公共预览版提供。 随着时间的推移，适用于 Teams 的 Skype for Business Online cmdlet 将在 Teams PowerShell 模块中以本机方式提供。 安装步骤在 [安装 Teams PowerShell](teams-powershell-install.md) 一文中提供。
> - 连接到 Skype for Business Online 后，该 cmdlet 将在 PowerShell 会话中提供。 有关详细信息，请参阅[使用 Office 365 PowerShell 管理联机Skype for Business](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

在[Skype for Business cmdlet 模块](/powershell/module/teams)中查找用于管理策略的 cmdlet。

策略是一组可细粒度应用于单个用户的设置。 每个策略类型都有自己的 cmdlet 集，用于创建、查看、删除和更新策略本身，然后将这些策略分配给用户。 一般结构为：

- GET **命令 (** 例如， ``Get-CsTeamsMeetingPolicy``) ：返回可用于在组织中分配的策略文档，包括 Microsoft 为你创建的要使用的策略以及已创建的自定义策略。
  - 若要仅查找在组织中创建的自定义策略，请使用 ``-Filter "tag:*"``。

- **例如** ``New-CsTeamsMeetingPolicy`` ，新命令 () ：为组织创建新策略以分配给组织中的用户。 并非所有策略都支持创建自定义策略。 通常，这是为了确保组织中使用的策略具有支持的设置组合。

- **例如，SET** 命令 () ``Set-CsTeamsMeetingPolicy`` ：设置给定策略上的特定值。 某些策略没有可用的 SET 命令，或者它们包含无法在策略中自定义的参数。 PowerShell 说明告诉你哪些参数无法自定义。
  - 若要编辑默认分配给组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global``。

- **例如** ``Remove-CsTeamsMeetingPolicy`` ，REMOVE 命令 () ：删除已在租户中创建的自定义策略。 如果删除已分配给组织中至少一个用户的自定义策略，则该用户将回退到全局策略。
  - 实际上无法删除组织中的全局策略，但如果要将组织中的全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global``。

- 例如 ``Grant-CsTeamsMeetingPolicy`` ，**GRANT** 命令 () ：将策略分配给特定用户。
  - 若要删除自定义策略分配并使用户回退到组织中的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。

> [!TIP]
> 并非所有策略都允许创建自定义策略，并且某些策略具有无法自定义 (的设置，因此可以在和) 期间 ``set-`` ``new-`` 查看设置但不能设置自定义值。 每个 cmdlet 的文档会指出参数是否可供客户使用。

常见参数：

- **标识**：对于``Get-``、``New-````Set-``和``Remove-``，**Identity** 参数将始终引用特定的策略实例。 对于 ``Grant``， **Identity** 参数是指要向其应用策略的特定用户对象。

## <a name="manage-configurations-via-powershell"></a>通过 PowerShell 管理配置

在 [Skype for Business cmdlet 模块](/powershell/module/skype)中查找用于管理配置的 cmdlet。

配置是在服务中维护的无法在用户级别指定的设置存储桶。 设置始终适用于整个组织。 全局配置是组织中唯一有效的配置。 每个配置类型都附带两个主要 cmdlet：

- ``Get-Cs<ConfigurationName>`` 例如， () ``Get-CsTeamsClientConfiguration`` ：

- 例如，SET 命令 () ``Set-CsTeamsClientConfiguration`` ：在该类型的配置中设置属性。 指定要修改的参数。
    > [!NOTE]
    > 可以通过以下两种方式之一引用要修改的配置：指定 -**Identity Global** 或运行 ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``。

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以做什么？

读 [取使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md) ，以了解哪些管理员角色可以运行每个 PowerShell cmdlet。

## <a name="related-topics"></a>相关主题

[安装 Teams PowerShell](teams-powershell-install.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)

[使用 Teams 管理员角色管理 Teams](using-admin-roles.md)
