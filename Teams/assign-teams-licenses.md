---
title: 分配 Teams 许可证
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: 了解如何将许可证分配等音频会议，电话系统的功能和呼叫计划。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c679a43262a5cd10756b0f5ea542f1341018b615
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461577"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="c8f66-103">将 Microsoft 团队许可证分配</span><span class="sxs-lookup"><span data-stu-id="c8f66-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="c8f66-104">您可以对等音频会议和电话系统，调用计划功能为用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c8f66-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="c8f66-105">本文说明如何添加这些许可证批量和针对个别用户。</span><span class="sxs-lookup"><span data-stu-id="c8f66-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c8f66-106">请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)有关您需要购买的许可证和如何购买，具体取决于您的 Office 365 的计划，以便用户获取音频会议和免费电话号码，能够调用您的公司外部的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c8f66-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c8f66-107">电话系统和通话套餐：分配许可证的提示和脚本</span><span class="sxs-lookup"><span data-stu-id="c8f66-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c8f66-108">下面是您需要知道分配音频会议和电话系统，调用规划许可证之前。</span><span class="sxs-lookup"><span data-stu-id="c8f66-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="c8f66-109">**使用的是面向混合用户的内部部署 PSTN 连接？**</span><span class="sxs-lookup"><span data-stu-id="c8f66-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="c8f66-110">如果是这样，您只需将电话系统许可证分配。</span><span class="sxs-lookup"><span data-stu-id="c8f66-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="c8f66-111">您不应将分配调用规划。</span><span class="sxs-lookup"><span data-stu-id="c8f66-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="c8f66-112">**延迟后分配许可证**： Office 365 与 Microsoft 团队之间的延迟，因为它可能需要多达 24 小时用户要分配调用规划后分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c8f66-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="c8f66-113">如果在 24 小时后用户未分配调用计划，请[与业务产品的管理员技术支持部门联系](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="c8f66-114">**错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c8f66-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="c8f66-115">如果您需要购买更多调用规划许可证，请选择**购买更多**。</span><span class="sxs-lookup"><span data-stu-id="c8f66-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="c8f66-116">**后续步骤**： 将调用规划许可证分配给您的用户后，您将需要获得您的组织，您的电话号码，然后将这些号码分配给您的组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="c8f66-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c8f66-117">有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="c8f66-118">将电话系统和调用规划许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="c8f66-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="c8f66-119">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="c8f66-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="c8f66-120">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="c8f66-121">分配电话系统和调用规划批量许可证</span><span class="sxs-lookup"><span data-stu-id="c8f66-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="c8f66-122">安装 适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手 。</span><span class="sxs-lookup"><span data-stu-id="c8f66-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="c8f66-123">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="c8f66-123">Don't have the module installed?</span></span> <span data-ttu-id="c8f66-124">请参阅[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以下载该。</span><span class="sxs-lookup"><span data-stu-id="c8f66-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="c8f66-125">安装 Windows Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="c8f66-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="c8f66-126">没有安装模块？</span><span class="sxs-lookup"><span data-stu-id="c8f66-126">Don't have the module installed?</span></span> <span data-ttu-id="c8f66-127">下载说明和 cmdlet 语法，请参阅[Manage 使用 Windows PowerShell 的 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="c8f66-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="c8f66-128">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="c8f66-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="c8f66-129">本示例指定一个 企业版 E3 许可证以及电话系统和国内通话套餐许可证。</span><span class="sxs-lookup"><span data-stu-id="c8f66-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="c8f66-130">斜体 （此示例之后，请参阅[电话系统和调用计划的产品名称或 Sku 用于脚本](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)，） 中列出的许可证的名称或脚本中的产品名称。</span><span class="sxs-lookup"><span data-stu-id="c8f66-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c8f66-131">电话系统和调用计划产品名称或 Sku 用于编写脚本</span><span class="sxs-lookup"><span data-stu-id="c8f66-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="c8f66-132">产品名称</span><span class="sxs-lookup"><span data-stu-id="c8f66-132">Product name</span></span> | <span data-ttu-id="c8f66-133">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="c8f66-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="c8f66-134">企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="c8f66-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="c8f66-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c8f66-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="c8f66-136">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="c8f66-136">Enterprise E3</span></span> | <span data-ttu-id="c8f66-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c8f66-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="c8f66-138">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="c8f66-138">Enterprise E1</span></span> | <span data-ttu-id="c8f66-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c8f66-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="c8f66-140">电话系统</span><span class="sxs-lookup"><span data-stu-id="c8f66-140">Phone System</span></span> | <span data-ttu-id="c8f66-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c8f66-141">MCOEV</span></span> |
| <span data-ttu-id="c8f66-142">国内 & 国际呼叫计划</span><span class="sxs-lookup"><span data-stu-id="c8f66-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="c8f66-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c8f66-143">MCOPSTN2</span></span> |
| <span data-ttu-id="c8f66-144">国内调用规划 （每用户每月美国/PR/CA，1200 分钟每用户每月欧盟国家/地区的 3000 分钟）</span><span class="sxs-lookup"><span data-stu-id="c8f66-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="c8f66-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c8f66-145">MCOPSTN1</span></span> |
| <span data-ttu-id="c8f66-146">国内调用规划 （120 分钟每用户每月的每个国家/地区）</span><span class="sxs-lookup"><span data-stu-id="c8f66-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="c8f66-147">*注意： 此计划在美国不可*。</span><span class="sxs-lookup"><span data-stu-id="c8f66-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="c8f66-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="c8f66-148">MCOPSTN5</span></span> |
| <span data-ttu-id="c8f66-149">国内调用规划 （240 分钟每用户每月的每个国家/地区）</span><span class="sxs-lookup"><span data-stu-id="c8f66-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="c8f66-150">*注意： 此计划在美国不可*。</span><span class="sxs-lookup"><span data-stu-id="c8f66-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="c8f66-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="c8f66-151">MCOPSTN6</span></span> |
| <span data-ttu-id="c8f66-152">通信点数</span><span class="sxs-lookup"><span data-stu-id="c8f66-152">Communications Credits</span></span> | <span data-ttu-id="c8f66-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c8f66-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c8f66-154">音频会议： 提示和分配许可证的脚本</span><span class="sxs-lookup"><span data-stu-id="c8f66-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c8f66-155">下面是您需要知道分配音频会议许可证之前。</span><span class="sxs-lookup"><span data-stu-id="c8f66-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="c8f66-156">**第三方音频会议提供商**： 如果某人已设置为使用第三方音频会议提供商，您将其分配的音频会议许可证时，他们将更改用于 Microsoft 为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="c8f66-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c8f66-157">你可以将他们更改回第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="c8f66-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="c8f66-158">**后续步骤**： 分配音频会议许可证后，您需要分配音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="c8f66-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="c8f66-159">请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="c8f66-160">将音频会议许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="c8f66-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="c8f66-161">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="c8f66-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="c8f66-162">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="c8f66-163">将批量音频会议许可证分配</span><span class="sxs-lookup"><span data-stu-id="c8f66-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="c8f66-164">下载并安装[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="c8f66-165">下载并安装 Windows Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="c8f66-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="c8f66-166">下载说明和 cmdlet 语法，请参阅[Manage 使用 Windows PowerShell 的 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。</span><span class="sxs-lookup"><span data-stu-id="c8f66-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="c8f66-167">在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：</span><span class="sxs-lookup"><span data-stu-id="c8f66-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="c8f66-168">斜体列出了在脚本中的产品名称或许可证的名称。</span><span class="sxs-lookup"><span data-stu-id="c8f66-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="c8f66-169">请参阅[音频会议产品名称或 SKU 用于编写脚本](#audio-conferencing-product-names-or-skus-used-for-scripting)的所有产品名称。</span><span class="sxs-lookup"><span data-stu-id="c8f66-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="c8f66-170">本示例指定一个要进行音频会议许可证以及一个企业版 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="c8f66-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c8f66-171">音频会议产品名称或 SKU 用于编写脚本</span><span class="sxs-lookup"><span data-stu-id="c8f66-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="c8f66-172">产品名称</span><span class="sxs-lookup"><span data-stu-id="c8f66-172">Product name</span></span> | <span data-ttu-id="c8f66-173">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="c8f66-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="c8f66-174">音频会议 （订阅）</span><span class="sxs-lookup"><span data-stu-id="c8f66-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="c8f66-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c8f66-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="c8f66-176">音频会议支付每分钟 （付费）</span><span class="sxs-lookup"><span data-stu-id="c8f66-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="c8f66-177">*注意： 需要 Communications 字幕式设置和启用*。</span><span class="sxs-lookup"><span data-stu-id="c8f66-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="c8f66-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="c8f66-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="c8f66-179">企业版 E1</span><span class="sxs-lookup"><span data-stu-id="c8f66-179">Enterprise E1</span></span> | <span data-ttu-id="c8f66-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c8f66-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="c8f66-181">企业版 E3</span><span class="sxs-lookup"><span data-stu-id="c8f66-181">Enterprise E3</span></span> | <span data-ttu-id="c8f66-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c8f66-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="c8f66-183">企业版 E5（无音频会议）</span><span class="sxs-lookup"><span data-stu-id="c8f66-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="c8f66-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c8f66-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="c8f66-185">企业 E5 （与音频会议）</span><span class="sxs-lookup"><span data-stu-id="c8f66-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="c8f66-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c8f66-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="c8f66-187">通信点数</span><span class="sxs-lookup"><span data-stu-id="c8f66-187">Communications Credits</span></span>

<span data-ttu-id="c8f66-188">下面是您需要知道分配 Communications 字幕式许可证之前。</span><span class="sxs-lookup"><span data-stu-id="c8f66-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="c8f66-189">**企业 E5 客户**： 即使您的用户分配了企业 E5 许可证，但仍建议您将为其分配 Communications 字幕式许可证。</span><span class="sxs-lookup"><span data-stu-id="c8f66-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="c8f66-190">**后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。</span><span class="sxs-lookup"><span data-stu-id="c8f66-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c8f66-191">有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="c8f66-192">将通信字幕式许可证分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="c8f66-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="c8f66-193">步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="c8f66-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="c8f66-194">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="c8f66-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="c8f66-195">将批量 Communications 字幕式许可证分配</span><span class="sxs-lookup"><span data-stu-id="c8f66-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="c8f66-196">请看一下分配音频会议许可证的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="c8f66-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="c8f66-197">更新其分配 Communications 字幕式许可证的信息。</span><span class="sxs-lookup"><span data-stu-id="c8f66-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8f66-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="c8f66-198">Related topics</span></span>

[<span data-ttu-id="c8f66-199">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="c8f66-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="c8f66-200">添加资金并管理通信点数</span><span class="sxs-lookup"><span data-stu-id="c8f66-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
