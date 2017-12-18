---
title: "分配 Skype for Business 和 Microsoft 团队合作的用户许可证"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# 分配 Skype for Business 和 Microsoft 团队合作的用户许可证

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
本文提供了有关您的音频会议、 电话系统和呼叫计划等功能的用户分配许可证的提示。它还提供了脚本分配批量许可证。
  
 **重要** ： 有关哪些许可证您的信息，请参阅[Skype for Business 和 Microsoft 团队许可加载项](skype-for-business-and-microsoft-teams-add-on-licensing.md)需要购买并 **了解如何购买** 他们的具体取决于您的 Office 365 计划的用户获取音频会议、 免费电话号码，以便和能够呼叫您的公司外部的电话号码。
  
## 电话系统和呼叫计划： 提示和分配许可证的脚本

### 您需要知道分配音频会议、 电话系统和呼叫计划许可证之前

- **重要提示** ：若要在 Skype for Business 管理中心的左侧导航中显示" **语音**"选项，必须先购买至少一个 **企业版 E5 许可证**、一个 **电话系统**附加设备许可证，或一个 **音频会议**附加设备许可证。
    
- **为混合用户使用本地 PSTN 连接？** 如果是这样，您只需要分配 **电话系统**许可证。应 **不** 分配呼叫计划。
    
- **分配许可证后的延迟** ： Office 365 和Skype for Business Online之间的延迟，由于它可能是可能需要多达 24 小时的用户分配调用计划后分配许可证。如果 24 小时后用户未分配调用计划，请[联系 Office 365 商业版支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。
    
- **错误消息** ： 如果尚未购买正确的许可证数，将收到一条错误消息。如果您需要购买更多调用计划的许可证，请选择 **购买更多**。
    
- **后续步骤** ： 为用户分配调用计划许可证后，您将需要为您的组织中获取您的电话号码，然后将这些数字分配给您的组织中的人员。分步说明，请参阅[设置呼叫计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。
    
### 如何为一个用户分配电话系统并调用计划许可证

步骤是相同分配Office 365许可证。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### 如何分配批量电话系统并调用计划许可证

1. 安装 **Microsoft Online Services 登录助手面向 IT 专业人员一项** 。没有安装该模块？请参阅[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以下载它。
    
2. 安装 **Windows Azure Active Directory 模块。** 没有安装该模块？请参阅[使用 Windows PowerShell 的 Azure AD 管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)下载说明和 cmdlet 语法。
    
3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：
    
    此示例中分配 **企业版 E3 许可证** 以及 **电话系统** 和 **国内调用计划** 许可证。
    
    斜体文本中列出的许可证的名称或在脚本产品名称 （示例之后，请参阅 **电话系统和呼叫计划的产品名称或 Sku 用于脚本** ，）。
    
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
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### 电话系统和呼叫计划产品名称或 Sku 用于脚本

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|企业 E5 （与电话系统）  <br/> |ENTERPRISEPREMIUM  <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业版 E1  <br/> |STANDARDPACK  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|电话系统  <br/> |MCOEV  <br/> |
|国际通话套餐  <br/> |MCOPSTN2  <br/> |
|国内通话套餐  <br/> |MCOPSTN1  <br/> |
|通讯信用额度  <br/> |MCOPSTNPP  <br/> |
   
## 音频会议： 提示和分配许可证的脚本

### 您需要知道之前分配音频会议许可证

- **第三方音频会议提供商** ： 如果某人已将设置为使用第三方音频会议提供商，当您分配的 **音频会议**许可证时，他们将更改为使用 Microsoft 作为音频会议提供商。您可以返回到第三方提供商对它们进行更改。
    
- 下一步行动： 指定 **音频会议**许可证之后，您需要的音频会议提供商分配。请执行下列操作之一：
    
  - [将 Microsoft 作为音频会议提供商分配](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - 或者，[分配第三方音频会议提供商为](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### 如何为一个用户分配音频会议许可证

步骤是相同分配Office 365许可证。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### 如何分配批量音频会议许可证

1. 下载并安装[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。
    
2. 下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 的 Azure AD 管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)下载说明和 cmdlet 语法。
    
    在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：
    
    斜体文本中列出了许可证的名称或在脚本产品名称。请参阅[音频会议产品名称或 Sku 用于脚本](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku)所有产品名称。
    
    本示例中指定的音频会议许可证以及企业版 E3 许可证。
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### 音频会议产品名称或 Sku 用于脚本
<a name="sku"> </a>

|**产品名称**|**SKU 部件名称**|
|:-----|:-----|
|音频会议  <br/> |MCOMEETADV  <br/> |
|Skype for Business Online 独立计划 2  <br/> |MCOSTANDARD  <br/> |
|企业版 E1  <br/> | STANDARDPACK <br/> |
|企业版 E3  <br/> |ENTERPRISEPACK  <br/> |
|企业 E5 （而不是音频会议）  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|企业 E5 （与音频会议）  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## 通讯信用额度

### 您需要知道分配通信贷项许可证之前

- **企业 E5 客户** ： 即使您的用户分配企业 E5 许可证，仍建议您将为其分配许可证 **通信贷项**。
    
- **后续步骤** ： 指定这些许可证之后，您将需要为您的组织中获取您的电话号码，然后将这些数字分配给您的组织中的人员。分步说明，请参阅[设置呼叫计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。
    
### 如何将通信贷项许可证分配给一个用户

步骤是相同分配Office 365许可证。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
  
### 如何分配批量通信贷项许可证

请看一下示例脚本用于分配 **音频会议**许可证。使用分配 **通信贷项**许可证的信息进行更新。
  
## 相关文章

[设置音频会议 for Skype Business 和 Microsoft 团队](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[设置呼叫计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[添加资金和管理通信贷项](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

