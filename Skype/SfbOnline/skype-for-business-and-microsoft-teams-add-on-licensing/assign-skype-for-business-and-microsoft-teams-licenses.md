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
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204843"
---
# <a name="assign-skype-for-business-licenses"></a>分配 Skype for Business 许可证

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> 有关需要购买哪些许可证以及**如何购买**许可证的信息，请参阅[Skype for business 加载项许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)（取决于 Microsoft 365 或 Office 365 计划），以便用户获得音频会议、免费电话号码以及拨打企业外部电话号码的能力。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

分配音频会议、电话系统和呼叫套餐许可证之前的注意事项

- **Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.

- **分配许可证后的延迟**：由于 Microsoft 365 或 Office 365 与 Skype For business Online 之间的延迟，在分配许可证后，可能需要长达24小时才能向用户分配呼叫计划。如果24小时后未向用户分配呼叫计划，请[联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何向一个用户分配电话系统和呼叫计划许可证

这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。 请参阅[分配或删除 Microsoft 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何批量分配电话系统和通话套餐许可证

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

   本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。

   脚本中的许可证或产品名称的名称以斜体文本列出（请参阅在此示例之后的**电话系统和通话计划产品名称或用于脚本的 sku**）。

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
|国际通话套餐  <br/> |MCOPSTN2  <br/> |
|国内呼叫计划（3000分美国/1200 最少欧盟计划）  <br/> |MCOPSTN1  <br/> |
|国内呼叫计划（120分钟通话计划）  <br/> |MCOPSTN5  <br/> |
|国内呼叫计划（240分钟通话计划）  <br/> |MCOPSTN6  <br/> |
|通信点数  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议：分配许可证的提示和脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>分配音频会议许可证之前需要了解的内容

- **第三方音频会议提供商**：如果某人已设置为使用第三方音频会议提供商，则当您为他们分配**音频会议**许可证时，他们将更改为使用 Microsoft 作为音频会议提供商。 你可以将他们更改回第三方提供商。

- 后续步骤：分配**音频会议**许可证后，你需要分配音频会议提供商。 请参阅 [将 Microsoft 指定为音频会议提供商]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何向一个用户分配音频会议许可证

这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。 请参阅[分配或删除 Microsoft 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何批量分配音频会议许可证

1. 下载并安装[适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。

    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

    [!注释] 此脚本中许可证名称或产品名称以斜体字列出。 请参阅用于为所有产品名称[编写脚本的音频会议产品名称或 sku](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 。

    此示例分配了一个企业版 E3 许可证和一个音频会议许可证。

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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
|企业版 E5 （带音频会议）  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>分配通讯信用许可证之前需要了解的内容

- **企业版 E5 客户**：即使你的用户已分配有企业版 e5 许可证，我们仍然建议你为其分配**通讯信用**许可证。
    
- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何向一个用户分配通讯信用许可证

这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。 请参阅[分配或删除 Microsoft 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何批量分配通讯信用许可证

请查看用于分配**音频会议**许可证的示例脚本。 用分配**通讯信用**许可证的信息更新它。

## <a name="related-topics"></a>相关主题
  
[设置通话套餐](/microsoftteams/set-up-calling-plans)
  
[添加资金并管理通信点数](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
