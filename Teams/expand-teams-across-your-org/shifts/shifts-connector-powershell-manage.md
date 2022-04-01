---
title: 使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593633"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接

## <a name="overview"></a>概述

使用 [Blue Yonder 的 Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) 连接器，可以将 Microsoft Teams 中的 Shifts 应用与 Blue Yonder Workforce Management (Blue Yonder WFM) 。 设置连接后，一线员工可以从 Shifts 中无缝查看和管理 Blue Yonder WFM 中的计划。

可以使用 [PowerShell 或 Microsoft 365 管理中心中的 Shifts](shifts-connector-blue-yonder-powershell-setup.md) 连接器向导设置连接。[](shifts-connector-wizard.md) 设置连接后，可以使用 [Shifts 连接器 PowerShell cmdlet 进行管理](#shifts-connector-cmdlets)。

本文介绍如何使用 PowerShell 执行以下操作：

- [检查连接设置状态](#check-connection-setup-status)
- [查看连接的错误报告](#view-an-error-report-for-a-connection)
- [解决连接错误](#resolve-connection-errors)
- [更改连接设置](#change-connection-settings)
- [从一个连接取消映射团队，并映射到另一个连接](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [为连接禁用同步](#disable-sync-for-a-connection)

> [!NOTE]
> 本文假设已使用向导或 PowerShell 设置与 Blue Yonder WFM 的连接。

## <a name="before-you-begin"></a>开始之前

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>设置环境

> [!NOTE]
> 在运行本文中的任意命令或脚本之前，请确保按照以下步骤设置环境。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>检查连接设置状态
<a name="setup_status"> </a>

若要使用在电子邮件中收到的操作 ID 检查设置的连接状态，请执行以下操作：

1. [如果尚未 (](#set-up-your-environment) ，请设置环境) 。
1. 运行以下命令。 此命令提供连接的团队映射的总体状态。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

有关详细信息，请参阅 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)。

## <a name="view-an-error-report-for-a-connection"></a>查看连接的错误报告
<a name="error_report"> </a>

可以运行显示连接错误详细信息的报表。 该报告列出成功和失败的团队和用户映射。 它还提供有关与与连接关联的帐户相关的任何问题的信息。

1. [如果尚未 (](#set-up-your-environment) ，请设置环境) 。
1. 获取连接的错误报告列表。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 若要查看特定错误报告，请运行以下命令：

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

有关详细信息，请参阅 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)。

## <a name="resolve-connection-errors"></a>解决连接错误

### <a name="user-mapping-errors"></a>用户映射错误

如果 Blue Yonder WFM 站点中的一个或多个用户不是云中映射团队的成员，则可能会发生用户映射Teams。 若要解决此问题，请确保映射团队中的用户与 Blue Yonder WFM 站点中的用户匹配。

若要查看未映射用户的详细信息，请 (环境 [](#set-up-your-environment) （如果尚未) ，然后运行以下脚本。

```powershell
#View sync errors script 
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x 
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>帐户授权错误

如果 Blue Yonder WFM 服务帐户或 Microsoft 365系统帐户凭据不正确或没有所需权限，则可能会发生帐户授权错误。

若要更改连接的 Blue Yonder WFM 服务帐户或 Microsoft 365 系统帐户凭据，可以运行 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) cmdlet，或使用本文更改连接设置部分中的 PowerShell 脚本。[](#change-connection-settings)

## <a name="change-connection-settings"></a>更改连接设置
<a name="change_settings"> </a>

使用此脚本更改连接设置。 设置包括 Blue Yonder WFM 服务帐户和密码、Microsoft 365帐户、团队映射和同步设置。

同步设置包括同步频率 (分钟) 以及 Blue Yonder WFM 和 Shifts 之间同步的计划数据。 计划数据在下列参数中定义，可以通过运行 [Get-CsTeamsShiftsConnectionConnector 查看这些数据](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。

- **enabledConnectorScenarios** 参数定义从 Blue Yonder WFM 同步到 Shifts 的数据。 选项包括 `Shift`、`SwapRequest`、、`UserShiftPreferences`、`OpenShiftRequest``OpenShift`、`TimeOff`、`TimeOffRequest`、 。
- **enabledWfiScenarios** 参数定义从 Shifts 同步到 Blue Yonder WFM 的数据。 选项包括 `SwapRequest`、 `OpenShiftRequest`、 `TimeOffRequest`、 `UserShiftPreferences`。

    > [!NOTE]
    > 如果选择不在 Shifts 和 Blue Yonder WFM 之间同步未调班、打开班次请求、调班请求或请假请求，则需要执行另一个步骤来隐藏 Shifts 中的功能。 运行此脚本后，请确保按照本文稍后的禁用班次、打开班次请求、调班请求和请假 [请求部分中](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 的步骤操作。

> [!IMPORTANT]
> 对于不希望更改的设置，当脚本提示时，需要重新输入原始设置。

[如果尚未 (](#set-up-your-environment) ，请设置环境) ，然后运行以下脚本。

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping 
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping 
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>禁用开班、打开班次请求、调班请求和请假请求

> [!IMPORTANT]
> 只有在使用本文前面"更改连接设置"部分中的脚本或 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) cmdlet 选择禁用[](#change-connection-settings)开班、打开班次请求、调班请求或请假请求时，才执行以下步骤。 完成此步骤会隐藏 Shifts 中的 功能。 如果不执行第二个步骤，用户仍将看到 Shifts 中的功能，如果用户尝试使用该功能，则收到"不支持的操作"错误消息。

若要在 Shifts 中隐藏未处理班次、调班请求和请假请求，请使用 图形 API [计划](/graph/api/resources/schedule?view=graph-rest-1.0)```false```资源类型，为映射到 Blue Yonder WFM 站点的每个团队设置以下参数：

- 打开班次： ```openShiftsEnabled```
- 交换请求：  ```swapShiftsRequestsEnabled```
- 请假请求： ```timeOffRequestsEnabled```

若要在 Shifts 中隐藏打开的班次请求，请转到设置中的"打开班次"设置，然后关闭"打开班次 **"** 设置。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>从一个连接取消映射团队，并映射到另一个连接

> [!NOTE]
> 两Microsoft 365连接的帐户必须相同。 如果没有，则会显示"此指定的执行组件配置文件没有团队所有权权限"错误消息。

如果要从一个连接取消映射团队，并映射到另一个连接：

1. [如果尚未 (](#set-up-your-environment) ，请设置环境) 。
1. 查看连接的所有团队映射列表。

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 从连接中删除团队映射。

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. 将团队映射到另一个连接。

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

有关详细信息，请参阅 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) 和 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)。

## <a name="disable-sync-for-a-connection"></a>为连接禁用同步

使用此脚本禁用连接的同步。 请记住，此脚本不会删除连接。 它会关闭同步，以便对于指定的连接，不会在 Shifts 和 Blue Yonder WFM 之间同步任何数据。

[如果尚未 (](#set-up-your-environment) ，请设置环境) ，然后运行以下脚本。

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Shifts 连接器 cmdlet

有关 Shifts 连接器 cmdlet 的帮助，请搜索 [PowerShell cmdlet](/powershell/teams/intro?view=teams-ps) Teams **CsTeamsShiftsConnection**。 下面是一些常用 cmdlet 的链接。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>相关文章

- [Shifts 连接线](shifts-connectors.md)
- [使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)