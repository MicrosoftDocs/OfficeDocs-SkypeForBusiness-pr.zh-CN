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
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '了解如何为电话系统、音频会议、通话套餐和通信点数分配 Skype for Business 许可证。 '
ms.openlocfilehash: beb4fa46133aa7a09ce3d0de0a08392dbf2d2591
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106488"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="82409-103">分配 Skype for Business 许可证</span><span class="sxs-lookup"><span data-stu-id="82409-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="82409-104">本文提供了有关将许可证分配给您的用户，以用于音频会议、电话系统和通话套餐等功能的提示。</span><span class="sxs-lookup"><span data-stu-id="82409-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="82409-105">它还提供了批量分配许可证的脚本。</span><span class="sxs-lookup"><span data-stu-id="82409-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82409-106">请参阅[Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md)附加许可，了解需要购买哪些许可证以及如何购买许可证（具体取决于 Microsoft 365 或 Office 365 计划）的信息，以便用户获得音频会议、免费号码以及拨打企业外部电话号码的能力。</span><span class="sxs-lookup"><span data-stu-id="82409-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="82409-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="82409-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="82409-108">分配音频会议、电话系统和呼叫套餐许可证之前的注意事项</span><span class="sxs-lookup"><span data-stu-id="82409-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="82409-109">**使用的是面向混合用户的内部部署 PSTN 连接？**</span><span class="sxs-lookup"><span data-stu-id="82409-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="82409-110">如果是这样，则只需分配电话 **系统** 许可证。</span><span class="sxs-lookup"><span data-stu-id="82409-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="82409-111">不应 **分配** 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="82409-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="82409-112">分配许可证后的延迟：由于 Microsoft 365 或 Office 365 与 Skype for Business Online 之间的延迟，在分配许可证后，最多可能需要 24 小时才能为用户分配呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="82409-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="82409-113">如果 24 小时后未为用户分配呼叫计划，请联系业务产品 [支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="82409-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="82409-114">**错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="82409-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="82409-115">如果需要购买更多通话套餐许可证，请选择"**购买更多"。**</span><span class="sxs-lookup"><span data-stu-id="82409-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="82409-116">**下一** 步：将呼叫计划许可证分配给用户后，需要获取组织的电话号码，然后将这些号码分配给组织中人员。</span><span class="sxs-lookup"><span data-stu-id="82409-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="82409-117">有关分步说明，请参阅 [设置呼叫计划](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="82409-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="82409-118">如何向一个用户分配电话系统和呼叫计划许可证</span><span class="sxs-lookup"><span data-stu-id="82409-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="82409-119">这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="82409-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="82409-120">请参阅 [分配或删除 Microsoft 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="82409-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="82409-121">如何批量分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="82409-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="82409-122">安装 **适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手** 。</span><span class="sxs-lookup"><span data-stu-id="82409-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="82409-123">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="82409-123">Don't have the module installed?</span></span> <span data-ttu-id="82409-124">请参阅 [Microsoft Online Services Sign-In RTW 专业助手](https://go.microsoft.com/fwlink/?LinkId=625123) 下载它。</span><span class="sxs-lookup"><span data-stu-id="82409-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="82409-125">安装 **Windows Azure Active Directory 模块。**</span><span class="sxs-lookup"><span data-stu-id="82409-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="82409-126">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="82409-126">Don't have the module installed?</span></span> <span data-ttu-id="82409-127">有关下载说明和 cmdlet [语法，请参阅Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) 管理 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="82409-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="82409-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="82409-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="82409-129">本示例指定一个 **企业版 E3 许可证** 以及 **电话系统** 和 **国内通话套餐** 许可证。</span><span class="sxs-lookup"><span data-stu-id="82409-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="82409-130">脚本中许可证或产品名称的名称以斜体文本列出 (请参阅示例名称之后用于脚本的电话系统和呼叫计划产品名称) 。</span><span class="sxs-lookup"><span data-stu-id="82409-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="82409-131">用于脚本的电话系统和呼叫计划产品名称或 SKUS</span><span class="sxs-lookup"><span data-stu-id="82409-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="82409-132">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="82409-132">**Product name**</span></span>|<span data-ttu-id="82409-133">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="82409-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82409-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="82409-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="82409-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="82409-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="82409-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="82409-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="82409-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="82409-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="82409-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="82409-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="82409-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="82409-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="82409-140">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="82409-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="82409-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="82409-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="82409-142">电话系统</span><span class="sxs-lookup"><span data-stu-id="82409-142">Phone System</span></span>  <br/> |<span data-ttu-id="82409-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="82409-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="82409-144">国际通话套餐</span><span class="sxs-lookup"><span data-stu-id="82409-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="82409-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="82409-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="82409-146">国内呼叫计划 (美国 3000 分钟/欧盟 1200 分钟) </span><span class="sxs-lookup"><span data-stu-id="82409-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="82409-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="82409-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="82409-148">国内呼叫套餐 (120 分钟通话套餐) </span><span class="sxs-lookup"><span data-stu-id="82409-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="82409-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="82409-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="82409-150">国内呼叫套餐 (240 分钟通话套餐) </span><span class="sxs-lookup"><span data-stu-id="82409-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="82409-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="82409-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="82409-152">通信点数</span><span class="sxs-lookup"><span data-stu-id="82409-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="82409-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="82409-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="82409-154">音频会议：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="82409-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="82409-155">分配音频会议许可证之前你需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="82409-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="82409-156">第三方音频会议提供商：如果某人已设置为使用第三方音频会议提供商，当你为其分配音频会议许可证时，他们将更改为使用Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="82409-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="82409-157">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="82409-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="82409-158">接下来的步骤：分配音频会议 **许可证** 后，你需要分配音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="82409-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="82409-159">请参阅 [将 Microsoft 指定为音频会议提供商]。</span><span class="sxs-lookup"><span data-stu-id="82409-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="82409-160">如何向一个用户分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="82409-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="82409-161">这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="82409-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="82409-162">请参阅 [分配或删除 Microsoft 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="82409-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="82409-163">如何批量分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="82409-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="82409-164">下载并Microsoft Online Services Sign-In [IT 专业人员 RTW 的助手](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="82409-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="82409-p112">下载并安装 **Windows Azure Active Directory 模块。** 请参阅 [使用 Windows PowerShell 管理 Azure AD](/previous-versions/azure/jj151815(v=azure.100))，以了解下载说明和 cmdlet 语法。</span><span class="sxs-lookup"><span data-stu-id="82409-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="82409-167">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="82409-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="82409-168">[!注释] 此脚本中许可证名称或产品名称以斜体字列出。</span><span class="sxs-lookup"><span data-stu-id="82409-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="82409-169">有关 [所有产品名称，请参阅音频会议产品名称或用于](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 脚本的 SKUS。</span><span class="sxs-lookup"><span data-stu-id="82409-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="82409-170">此示例分配企业 E3 许可证以及音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="82409-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="82409-171">音频会议产品名称或用于脚本的 SKUS</span><span class="sxs-lookup"><span data-stu-id="82409-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="82409-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="82409-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="82409-173">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="82409-173">**Product name**</span></span>|<span data-ttu-id="82409-174">**SKU 部件名称**</span><span class="sxs-lookup"><span data-stu-id="82409-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82409-175">音频会议</span><span class="sxs-lookup"><span data-stu-id="82409-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="82409-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="82409-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="82409-177">Skype for Business Online 独立计划 2</span><span class="sxs-lookup"><span data-stu-id="82409-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="82409-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="82409-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="82409-179">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="82409-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="82409-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="82409-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="82409-181">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="82409-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="82409-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="82409-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="82409-183">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="82409-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="82409-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="82409-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="82409-185">使用音频 (的企业 E5) </span><span class="sxs-lookup"><span data-stu-id="82409-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="82409-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="82409-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="82409-187">通信点数</span><span class="sxs-lookup"><span data-stu-id="82409-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="82409-188">分配通信信用额度许可证之前需了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="82409-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="82409-189">**企业版 E5** 客户：即使为用户分配了企业版 E5 许可证，仍建议为其分配通信 **信用额度** 许可证。</span><span class="sxs-lookup"><span data-stu-id="82409-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="82409-190">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="82409-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="82409-191">有关分步说明，请参阅 [设置呼叫计划](/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="82409-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="82409-192">如何向一个用户分配通信信用额度许可证</span><span class="sxs-lookup"><span data-stu-id="82409-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="82409-193">这些步骤与分配 Microsoft 365 或 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="82409-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="82409-194">请参阅 [分配或删除 Microsoft 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="82409-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="82409-195">如何批量分配通信信用额度许可证</span><span class="sxs-lookup"><span data-stu-id="82409-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="82409-196">查看分配音频会议许可证 **的示例** 脚本。</span><span class="sxs-lookup"><span data-stu-id="82409-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="82409-197">使用分配通信信用额度许可证 **的信息更新** 它。</span><span class="sxs-lookup"><span data-stu-id="82409-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="82409-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="82409-198">Related topics</span></span>
  
[<span data-ttu-id="82409-199">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="82409-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="82409-200">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="82409-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
