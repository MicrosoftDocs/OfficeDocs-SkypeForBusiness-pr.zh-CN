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
ms.openlocfilehash: 61d8eca21fec85f7f729e0d0de9cc5d43fd5ca96567e2abe49cf7b6b5f651500
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281325"
---
# <a name="assign-skype-for-business-licenses"></a>分配 Skype for Business 许可证

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文提供了有关将许可证分配给您的用户，以用于音频会议、电话系统和通话套餐等功能的提示。 它还提供了批量分配许可证的脚本。

> [!IMPORTANT]
> 请参阅[Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md)附加许可，了解需要购买哪些许可证以及如何购买许可证（具体取决于 Microsoft 365或 Office 365 计划）以便用户获得音频会议、免费号码以及拨打企业外部电话号码的能力。


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

分配音频会议、电话系统和呼叫套餐许可证之前的注意事项

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，则只需分配 **一个电话系统** 许可证。 不应 **分配** 呼叫计划。

- 分配许可证后的延迟：由于 Microsoft 365 或 Office 365 与 Skype for Business Online 之间的延迟，在分配许可证后，可能需要最多 24 小时才能为用户分配呼叫计划。 如果 24 小时后未为用户分配呼叫计划，请联系业务产品 [支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。 如果需要购买更多通话套餐许可证，请选择"**购买更多"。**
    
- **下一** 步：将呼叫计划许可证分配给用户后，需要获取组织的电话号码，然后将这些号码分配给组织中人员。 有关分步说明，请参阅 [设置呼叫计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>如何向一电话系统分配通话套餐和通话套餐许可证

这些步骤与分配许可证或Microsoft 365 Office 365相同。 请参阅[为企业分配Microsoft 365许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>如何批量分配电话系统和通话套餐许可证

1. 安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。 没有安装模块？ 请参阅 [Microsoft Online Services Sign-In RTW 专业助手](https://go.microsoft.com/fwlink/?LinkId=625123) 下载它。

2. 安装 **Windows Azure Active Directory 模块。** 没有安装模块？ 有关下载说明和 cmdlet 语法，请参阅Windows PowerShell管理 Azure [AD。](/previous-versions/azure/jj151815(v=azure.100))

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

   本示例指定一个 **企业版 E3 许可证** 以及 **电话系统** 和 **国内通话套餐** 许可证。

   脚本中许可证或产品名称的名称以斜体文本列出 (请参阅 电话系统 和调用计划产品名称或用于脚本的 **SKUS，** 在示例) 之后。

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统脚本使用的产品名称和调用计划产品名称或 SKUS

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业版 E5 （带电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际通话套餐  <br/> |MCOPSTN2  <br/> |
|国内呼叫计划 (美国 3000 分钟/欧盟 1200 分钟)   <br/> |MCOPSTN1  <br/> |
|国内呼叫套餐 (120 分钟通话套餐)   <br/> |MCOPSTN5  <br/> |
|国内呼叫套餐 (240 分钟通话套餐)   <br/> |MCOPSTN6  <br/> |
|通信点数  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议：使用技巧许可证的脚本和脚本

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>分配音频会议许可证之前你需要了解哪些信息

- 第三方音频会议提供商：如果某人已设置为使用第三方音频会议提供商，当你为其分配音频会议许可证时，他们将更改为使用Microsoft 作为音频会议提供商。 你可以将他们更改回第三方提供商。

- 接下来的步骤：分配音频会议 **许可证** 后，你需要分配音频会议提供商。 请参阅 [将 Microsoft 指定为音频会议提供商]。

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>如何向一个用户分配音频会议许可证

这些步骤与分配许可证或Microsoft 365 Office 365相同。 请参阅[为企业分配Microsoft 365许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>如何批量分配音频会议许可证

1. 下载并Microsoft Online Services Sign-In [IT 专业人员 RTW 的助手](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅 [使用 Windows PowerShell 管理 Azure AD](/previous-versions/azure/jj151815(v=azure.100))，以了解下载说明和 cmdlet 语法。

    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

    [!注释] 此脚本中许可证名称或产品名称以斜体字列出。 有关 [所有产品名称，请参阅音频会议产品名称或用于](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 脚本的 SKUS。

    此示例分配一个Enterprise E3 许可证以及一个音频会议许可证。

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音频会议产品名称或用于脚本的 SKUS
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E5（无音频会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|EnterpriseE5 (音频会议)   <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>通信点数

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>分配通信信用额度许可证之前需了解哪些信息

- **Enterprise E5** 客户：即使为用户分配了 Enterprise E5 许可证，我们也仍建议为其分配通信 **信用额度** 许可证。
    
- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅 [设置呼叫计划](/microsoftteams/set-up-calling-plans)。
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>如何向一个用户分配通信信用额度许可证

这些步骤与分配许可证或Microsoft 365 Office 365相同。 请参阅[为企业分配Microsoft 365许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>如何批量分配通信信用额度许可证

查看分配音频会议许可证 **的示例** 脚本。 使用分配通信信用额度许可证 **的信息更新** 它。

## <a name="related-topics"></a>相关主题
  
[设置通话套餐](/microsoftteams/set-up-calling-plans)
  
[添加资金并管理通信点数](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
