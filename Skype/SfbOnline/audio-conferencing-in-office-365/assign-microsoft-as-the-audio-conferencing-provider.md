---
title: "将 Microsoft 指定为音频会议提供商"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
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
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: 0193743f9dd2ed6486d93d55c881f3e582e4eb04
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>将 Microsoft 指定为音频会议提供商

音频会议提供商提供*会议桥*。 会议桥提供拨入电话号码、 针和为会议创建的会议 Id。 您只需要将音频会议提供商给人打算安排或导致 Skype 业务或 Microsoft 小组会议。
  
如果您想要能够看到**Microsoft**列为音频提供商，您必须分配给用户的**音频会议**许可。
  
> [!NOTE]
> 如果没有第三方音频会议提供商的人为指定**音频会议**许可，Microsoft 自动指派为音频会议提供商。 您可以[指定第三方音频会议提供商作为](assign-a-third-party-as-the-audio-conferencing-provider.md)如果需要。
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>将 Microsoft 指定为音频会议提供商

### <a name="using-the-skype-for-business-admin-center"></a>使用 Skype for Business 管理中心

1. Go to the **Office 365 admin center** > **Skype for Business**.
    
    > [!NOTE]
    > 当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。 你应该先保存此信息，再更改提供商。 
  
2. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，然后选择可用的用户列表中用户。
    
3. 在"操作"窗格中，单击" **编辑**"。
    
4. 在属性页上的用户，在**提供程序名称**下拉列表中选择**Microsoft** 。
    
    > [!NOTE]
    > 由于您使用的 Microsoft 作为音频会议提供商，有多个电话号码，可以使用**默认收费电话号码**的下拉列表中选择用户的默认音频数字。
  
5. 单击" **保存**"。
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>对少量用户使用 Windows PowerShell 脚本

若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为用户的一小部分音频会议提供商。

> [!NOTE]
> 当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。 你应该先保存此信息，再更改提供商。 
  
你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。
  
要更改 Microsoft 为少数用户提供程序，您可以使用[启用 CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)。
  
**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>对大量用户使用 Windows PowerShell 脚本
若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。

当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。 你应该先保存此信息，再更改提供商。 
  
你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。

**示例 1:**在此示例中，您可以使用此脚本更改音频会议提供商，从 Intercall （或另一个提供商） 向**微软**大用户数为您的组织中。
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  以下是该脚本：

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
  
## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 只能有一个音频会议提供商，可以分配用户。
    
- 您可以更改音频会议提供商从 Microsoft 给第三方提供商任何时候。 若要了解详细信息，请参阅[指派第三方音频会议提供商作为](assign-a-third-party-as-the-audio-conferencing-provider.md)。
    
- 在您的组织中，您可以使用 Microsoft 作为其音频会议提供商中，一些人和其他人使用第三方提供程序。 但是这样会使设置和管理变得更加复杂。
    
## <a name="related-topics"></a>相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

