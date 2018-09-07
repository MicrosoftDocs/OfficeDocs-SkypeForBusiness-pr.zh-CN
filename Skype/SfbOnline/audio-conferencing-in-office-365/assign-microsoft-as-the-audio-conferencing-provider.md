---
title: 将 Microsoft 指定为音频会议提供商
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解如何将 Microsoft 指定为 Skype for Business 的电话拨入会议提供商。
ms.openlocfilehash: efa3b1987feab2ba830f87e8fb8a402fed82684b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857256"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>将 Microsoft 指定为音频会议提供商

如需在包含有 Skype for Business 和 Microsoft Teams 的 Office 365 中使用音频会议，你的组织中的用户需要已分配给他们的音频会议许可证。 请参阅 [试用或购买 Office 365 中的音频会议](try-or-purchase-audio-conferencing-in-office-365.md)以了解有关许可和费用的详细信息。

Microsoft 音频会议提供电话拨入电话号码、PIN 和会议 ID，与会者可时用其加入你所在组织的会议。 你只需向计划或主持 Skype for Business 或  Microsoft Teams 会议的人员将 Microsoft 指定为音频会议提供商。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>将 Microsoft 指定为音频会议提供商

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) 使用 Skype for Business 管理中心

1. 转到 **Office 365 管理中心** > **Skype for Business**。
    
2. 在**Skype for Business 管理中心**中的左侧导航中，转到**音频会议**。
    
3. 如果看到横幅通知你有用户已被分配了**音频会议**许可证但是还没有将 Microsoft 设置为他们的音频会议提供商，请单击**单击此处移动他们**。 如果没有看到横幅，请在 **Skype for Business 管理中心**单击**用户**，然后选择**已准备好移动到音频会议的用户** 筛选器。
    
4. 在用户的属性页上，在**提供商名称**下，使用下拉列表选择 **Microsoft**。
    
    > [!NOTE]
    > 由于你使用 Microsoft 作为音频会议提供商并且有多个电话号码，你可以使用 **默认收费电话号码**下拉列表选择用户的默认音频号码。
  
5. 单击**保存**。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>对少量用户使用 Windows PowerShell 脚本

为了节省时间或自动执行此操作，你可以使用以下 PowerShell 脚本为少量用户将 Microsoft 设置为音频会议提供商。

> [!NOTE]
> 当提供商从其他提供商更改为 **Microsoft** 时，用户的拨入式会议信息（会议 ID、收费和免费电话号码）将被替换。 你应该先保存此信息，再更改提供商。 

  
要为少量用户将提供商更改为 Microsoft，你可以使用 [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)。
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>对大量用户使用 Windows PowerShell 脚本
为了节省时间或自动执行此操作，你可以使用以下 PowerShell 脚本为大量用户将 Microsoft 设置为音频会议提供商。

当提供商从其他提供商更改为 **Microsoft** 时，用户的拨入式会议信息（会议 ID、收费和免费电话号码）将被替换。 你应该先保存此信息，再更改提供商。 
  
可将以下脚本另存为的 PowerShell 脚本文件，然后使用其任何输入参数运行。

**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**示例 3：** 在此示例中，你可以使用此脚本为你组织中的大量用户将电话拨入式会议提供商从 Intercall（或其他提供商）更改为 **Microsoft**。
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  这里就是脚本：

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。
  
## <a name="related-topics"></a>相关主题
[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

