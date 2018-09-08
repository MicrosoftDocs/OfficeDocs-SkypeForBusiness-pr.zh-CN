---
title: 分配 Skype for Business 和 Microsoft Teams 许可证
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: 1131d8daf4b865d648f51b011fc8819dee55f6b9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883499"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>分配 Skype for Business 和 Microsoft Teams 许可证

本文提供了有关将许可证分配给您的用户，以用于音频会议、电话系统和通话套餐等功能的提示。 它还提供了批量分配许可证的脚本。

> [!IMPORTANT]
> 信息，请参阅[业务和 Microsoft 团队的加载项的 Skype 许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)**如何购买**哪些需要购买的许可证以及它们的具体取决于您的 Office 365 计划-以便用户获取音频会议、 免费电话号码，以及呼叫的功能外部业务电话号码。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

分配音频会议、电话系统和呼叫套餐许可证之前的注意事项

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，您只需将**电话系统**许可证分配。 您应该**不**调用规划的分配。

- **延迟后分配许可证**： Office 365 和 Skype 业务 online 之间的延迟，因为它可能可能需要多达 24 小时用户要分配调用规划后分配许可证。 如果 24 小时后用户未分配调用计划，请[对业务产品-管理员技术联系人支持](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。 如果您需要购买更多调用规划许可证，请选择**购买更多**。
    
- **后续步骤**： 将调用规划许可证分配给您的用户后，您将需要获得您的组织，您的电话号码，然后将这些号码分配给您的组织中的人员。 有关分步说明，请参阅[Set up 调用计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何将电话系统和调用规划许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何批量分配电话系统和通话套餐许可证

1. 安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。 没有安装模块？ 请参阅[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以下载该。

2. 安装 **Windows Azure Active Directory 模块。** 没有安装模块？ 下载说明和 cmdlet 语法，请参阅[Manage 使用 Windows PowerShell 的 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

  本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。

  斜体文本中列出的许可证的名称或脚本中的产品名称 （此示例之后，请参阅**电话系统和调用规划产品名称或 Sku 用于脚本**，）。

  ```
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统和调用计划产品名称或 Sku 用于编写脚本

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业版 E5 （带电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际呼叫计划  <br/> |MCOPSTN2  <br/> |
|国内通话套餐  <br/> |MCOPSTN1  <br/> |
|通信点数  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议： 提示和分配许可证的脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>您需要知道分配音频会议许可证之前

- **第三方音频会议提供商**： 如果某人已设置为使用第三方音频会议提供商，您将其分配的**音频会议**许可证时，他们将更改用于 Microsoft 为音频会议提供程序。 你可以将他们更改回第三方提供商。

- 后续步骤： 分配**音频会议**许可证后，您需要分配音频会议提供商。 请参阅 [将 Microsoft 指定为音频会议提供商]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何将音频会议许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何将音频会议许可证批量分配

1. 下载并安装[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。

    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

    [!注释] 此脚本中许可证名称或产品名称以斜体字列出。 请参阅[音频会议产品名称或 Sku 用于编写脚本](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)的所有产品名称。

    本示例指定一个要进行音频会议许可证以及一个企业版 E3 许可证。

```
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音频会议产品名称或 Sku 用于编写脚本
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E5（无音频会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企业 E5 （与音频会议）  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>您需要知道分配 Communications 字幕式许可证之前

- **企业 E5 客户**： 即使您的用户分配了企业 E5 许可证，但仍建议您将为其分配**Communications 字幕式**许可证。
    
- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[Set up 调用计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何将 Communications 字幕式许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何将批量 Communications 字幕式许可证分配

请看一下分配**音频会议**许可证的示例脚本。 更新其分配**Communications 字幕式**许可证的信息。

## <a name="related-topics"></a>相关主题
  
[设置通话套餐](/microsoftteams/set-up-calling-plans)
  
[存入资金和管理通信点数](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
