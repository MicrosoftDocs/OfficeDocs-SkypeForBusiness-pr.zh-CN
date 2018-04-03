---
title: 将 Microsoft 指定为音频会议提供商
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
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
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="195e1-104">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="195e1-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="195e1-105">要业务和 Microsoft 小组使用 Skype 与 Office 365 音频会议，请您组织中的用户需要有分配给他们一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="195e1-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="195e1-106">查看[试用或购买 Office 365 中的音频会议](try-or-purchase-audio-conferencing-in-office-365.md)若要获得许可和多少它的成本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="195e1-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="195e1-107">Microsoft 的音频会议提供拨入电话号码、 针和会议 Id，可以使用的会议参与者加入您的组织的会议。</span><span class="sxs-lookup"><span data-stu-id="195e1-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="195e1-108">您只需将 Microsoft 作为音频会议提供商分配给要安排或导致 Skype 业务或 Microsoft 小组会议的人。</span><span class="sxs-lookup"><span data-stu-id="195e1-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="195e1-109">如果**Microsoft 音频会议**许可分配给不具备音频会议提供商的用户，用户的提供商将被自动设置为**Microsoft** ，您不必执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="195e1-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="195e1-110">如果该用户已经具有音频会议提供商，必须将它们分配音频会议许可证后到 Microsoft 更改用户的提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="195e1-111">如果您想要能够看到 Microsoft 列为音频会议提供商，您必须分配给用户的音频会议许可。</span><span class="sxs-lookup"><span data-stu-id="195e1-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="195e1-112">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="195e1-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="195e1-113">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="195e1-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="195e1-114">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="195e1-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="195e1-115">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="195e1-115">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="195e1-116">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-116">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="195e1-117">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="195e1-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="195e1-118">如果您看到一个横幅通知您存在具有**音频会议**的用户许可证分配但没有 Microsoft 设置为其音频会议提供商，但单击**以将其移动，请单击此处**。</span><span class="sxs-lookup"><span data-stu-id="195e1-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="195e1-119">如果您看不到标语，在**业务管理中心的 Skype**单击**用户**，然后选择**用户可以转移到会议音频**筛选器。</span><span class="sxs-lookup"><span data-stu-id="195e1-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="195e1-120">在属性页上的用户，在**提供程序名称**下拉列表中选择**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="195e1-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="195e1-121">由于您使用的 Microsoft 作为音频会议提供商，有多个电话号码，可以使用**默认收费电话号码**的下拉列表中选择用户的默认音频数字。</span><span class="sxs-lookup"><span data-stu-id="195e1-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="195e1-122">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="195e1-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="195e1-123">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="195e1-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="195e1-124">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为用户的一小部分音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="195e1-125">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="195e1-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="195e1-126">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-126">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="195e1-127">要更改 Microsoft 为少数用户提供程序，您可以使用[启用 CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="195e1-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="195e1-128">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="195e1-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="195e1-129">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="195e1-130">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="195e1-130">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="195e1-131">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="195e1-131">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="195e1-132">您可以将以下脚本另存为 PowerShell 脚本文件，然后运行它使用任何其输入参数。</span><span class="sxs-lookup"><span data-stu-id="195e1-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="195e1-133">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="195e1-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="195e1-134">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="195e1-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="195e1-135">**示例 3:**在此示例中，您可以使用此脚本更改音频会议提供商，从 Intercall （或另一个提供商） 向**微软**大用户数为您的组织中。</span><span class="sxs-lookup"><span data-stu-id="195e1-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="195e1-136">以下是该脚本：</span><span class="sxs-lookup"><span data-stu-id="195e1-136">Here is the script:</span></span>

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
<span data-ttu-id="195e1-137">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="195e1-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="195e1-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="195e1-138">Related topics</span></span>

[<span data-ttu-id="195e1-139">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="195e1-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="195e1-140">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="195e1-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

