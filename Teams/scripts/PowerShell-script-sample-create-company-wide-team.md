---
title: PowerShell 脚本示例 - 在 Microsoft Teams 中创建公司范围的团队
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
description: 使用此 PowerShell 脚本在 Teams 中创建公司范围的公共团队。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
ms.openlocfilehash: 99de14049a0811227c74d0199e322761490dc69f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013190"
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>PowerShell 脚本示例 - 在 Microsoft Teams 中创建公司范围的团队
-------------------------------------------------------------------------

此 PowerShell 脚本用于在 Teams 中创建公司范围的公共团队。 该脚本使用 MicrosoftTeams PowerShell 模块（当前在 beta 版中提供）创建公司范围的公共团队。 它还使用 AzureAD PowerShell 模块提取你的租户中的用户列表。 

有关使用此 PowerShell 脚本的完整说明，请查看我们的教程[使用 PowerShell 在 Teams 中创建公司范围的团队](../Company-wide-team-creation-powershell.yml)。

如果你不了解 PowerShell 并需要入门帮助，请参阅 [Azure PowerShell 概述](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)。


## <a name="sample-script"></a>示例脚本

> [!TIP]
> PowerShell 脚本文件是扩展名为 .PS1 的文本文件。 要使用此脚本，请单击“**复制**”，然后将代码粘贴到文本文件中。 使用文件名 CreateCompanyWideTeam.ps1 保存该文件，你即得到一个 PowerShell 脚本。

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>脚本说明


有关使用此 PowerShell 脚本的完整说明，请查看我们的教程[使用 PowerShell 在 Teams 中创建公司范围的团队](../Company-wide-team-creation-powershell.yml)

此脚本有 5 个部分（按从上到下的顺序列出）：
1. **文档和变量定义**
2. **Function Create-Team**：创建团队（如果需要）。 如果你未指定 GroupID，则此部分将使用指定的 TeamName 和 TeamDescription 创建团队。
3. **Function Add-Channels**：如果你指定了频道，则在此提供频道说明，然后创建频道。 
4. **Function Add-Members**：在此部分进行所有成员管理。 此部分连接到 AzureAD、提取一组用户，然后将其添加到团队（如果你未提供成员列表）。 此部分处理添加所有者和成员以及不添加已属于团队的成员的逻辑。 
5. **Main program**：这是各功能的执行顺序。 


