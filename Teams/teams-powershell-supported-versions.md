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
ms.openlocfilehash: 9254afde824f072f6015531b90f4cacfb38acafe
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63689059"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模块 - 支持的版本

Microsoft Teams 4.x.x (系列中的) TPM 模块模块是以后唯一支持的版本。 所有早期版本都位于停用路径上。



## <a name="new-organizations"></a>新组织

从 2022 年 4 月 1 Teams起，新加入 Teams 的组织只能使用 Teams PowerShell 模块 4.0.0 或以上。



## <a name="current-organizations-non-tpm-active"></a>当前组织 (TPM 活动) 

自 2022 年 1 月 1 日起，过去 3 个月（ (年 1 月 22 日至) 日）未使用 TPM 的组织只能使用 TPM 4.0.0 或以上。



## <a name="current-organizations-tpm-active"></a>当前组织 (TPM 活动) 

过去三个月内使用 TPM 的组织 (1 月 22 日至 3 月 22 日) 将有更多的时间来更新到 TPM 4.x.x。 即将推出更多详细信息。



## <a name="important-notes"></a>重要说明

- 有关 PowerShell 模块Teams发行说明，可Teams [PowerShell 发行说明](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模块，应使用相同的方法来安装该模块。 例如，如果最初使用 Install-Module，则应该使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果从 powerShell Teams 1.1.6 版本进行更新，请更新脚本以使用 `Connect-MicrosoftTeams` 而不是 `New-CsOnlineSession`。

-   在更新期间，建议不要将 TPM 4.x.x/3.x.x 与低于 3.0.0 的版本一起使用。 例如，不建议将版本 4.0.0 & 2.6.0 用于同一组织中不同的管理员操作。 

- 相关更改
  * TPM 3.0.0 及Get-CsOnlineUser & Get-CsOnlineVoiceUser更新 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) [](/powershell/module/skype/get-csonlineuser) &  (消息中心帖子 - MC340774) 。

  * 电话 数字分配的更改 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (消息中心帖子 - MC316139) [](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>相关主题

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[安装 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/module/teams) 

[Skype for Business cmdlet 参考](/powershell/module/skype) 
