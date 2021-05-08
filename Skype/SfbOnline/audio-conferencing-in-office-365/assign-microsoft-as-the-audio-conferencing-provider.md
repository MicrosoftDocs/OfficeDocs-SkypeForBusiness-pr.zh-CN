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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237758"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="7daa9-103">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="7daa9-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="7daa9-104">要通过 Microsoft 365 或 Office 365 Skype for Business Microsoft Teams 使用音频会议，组织中用户需要为其分配音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="7daa9-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="7daa9-105">有关[许可及其费用](try-or-purchase-audio-conferencing-in-office-365.md)Microsoft 365，Office 365试用或购买音频会议。</span><span class="sxs-lookup"><span data-stu-id="7daa9-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="7daa9-106">Microsoft 音频会议提供电话拨入电话号码、PIN 和会议 ID，与会者可时用其加入你所在组织的会议。</span><span class="sxs-lookup"><span data-stu-id="7daa9-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="7daa9-107">你只需将 Microsoft 作为音频会议提供商分配给要安排或Skype for Business或Microsoft Teams会议。</span><span class="sxs-lookup"><span data-stu-id="7daa9-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="7daa9-108">将 Microsoft 指定为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="7daa9-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![一个图标，显示Skype for Business徽标](../images/sfb-logo-30x30.png) <span data-ttu-id="7daa9-110">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="7daa9-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="7daa9-111">转到管理 **Microsoft Teams**  >  **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="7daa9-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="7daa9-112">在 **Skype for Business管理中心的** 左侧导航中，转到"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="7daa9-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7daa9-113">如果看到横幅通知你有用户已被分配了 **音频会议** 许可证但是还没有将 Microsoft 设置为他们的音频会议提供商，请单击 **单击此处移动他们**。</span><span class="sxs-lookup"><span data-stu-id="7daa9-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="7daa9-114">如果没有看到横幅，请在 **Skype for Business 管理中心** 单击 **用户**，然后选择 **已准备好移动到音频会议的用户** 筛选器。</span><span class="sxs-lookup"><span data-stu-id="7daa9-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="7daa9-115">在用户的属性页上，在"提供者名称 **"下**，在下拉列表中选择 **"Microsoft"。**</span><span class="sxs-lookup"><span data-stu-id="7daa9-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7daa9-116">由于你使用 Microsoft 作为音频会议提供商并且有多个电话号码，因此可以使用"默认收费号码"下拉列表为用户选择默认音频号码。</span><span class="sxs-lookup"><span data-stu-id="7daa9-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="7daa9-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7daa9-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="7daa9-118">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="7daa9-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="7daa9-119">为节省时间或自动执行此操作，可以使用以下 PowerShell 脚本将 Microsoft 设置为少数用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="7daa9-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="7daa9-120">当提供商从另一个提供商更改为 **Microsoft** 时，将 (会议 ID、收费和免费号码的用户) 信息。</span><span class="sxs-lookup"><span data-stu-id="7daa9-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="7daa9-121">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="7daa9-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="7daa9-122">若要为少量用户将提供程序更改为 Microsoft，可以使用  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7daa9-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="7daa9-123">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="7daa9-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="7daa9-124">为节省时间或自动执行此操作，可以使用以下 PowerShell 脚本将 Microsoft 设置为大量用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="7daa9-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="7daa9-125">当提供商从另一个提供商更改为 **Microsoft** 时，将 (会议 ID、收费和免费号码的用户) 信息。</span><span class="sxs-lookup"><span data-stu-id="7daa9-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="7daa9-126">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="7daa9-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="7daa9-127">可将以下脚本另存为的 PowerShell 脚本文件，然后使用其任何输入参数运行。</span><span class="sxs-lookup"><span data-stu-id="7daa9-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="7daa9-128">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="7daa9-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="7daa9-129">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="7daa9-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="7daa9-130">**示例 3：** 此示例中，可以使用此脚本将音频会议提供商从 Intercall (或另一个提供商) 组织中大量用户更改为 **Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="7daa9-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="7daa9-131">这里就是脚本：</span><span class="sxs-lookup"><span data-stu-id="7daa9-131">Here is the script:</span></span>

  ```PowerShell
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
<span data-ttu-id="7daa9-132">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="7daa9-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7daa9-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="7daa9-133">Related topics</span></span>
<span data-ttu-id="7daa9-134">[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="7daa9-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
