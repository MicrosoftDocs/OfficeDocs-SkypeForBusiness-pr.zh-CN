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
description: 了解用于管理Microsoft Teams的 Teams PowerShell 模块支持的版本。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712956"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模块 - 支持的版本

Microsoft Teams PowerShell 模块 (4.x.x 系列或更高版本中的 TPM) 版本将是未来唯一支持的版本。 所有早期版本都在停用路径上。 建议将 Teams PowerShell 模块更新到最新版本。



## <a name="new-organizations"></a>新组织

从 2022 年 4 月 1 日起，新加入Teams的组织只能在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。



## <a name="current-organizations-non-tpm-active"></a>当前组织 (非 TPM 活动) 

自 2022 年 4 月 1 日起，在过去三个月中未使用过 Teams PowerShell 模块的组织 (1 月 22 日 - 3 月 22 日) ，只能在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。



## <a name="current-organizations-tpm-active"></a>当前组织 (TPM 活动) 

自 2022 年 6 月 15 日起，在过去三个月中使用 Teams PowerShell 模块的组织 (1 月 22 日 - 3 月 22 日) ，只能在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。 消息中心帖子供参考 - MC350371。 



## <a name="important-notes"></a>重要说明

- 有关所有 Teams PowerShell 模块版本的发行说明，请参[阅 Teams PowerShell 发行说明](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模块，应使用用于安装模块的相同方法。 例如，如果最初使用 Install-Module，则应使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果从 Teams PowerShell 模块版本 1.1.6 更新，请更新要使用的`Connect-MicrosoftTeams`脚本，而不是`New-CsOnlineSession`更新脚本。

-   在更新期间，建议不要将 TPM 4.x.x/3.x.x 与低于 3.0.0 的版本一起使用。 例如，不建议将版本 4.x.x & 2.6.0 一起用于同一组织中的不同管理员操作。 

- 相关更改
  * TPM 3.x.x 及更高版本中Get-CsOnlineUser & Get-CsOnlineVoiceUser的更新 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (消息中心帖子[中的](/powershell/module/skype/get-csonlinevoiceuser)更多详细信息 – MC340774) 。

  * 电话号码分配的更改 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (消息中心帖子中的更多详细信息 - MC316139) [](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>已弃用的 cmdlet

下面列出了最近弃用或不支持Microsoft Teams方案的一些 cmdlet。 有关相同内容的详细信息，请参阅相应的公共文档。 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings)、 [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)、 [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)、 [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)、 [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom)、 [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom)、 [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom)、 [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities)、 [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas)、 [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)、 [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)、 [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)、 [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)、 [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)、 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)、 [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation)、 [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation)、 [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>相关主题

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[安装Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/module/teams) 

[Skype for Business cmdlet 参考](/powershell/module/skype) 
