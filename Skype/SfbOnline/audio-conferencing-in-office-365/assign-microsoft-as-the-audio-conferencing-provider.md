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
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 2ccb2b9a2b0a611d46056a8369dcb92d294c081f
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="8cdff-103">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="8cdff-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="8cdff-104">要业务和 Microsoft 小组使用 Skype 与 Office 365 音频会议，请您组织中的用户需要有分配给他们一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="8cdff-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="8cdff-105">查看[试用或购买 Office 365 中的音频会议](try-or-purchase-audio-conferencing-in-office-365.md)若要获得许可和多少它的成本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cdff-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="8cdff-106">Microsoft 的音频会议提供拨入电话号码、 针和会议 Id，可以使用的会议参与者加入您的组织的会议。</span><span class="sxs-lookup"><span data-stu-id="8cdff-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="8cdff-107">您只需将 Microsoft 作为音频会议提供商分配给要安排或导致 Skype 业务或 Microsoft 小组会议的人。</span><span class="sxs-lookup"><span data-stu-id="8cdff-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="8cdff-108">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="8cdff-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="8cdff-109">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="8cdff-109">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="8cdff-110">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="8cdff-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="8cdff-111">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="8cdff-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="8cdff-112">如果您看到一个横幅通知您存在具有**音频会议**的用户许可证分配但没有 Microsoft 设置为其音频会议提供商，但单击**以将其移动，请单击此处**。</span><span class="sxs-lookup"><span data-stu-id="8cdff-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="8cdff-113">如果您看不到标语，在**业务管理中心的 Skype**单击**用户**，然后选择**用户可以转移到会议音频**筛选器。</span><span class="sxs-lookup"><span data-stu-id="8cdff-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="8cdff-114">在属性页上的用户，在**提供程序名称**下拉列表中选择**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="8cdff-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cdff-115">由于您使用的 Microsoft 作为音频会议提供商，有多个电话号码，可以使用**默认收费电话号码**的下拉列表中选择用户的默认音频数字。</span><span class="sxs-lookup"><span data-stu-id="8cdff-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="8cdff-116">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="8cdff-116">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="8cdff-117">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="8cdff-117">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="8cdff-118">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为用户的一小部分音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="8cdff-118">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="8cdff-119">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="8cdff-119">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="8cdff-120">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="8cdff-120">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="8cdff-121">要更改 Microsoft 为少数用户提供程序，您可以使用[启用 CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cdff-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="8cdff-122">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="8cdff-122">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="8cdff-123">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="8cdff-123">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="8cdff-124">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="8cdff-124">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="8cdff-125">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="8cdff-125">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="8cdff-126">您可以将以下脚本另存为 PowerShell 脚本文件，然后运行它使用任何其输入参数。</span><span class="sxs-lookup"><span data-stu-id="8cdff-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="8cdff-127">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="8cdff-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="8cdff-128">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="8cdff-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="8cdff-129">**示例 3:**在此示例中，您可以使用此脚本更改音频会议提供商，从 Intercall （或另一个提供商） 向**微软**大用户数为您的组织中。</span><span class="sxs-lookup"><span data-stu-id="8cdff-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="8cdff-130">以下是该脚本：</span><span class="sxs-lookup"><span data-stu-id="8cdff-130">Here is the script:</span></span>

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
<span data-ttu-id="8cdff-131">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="8cdff-131">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8cdff-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="8cdff-132">Related topics</span></span>
<span data-ttu-id="8cdff-133">[请尝试或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[设置了 Skype 的在线业务](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="8cdff-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

