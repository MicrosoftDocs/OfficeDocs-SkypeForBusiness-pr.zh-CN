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
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: d6c0f4f3a8f903ff180785214d3a4e987321a5b3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="78092-104">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="78092-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="78092-105">音频会议提供商提供*会议桥*。</span><span class="sxs-lookup"><span data-stu-id="78092-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="78092-106">会议桥提供拨入电话号码、 针和为会议创建的会议 Id。</span><span class="sxs-lookup"><span data-stu-id="78092-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="78092-107">您只需要将音频会议提供商给人打算安排或导致 Skype 业务或 Microsoft 小组会议。</span><span class="sxs-lookup"><span data-stu-id="78092-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="78092-108">如果您想要能够看到**Microsoft**列为音频提供商，您必须分配给用户的**音频会议**许可。</span><span class="sxs-lookup"><span data-stu-id="78092-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78092-109">如果没有第三方音频会议提供商的人为指定**音频会议**许可，Microsoft 自动指派为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="78092-110">您可以[指定第三方音频会议提供商作为](assign-a-third-party-as-the-audio-conferencing-provider.md)如果需要。</span><span class="sxs-lookup"><span data-stu-id="78092-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="78092-111">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="78092-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="78092-112">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="78092-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="78092-113">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="78092-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78092-114">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="78092-114">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="78092-115">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-115">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="78092-116">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，然后选择可用的用户列表中用户。</span><span class="sxs-lookup"><span data-stu-id="78092-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="78092-117">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="78092-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="78092-118">在属性页上的用户，在**提供程序名称**下拉列表中选择**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="78092-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78092-119">由于您使用的 Microsoft 作为音频会议提供商，有多个电话号码，可以使用**默认收费电话号码**的下拉列表中选择用户的默认音频数字。</span><span class="sxs-lookup"><span data-stu-id="78092-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="78092-120">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="78092-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="78092-121">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="78092-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="78092-122">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为用户的一小部分音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="78092-123">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="78092-123">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="78092-124">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-124">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="78092-125">你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。</span><span class="sxs-lookup"><span data-stu-id="78092-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="78092-126">要更改 Microsoft 为少数用户提供程序，您可以使用[启用 CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)。</span><span class="sxs-lookup"><span data-stu-id="78092-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="78092-127">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="78092-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="78092-128">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="78092-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="78092-129">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="78092-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="78092-130">若要节省时间或实现自动操作，您可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="78092-131">当提供程序将从另一个提供程序更改为**Microsoft**时，（会议 ID，收费和免费电话号码） 的用户的音频会议信息将被替换。</span><span class="sxs-lookup"><span data-stu-id="78092-131">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="78092-132">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="78092-132">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="78092-133">你可以将以下脚本中的一个或多个保存为 PowerShell 脚本文件，然后运行该文件。</span><span class="sxs-lookup"><span data-stu-id="78092-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="78092-134">**示例 1:**在此示例中，您可以使用此脚本更改音频会议提供商，从 Intercall （或另一个提供商） 向**微软**大用户数为您的组织中。</span><span class="sxs-lookup"><span data-stu-id="78092-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="78092-135">以下是该脚本：</span><span class="sxs-lookup"><span data-stu-id="78092-135">Here is the script:</span></span>

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
<span data-ttu-id="78092-136">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="78092-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="78092-137">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="78092-137">What else should I know?</span></span>

- <span data-ttu-id="78092-138">只能有一个音频会议提供商，可以分配用户。</span><span class="sxs-lookup"><span data-stu-id="78092-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="78092-139">您可以更改音频会议提供商从 Microsoft 给第三方提供商任何时候。</span><span class="sxs-lookup"><span data-stu-id="78092-139">You can change the audio conferencing provider from Microsoft to a third-party provider at any time.</span></span> <span data-ttu-id="78092-140">若要了解详细信息，请参阅[指派第三方音频会议提供商作为](assign-a-third-party-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="78092-140">To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="78092-141">在您的组织中，您可以使用 Microsoft 作为其音频会议提供商中，一些人和其他人使用第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="78092-141">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="78092-142">但是这样会使设置和管理变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="78092-142">But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="78092-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="78092-143">Related topics</span></span>

[<span data-ttu-id="78092-144">设置音频会议 for Skype Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="78092-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="78092-145">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="78092-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)