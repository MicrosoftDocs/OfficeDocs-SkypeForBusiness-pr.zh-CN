---
title: 分配 Skype for Business 许可证
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: 96f2805a031ab122dce0fc354da4a4e60dbded32
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301265"
---
# <a name="assign-skype-for-business-licenses"></a>分配 Skype for Business 许可证

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> 有关需要购买哪些许可证以及**如何购买**许可证的信息, 请参阅[Skype for business 加载项许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)(具体取决于 Office 365 计划), 以便用户获得音频会议、免费电话号码以及拨打外线电话号码的能力您的企业。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

分配音频会议、电话系统和呼叫套餐许可证之前的注意事项

- **Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.

- **Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何向一个用户分配电话系统和呼叫计划许可证

The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何批量分配电话系统和通话套餐许可证

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

   本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。

   脚本中的许可证或产品名称的名称以斜体文本列出 (请参阅在此示例之后的**电话系统和通话计划产品名称或用于脚本的 sku**)。

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统和通话计划用于脚本的产品名称或 Sku

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业版 E5 （带电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际通话计划  <br/> |MCOPSTN2  <br/> |
|国内通话套餐  <br/> |MCOPSTN1  <br/> |
|通信点数  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议: 分配许可证的提示和脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>分配音频会议许可证之前需要了解的内容

- **Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.

- Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何向一个用户分配音频会议许可证

The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何批量分配音频会议许可证

1. 下载并安装[适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。

    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

    The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.

    此示例分配了一个企业版 E3 许可证和一个音频会议许可证。

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>用于脚本的音频会议产品名称或 Sku
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E5（无音频会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企业版 E5 (带音频会议)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>分配通讯信用许可证之前需要了解的内容

- **企业版 E5 客户**: 即使你的用户已分配有企业版 e5 许可证, 我们仍然建议你为其分配**通讯信用**许可证。
    
- **Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何向一个用户分配通讯信用许可证

The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何批量分配通讯信用许可证

Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.

## <a name="related-topics"></a>相关主题
  
[设置通话套餐](/microsoftteams/set-up-calling-plans)
  
[添加资金并管理通信点数](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
