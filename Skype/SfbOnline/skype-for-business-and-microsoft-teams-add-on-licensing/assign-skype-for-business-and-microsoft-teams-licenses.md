---
title: 将 Skype 分配业务和 Microsoft 小组许可证
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: '了解如何将 Skype 业务许可证分配对电话系统、 音频会议、 调用计划，和通信贷。 '
ms.openlocfilehash: 12a26dc7b9ebd47ae10005afb66f23a8cb278237
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>将 Skype 分配业务和 Microsoft 小组许可证

这篇文章为您提供了有关将许可证分配给用户的音频会议、 电话系统和调用计划等功能的提示。 它还提供脚本分配中批量许可证。
  
 **重要提示**： 请参阅[附加业务和 Microsoft 小组授权的 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)有关内容许可证，您需要购买和**购买**他们-这取决于您的 Office 365 计划-使用户获取音频会议，提供免费电话号码，和能够调用外部业务的电话号码。
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和调用计划： 提示和分配许可的脚本

您需要知道分配音频会议、 电话系统和调用规划许可证之前

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，只需将**电话系统**许可证。 应**不**调用计划分配。
    
- **延迟分配许可之后**： 由于 Office 365 和 Skype 的在线业务之间的延迟，它可能是可能需要 24 小时为用户分配调用计划后分派许可证。 如果 24 小时后用户未赋值调用计划，请[与客户支持联系业务产品的管理帮助](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。
    
- **错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。 如果您需要购买更多的调用规划许可证，可选择**购买更多**。
    
- **接下来的步骤**： 将调用规划许可证分配给用户后，您需要为您的组织中获得您的电话号码，然后将这些数字分配给您的组织中的人员。 有关分步说明，请参阅[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何分配给一个用户的电话系统和调用规划许可证

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何分配电话系统，并调用计划批量许可

1. 安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。 没有安装模块？ 查看[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以将其下载。
    
2. 安装 **Windows Azure Active Directory 模块。** 没有安装模块？ 下载说明和 cmdlet 的语法，请参阅[管理 Azure 使用 Windows PowerShell 的广告](https://go.microsoft.com/fwlink/p/?LinkId=320628)。
    
3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：
    
  本示例指定**企业 E3 许可证**以及**电话系统**和一个**国内调用规划**许可证。
    
  斜体文本中列出的许可证名称或产品名称在脚本中的 （请参阅**电话系统和调用计划的产品名称或用于脚本编写的 Sku**，后面的示例）。
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统和调用计划产品名称或用于脚本编写的 Sku

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业 E5 （与电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际长途计划  <br/> |MCOPSTN2  <br/> |
|国内通话套餐  <br/> |MCOPSTN1  <br/> |
|通信点数  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议： 提示和分配许可的脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>您需要分配音频会议许可之前，了解

- **第三方音频会议提供商**： 如果某人已经设置时要使用第三方音频会议提供商，您分配**音频会议**许可，他们将会更改 Microsoft 作为音频会议提供程序。 你可以将他们更改回第三方提供商。
    
- 下一步行动： 指定**音频会议**许可证后，您需要指定音频会议提供商。 请参阅 [分配作为音频会议提供商]。
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何将音频会议许可分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何分配音频会议批量许可

1. 下载并安装[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。
    
2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。
    
    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：
    
    [!注释] 此脚本中许可证名称或产品名称以斜体字列出。 请参阅[音频会议产品名称或用于脚本编写的 Sku](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)为所有产品名称。
    
    本示例指定音频会议许可证以及企业 E3 许可证。
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音频会议产品名称或用于脚本编写的 Sku
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业 E5 （不带音频的会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企业 E5 （使用音频会议）  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>您需要分配通信信用许可之前，了解

- **企业 E5 客户**： 即使您的用户分配企业 E5 许可，我们仍然建议您将为其分配**通信片尾**许可证。
    
- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何将通讯片尾许可证分配给一个用户

步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何分配通信片尾批量许可

看一看分配**音频会议**许可的示例脚本。 与分配**通信信用**许可的信息对其进行更新。
  
## <a name="related-topics"></a>相关主题
  
[设置通话套餐](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[存入资金和管理通信点数](add-funds-and-manage-communications-credits.md)
  
  
 