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
ms.openlocfilehash: ac948022050babeff0c5ea3c0dbde853e0fabc54
ms.sourcegitcommit: 8cda22925ccddb612f91351a7593b521eee10f0e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2022
ms.locfileid: "65019324"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模块 - 支持的版本

Microsoft Teams PowerShell 模块 (4.x.x 系列或更高版本中的 TPM) 版本将是未来唯一支持的版本。 所有早期版本都在停用路径上。 建议将 Teams PowerShell 模块更新到最新版本。



## <a name="new-organizations"></a>新组织

从 2022 年 4 月 1 日起，新加入Teams的组织只能在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。



## <a name="current-organizations-non-tpm-active"></a>当前组织 (非 TPM 活动) 

 (1 月 22 日 – 3 月 22 日) ，在过去三个月中未使用过 Teams PowerShell 模块的组织只能从 2022 年 4 月 1 日起在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。



## <a name="current-organizations-tpm-active"></a>当前组织 (TPM 活动) 

在过去三个月中使用 Teams PowerShell 模块的组织 (1 月 22 日 – 3 月 22 日) ，从 2022 年 6 月 15 日开始，只能在 4.x.x 系列或更高版本中使用 Teams PowerShell 模块。 消息中心帖子供参考 - MC350371。 



## <a name="important-notes"></a>重要说明

- 有关所有 Teams PowerShell 模块版本的发行说明，请参[阅 Teams PowerShell 发行说明](teams-powershell-release-notes.md)。

- 若要更新任何 PowerShell 模块，应使用用于安装模块的相同方法。 例如，如果最初使用 Install-Module，则应使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果从 Teams PowerShell 模块版本 1.1.6 更新，请更新要使用的`Connect-MicrosoftTeams`脚本，而不是`New-CsOnlineSession`更新脚本。

-   在更新期间，建议不要将 TPM 4.x.x/3.x.x 与低于 3.0.0 的版本一起使用。 例如，不建议将版本 4.x.x & 2.6.0 一起用于同一组织中的不同管理员操作。 

- 相关更改
  * 在 TPM 3.x.x 及更高版本中更新Get-CsOnlineUser & Get-CsOnlineVoiceUser - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (消息中心帖子[中的](/powershell/module/skype/get-csonlinevoiceuser)更多详细信息 – MC340774) 。

  * 电话号码分配的更改 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (消息中心帖子中的更多详细信息 - MC316139) [](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

-   在使用 TPM 4.x.x 或更高版本时，建议不要使用 [下面](#deprecated-cmdlets)提到的任何已弃用或不受支持的 cmdlet。 



## <a name="deprecated-cmdlets"></a>已弃用的 cmdlet

- 下面列出了最近弃用的一些 cmdlet。 有关相同内容的详细信息，请参阅相应的公共文档。 
  * [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo)、 [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate)、 [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser)、 [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint)、 [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint)、 [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint)、 [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities)、 [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas)、 [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries)、 [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions)、 [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes)、 [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory)、 [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory)、 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount)、 [Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation)、 [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation)、 [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)、 [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy)、 [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy)、 [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- 下面列出了不支持/不适用于Microsoft Teams方案的 cmdlet。 
  * [Get|Set]-CsUserPstnSettings
  * [Get|设置|启用|Disable]-CsMeetingRoom
  * [Grant|Get|设置|新增功能|Remove]-CsConferencingPolicy
  * [Grant|Get|设置|新增功能|Remove]-CsClientPolicy
  * [Grant|Get]-CsHostedVoicemailPolicy
  * [Grant|Get|设置|新增功能|Remove]-CsMobilityPolicy
  * [Grant|Get] CsVoiceRoutingPolicy
  * [Grant|Get]-CsBroadcastMeetingPolicy
  * [Grant|Get]-CsCloudMeetingPolicy
  * [Grant|Get]-CsGraphPolicy
  * [Grant|Get|设置|新增功能|Remove]-CsExternalUserCommunicationPolicy
  * [Grant|Get|Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Get|Set]-CsBroadcastMeetingConfiguration
  * [Get|Set]-CsOAuthConfiguration
  * [Get|Set]-CsMeetingConfiguration
  * [Get|Set]-CsTenantHybridConfiguration
  * [Get|Set]-CsPushNotificationConfiguration
  * [Get|Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Get|Set]-CsTenantPublicProvider
  * Get-CsHostingProvider
  * [Get|设置|注册|Unregister]-CsHybridPSTNAppliance
  * [Get|设置|新增功能|Remove]-CsHybridPSTNSite
  * [Get|Set]- CsHybridMediationServer
  * [Get|设置|新增功能|Remove]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Get|设置|新增功能|Remove]-CsTeamsPinnedApp
  * [Get|设置|新增功能|Remove]-CsTenantCatalogApp
  * [Get|设置|新增功能|Remove]-CsGlobalCatalogApp
  * [Get|设置|新增功能|Remove]-CsDefaultCatalogApp
  * [Get|设置|新增功能|Remove]-CsTeamsAppPreset



## <a name="related-topics"></a>相关主题

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[安装Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 参考](/powershell/module/teams) 

[Skype for Business cmdlet 参考](/powershell/module/skype) 
