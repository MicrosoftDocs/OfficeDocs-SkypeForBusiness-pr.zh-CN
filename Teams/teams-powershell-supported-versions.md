---
title: Teams PowerShell 模块 - 支持的版本
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解 PowerShell 模块Teams版本，用于管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e292e3ea5659920bca6fe6f663afc53164da5b49
ms.sourcegitcommit: e3a4df81721abe83886714a7c3c798e4c0888c35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2022
ms.locfileid: "64617703"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模块 - 支持的版本

Microsoft Teams 4.x.x (或) 版本的 TPM 模块是以后唯一支持的版本。 所有早期版本都位于停用路径上。 建议将 PowerShell Teams更新到最新版本。



## <a name="new-organizations"></a>新组织

从 2022 年 4 月 1 Teams起，新加入 Teams 的组织只能使用 4.x.x 系列或 Teams 系列中的 Teams PowerShell 模块。



## <a name="current-organizations-non-tpm-active"></a>当前组织 (TPM 活动) 

自 2022 年 4 月 1 日起，过去三个月（ (年 1 月 22 日至) 3 月 22 日）未使用 Teams PowerShell 模块的组织只能使用 4.x.x 或以上系列中的 Teams PowerShell 模块。



## <a name="current-organizations-tpm-active"></a>当前组织 (TPM 活动) 

过去三个月（ (年 1 月 22 日至) 3 月 22 日）使用 Teams PowerShell 模块的组织只能从 2022 年 6 月 15 日开始在 4.x.x 系列或以上系列使用 Teams PowerShell 模块。 消息中心帖子供参考 - MC350371。 



## <a name="important-notes"></a>重要说明

- 有关 PowerShell 模块Teams发行说明，可Teams [PowerShell 发行说明](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模块，应使用相同的方法来安装该模块。 例如，如果最初使用 Install-Module，则应该使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果从 powerShell Teams 1.1.6 版本进行更新，请更新脚本以使用 `Connect-MicrosoftTeams` 而不是 `New-CsOnlineSession`。

-   在更新期间，建议不要将 TPM 4.x.x/3.x.x 与低于 3.0.0 的版本一起使用。 例如，不建议将版本 4.x.x & 2.6.0 用于同一组织中不同的管理员操作。 

- 相关更改
  * 更新Get-CsOnlineUser & Get-CsOnlineVoiceUser TPM 3.x.x 及以上版本 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) [](/powershell/module/skype/get-csonlineuser) &  (消息中心帖子 - MC340774) 。

  * 电话 数字分配的更改 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (消息中心帖子 - MC316139) [](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

  * 弃用 Get-CsOnlineDirectoryTenant - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant) (消息中心帖子 - MC346902) 。



## <a name="related-topics"></a>相关主题

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[安装 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/module/teams) 

[Skype for Business cmdlet 参考](/powershell/module/skype) 
