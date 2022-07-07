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
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647820"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接

## <a name="overview"></a>概述

使用[适用于 Blue Yonder 的 Microsoft Teams Shifts 连接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)，可将 Microsoft Teams 中的 Shifts 应用与 Blue Yonder Workforce Management (Blue Yonder WFM) 集成。 建立连接后，一线工作人员可以无缝查看和管理他们的日程安排，在 Blue Yonder WFM从班次内部。

可以使用 Microsoft 365 管理中心 或 [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) 中的 [Shifts 连接器向导](shifts-connector-wizard.md)来设置连接。 设置连接后，可使用 [Shifts 连接器 PowerShell cmdlet](#shifts-connector-cmdlets) 对其进行管理。

本文介绍如何使用 PowerShell 执行以下操作：

- [检查连接设置状态](#check-connection-setup-status)
- [查看连接的错误报告](#view-an-error-report-for-a-connection)
- [解决连接错误](#resolve-connection-errors)
- [更改连接设置](#change-connection-settings)
- [从一个连接中取消映射团队并将其映射到另一个连接](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [禁用连接同步](#disable-sync-for-a-connection)

> [!NOTE]
> 本文假定已使用向导或 PowerShell 设置与 Blue Yonder WFM 的连接。

## <a name="before-you-begin"></a>开始之前

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>设置环境

> [!NOTE]
> 在运行本文中的任何命令或脚本之前，请确保按照以下步骤设置环境。

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. 连接到 Teams。

    ```powershell
    Connect-MicrosoftTeams
    ```

    出现提示时，请使用管理员凭据登录。 现在，你已设置为运行本文和 Shifts 连接器 cmdlet 中的脚本。

## <a name="check-connection-setup-status"></a>检查连接设置状态

<a name="setup_status"> </a>

若要使用电子邮件中收到的操作 ID 检查设置的连接的状态：

1. 如果尚未) ，请设置[环境](#set-up-your-environment) (。
1. 运行以下命令。 此命令提供连接的团队映射的总体状态。

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

若要了解详细信息，请参阅 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)。

## <a name="view-an-error-report-for-a-connection"></a>查看连接的错误报告

<a name="error_report"> </a>

可以运行显示连接错误详细信息的报表。 报表列出了成功和失败的团队和用户映射。 它还提供与连接关联的帐户相关的任何问题的信息。

1. 如果尚未) ，请设置[环境](#set-up-your-environment) (。
1. 获取连接的错误报告列表。

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 若要查看特定的错误报告，请运行以下命令：

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

若要了解详细信息，请参阅 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)。

## <a name="resolve-connection-errors"></a>解决连接错误

### <a name="user-mapping-errors"></a>用户映射错误

如果 Blue Yonder WFM实例中的一个或多个用户不是 Teams 中映射团队的成员，则可能会发生用户映射错误。 若要解决此问题，请确保映射团队中的用户与 Blue Yonder WFM 实例中的用户匹配。

若要查看未映射用户的详细信息，请在尚未) [的情况下设置环境](#set-up-your-environment) (，然后运行以下脚本。

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

如果 Blue Yonder WFM服务帐户或 Microsoft 365 系统帐户凭据不正确或没有所需的权限，则可能会发生帐户授权错误。

若要更改 Blue Yonder WFM服务帐户或 Microsoft 365 系统帐户的连接凭据，可以运行 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet 或在本文的[“更改连接设置”](#change-connection-settings)部分中使用 PowerShell 脚本。

## <a name="change-connection-settings"></a>更改连接设置
<a name="change_settings"> </a>

使用此脚本更改连接设置。 可以更改的设置包括 Blue Yonder WFM服务帐户和密码、Microsoft 365 系统帐户、团队映射和同步设置。

同步设置包括同步频率 (分钟) 以及在 Blue Yonder WFM 和 Shifts 之间同步的计划数据。 计划数据在以下参数中定义，可以通过运行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector) 来查看这些参数。

- **enabledConnectorScenarios** 参数定义从 Blue Yonder WFM同步到 Shifts 的数据。 选项包括`Shift`： ， `UserShiftPreferences``SwapRequest`， ， `OpenShift`， `TimeOff``OpenShiftRequest``TimeOffRequest`
- **enabledWfiScenarios** 参数定义从 Shifts 同步到 Blue Yonder WFM 的数据。 选项包括`SwapRequest`： `OpenShiftRequest``TimeOffRequest``UserShiftPreferences`

    > [!NOTE]
    > 如果选择在 Shifts 和 Blue Yonder WFM之间不同步打开的班次、打开的班次请求、交换请求或休假请求，则需要执行另一个步骤来隐藏 Shifts 中的功能。 运行此脚本后，请确保按照本文后面的 [“禁用打开的班次”、“打开班次请求”、“交换请求”和“休假请求](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) ”部分中的步骤操作。

> [!IMPORTANT]
> 对于不想更改的设置，需要在脚本提示时重新输入原始设置。

如果尚未) ，请设置[环境](#set-up-your-environment) (，然后运行以下脚本。

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>禁用打开的班次、打开的班次请求、交换请求和休假请求

> [!IMPORTANT]
> 仅当您选择使用本文前面的“ [更改连接设置”](#change-connection-settings) 部分中的脚本或使用 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet 禁用打开的班次、打开班次请求、交换请求或超时请求时，才执行以下步骤。 完成此步骤会隐藏 Shifts 中的功能。 如果没有第二步，用户仍会在 Shifts 中看到该功能，如果尝试使用该功能，则会收到“不受支持的操作”错误消息。

若要隐藏 Shifts 中的打开班次、交换请求和休假请求，请使用图形 API[计划资源类型](/graph/api/resources/schedule)为映射到 ```false``` Blue Yonder WFM 实例的每个团队设置以下参数：

- 打开班次： ```openShiftsEnabled```
- 交换请求：  ```swapShiftsRequestsEnabled```
- 休假请求： ```timeOffRequestsEnabled```

若要在 Shifts 中隐藏打开的班次请求，请转到 **Shifts 中的“设置”** ，然后关闭 **“打开班次** ”设置。

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>从一个连接中取消映射团队并将其映射到另一个连接

> [!NOTE]
> 对于这两个连接，Microsoft 365 系统帐户必须相同。 否则，会收到“此指定的执行组件配置文件没有团队所有权权限”错误消息。

如果要从一个连接中取消映射团队并将其映射到另一个连接：

1. 如果尚未) ，请设置[环境](#set-up-your-environment) (。
1. 查看连接的所有团队映射的列表。

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

若要了解详细信息，请参阅 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)、 [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) 和 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)。

## <a name="disable-sync-for-a-connection"></a>禁用连接同步

使用此脚本禁用连接的同步。 请记住，此脚本不会删除或删除连接。 它将关闭同步，以便在 Shifts 和 Blue Yonder WFM之间不同步指定的连接。

如果尚未) ，请设置[环境](#set-up-your-environment) (，然后运行以下脚本。

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

有关 Shifts 连接器 cmdlet 的帮助，请在 [Teams PowerShell cmdlet 参考](/powershell/teams/intro)中搜索 **CsTeamsShiftsConnection**。 下面是一些常用 cmdlet 的链接。

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>相关文章

- [Shifts 连接器](shifts-connectors.md)
- [使用 Shifts 连接器向导将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)
