---
title: 指定 Microsoft 作为音频会议提供商
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: abb9a526a73951c3b3d4326fff67dc928691e2f1
ms.sourcegitcommit: 7bb52d5d998415555a535a32419e99b68e3be6a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="91802-103">指定 Microsoft 作为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="91802-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="91802-104">商业和 Microsoft 团队，与 Skype 的 Office 365 中使用音频会议，您的组织中的用户需要已分配给它们的音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="91802-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="91802-105">请参阅[尝试或购买 Office 365 中的音频会议](try-or-purchase-audio-conferencing-in-office-365.md)获取许可和成本的详细信息。</span><span class="sxs-lookup"><span data-stu-id="91802-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="91802-106">Microsoft 音频会议提供电话拨入电话号码和 Pin，会议程序可以使用的会议参与者加入您所在组织的会议 Id。</span><span class="sxs-lookup"><span data-stu-id="91802-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="91802-107">您只需将 Microsoft 作为音频会议提供商分配给要安排或导致 Skype 业务或 Microsoft 团队会议的人员。</span><span class="sxs-lookup"><span data-stu-id="91802-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="91802-108">指定 Microsoft 作为音频会议提供商</span><span class="sxs-lookup"><span data-stu-id="91802-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="91802-110">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="91802-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="91802-111">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="91802-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="91802-112">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="91802-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="91802-113">如果您看到横幅通知您拥有**音频会议**的用户许可证分配但不让 Microsoft 负责设置为其音频会议提供商，又单击**将他们移动，请单击此处**。</span><span class="sxs-lookup"><span data-stu-id="91802-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="91802-114">如果您看不到横幅，**业务管理中心的 Skype**中单击**用户**，然后选择**已准备好将移动到音频会议用户**筛选器。</span><span class="sxs-lookup"><span data-stu-id="91802-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="91802-115">对于用户，在**提供程序名称**下的属性页上选择下拉列表中的**Microsoft** 。</span><span class="sxs-lookup"><span data-stu-id="91802-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="91802-116">因为您使用 Microsoft 为音频会议提供商，并且有多个电话号码，您可以使用**默认收费电话号码**下拉列表选择一个默认音频号以供用户。</span><span class="sxs-lookup"><span data-stu-id="91802-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="91802-117">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="91802-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="91802-118">对少量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="91802-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="91802-119">来节省时间或自动此操作，可以使用以下 PowerShell 脚本以将 Microsoft 设置为少量用户音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="91802-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="91802-120">当向**Microsoft**更改从其他提供程序提供程序时，将替换 （会议 ID、 收费和免费电话号码） 用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="91802-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="91802-121">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="91802-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="91802-122">要更改为小型数量的用户的 Microsoft 提供程序，您可以使用[启用 CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91802-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="91802-123">对大量用户使用 Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="91802-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="91802-124">要保存时间或自动化这，可以使用以下 PowerShell 脚本的大量用户将 Microsoft 设置为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="91802-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="91802-125">当向**Microsoft**更改从其他提供程序提供程序时，将替换 （会议 ID、 收费和免费电话号码） 用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="91802-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="91802-126">你应该先保存此信息，再更改提供商。</span><span class="sxs-lookup"><span data-stu-id="91802-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="91802-127">您可以将以下脚本另存为的 PowerShell 脚本文件，然后运行它使用任何其输入参数。</span><span class="sxs-lookup"><span data-stu-id="91802-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="91802-128">**示例 1：** 你可以通过提供你希望更新的用户列表来运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="91802-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="91802-129">**示例 2：** 你可以通过提供一个 .csv 文件来运行此脚本，该文件中包含你希望更新的每个用户的电子邮件地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="91802-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="91802-130">**示例 3:** 本示例中，您可以使用此脚本更改 Intercall 的音频会议提供程序 （或其他提供程序） 到**Microsoft**的大用户数组织中。</span><span class="sxs-lookup"><span data-stu-id="91802-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="91802-131">下面是该脚本：</span><span class="sxs-lookup"><span data-stu-id="91802-131">Here is the script:</span></span>

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
<span data-ttu-id="91802-132">有关使用 Windows PowerShell 的详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)。</span><span class="sxs-lookup"><span data-stu-id="91802-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="91802-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="91802-133">Related topics</span></span>
<span data-ttu-id="91802-134">[尝试或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[设置业务 online Skype](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="91802-134">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

