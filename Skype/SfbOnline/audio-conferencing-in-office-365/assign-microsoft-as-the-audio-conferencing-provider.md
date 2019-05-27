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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 18792e87b83f9ee69030a6d83fecdbb9513c6f73
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "34432600"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="661f5-103">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="661f5-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="661f5-p101">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them. See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span><span class="sxs-lookup"><span data-stu-id="661f5-p101">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them. See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="661f5-p102">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization. You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span><span class="sxs-lookup"><span data-stu-id="661f5-p102">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization. You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="661f5-108">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="661f5-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) <span data-ttu-id="661f5-110">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="661f5-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="661f5-111">转到**Microsoft 团队管理中心** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="661f5-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="661f5-112">在**Skype For business 管理中心**的左侧导航中, 转到 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="661f5-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="661f5-p103">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**. If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span><span class="sxs-lookup"><span data-stu-id="661f5-p103">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**. If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="661f5-115">在用户的属性页上, 在 "**提供商名称**" 下的下拉列表中选择 " **Microsoft** "。</span><span class="sxs-lookup"><span data-stu-id="661f5-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="661f5-116">由于你使用 Microsoft 作为音频会议提供商, 并且有多个电话号码, 你可以使用 "**默认收费号码**" 下拉列表选择用户的默认音频号码。</span><span class="sxs-lookup"><span data-stu-id="661f5-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="661f5-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="661f5-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="661f5-118">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="661f5-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="661f5-119">为节省时间或自动执行此操作, 你可以使用以下 PowerShell 脚本将 Microsoft 设置为适用于少数用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="661f5-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="661f5-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span><span class="sxs-lookup"><span data-stu-id="661f5-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="661f5-122">若要为少量用户将提供商更改为 Microsoft, 你可以使用[get-csonlinedialinconferencinguser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="661f5-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="661f5-123">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="661f5-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="661f5-124">为了节省时间或自动执行此操作, 你可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="661f5-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="661f5-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span><span class="sxs-lookup"><span data-stu-id="661f5-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="661f5-127">可将以下脚本另存为的 PowerShell 脚本文件，然后使用其任何输入参数运行。</span><span class="sxs-lookup"><span data-stu-id="661f5-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="661f5-128">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="661f5-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="661f5-129">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="661f5-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="661f5-130">**示例 3:** 在此示例中, 你可以使用此脚本将音频会议提供商从 Intercall (或另一个提供商) 更改为你组织中的大量用户的**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="661f5-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="661f5-131">这里就是脚本：</span><span class="sxs-lookup"><span data-stu-id="661f5-131">Here is the script:</span></span>

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
<span data-ttu-id="661f5-132">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="661f5-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="661f5-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="661f5-133">Related topics</span></span>
<span data-ttu-id="661f5-134">[在 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
中试用或购买音频会议[设置 Skype for business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="661f5-134">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

