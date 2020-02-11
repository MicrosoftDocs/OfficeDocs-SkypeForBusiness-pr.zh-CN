---
title: 分配 Teams 许可证
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 了解如何为音频会议、电话系统和通话计划等功能分配许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46ae5952d79f3f0ef0a6137b240661550ecead00
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888681"
---
# <a name="assign-microsoft-teams-licenses"></a>分配 Microsoft 团队许可证

你可以为用户分配许可证，例如音频会议、电话系统和通话计划等功能。 本文介绍如何批量添加这些许可证以及针对单个用户添加这些许可证。 

> [!IMPORTANT]
> 有关需要购买哪些许可证以及如何购买这些许可证的信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)，具体取决于 Office 365 计划，让用户获得音频会议、免费电话号码以及拨打企业外部电话号码的能力。

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

下面是在分配音频会议、电话系统和通话计划许可证之前需要了解的内容。

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，您只需分配一个电话系统许可证。 不应分配呼叫计划。

- **分配许可证后的延迟**：由于 Office 365 和 Microsoft 团队之间的延迟，在分配许可证后，将为用户分配呼叫计划最多可能需要24小时。 如果24小时后未向用户分配呼叫计划，请[联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。 如果需要购买更多通话计划许可证，请选择 "**购买更多**"。

- **后续步骤**：向用户分配呼叫计划许可证后，你需要为你的组织获取电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[设置呼叫计划](set-up-calling-plans.md)。

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>为一个用户分配电话系统和呼叫计划许可证

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>批量分配电话系统和呼叫计划许可证

1. 安装 适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手 。 没有安装模块？ 请参阅[适用于 It 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)下载。

2. 安装 Windows Azure Active Directory 模块。 没有安装模块？ 有关下载说明和 cmdlet 语法，请参阅[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

本示例指定一个 企业版 E3 许可证以及电话系统和国内通话套餐许可证。

脚本中的许可证或产品名称的名称以斜体列出（请参阅在示例之后[使用的电话系统和通话计划产品名称或 sku](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)）。

```powershell
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统和通话计划用于脚本的产品名称或 Sku

| 产品名称 | SKU 部件名称 |
|--------------|---------------|
| 企业版 E5 （带电话系统） | ENTERPRISEPREMIUM |
| 企业版 E3 | ENTERPRISEPACK | 
| 企业版 E1 | STANDARDPACK | 
| 电话系统 | MCOEV |
| 国内 & 国际通话计划 | MCOPSTN2 |
| 国内呼叫计划（每个用户每月每月3000分钟，对于欧盟国家/地区，每个用户每月1200分钟） | MCOPSTN1 |
| 国内呼叫计划（每个国家/地区每个用户/月120分钟） </br>*注意：此计划在美国不可用*。 | MCOPSTN5 |
| 国内呼叫计划（每个国家/地区每个用户/月240分钟） </br>*注意：此计划在美国不可用*。 | MCOPSTN6 |
| 通信点数 | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议：分配许可证的提示和脚本

下面是在分配音频会议许可证之前需要了解的信息。

- **第三方音频会议提供商**：如果某人已设置为使用第三方音频会议提供商，则当您为他们分配音频会议许可证时，他们将更改为使用 Microsoft 作为音频会议提供商。 你可以将他们更改回第三方提供商。

- **后续步骤**：分配音频会议许可证后，你需要分配音频会议提供商。 请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>将音频会议许可证分配给一个用户

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>批量分配音频会议许可证

1. 下载并安装[适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 Windows Azure Active Directory 模块。 有关下载说明和 cmdlet 语法，请参阅[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

脚本中的许可证或产品名称的名称以斜体列出。 请参阅用于为所有产品名称[编写脚本的音频会议产品名称或 sku](#audio-conferencing-product-names-or-skus-used-for-scripting) 。

此示例分配了一个企业版 E3 许可证和一个音频会议许可证。

```powershell
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>用于脚本的音频会议产品名称或 SKU

| 产品名称 | SKU 部件名称 |
|--------------|---------------|
| 音频会议（订阅） | MCOMEETADV | 
| 每分钟支付的音频会议（即付即用）</br>*注意：要求设置和启用通讯信用点数*。 | MCOMEETACPEA |
| 企业版 E1 | STANDARDPACK | 
| 企业版 E3 | ENTERPRISEPACK |
| 企业版 E5（无音频会议） |  ENTERPRISEPREMIUM_NOPSTNCONF |
| 企业版 E5 （带音频会议） | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>通信点数

下面是在分配通讯信用许可证之前需要了解的信息。

- **企业版 E5 客户**：即使你的用户已分配有企业版 e5 许可证，我们仍然建议你为其分配通讯信用许可证。

- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[设置呼叫计划](set-up-calling-plans.md)。

## <a name="assign-a-communications-credits-license-to-one-user"></a>为一个用户分配通讯信用许可证

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-communications-credits-licenses-in-bulk"></a>批量分配通讯信用许可证

请查看用于分配音频会议许可证的示例脚本。 用分配通讯信用许可证的信息更新它。

## <a name="related-topics"></a>相关主题

[设置通话套餐](set-up-calling-plans.md)
</br>
[添加资金并管理通信点数](add-funds-and-manage-communications-credits.md)
