---
title: 将 Skype 分配业务和 Microsoft 小组许可证
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
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
- Licensing
- Strat_SB_PSTN
description: '了解如何将 Skype 业务许可证分配对电话系统、 音频会议、 调用计划，和通信贷。 '
ms.openlocfilehash: 12a26dc7b9ebd47ae10005afb66f23a8cb278237
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="055a2-103">将 Skype 分配业务和 Microsoft 小组许可证</span><span class="sxs-lookup"><span data-stu-id="055a2-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="055a2-104">这篇文章为您提供了有关将许可证分配给用户的音频会议、 电话系统和调用计划等功能的提示。</span><span class="sxs-lookup"><span data-stu-id="055a2-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="055a2-105">它还提供脚本分配中批量许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="055a2-106">**重要提示**： 请参阅[附加业务和 Microsoft 小组授权的 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)有关内容许可证，您需要购买和**购买**他们-这取决于您的 Office 365 计划-使用户获取音频会议，提供免费电话号码，和能够调用外部业务的电话号码。</span><span class="sxs-lookup"><span data-stu-id="055a2-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="055a2-107">电话系统和调用计划： 提示和分配许可的脚本</span><span class="sxs-lookup"><span data-stu-id="055a2-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="055a2-108">您需要知道分配音频会议、 电话系统和调用规划许可证之前</span><span class="sxs-lookup"><span data-stu-id="055a2-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="055a2-109">**使用的是面向混合用户的内部部署 PSTN 连接？**</span><span class="sxs-lookup"><span data-stu-id="055a2-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="055a2-110">如果是这样，只需将**电话系统**许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="055a2-111">应**不**调用计划分配。</span><span class="sxs-lookup"><span data-stu-id="055a2-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="055a2-112">**延迟分配许可之后**： 由于 Office 365 和 Skype 的在线业务之间的延迟，它可能是可能需要 24 小时为用户分配调用计划后分派许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="055a2-113">如果 24 小时后用户未赋值调用计划，请[与客户支持联系业务产品的管理帮助](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="055a2-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="055a2-114">**错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="055a2-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="055a2-115">如果您需要购买更多的调用规划许可证，可选择**购买更多**。</span><span class="sxs-lookup"><span data-stu-id="055a2-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="055a2-116">**接下来的步骤**： 将调用规划许可证分配给用户后，您需要为您的组织中获得您的电话号码，然后将这些数字分配给您的组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="055a2-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="055a2-117">有关分步说明，请参阅[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="055a2-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="055a2-118">如何分配给一个用户的电话系统和调用规划许可证</span><span class="sxs-lookup"><span data-stu-id="055a2-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="055a2-p106">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="055a2-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="055a2-121">如何分配电话系统，并调用计划批量许可</span><span class="sxs-lookup"><span data-stu-id="055a2-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="055a2-122">安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。</span><span class="sxs-lookup"><span data-stu-id="055a2-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="055a2-123">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="055a2-123">Don't have the module installed?</span></span> <span data-ttu-id="055a2-124">查看[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以将其下载。</span><span class="sxs-lookup"><span data-stu-id="055a2-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="055a2-125">安装 **Windows Azure Active Directory 模块。**</span><span class="sxs-lookup"><span data-stu-id="055a2-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="055a2-126">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="055a2-126">Don't have the module installed?</span></span> <span data-ttu-id="055a2-127">下载说明和 cmdlet 的语法，请参阅[管理 Azure 使用 Windows PowerShell 的广告](https://go.microsoft.com/fwlink/p/?LinkId=320628)。</span><span class="sxs-lookup"><span data-stu-id="055a2-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="055a2-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="055a2-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="055a2-129">本示例指定**企业 E3 许可证**以及**电话系统**和一个**国内调用规划**许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="055a2-130">斜体文本中列出的许可证名称或产品名称在脚本中的 （请参阅**电话系统和调用计划的产品名称或用于脚本编写的 Sku**，后面的示例）。</span><span class="sxs-lookup"><span data-stu-id="055a2-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="055a2-131">电话系统和调用计划产品名称或用于脚本编写的 Sku</span><span class="sxs-lookup"><span data-stu-id="055a2-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="055a2-132">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="055a2-132">**Product name**</span></span>|<span data-ttu-id="055a2-133">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="055a2-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="055a2-134">企业 E5 （与电话系统）</span><span class="sxs-lookup"><span data-stu-id="055a2-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="055a2-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="055a2-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="055a2-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="055a2-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="055a2-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="055a2-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="055a2-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="055a2-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="055a2-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="055a2-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="055a2-140">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="055a2-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="055a2-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="055a2-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="055a2-142">电话系统</span><span class="sxs-lookup"><span data-stu-id="055a2-142">Phone System</span></span>  <br/> |<span data-ttu-id="055a2-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="055a2-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="055a2-144">国际长途计划</span><span class="sxs-lookup"><span data-stu-id="055a2-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="055a2-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="055a2-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="055a2-146">国内通话套餐</span><span class="sxs-lookup"><span data-stu-id="055a2-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="055a2-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="055a2-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="055a2-148">通信点数</span><span class="sxs-lookup"><span data-stu-id="055a2-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="055a2-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="055a2-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="055a2-150">音频会议： 提示和分配许可的脚本</span><span class="sxs-lookup"><span data-stu-id="055a2-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="055a2-151">您需要分配音频会议许可之前，了解</span><span class="sxs-lookup"><span data-stu-id="055a2-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="055a2-152">**第三方音频会议提供商**： 如果某人已经设置时要使用第三方音频会议提供商，您分配**音频会议**许可，他们将会更改 Microsoft 作为音频会议提供程序。</span><span class="sxs-lookup"><span data-stu-id="055a2-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="055a2-153">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="055a2-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="055a2-154">下一步行动： 指定**音频会议**许可证后，您需要指定音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="055a2-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="055a2-155">请参阅 [分配作为音频会议提供商]。</span><span class="sxs-lookup"><span data-stu-id="055a2-155">See [Assign Microsoft as the audio conferencing provider].</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="055a2-156">如何将音频会议许可分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="055a2-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="055a2-p111">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="055a2-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="055a2-159">如何分配音频会议批量许可</span><span class="sxs-lookup"><span data-stu-id="055a2-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="055a2-160">下载并安装[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="055a2-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="055a2-p112">下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="055a2-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="055a2-163">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="055a2-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="055a2-164">[!注释] 此脚本中许可证名称或产品名称以斜体字列出。</span><span class="sxs-lookup"><span data-stu-id="055a2-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="055a2-165">请参阅[音频会议产品名称或用于脚本编写的 Sku](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)为所有产品名称。</span><span class="sxs-lookup"><span data-stu-id="055a2-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="055a2-166">本示例指定音频会议许可证以及企业 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="055a2-167">音频会议产品名称或用于脚本编写的 Sku</span><span class="sxs-lookup"><span data-stu-id="055a2-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="055a2-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="055a2-168"></span></span>

|<span data-ttu-id="055a2-169">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="055a2-169">**Product name**</span></span>|<span data-ttu-id="055a2-170">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="055a2-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="055a2-171">音频会议</span><span class="sxs-lookup"><span data-stu-id="055a2-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="055a2-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="055a2-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="055a2-173">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="055a2-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="055a2-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="055a2-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="055a2-175">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="055a2-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="055a2-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="055a2-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="055a2-177">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="055a2-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="055a2-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="055a2-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="055a2-179">企业 E5 （不带音频的会议）</span><span class="sxs-lookup"><span data-stu-id="055a2-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="055a2-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="055a2-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="055a2-181">企业 E5 （使用音频会议）</span><span class="sxs-lookup"><span data-stu-id="055a2-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="055a2-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="055a2-182">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="055a2-183">通信点数</span><span class="sxs-lookup"><span data-stu-id="055a2-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="055a2-184">您需要分配通信信用许可之前，了解</span><span class="sxs-lookup"><span data-stu-id="055a2-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="055a2-185">**企业 E5 客户**： 即使您的用户分配企业 E5 许可，我们仍然建议您将为其分配**通信片尾**许可证。</span><span class="sxs-lookup"><span data-stu-id="055a2-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="055a2-186">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="055a2-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="055a2-187">有关分步说明，请参阅[设置调用计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="055a2-187">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="055a2-188">如何将通讯片尾许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="055a2-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="055a2-p115">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="055a2-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="055a2-191">如何分配通信片尾批量许可</span><span class="sxs-lookup"><span data-stu-id="055a2-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="055a2-192">看一看分配**音频会议**许可的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="055a2-192">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="055a2-193">与分配**通信信用**许可的信息对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="055a2-193">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="055a2-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="055a2-194">Related topics</span></span>
  
[<span data-ttu-id="055a2-195">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="055a2-195">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="055a2-196">存入资金和管理通信点数</span><span class="sxs-lookup"><span data-stu-id="055a2-196">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  
  
 