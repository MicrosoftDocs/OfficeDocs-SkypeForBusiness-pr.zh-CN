---
title: 使用 Teams PowerShell Microsoft Teams管理资源
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
description: 了解如何使用 Microsoft Teams PowerShell Teams管理应用程序。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86d5069794d160d4c4241a67f0c8d45fc9cac708
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046018"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 Teams PowerShell Microsoft Teams管理资源

本文演示如何使用 PowerShell Microsoft Teams管理Teams Skype for Business。

将本指南与 Microsoft Teams [cmdlet 参考](/powershell/teams/?view=teams-ps)和 Skype for Business [cmdlet 参考结合使用](/powershell/skype/intro?view=skype-ps)。

若要在 Teams 管理Teams管理中心，请参阅使用 Azure Cloud Shell Teams[管理应用程序](#manage-teams-with-azure-cloud-shell)。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 创建和管理团队

用于创建和管理团队的 cmdlet Microsoft Teams [PowerShell 模块 中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。

Teams组Office 365，因此创建团队时，会创建一个组。 提供一组 cmdlet 用于核心团队及其设置（ (、、) 、管理团队用户 (、) ）以及用于管理团队 (、) 频道的 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` cmdlet。 所有这些 cmdlet 都可以作为最终用户运行，但它们只能在你拥有或成员的团队中运行。 如果你是全局管理员或Teams管理员，你将能够对组织的所有团队采取行动。

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> PowerShell 模块 cmdlet Microsoft Teams中使用的 **GroupId** 与 PowerShell 模块中返回的 **标识** Exchange ``Get-UnifiedGroup`` 相同。

## <a name="manage-teams-with-azure-cloud-shell"></a>使用 Azure Cloud Shell Teams管理应用程序

Cloud Shell 是一种交互式的、经过身份验证且可通过浏览器访问的 shell，可用于管理资源。 有关 Cloud Shell 详细信息，请参阅[Azure Cloud Shell。](/azure/cloud-shell/overview)

若要访问 Azure Cloud Shell 并使用 PowerShell Teams，请登录到 Teams 管理中心。

1. 选择右上角的 Cloud Shell 图标。

    ![Cloud Shell Teams管理中心标头的屏幕截图。](media/cloud-shell-icon-select.png)

1. 系统提示时，选择 **"PowerShell"。**

    ![Azure Cloud Shell 提示符的屏幕截图。](media/cloud-shell.png)

1. 运行以下命令以启动 Teams PowerShell 会话：

    ```powershell
    Connect-MicrosoftTeams
    ```

完成这些步骤后，即可使用 PowerShell Teams运行。

> [!IMPORTANT]
> 如果要使用 Cs* cmdlet，首先需要使用 命令Teams连接到 ``Connect-MicrosoftTeams -UseDeviceAuthentication`` 该 cmdlet。

## <a name="manage-policies-via-powershell"></a>通过 PowerShell 管理策略

> [!NOTE]
> - Skype for Business联机连接器正在整合到 PowerShell Teams中。 它目前以公共预览版提供。 随着时间的推移，Skype for Business PowerShell 模块中Teams本地可用的 Teams Online cmdlet。 安装步骤可在[PowerShell](teams-powershell-install.md) Teams安装。
> - 连接到 Skype for Business Online 后，可在 PowerShell 会话中Skype for Business cmdlet。 有关详细信息，请参阅使用 Skype for Business [PowerShell Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

在 Skype for Business [cmdlet 模块 中查找用于管理策略的 cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

策略是一组设置，可以精细地应用于单个用户。 每个策略类型都有其自己的一组 cmdlet，用于创建、查看、删除和更新策略本身，然后将这些策略分配给用户。 一般结构为：

- **GET** (例如，) ：返回可供你在组织中分配的策略文档，包括 Microsoft 创建供你使用的策略以及你创建的自定义策略。 ``Get-CsTeamsMeetingPolicy``
  - 若要仅查找在组织中创建的自定义策略，请使用 ``-Filter "tag:*"`` 。

- **新** (例如，) ：为组织创建新策略 ``New-CsTeamsMeetingPolicy`` 以分配给组织的用户。 并非所有策略都支持创建自定义策略。 通常，这是为了确保在组织中使用的策略具有受支持的设置组合。

- **SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy`` ，) ：在给定策略上设置特定值。 某些策略没有可用的 SET 命令，或者它们包含的参数无法自定义在策略中。 PowerShell 说明告知无法自定义哪些参数。
  - 若要编辑默认情况下将分配给组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **删除** (，例如) ：删除已在租户 ``Remove-CsTeamsMeetingPolicy`` 中创建的自定义策略。 如果删除已分配给组织中至少一个用户的自定义策略，该用户将回退到全局策略。
  - 实际上无法删除组织的全局策略，但如果要将组织中全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT** (例如 ``Grant-CsTeamsMeetingPolicy`` ，) ：向特定用户分配策略。
  - 若要删除自定义策略分配，并让用户回退到组织的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 并非所有策略都允许创建自定义策略，并且某些策略具有无法自定义 (因此可以查看设置，但无法设置自定义值期间和 ``set-`` ``new-``) 。 每个 cmdlet 的文档会指出参数是否可供客户使用。

常见参数：

- **标识**： ``Get-`` 对于 ``Set-`` 、、 ``New-`` 和 ``Remove-`` **，Identity** 参数将始终引用特定的策略实例。 对于 ``Grant`` **，Identity** 参数是指要应用策略的特定用户对象。

## <a name="manage-configurations-via-powershell"></a>通过 PowerShell 管理配置

在 Skype for Business [cmdlet 模块 中查找用于管理配置的 cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

配置是服务中维护的设置存储桶，无法以用户级别指定。 设置始终应用于整个组织。 全局配置是组织中唯一有效的配置。 每个配置类型附带两个主要 cmdlet：

- ``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：

- SET (例如 ``Set-CsTeamsClientConfiguration`` ，) ：设置该类型的配置中的属性。 指定要修改的参数。
    > [!NOTE]
    > 可以通过以下两种方式之一引用要修改的配置：通过指定 -**Identity Global** 或运行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="what-can-each-admin-role-do"></a>每个管理员角色可以执行哪些功能？

请参阅[使用Microsoft Teams角色来管理Teams，](using-admin-roles.md)了解哪些管理员角色可以运行每个 PowerShell cmdlet。

## <a name="related-topics"></a>相关主题

[安装 Teams PowerShell](teams-powershell-install.md)

[TeamsPowerShell 发行说明](teams-powershell-release-notes.md)

[Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)

[使用 Teams 管理员角色管理 Teams](using-admin-roles.md)
