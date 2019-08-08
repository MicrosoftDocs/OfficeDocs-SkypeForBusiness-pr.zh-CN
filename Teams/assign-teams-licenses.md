---
title: 分配 Teams 许可证
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: 了解如何为音频会议、电话系统和通话计划等功能分配许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d51e2cf8a563c5094da923949c8e736aceeb864
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241879"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="b3f3f-103">分配 Microsoft 团队许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="b3f3f-104">你可以为用户分配许可证, 例如音频会议、电话系统和通话计划等功能。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="b3f3f-105">本文介绍如何批量添加这些许可证以及针对单个用户添加这些许可证。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b3f3f-106">有关需要购买哪些许可证以及如何购买这些许可证的信息, 请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md), 具体取决于 Office 365 计划, 让用户获得音频会议、免费电话号码以及拨打企业外部电话号码的能力。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b3f3f-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="b3f3f-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b3f3f-108">下面是在分配音频会议、电话系统和通话计划许可证之前需要了解的内容。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="b3f3f-109">**使用的是面向混合用户的内部部署 PSTN 连接？**</span><span class="sxs-lookup"><span data-stu-id="b3f3f-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="b3f3f-110">如果是这样, 您只需分配一个电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="b3f3f-111">不应分配呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="b3f3f-112">**分配许可证后的延迟**: 由于 Office 365 和 Microsoft 团队之间的延迟, 在分配许可证后, 将为用户分配呼叫计划最多可能需要24小时。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="b3f3f-113">如果24小时后未向用户分配呼叫计划, 请[联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b3f3f-114">**错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="b3f3f-115">如果需要购买更多通话计划许可证, 请选择 "**购买更多**"。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="b3f3f-116">**后续步骤**: 向用户分配呼叫计划许可证后, 你需要为你的组织获取电话号码, 然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b3f3f-117">有关分步说明, 请参阅[设置呼叫计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="b3f3f-118">为一个用户分配电话系统和呼叫计划许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="b3f3f-119">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b3f3f-120">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="b3f3f-121">批量分配电话系统和呼叫计划许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="b3f3f-122">安装 适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手 。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="b3f3f-123">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="b3f3f-123">Don't have the module installed?</span></span> <span data-ttu-id="b3f3f-124">请参阅[适用于 It 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)下载。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="b3f3f-125">安装 Windows Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="b3f3f-126">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="b3f3f-126">Don't have the module installed?</span></span> <span data-ttu-id="b3f3f-127">有关下载说明和 cmdlet 语法, 请参阅[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="b3f3f-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="b3f3f-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="b3f3f-129">本示例指定一个 企业版 E3 许可证以及电话系统和国内通话套餐许可证。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="b3f3f-130">脚本中的许可证或产品名称的名称以斜体列出 (请参阅在示例之后[使用的电话系统和通话计划产品名称或 sku](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting))。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b3f3f-131">电话系统和通话计划用于脚本的产品名称或 Sku</span><span class="sxs-lookup"><span data-stu-id="b3f3f-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="b3f3f-132">产品名称</span><span class="sxs-lookup"><span data-stu-id="b3f3f-132">Product name</span></span> | <span data-ttu-id="b3f3f-133">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="b3f3f-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="b3f3f-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="b3f3f-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="b3f3f-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b3f3f-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b3f3f-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="b3f3f-136">Enterprise E3</span></span> | <span data-ttu-id="b3f3f-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b3f3f-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="b3f3f-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="b3f3f-138">Enterprise E1</span></span> | <span data-ttu-id="b3f3f-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b3f3f-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="b3f3f-140">电话系统</span><span class="sxs-lookup"><span data-stu-id="b3f3f-140">Phone System</span></span> | <span data-ttu-id="b3f3f-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b3f3f-141">MCOEV</span></span> |
| <span data-ttu-id="b3f3f-142">国内 & 国际通话计划</span><span class="sxs-lookup"><span data-stu-id="b3f3f-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="b3f3f-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b3f3f-143">MCOPSTN2</span></span> |
| <span data-ttu-id="b3f3f-144">国内呼叫计划 (每个用户每月每月3000分钟, 对于欧盟国家/地区, 每个用户每月1200分钟)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="b3f3f-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b3f3f-145">MCOPSTN1</span></span> |
| <span data-ttu-id="b3f3f-146">国内呼叫计划 (每个国家/地区每个用户/月120分钟)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b3f3f-147">*注意: 此计划在美国不可用*。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="b3f3f-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b3f3f-148">MCOPSTN5</span></span> |
| <span data-ttu-id="b3f3f-149">国内呼叫计划 (每个国家/地区每个用户/月240分钟)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b3f3f-150">*注意: 此计划在美国不可用*。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="b3f3f-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b3f3f-151">MCOPSTN6</span></span> |
| <span data-ttu-id="b3f3f-152">通信点数</span><span class="sxs-lookup"><span data-stu-id="b3f3f-152">Communications Credits</span></span> | <span data-ttu-id="b3f3f-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b3f3f-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b3f3f-154">音频会议: 分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="b3f3f-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b3f3f-155">下面是在分配音频会议许可证之前需要了解的信息。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="b3f3f-156">**第三方音频会议提供商**: 如果某人已设置为使用第三方音频会议提供商, 则当您为他们分配音频会议许可证时, 他们将更改为使用 Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b3f3f-157">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="b3f3f-158">**后续步骤**: 分配音频会议许可证后, 你需要分配音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="b3f3f-159">请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="b3f3f-160">将音频会议许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="b3f3f-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="b3f3f-161">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b3f3f-162">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="b3f3f-163">批量分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="b3f3f-164">下载并安装[适用于 IT 专业人员的 Microsoft Online Services 登录助手 RTW](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="b3f3f-165">下载并安装 Windows Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="b3f3f-166">有关下载说明和 cmdlet 语法, 请参阅[使用 Windows PowerShell 管理 AZURE AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="b3f3f-167">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="b3f3f-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="b3f3f-168">脚本中的许可证或产品名称的名称以斜体列出。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="b3f3f-169">请参阅用于为所有产品名称[编写脚本的音频会议产品名称或 sku](#audio-conferencing-product-names-or-skus-used-for-scripting) 。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="b3f3f-170">此示例分配了一个企业版 E3 许可证和一个音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b3f3f-171">用于脚本的音频会议产品名称或 SKU</span><span class="sxs-lookup"><span data-stu-id="b3f3f-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="b3f3f-172">产品名称</span><span class="sxs-lookup"><span data-stu-id="b3f3f-172">Product name</span></span> | <span data-ttu-id="b3f3f-173">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="b3f3f-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="b3f3f-174">音频会议 (订阅)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="b3f3f-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b3f3f-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="b3f3f-176">每分钟支付的音频会议 (即付即用)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="b3f3f-177">*注意: 要求设置和启用通讯信用点数*。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="b3f3f-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="b3f3f-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="b3f3f-179">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="b3f3f-179">Enterprise E1</span></span> | <span data-ttu-id="b3f3f-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b3f3f-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="b3f3f-181">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="b3f3f-181">Enterprise E3</span></span> | <span data-ttu-id="b3f3f-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b3f3f-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="b3f3f-183">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="b3f3f-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="b3f3f-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b3f3f-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="b3f3f-185">企业版 E5 (带音频会议)</span><span class="sxs-lookup"><span data-stu-id="b3f3f-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="b3f3f-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b3f3f-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="b3f3f-187">通信点数</span><span class="sxs-lookup"><span data-stu-id="b3f3f-187">Communications Credits</span></span>

<span data-ttu-id="b3f3f-188">下面是在分配通讯信用许可证之前需要了解的信息。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="b3f3f-189">**企业版 E5 客户**: 即使你的用户已分配有企业版 e5 许可证, 我们仍然建议你为其分配通讯信用许可证。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="b3f3f-190">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b3f3f-191">有关分步说明, 请参阅[设置呼叫计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="b3f3f-192">为一个用户分配通讯信用许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="b3f3f-193">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b3f3f-194">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="b3f3f-195">批量分配通讯信用许可证</span><span class="sxs-lookup"><span data-stu-id="b3f3f-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="b3f3f-196">请查看用于分配音频会议许可证的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="b3f3f-197">用分配通讯信用许可证的信息更新它。</span><span class="sxs-lookup"><span data-stu-id="b3f3f-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3f3f-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3f3f-198">Related topics</span></span>

[<span data-ttu-id="b3f3f-199">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="b3f3f-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="b3f3f-200">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="b3f3f-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
