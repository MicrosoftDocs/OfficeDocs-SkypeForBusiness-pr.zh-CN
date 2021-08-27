---
title: PowerShell 脚本示例 - 为学校中的教师和学生创建安全组
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: angch
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本创建管理学校教师和学生Teams策略所需的安全组。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3cb1f40d79c25b7e0832c5d1576427b83ba980b2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577806"
---
# <a name="powershell-script-sample---create-security-groups-for-educators-and-students-in-your-school"></a>PowerShell 脚本示例 - 为学校中的教师和学生创建安全组

使用此 PowerShell 脚本创建管理学校策略Microsoft Teams安全组。 将[策略分配到组](../assign-policies.md#assign-a-policy-to-a-group)功能Teams向一组用户（例如安全组）分配策略。 根据优先级规则，将策略分配传播到组中的成员。 将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。

此 PowerShell 脚本基于许可证类型创建两个安全组，一个组用于教职员工和教师，另一个组用于学校中的学生。 然后，可以将策略分配到创建的安全组。 有关使用此脚本的信息，请参阅 [向学校中的大量用户分配策略](../batch-group-policy-assignment-edu.md)。

此脚本执行以下操作：

- 标识分配有教职员工 SKU 的员工和教师，创建安全组，然后将教职员工和教师添加到该组。
- 标识分配有学生 SKU 的学生，创建安全组，然后将学生添加到该组。
- 更新每个安全组的成员身份，以根据员工、教师和学生是否拥有许可证来添加或删除他们。

需要定期运行此脚本，使安全组保持最新状态。

> [!IMPORTANT]
> 将策略 [分配到组时](../assign-policies.md#precedence-rules) ，必须了解优先级 [规则和组](../assign-policies.md#group-assignment-ranking) 分配排名。 请确保阅读并了解有关组的策略分配的信息 [中的概念](../assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

## <a name="before-you-start"></a>开始前

下载并安装[Skype for Business Online PowerShell 模块](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)，然后在系统提示时重启计算机。

若要了解更多信息，请参阅使用 powerShell Skype for Business [Online Office 365 powerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) Teams [PowerShell 概述](../teams-powershell-overview.md)。


## <a name="sample-script"></a>示例脚本

```powershell
<#
Script Name:
CreateOrUpdate_SecurityGroup_Per_LicenseType.ps1
Synopsis:
This script is designed to perform following operations:
1. Create a security group for faculty and student members based on the assigned license SKU and add the members accordingly.
2. Update the security group to add/remove teachers and students so that only users who have a valid teacher/student license are present in the group.
The output of the script is written in a log file present at location: C:\results\log.txt
Written By: 
Mihir Roy
Change Log:
Version 1.0, 10/08/2019 - First Draft
#>

#Figure out to determine if the user is using an existing group or creating a new one
param
(
    [string]$teachergroupname,
    [string]$teachergroupdesc,
    [string]$studentgroupname,
    [string]$studentgroupdesc,
    [Guid]$facultyid,
    [Guid]$studentid
)

[bool] $create = $false

if ([string]::IsNullOrEmpty($teachergroupname) -and [string]::IsNullOrEmpty($studentgroupname) -and [string]::IsNullOrEmpty($studentid) -and [string]::IsNullOrEmpty($facultyid)) {
    throw "Please enter valid groupnames to create groups for Teachers and Students. In order to update a group, please enter the teacher and/or student group id's."
}

#Connect to Azure AD
Write-Host "`n"
Write-Host -ForegroundColor Green "Please enter your Global Administrator Username and Password"
Write-Host "`n"
Connect-MsolService

[Guid] $teachergroupid = New-Guid
[Guid] $studentgroupid = New-Guid

if (![string]::IsNullOrEmpty($teachergroupname)) {
    New-MsolGroup -DisplayName $teachergroupname -Description $teachergroupdesc
    $Group = Get-MsolGroup -SearchString $teachergroupname
    $teachergroupid = $Group.ObjectId
    $create = $true
}

if (![string]::IsNullOrEmpty($studentgroupname)) {
    New-MsolGroup -DisplayName $studentgroupname -Description $studentgroupdesc
    $Group = Get-MsolGroup -SearchString $studentgroupname
    $studentgroupid = $Group.ObjectId
    $create = $true
}


#Build the Students Array
$StudentsArray = @()

#Build the Teachers Array
$TeachersArray = @()

#Build the Student Sku Array
$StudentSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$StudentSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*student*"}).skuid
Write-Host -ForegroundColor Green "The Student Skus identified are listed below:"
Foreach ($Element in $StudentSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Student SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Build the Teacher Sku Array
$TeacherSkus = @()
$AllSkus = Get-AzureADSubscribedSku
$TeacherSkuIDs = ($AllSkus | ? {$_.skupartnumber -like "*faculty*"}).skuid
Write-Host -ForegroundColor Green "The Teacher Skus identified are listed below:"
Foreach ($Element in $TeacherSkuIDs) {
$SkuPart = (Get-AzureADSubscribedSku | ? {$_.SkuID -eq $Element}).SkuPartNumber
Write-Host -ForegroundColor Green "Teacher SkuID ${Element} for License $SkuPart"
}
Write-Host "`n"

#Get All Users in AAD
Write-Host -ForegroundColor Green "Getting All Users in Azure Active Directory with an assigned license"
Write-Host "`n"
$AllUsers = Get-AzureADUser -All $true | ? {$_.AssignedLicenses -ne $null}

$teacherAdd = $create -and ($teachergroupid -ne $null)
$studentAdd = $create -and ($studentgroupid -ne $null)

#Start foreach loop for all users with student licenses
if ($teacherAdd -or $studentAdd) {
    Foreach ($User in $AllUsers) {
    $ObjectID = $User.ObjectID
    Write-host "`n"
    Write-Host -ForegroundColor Green "Getting Assigned Licenses for $DN"
    $GetUser = Get-AzureADUser -objectid $user.objectid
    $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
    Write-Host -ForegroundColor Green "User Assigned License: " $User.Displayname "-" $AssignedLicenses "-" $User.ObjectId


    #Set Variables
    $UPN = $User.userprincipalname
    $DN = $User.Displayname
    $OBJ = $User.ObjectID
    $Age = $User.AgeGroup
    $Consent = $User.ConsentProvidedForMinor
    $Legal = $User.LegalAgeGroupClassification

        #Start foreach loop for all assigned skus
        Foreach ($License in $AssignedLicenses) {

            #Creating new PS Object for each Sku and adding to the array
            If ($TeacherSkuIDs -contains $License) {
                $TeacherObj = New-Object PSObject
                $TeacherObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $TeacherObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $TeacherObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $TeacherObj | Add-Member NoteProperty -Name SkuID -Value $License
                $TeacherObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $TeacherObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $TeacherObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $TeachersArray += $TeacherObj
                if ($teachergroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $teachergroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
                        
            If ($StudentSkuIDs -contains $License) {
                $StudentObj = New-Object PSObject
                $StudentObj | Add-Member NoteProperty -Name UserPrincipalName -Value $UPN
                $StudentObj | Add-Member NoteProperty -Name DisplayName -Value $DN
                $StudentObj | Add-Member NoteProperty -Name ObjectID -Value $OBJ
                $StudentObj | Add-Member NoteProperty -Name SkuID -Value $License
                $StudentObj | Add-Member NoteProperty -Name AgeGroup -Value $Age
                $StudentObj | Add-Member NoteProperty -Name ConsentProvidedForMinor -Value $Consent
                $StudentObj | Add-Member NoteProperty -Name LegalAgeGroupClassification -Value $Legal
                $StudentsArray += $StudentObj
                if ($studentgroupid -ne $null) {
                    Add-MsolGroupMember -GroupObjectId $studentgroupid -GroupMemberType User -GroupMemberObjectId $OBJ
                }
            }
        }
    }
}

if ((!$teacherAdd) -and ($facultyid -ne $null)) {
    #Users to be Added in the Teacher Group that are not present
    $teacherGrpMembers = Get-MsolGroupMember -GroupObjectId $facultyid
    $teachersToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $teachersToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding faculty members to the security group
            If ($TeacherSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Faculty) to be removed from the group that are not in tenant anymore
    $teachersToRemove = ($teacherGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($teachersToRemove.Count > 0) {
        Foreach ($id in $teachersToRemove) {
            Remove-MsoLGroupMember -GroupObjectId $facultyid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

if ((!$studentAdd) -and ($studentid -ne $null)) {
    #Users to be Added in the Student Group that are not present
    $studentGrpMembers = Get-MsolGroupMember -GroupObjectId $studentid
    $studentsToAdd = ($AllUsers | ? {$_.ObjectId -ne $null}).objectid | Where {($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    Foreach ($id in $studentsToAdd) {
        $GetUser = Get-AzureADUser -objectid $id
        $AssignedLicenses = ($GetUser | select -ExpandProperty assignedlicenses).skuid
        Foreach ($License in $AssignedLicenses) {

            #Adding student members to the security group
            If ($StudentSkuIDs -contains $License) {
                Add-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupMemberObjectId $id
            }
        }
    }
    
    #Users (Students) to be removed the group that are not in tenant anymore
    $studentsToRemove = ($studentGrpMembers | ? {$_.ObjectId -ne $null}).objectid | Where {($AllUsers | ? {$_.ObjectId -ne $null}).objectid -NotContains $_}
    if ($studentsToRemove.Count > 0) {
        Foreach ($id in $studentsToRemove) {
            Remove-MsolGroupMember -GroupObjectId $studentid -GroupMemberType User -GroupmemberObjectId $id
        }
    }
}

Start-Transcript -Path "C:\results\log.txt"
if ($facultyid -ne $null) {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $facultyid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $facultyid
}
else {
    $TeacherGroup = Get-MsolGroupMember -GroupObjectId $teachergroupid
    Write-Host -ForegroundColor Green "Teacher Group Count:" $TeacherGroup.Count
    Write-Host -ForegroundColor Green "Teacher Group Id:" $teachergroupid
}

if ($studentid -ne $null) {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentid
}
else {
    $StudentGroup = Get-MsolGroupMember -GroupObjectId $studentgroupid
    Write-Host -ForegroundColor Green "Student Group Count:" $StudentGroup.Count
    Write-Host -ForegroundColor Green "Student Group Id:" $studentgroupid
}
Stop-Transcript
```

## <a name="related-topics"></a>相关主题

[向 Teams 中的用户分配策略](../assign-policies.md)