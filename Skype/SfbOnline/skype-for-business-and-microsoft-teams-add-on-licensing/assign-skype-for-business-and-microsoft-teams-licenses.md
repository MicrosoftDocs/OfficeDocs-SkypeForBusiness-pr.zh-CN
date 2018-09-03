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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: fef4bea3971f2984e46de7a3592b1a157076c879
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780664"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>分配 Skype for Business 和 Microsoft Teams 许可证

本文提供了有关将许可证分配给您的用户，以用于音频会议、电话系统和通话套餐等功能的提示。 它还提供了批量分配许可证的脚本。

> [!IMPORTANT]
> 请参阅 [Skype for Business 和 Microsoft Teams 的加载项许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)，了解有关需要购买哪些许可证及其**购买方法**的信息，以便用户能够使用音频会议、免费号码并且呼叫企业外的电话号码。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

分配音频会议、电话系统和呼叫套餐许可证之前的注意事项

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，您只需分配一个**电话系统**许可证。 您**不**应该分配通话套餐。

- **分配许可证之后的延迟**：由于 Office 365 和 Skype for Business Online 之间的延迟，在你分配许可证后，可能需要长达 24 小时，用户才能使用通话套餐。 如果 24 小时后仍未向用户分配通话套餐，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **错误消息**：如果您还没有购买正确数量的许可证，则会收到一条错误消息。 如果您需要购买更多通话套餐许可证，请选择**购买更多**。
    
- **后续步骤**：向用户分配通话套餐许可证后，您需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步设置说明，请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何将电话系统和通话套餐许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何批量分配电话系统和通话套餐许可证

1. 安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。 未安装模块？ 请参阅[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/?LinkId=625123)以下载它。

2. 安装 **Windows Azure Active Directory 模块。** 未安装模块？ 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，查看下载说明和 cmdlet 语法。

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

  本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。

  脚本中的许可证名称或产品名称将以斜体文本列出（请参阅示例后面的**用于脚本的电话系统和通话套餐产品名称或 SKU**）。

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>用于脚本的电话系统和通话套餐产品名称或 SKU

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业版 E5 （带电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际通话套餐  <br/> |MCOPSTN2  <br/> |
|国内通话套餐  <br/> |MCOPSTN1  <br/> |
|通信点数  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议：关于分配许可证的提示和脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>分配音频会议许可证之前的注意事项

- **第三方音频会议提供商**：如果有人已设置为使用第三方音频会议提供商，您为他们分配**音频会议**许可证时，他们将改为使用 Microsoft 为音频会议提供商。 您可以将他们更改回第三方提供商。

- 后续步骤：分配**音频会议**许可证后，您需要分配音频会议提供商。 请参阅 [将 Microsoft 指定为音频会议提供商]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何将音频会议许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何批量分配音频会议许可证

1. 下载并安装[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。

    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

    此脚本中许可证名称或产品名称以斜体字列出。 请参阅[用于脚本的电话拨入式会议产品名称或 SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)，查看所有产品名称。

    此示例分配了一个企业版 E3 许可证以及一个音频会议许可证。

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>用于脚本的音频会议产品名称或 SKU
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E5（无音频会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企业 E5 （带音频会议）  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>分配通信点数式许可证之前的注意事项

- **企业版 E5 客户**：即使您的用户分配了企业版 E5 许可证，但仍建议您将为其分配**通信点数**许可证。
    
- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步设置说明，请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何向一个用户分配通信点数许可证

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何批量分配通信点数许可证

查看用于分配**音频会议**许可证的示例脚本。 以分配**通信点数**许可证的信息进行更新。

## <a name="related-topics"></a>相关主题
  
[设置通话套餐](/microsoftteams/set-up-calling-plans)
  
[存入资金和管理通信点数](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
