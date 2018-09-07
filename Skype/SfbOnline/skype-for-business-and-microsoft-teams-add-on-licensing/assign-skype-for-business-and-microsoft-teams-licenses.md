---
title: 分配 Skype for Business 和 Microsoft Teams 许可证
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: af2b7357c5dbe9e11b84ac87e0f72721d10a6a30
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856050"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="b5fa0-103">分配 Skype for Business 和 Microsoft Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="b5fa0-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="b5fa0-104">本文提供了有关将许可证分配给您的用户，以用于音频会议、电话系统和通话套餐等功能的提示。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="b5fa0-105">它还提供了批量分配许可证的脚本。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5fa0-106">请参阅 [Skype for Business 和 Microsoft Teams 的加载项许可](skype-for-business-and-microsoft-teams-add-on-licensing.md)，了解有关需要购买哪些许可证及其**购买方法**的信息，以便用户能够使用音频会议、免费号码并且呼叫企业外的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-106">IMPORTANT: See[Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get dial-in conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b5fa0-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="b5fa0-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b5fa0-108">分配音频会议、电话系统和呼叫套餐许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="b5fa0-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="b5fa0-109">**使用的是面向混合用户的内部部署 PSTN 连接？**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="b5fa0-110">如果是这样，只需分配一个**电话系统**许可证。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-110">If so, you only need to assign a Skype for Business Cloud PBX license.</span></span> <span data-ttu-id="b5fa0-111">**不**应该分配通话套餐。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-111">You should **NOT** assign a PSTN Calling plan.</span></span>

- <span data-ttu-id="b5fa0-112">**分配许可证之后的延迟**：由于 Office 365 和 Skype for Business Online 之间的延迟，在你分配许可证后，最长可能需要 24 小时的时间，用户才能使用通话套餐。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be enabled for PSTN Calling after you assign a license.</span></span> <span data-ttu-id="b5fa0-113">如果 24 小时后仍未向用户分配通话套餐，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-113">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b5fa0-114">**错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="b5fa0-115">如果需要购买更多通话套餐许可证，请选择**购买更多**。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-115">If you need to buy more licenses to enable this user for PSTN Calling, choose **Buy more**.</span></span>
    
- <span data-ttu-id="b5fa0-116">**后续步骤**：向用户分配通话套餐许可证后，需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-116">**Next steps**: After you assign PSTN Calling plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b5fa0-117">有关分步设置说明，请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-117">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="b5fa0-118">如何将电话系统和通话套餐许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="b5fa0-118">How to assign a Cloud PBX and PSTN Calling license to one user</span></span>

<span data-ttu-id="b5fa0-p106">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="b5fa0-121">如何批量分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="b5fa0-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="b5fa0-122">安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="b5fa0-123">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="b5fa0-123">Don't have the module installed?</span></span> <span data-ttu-id="b5fa0-124">请参阅[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/?LinkId=625123)以下载它。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-124">See[Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="b5fa0-125">安装 **Windows Azure Active Directory 模块。**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="b5fa0-126">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="b5fa0-126">Don't have the module installed?</span></span> <span data-ttu-id="b5fa0-127">请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，查看下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="b5fa0-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="b5fa0-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="b5fa0-129">本示例指定一个 **企业版 E3 许可证**以及**电话系统**和**国内通话套餐**许可证。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="b5fa0-130">脚本中的许可证名称或产品名称将以斜体文本列出（请参阅示例后面的**用于脚本的电话系统和通话套餐产品名称或 SKU**）。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-130">The name of the licenses or product names in the script are listed in italics text (see **Cloud PBX and PSTN Calling product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b5fa0-131">用于脚本的电话系统和通话套餐产品名称或 SKU</span><span class="sxs-lookup"><span data-stu-id="b5fa0-131">Cloud PBX and PSTN Calling product names or SKUs used for scripting</span></span>

|<span data-ttu-id="b5fa0-132">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-132">**Product name**</span></span>|<span data-ttu-id="b5fa0-133">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5fa0-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="b5fa0-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="b5fa0-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b5fa0-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="b5fa0-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="b5fa0-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b5fa0-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b5fa0-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b5fa0-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="b5fa0-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b5fa0-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b5fa0-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b5fa0-140">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="b5fa0-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b5fa0-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b5fa0-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b5fa0-142">电话系统</span><span class="sxs-lookup"><span data-stu-id="b5fa0-142">Phone System</span></span>  <br/> |<span data-ttu-id="b5fa0-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b5fa0-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="b5fa0-144">国际通话套餐</span><span class="sxs-lookup"><span data-stu-id="b5fa0-144">International and Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="b5fa0-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b5fa0-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="b5fa0-146">国内通话套餐</span><span class="sxs-lookup"><span data-stu-id="b5fa0-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="b5fa0-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b5fa0-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="b5fa0-148">通信点数</span><span class="sxs-lookup"><span data-stu-id="b5fa0-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="b5fa0-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b5fa0-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b5fa0-150">音频会议：关于分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="b5fa0-150">PSTN conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="b5fa0-151">分配音频会议许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="b5fa0-151">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="b5fa0-152">你**第三方音频会议提供商**：如果有人已设置为使用第三方音频会议提供商，为他们分配**音频会议**许可证时，他们将改为使用 Microsoft 为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-152">**Third-party conferencing provider**: If someone is already set up to use a third-party dial-in conferencing provider, when you assign them a **Skype for Business PSTN Conferencing** license, they will be changed to use Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="b5fa0-153">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="b5fa0-154">后续步骤：分配**音频会议**许可证后，需要分配音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-154">Next steps: After you assign PSTN conferencing licenses, you need to assign a dial-in conferencing provider.</span></span> <span data-ttu-id="b5fa0-155">请参阅 [将 Microsoft 指定为音频会议提供商]。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="b5fa0-156">如何将音频会议许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="b5fa0-156">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="b5fa0-p111">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="b5fa0-159">如何批量分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="b5fa0-159">How to assign PSTN conferencing licenses in bulk</span></span>

1. <span data-ttu-id="b5fa0-160">下载并安装[适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="b5fa0-p112">下载并安装 **Windows Azure Active Directory 模块。** 请参阅[使用 Windows PowerShell 管理 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)，以了解下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="b5fa0-163">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="b5fa0-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="b5fa0-164">[!注释] 此脚本中许可证名称或产品名称以斜体字列出。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="b5fa0-165">请参阅[用于脚本的电话拨入式会议产品名称或 SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)，查看所有产品名称。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="b5fa0-166">此示例分配了一个企业版 E3 许可证以及一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-166">This example assigns an Enterprise E3 license along with a PSTN Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b5fa0-167">用于脚本的音频会议产品名称或 SKU</span><span class="sxs-lookup"><span data-stu-id="b5fa0-167">Dial-in conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="b5fa0-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="b5fa0-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="b5fa0-169">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-169">**Product name**</span></span>|<span data-ttu-id="b5fa0-170">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="b5fa0-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5fa0-171">音频会议</span><span class="sxs-lookup"><span data-stu-id="b5fa0-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="b5fa0-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b5fa0-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="b5fa0-173">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="b5fa0-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b5fa0-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b5fa0-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b5fa0-175">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="b5fa0-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b5fa0-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b5fa0-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b5fa0-177">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="b5fa0-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b5fa0-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b5fa0-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b5fa0-179">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="b5fa0-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b5fa0-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b5fa0-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="b5fa0-181">企业 E5 （带音频会议）</span><span class="sxs-lookup"><span data-stu-id="b5fa0-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b5fa0-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b5fa0-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="b5fa0-183">通信点数</span><span class="sxs-lookup"><span data-stu-id="b5fa0-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="b5fa0-184">分配通信点数式许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="b5fa0-184">What you need to know before assigning PSTN Consumption licenses</span></span>

- <span data-ttu-id="b5fa0-185">**企业版 E5 客户**：即使你的用户分配了企业版 E5 许可证，但仍建议你为其分配**通信点数**许可证。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Skype for Business PSTN Consumption** licenses.</span></span>
    
- <span data-ttu-id="b5fa0-186">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b5fa0-187">有关分步设置说明，请参阅[设置呼叫计划](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-187">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="b5fa0-188">如何向一个用户分配通信点数许可证</span><span class="sxs-lookup"><span data-stu-id="b5fa0-188">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="b5fa0-p115">步骤与分配 Office 365 许可证相同。请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="b5fa0-191">如何批量分配通信点数许可证</span><span class="sxs-lookup"><span data-stu-id="b5fa0-191">How to assign PSTN conferencing licenses in bulk</span></span>

<span data-ttu-id="b5fa0-192">查看用于分配**音频会议**许可证的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-192">Take a look at the sample script for assigning PSTN Conferencing licenses.</span></span> <span data-ttu-id="b5fa0-193">以分配**通信点数**许可证的信息进行更新。</span><span class="sxs-lookup"><span data-stu-id="b5fa0-193">Update it with the info for assigning PSTN Consumption licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5fa0-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="b5fa0-194">Related topics</span></span>
  
[<span data-ttu-id="b5fa0-195">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="b5fa0-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="b5fa0-196">存入资金和管理通信点数</span><span class="sxs-lookup"><span data-stu-id="b5fa0-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
