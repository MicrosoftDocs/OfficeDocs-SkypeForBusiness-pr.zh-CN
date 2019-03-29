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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: e81c4c4d2fc11202ac114912ca309d93b00f2062
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952462"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="fe6fe-103">分配 Skype for Business 许可证</span><span class="sxs-lookup"><span data-stu-id="fe6fe-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="fe6fe-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe6fe-106">信息，请参阅[业务加载项授权的 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) **如何购买**哪些需要购买的许可证以及它们的具体取决于您的 Office 365 计划-使用户获取音频会议、 免费电话号码，以及呼叫电话号码之外的功能您的业务。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="fe6fe-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="fe6fe-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="fe6fe-108">分配音频会议、电话系统和呼叫套餐许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="fe6fe-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="fe6fe-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="fe6fe-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="fe6fe-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="fe6fe-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="fe6fe-118">如何将电话系统和调用规划许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="fe6fe-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="fe6fe-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="fe6fe-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="fe6fe-121">如何批量分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="fe6fe-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="fe6fe-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="fe6fe-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="fe6fe-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="fe6fe-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="fe6fe-129">本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="fe6fe-130">斜体文本中列出的许可证的名称或脚本中的产品名称 （此示例之后，请参阅**电话系统和调用规划产品名称或 Sku 用于脚本**，）。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="fe6fe-131">电话系统和调用计划产品名称或 Sku 用于编写脚本</span><span class="sxs-lookup"><span data-stu-id="fe6fe-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="fe6fe-132">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="fe6fe-132">**Product name**</span></span>|<span data-ttu-id="fe6fe-133">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="fe6fe-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe6fe-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="fe6fe-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="fe6fe-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="fe6fe-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="fe6fe-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="fe6fe-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fe6fe-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="fe6fe-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="fe6fe-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="fe6fe-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="fe6fe-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="fe6fe-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="fe6fe-140">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="fe6fe-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="fe6fe-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="fe6fe-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="fe6fe-142">电话系统</span><span class="sxs-lookup"><span data-stu-id="fe6fe-142">Phone System</span></span>  <br/> |<span data-ttu-id="fe6fe-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="fe6fe-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="fe6fe-144">国际呼叫计划</span><span class="sxs-lookup"><span data-stu-id="fe6fe-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="fe6fe-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="fe6fe-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="fe6fe-146">国内通话套餐</span><span class="sxs-lookup"><span data-stu-id="fe6fe-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="fe6fe-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="fe6fe-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="fe6fe-148">通信点数</span><span class="sxs-lookup"><span data-stu-id="fe6fe-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="fe6fe-149">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="fe6fe-149">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="fe6fe-150">音频会议： 提示和分配许可证的脚本</span><span class="sxs-lookup"><span data-stu-id="fe6fe-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="fe6fe-151">您需要知道分配音频会议许可证之前</span><span class="sxs-lookup"><span data-stu-id="fe6fe-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="fe6fe-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="fe6fe-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="fe6fe-156">如何将音频会议许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="fe6fe-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="fe6fe-157">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-157">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="fe6fe-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="fe6fe-159">如何将音频会议许可证批量分配</span><span class="sxs-lookup"><span data-stu-id="fe6fe-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="fe6fe-160">下载并安装[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="fe6fe-p112">下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="fe6fe-163">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="fe6fe-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="fe6fe-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="fe6fe-166">本示例指定一个要进行音频会议许可证以及一个企业版 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="fe6fe-167">音频会议产品名称或 Sku 用于编写脚本</span><span class="sxs-lookup"><span data-stu-id="fe6fe-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="fe6fe-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="fe6fe-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="fe6fe-169">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="fe6fe-169">**Product name**</span></span>|<span data-ttu-id="fe6fe-170">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="fe6fe-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe6fe-171">音频会议</span><span class="sxs-lookup"><span data-stu-id="fe6fe-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="fe6fe-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="fe6fe-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="fe6fe-173">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="fe6fe-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="fe6fe-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="fe6fe-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="fe6fe-175">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="fe6fe-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="fe6fe-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="fe6fe-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="fe6fe-177">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="fe6fe-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fe6fe-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="fe6fe-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="fe6fe-179">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="fe6fe-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="fe6fe-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="fe6fe-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="fe6fe-181">企业 E5 （与音频会议）</span><span class="sxs-lookup"><span data-stu-id="fe6fe-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="fe6fe-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="fe6fe-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="fe6fe-183">通信点数</span><span class="sxs-lookup"><span data-stu-id="fe6fe-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="fe6fe-184">您需要知道分配 Communications 字幕式许可证之前</span><span class="sxs-lookup"><span data-stu-id="fe6fe-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="fe6fe-185">**企业 E5 客户**： 即使您的用户分配了企业 E5 许可证，但仍建议您将为其分配**Communications 字幕式**许可证。</span><span class="sxs-lookup"><span data-stu-id="fe6fe-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="fe6fe-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="fe6fe-188">如何将 Communications 字幕式许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="fe6fe-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="fe6fe-189">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-189">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="fe6fe-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="fe6fe-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="fe6fe-191">如何将批量 Communications 字幕式许可证分配</span><span class="sxs-lookup"><span data-stu-id="fe6fe-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="fe6fe-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span><span class="sxs-lookup"><span data-stu-id="fe6fe-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe6fe-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="fe6fe-194">Related topics</span></span>
  
[<span data-ttu-id="fe6fe-195">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="fe6fe-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="fe6fe-196">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="fe6fe-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
