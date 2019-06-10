---
title: 分配 Skype for Business 许可证
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: 997cffce5b98ed992371a0f43e701b2efc1ae128
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "34768772"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="ad737-103">分配 Skype for Business 许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="ad737-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="ad737-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad737-106">有关需要购买哪些许可证以及**如何购买**许可证的信息, 请参阅[Skype for business 加载项许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)(具体取决于 Office 365 计划), 以便用户获得音频会议、免费电话号码以及拨打外线电话号码的能力您的企业。</span><span class="sxs-lookup"><span data-stu-id="ad737-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="ad737-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="ad737-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="ad737-108">分配音频会议、电话系统和呼叫套餐许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="ad737-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="ad737-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="ad737-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="ad737-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="ad737-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="ad737-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="ad737-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="ad737-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="ad737-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="ad737-118">如何向一个用户分配电话系统和呼叫计划许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="ad737-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="ad737-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="ad737-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="ad737-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="ad737-121">如何批量分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="ad737-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="ad737-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="ad737-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="ad737-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="ad737-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="ad737-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="ad737-129">本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。</span><span class="sxs-lookup"><span data-stu-id="ad737-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="ad737-130">脚本中的许可证或产品名称的名称以斜体文本列出 (请参阅在此示例之后的**电话系统和通话计划产品名称或用于脚本的 sku**)。</span><span class="sxs-lookup"><span data-stu-id="ad737-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="ad737-131">电话系统和通话计划用于脚本的产品名称或 Sku</span><span class="sxs-lookup"><span data-stu-id="ad737-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="ad737-132">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="ad737-132">**Product name**</span></span>|<span data-ttu-id="ad737-133">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="ad737-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad737-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="ad737-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="ad737-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="ad737-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="ad737-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="ad737-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="ad737-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="ad737-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="ad737-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="ad737-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="ad737-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="ad737-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="ad737-140">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="ad737-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="ad737-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="ad737-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="ad737-142">电话系统</span><span class="sxs-lookup"><span data-stu-id="ad737-142">Phone System</span></span>  <br/> |<span data-ttu-id="ad737-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="ad737-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="ad737-144">国际通话计划</span><span class="sxs-lookup"><span data-stu-id="ad737-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="ad737-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="ad737-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="ad737-146">国内呼叫计划 (3000 分美国/1200 最少欧盟计划)</span><span class="sxs-lookup"><span data-stu-id="ad737-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="ad737-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="ad737-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="ad737-148">国内呼叫计划 (120 分钟通话计划)</span><span class="sxs-lookup"><span data-stu-id="ad737-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="ad737-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="ad737-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="ad737-150">国内呼叫计划 (240 分钟通话计划)</span><span class="sxs-lookup"><span data-stu-id="ad737-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="ad737-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="ad737-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="ad737-152">通信点数</span><span class="sxs-lookup"><span data-stu-id="ad737-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="ad737-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="ad737-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="ad737-154">音频会议: 分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="ad737-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="ad737-155">分配音频会议许可证之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="ad737-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="ad737-156">**第三方音频会议提供商**: 如果某人已设置为使用第三方音频会议提供商, 则当您为他们分配**音频会议**许可证时, 他们将更改为使用 Microsoft 作为音频会议程序.</span><span class="sxs-lookup"><span data-stu-id="ad737-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="ad737-157">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="ad737-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="ad737-158">后续步骤: 分配**音频会议**许可证后, 你需要分配音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ad737-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="ad737-159">请参阅 [将 Microsoft 指定为音频会议提供商]。</span><span class="sxs-lookup"><span data-stu-id="ad737-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="ad737-160">如何向一个用户分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="ad737-161">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="ad737-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="ad737-162">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="ad737-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="ad737-163">如何批量分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="ad737-164">下载并安装[适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="ad737-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="ad737-p112">下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="ad737-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="ad737-167">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="ad737-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="ad737-168">[!注释] 此脚本中许可证名称或产品名称以斜体字列出。</span><span class="sxs-lookup"><span data-stu-id="ad737-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="ad737-169">请参阅用于为所有产品名称[编写脚本的音频会议产品名称或 sku](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 。</span><span class="sxs-lookup"><span data-stu-id="ad737-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="ad737-170">此示例分配了一个企业版 E3 许可证和一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="ad737-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="ad737-171">用于脚本的音频会议产品名称或 Sku</span><span class="sxs-lookup"><span data-stu-id="ad737-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="ad737-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="ad737-172"></span></span>

|<span data-ttu-id="ad737-173">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="ad737-173">**Product name**</span></span>|<span data-ttu-id="ad737-174">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="ad737-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad737-175">音频会议</span><span class="sxs-lookup"><span data-stu-id="ad737-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="ad737-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="ad737-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="ad737-177">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="ad737-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="ad737-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="ad737-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="ad737-179">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="ad737-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="ad737-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="ad737-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="ad737-181">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="ad737-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="ad737-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="ad737-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="ad737-183">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="ad737-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="ad737-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="ad737-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="ad737-185">企业版 E5 (带音频会议)</span><span class="sxs-lookup"><span data-stu-id="ad737-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="ad737-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="ad737-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="ad737-187">通信点数</span><span class="sxs-lookup"><span data-stu-id="ad737-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="ad737-188">分配通讯信用许可证之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="ad737-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="ad737-189">**企业版 E5 客户**: 即使你的用户已分配有企业版 e5 许可证, 我们仍然建议你为其分配**通讯信用**许可证。</span><span class="sxs-lookup"><span data-stu-id="ad737-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="ad737-190">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="ad737-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="ad737-191">有关分步说明, 请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="ad737-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="ad737-192">如何向一个用户分配通讯信用许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="ad737-193">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="ad737-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="ad737-194">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="ad737-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="ad737-195">如何批量分配通讯信用许可证</span><span class="sxs-lookup"><span data-stu-id="ad737-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="ad737-196">请查看用于分配**音频会议**许可证的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="ad737-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="ad737-197">用分配**通讯信用**许可证的信息更新它。</span><span class="sxs-lookup"><span data-stu-id="ad737-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad737-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad737-198">Related topics</span></span>
  
[<span data-ttu-id="ad737-199">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="ad737-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="ad737-200">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="ad737-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
