---
title: 使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用 PowerShell 将 Shifts 与 Blue Yonder Workforce Management 集成。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b78f45919649fda29f09ea338a160c2ab376c1a
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593653"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>使用 PowerShell 将 Shifts 连接到 Blue Yonder Workforce Management

## <a name="overview"></a>概述

使用 [Blue Yonder 的 Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) 连接器将 Microsoft Teams 中的 Shifts 应用与 Blue Yonder Workforce Management (Blue Yonder WFM) 。 设置连接后，一线员工可以从 Shifts 中无缝查看和管理 Blue Yonder WFM 中的计划。

本文将演练如何使用 PowerShell 设置和配置连接器，以将 Shifts 与 Blue Yonder WFM 集成。

若要设置连接，请运行 PowerShell 脚本。 该脚本配置连接器、应用同步设置、创建连接，以及将 Blue Yonder WFM 站点映射到团队。 同步设置确定 Shifts 中启用的功能，以及 Blue Yonder WFM 和 Shifts 之间同步的计划信息。 映射定义 Blue Yonder WFM 站点与云中团队Teams。 可以映射到现有团队和新团队。

我们提供了两个脚本。 可以使用任一脚本，具体取决于是映射到现有团队还是创建新团队进行映射。

可以设置多个连接，每个连接具有不同的同步设置。 例如，如果组织有多个具有不同计划要求的位置，请为每个位置创建具有唯一同步设置的连接。 请记住，在任何给定时间，蓝色 Yonder WFM 站点只能映射到一个团队。 如果网站已映射到团队，则不能映射到另一个团队。

使用 Blue Yonder WFM 作为记录系统，一线员工可以在他们的设备上查看和调班、管理其可用性以及请求请假。 一线经理可以继续使用 Blue Yonder WFM 来设置计划。

> [!NOTE]
> 还可使用"[Shifts 连接器"向导Microsoft 365 管理中心](shifts-connector-wizard.md) Shifts 连接到 Blue Yonder WFM。

## <a name="before-you-begin"></a>开始之前

### <a name="prerequisites"></a>先决条件

[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>使用 PowerShell 管理连接器的管理员角色

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>设置环境

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="identify-the-teams-you-want-to-map"></a>确定要映射的团队

> [!NOTE]
> 如果要将 Blue Yonder WFM 站点映射到现有团队，请完成此步骤。 如果要创建要映射到的新团队，可以跳过此步骤。

在Azure 门户，转到"所有组"页，[](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)获取组织中团队的 TeamId 列表。

记下要映射的团队的 TeamId。 该脚本将提示输入此信息。

> [!NOTE]
> 如果一个或多个团队已有计划，脚本会从这些团队中删除计划。 否则，你将看到重复的班次。

## <a name="run-the-script"></a>运行脚本

运行脚本：

- 若要设置连接并创建新团队进行映射，请 [运行此脚本](#set-up-a-connection-and-create-new-teams-to-map)。
- 若要设置连接并映射到现有团队，请 [运行此脚本](#set-up-a-connection-and-map-to-existing-teams)。

该脚本执行以下操作。 系统会提示输入设置和配置详细信息。

1. 使用输入的 Blue Yonder WFM 服务帐户凭据和服务 URL 测试并验证与 Blue Yonder WFM 的连接。
1. 配置 Shifts 连接器。
1. 应用同步设置。 这些设置包括同步频率 (分钟) 以及 Blue Yonder WFM 和 Shifts 之间同步的计划数据。 计划数据在下列参数中定义：

    - **enabledConnectorScenarios** 参数定义从 Blue Yonder WFM 同步到 Shifts 的数据。 选项包括 `Shift`、`SwapRequest`、、`UserShiftPreferences`、`OpenShiftRequest``OpenShift`、`TimeOff`、`TimeOffRequest`、 。
    - **enabledWfiScenarios** 参数定义从 Shifts 同步到 Blue Yonder WFM 的数据。 选项包括 `SwapRequest`、 `OpenShiftRequest`、 `TimeOffRequest`、 `UserShiftPreferences`。

    有关详细信息，请参阅 [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)。 若要查看每个参数支持的同步选项列表，请运行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。

    > [!IMPORTANT]
    > 该脚本为所有这些选项启用同步。 如果要更改同步设置，可以在设置连接后更改同步设置。 有关详细信息，请参阅 [使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)。

1. 创建连接。
1. 地图团队访问 Blue Yonder WFM 网站。 映射基于你输入的 Blue Yonder WFM 站点 ID 和 TeamId 或你创建的新团队，具体取决于运行的脚本。 如果团队已有计划，脚本会删除指定日期和时间范围的计划数据。

屏幕上的"成功"消息表示已成功设置连接。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>如果需要对连接进行更改

若要在设置连接后对连接进行更改，请参阅使用 [PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)。 例如，可以更新同步设置、团队映射和禁用连接的同步。

## <a name="scripts"></a>脚本

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>设置连接并创建新团队进行映射

```powershell
#Map WFM sites to teams script
Write-Host "Map WFM sites to teams"
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
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail $AdminEmailList
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Suceess"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

#The Teams admin was set as an owner directly when creating a new team, removing it from owners
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
Disconnect-MicrosoftTeams
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>设置连接并映射到现有团队

```powershell
#Map WFM sites to existing teams script
Write-Host "Map WFM sites to existing teams"
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
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365 user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency in minutes. Value should be equal to or more than 10."

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail AdminEmailList

$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $$teamsUserId

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the existing team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
Disconnect-MicrosoftTeams
```

## <a name="shifts-connector-cmdlets"></a>Shifts 连接器 cmdlet

有关 Shifts 连接器 cmdlet（包括脚本中使用的 cmdlet）的帮助，请搜索 [Teams PowerShell cmdlet 参考中的](/powershell/teams/intro?view=teams-ps) **CsTeamsShiftsConnection**。 下面是一些常用 cmdlet 的链接。

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
- [使用 PowerShell 管理与 Blue Yonder Workforce Management 的 Shifts 连接](shifts-connector-powershell-manage.md)
- [管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)
- [Teams PowerShell cmdlet 参考](/powershell/teams/intro?view=teams-ps)