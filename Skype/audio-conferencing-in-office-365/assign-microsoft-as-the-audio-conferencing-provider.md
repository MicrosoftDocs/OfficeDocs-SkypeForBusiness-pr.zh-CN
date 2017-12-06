---
title: "将 Microsoft 作为音频会议提供商分配"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# 将 Microsoft 作为音频会议提供商分配

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d) 中查找本文的英文版本以便参考。
  
音频会议提供商提供 *会议网桥*  。会议网桥提供拨入电话号码、 Pin，并创建的会议的会议 Id。只需将音频会议提供商分配给将要安排或主持Skype for Business或 Microsoft 小组会议的人员。
  
如果您想要能够看到 **Microsoft**列为音频提供商，您必须向用户分配的 **音频会议**许可证。
  
> [!NOTE]
> 如果没有第三方音频会议提供商的人员分配的 **音频会议**许可证，则 Microsoft 自动分配作为音频会议提供商。您可以根据需要[分配第三方音频会议提供商为](assign-a-third-party-as-the-audio-conferencing-provider.md)。 
  
## 将 Microsoft 作为音频会议提供商分配

### 使用 Skype for Business 管理中心

1. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
    > [!NOTE]
    > 当向 **Microsoft**更改从另一个提供商提供程序时，将替换用户 （会议 ID、 收费和免费电话号码） 的音频会议信息。您应保存此信息，然后再更改提供商。 
  
2. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **用户**，然后选择可用的用户列表中的用户。
    
3. 在"操作"窗格中，单击" **编辑**"。
    
4. 用户，在 **提供商名称**下的属性页面上选择下拉列表中的 **Microsoft** 。
    
    > [!NOTE]
    > 因为您使用 Microsoft 作为音频会议提供商并且有多个电话号码，您可以使用 **默认收费电话号码**下拉列表选择用户的默认音频号码。 
  
5. 单击" **保存**"。
    
### 对于少量用户使用 Windows PowerShell 脚本

若要节省时间或自动执行此操作，您可以使用下列 PowerShell 脚本将 Microsoft 设置为少量用户的音频会议提供商。
  
> [!NOTE]
> 当向 **Microsoft**更改从另一个提供商提供程序时，将替换用户 （会议 ID、 收费和免费电话号码） 的音频会议信息。您应保存此信息，然后再更改提供商。 
  
你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。
  
要为少量用户将提供商更改为 Microsoft，你可以使用 [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)。
  
> **示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### 对大量用户使用 Windows PowerShell 脚本

若要节省时间或自动执行此操作，您可以使用下列 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。
  
> [!NOTE]
> 当向 **Microsoft**更改从另一个提供商提供程序时，将替换用户 （会议 ID、 收费和免费电话号码） 的音频会议信息。您应保存此信息，然后再更改提供商。 
  
你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。
  
> **示例 1:** 在此示例中，您可用于此脚本更改 Intercall 从音频会议提供商 （或另一个提供商） 到 **Microsoft**大用户数为您的组织中。
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **下面是脚本：**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。
  
## 我还需了解哪些信息？

- 用户可以分配只有一个音频会议提供商。
    
- 您可以更改音频会议提供商从 Microsoft 到第三方提供商在任何时间。若要了解详细信息，请参阅[分配第三方音频会议提供商为](assign-a-third-party-as-the-audio-conferencing-provider.md)。
    
- 在您的组织，您可以使用 Microsoft 作为其音频会议提供商，某些人员和其他人使用第三方提供商。但是，这是更复杂的设置和管理。
    
## 相关主题

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

