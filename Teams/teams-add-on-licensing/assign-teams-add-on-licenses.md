---
title: 向用户分配 Teams 附加许可证
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 了解如何为音频会议、电话系统和呼叫计划等功能的用户分配 Teams 附加许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196926"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="272f3-103">向用户分配 Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="272f3-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="272f3-104">附加许可证是特定 Teams 功能（如音频会议、电话系统和通话计划）的许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="272f3-105">本文介绍如何将附加许可证批量分配给单个用户和大型用户集。</span><span class="sxs-lookup"><span data-stu-id="272f3-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="272f3-106">有关 [随附加许可证一](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 起提供的 Teams 功能，请参阅 Teams 附加许可。</span><span class="sxs-lookup"><span data-stu-id="272f3-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="272f3-107">你还将找到有关需要购买哪些许可证以及如何购买许可证的信息 (具体取决于你的计划) ，以便用户可以获取音频会议、免费电话号码等功能，以及拨打组织外部的电话号码的功能。</span><span class="sxs-lookup"><span data-stu-id="272f3-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="272f3-108">确定要为用户提供哪些功能后，为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="272f3-109">可以使用 Microsoft 365 管理中心或 PowerShell 向组织的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="272f3-110">只有全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="272f3-111">分配电话系统、呼叫计划和通信信用额度许可证之前需了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="272f3-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="272f3-112">在开始使用之前，请查看以下要求：</span><span class="sxs-lookup"><span data-stu-id="272f3-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="272f3-113">如果为混合用户使用本地公用电话交换网 (PSTN) 连接，则只需分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="272f3-114">不要分配呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="272f3-115">由于 Microsoft 365 和 Microsoft Teams 之间的延迟，分配许可证后，最多可能需要 24 小时才能为用户分配呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="272f3-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="272f3-116">如果 24 小时后未为用户分配呼叫计划，请联系业务产品 [支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="272f3-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="272f3-117">如果尚未购买正确数量的许可证，则会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="272f3-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="272f3-118">如果需要购买更多通话套餐许可证，请选择购买更多许可证的选项。</span><span class="sxs-lookup"><span data-stu-id="272f3-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="272f3-119">即使为用户分配了企业版 E5 许可证，如果用户希望拨打或[](../what-are-communications-credits.md)接听来自 PSTN 的呼叫，你仍然需要为其分配通信信用额度许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="272f3-120">向用户分配"呼叫计划"或"通信积分"许可证后，需要获取组织的电话号码，然后将这些号码分配给用户。</span><span class="sxs-lookup"><span data-stu-id="272f3-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="272f3-121">有关分步说明，请参阅"[设置呼叫计划"。](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="272f3-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="272f3-122">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="272f3-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="272f3-123">使用 Microsoft 365 管理中心一次向单个用户或少量用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="272f3-124">在"许可证"页面上 **(许可证** ，一次最多为 20) 或 **"活动用户"** 页面。</span><span class="sxs-lookup"><span data-stu-id="272f3-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="272f3-125">选择的方法取决于是管理特定用户的产品许可证，还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="272f3-126">有关分步说明，请参阅"[向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="272f3-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="272f3-127">如果需要为大量用户（如数百或数千个用户）分配许可证，请使用 Azure Active Directory (Azure AD) 中的 [Powershell 或基于组的许可 ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="272f3-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="272f3-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="272f3-128">Using PowerShell</span></span>

<span data-ttu-id="272f3-129">使用 PowerShell 将许可证批量分配给用户。</span><span class="sxs-lookup"><span data-stu-id="272f3-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="272f3-130">若要了解有关详细信息，请参阅使用 [PowerShell 将许可证分配给用户帐户](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="272f3-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="272f3-131">示例脚本</span><span class="sxs-lookup"><span data-stu-id="272f3-131">Example script</span></span>

<span data-ttu-id="272f3-132">以下示例演示了如何使用脚本向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="272f3-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="272f3-133">安装适用于 IT 专业人员 RTW Microsoft Online Services [64 位版本的登录助手](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)。</span><span class="sxs-lookup"><span data-stu-id="272f3-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="272f3-134">安装 Microsoft Azure Active Directory 模块Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="272f3-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="272f3-135">打开提升的 Windows PowerShell 命令提示符 (以管理员Windows PowerShell运行) 。</span><span class="sxs-lookup"><span data-stu-id="272f3-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="272f3-136">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="272f3-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="272f3-137">如果系统提示安装 NuGet 提供程序，请键入 **Y，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="272f3-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="272f3-138">如果系统提示从 PSGallery 安装模块，请键入 **Y，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="272f3-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="272f3-139">在Windows PowerShell命令提示符下，运行以下脚本将许可证分配给用户，组织名称和要分配的许可证 \<CompanyName:License> 的标识符在哪里。</span><span class="sxs-lookup"><span data-stu-id="272f3-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="272f3-140">例如，litwareinc：MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="272f3-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="272f3-141">标识符不同于许可证的友好名称。</span><span class="sxs-lookup"><span data-stu-id="272f3-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="272f3-142">例如，音频会议标识符是 MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="272f3-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="272f3-143">若要了解有关详细信息，请参阅 [许可的产品名称和 SKU 标识符](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="272f3-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="272f3-144">例如，若要分配 Microsoft 365 企业版 1 和音频会议许可证，请使用脚本中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="272f3-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="272f3-145">若要在不使用呼叫 (许可证的情况下分配 Microsoft Business Voice) ，请使用脚本中的以下语法：</span><span class="sxs-lookup"><span data-stu-id="272f3-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="272f3-146">用于许可的产品名称和 SKU 标识符</span><span class="sxs-lookup"><span data-stu-id="272f3-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="272f3-147">下面是部分产品名称及其对应的 SKU 部件名称列表，使用 PowerShell 在 Teams 中管理许可证时，可以使用这些部件名称作为参考。</span><span class="sxs-lookup"><span data-stu-id="272f3-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="272f3-148">有关详细信息，请参阅使用[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)查看许可证和服务、许可[](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的产品名称和服务计划标识符，以及教育[版 SKU 参考](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="272f3-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="272f3-149">产品名称</span><span class="sxs-lookup"><span data-stu-id="272f3-149">Product name</span></span>| <span data-ttu-id="272f3-150">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="272f3-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="272f3-151">将 Microsoft 企业版 E5 (手机系统) </span><span class="sxs-lookup"><span data-stu-id="272f3-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="272f3-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="272f3-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="272f3-153">无需音频会议 (Microsoft 企业版 E5) </span><span class="sxs-lookup"><span data-stu-id="272f3-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="272f3-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="272f3-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="272f3-155">将 Microsoft 企业版 E5 (音频会议) </span><span class="sxs-lookup"><span data-stu-id="272f3-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="272f3-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="272f3-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="272f3-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="272f3-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="272f3-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="272f3-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="272f3-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="272f3-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="272f3-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="272f3-160">STANDARDPACK</span></span> |
| <span data-ttu-id="272f3-161">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="272f3-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="272f3-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="272f3-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="272f3-163">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="272f3-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="272f3-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="272f3-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="272f3-165">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="272f3-165">Microsoft 365 Business</span></span> | <span data-ttu-id="272f3-166">SPB</span><span class="sxs-lookup"><span data-stu-id="272f3-166">SPB</span></span>|
| <span data-ttu-id="272f3-167">Microsoft Business Voice (Canada) </span><span class="sxs-lookup"><span data-stu-id="272f3-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="272f3-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="272f3-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="272f3-169">Microsoft Business Voice (英国) </span><span class="sxs-lookup"><span data-stu-id="272f3-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="272f3-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="272f3-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="272f3-171">Microsoft Business Voice (美国) </span><span class="sxs-lookup"><span data-stu-id="272f3-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="272f3-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="272f3-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="272f3-173">无需呼叫 (Microsoft Business Voice) </span><span class="sxs-lookup"><span data-stu-id="272f3-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="272f3-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="272f3-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="272f3-175">Microsoft Business Voice (美国) 套餐</span><span class="sxs-lookup"><span data-stu-id="272f3-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="272f3-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="272f3-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="272f3-177">音频会议</span><span class="sxs-lookup"><span data-stu-id="272f3-177">Audio Conferencing</span></span> | <span data-ttu-id="272f3-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="272f3-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="272f3-179">音频会议按分钟付费 (即用即付) </span><span class="sxs-lookup"><span data-stu-id="272f3-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="272f3-180">*要求设置和启用通信信用额度。*</span><span class="sxs-lookup"><span data-stu-id="272f3-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="272f3-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="272f3-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="272f3-182">电话系统</span><span class="sxs-lookup"><span data-stu-id="272f3-182">Phone System</span></span> | <span data-ttu-id="272f3-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="272f3-183">MCOEV</span></span> |
| <span data-ttu-id="272f3-184">国内和国际呼叫计划</span><span class="sxs-lookup"><span data-stu-id="272f3-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="272f3-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="272f3-185">MCOPSTN2</span></span> |
| <span data-ttu-id="272f3-186">美国/ (/CA 的国内呼叫计划为每个用户/月 3000 分钟，欧盟/地区/地区为每个用户/月 1200) </span><span class="sxs-lookup"><span data-stu-id="272f3-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="272f3-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="272f3-187">MCOPSTN1</span></span> |
| <span data-ttu-id="272f3-188">每个用户/ (的国内呼叫计划为 120 分钟) </span><span class="sxs-lookup"><span data-stu-id="272f3-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="272f3-189">*此计划在美国不可用。*</span><span class="sxs-lookup"><span data-stu-id="272f3-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="272f3-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="272f3-190">MCOPSTN5</span></span> |
| <span data-ttu-id="272f3-191">每个用户/ (的国内呼叫计划为 240 分钟) </span><span class="sxs-lookup"><span data-stu-id="272f3-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="272f3-192">*此计划在美国不可用。*</span><span class="sxs-lookup"><span data-stu-id="272f3-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="272f3-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="272f3-193">MCOPSTN6</span></span> |
| <span data-ttu-id="272f3-194">通信点数</span><span class="sxs-lookup"><span data-stu-id="272f3-194">Communications Credits</span></span> | <span data-ttu-id="272f3-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="272f3-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="272f3-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="272f3-196">Related topics</span></span>

- [<span data-ttu-id="272f3-197">Teams 附加许可</span><span class="sxs-lookup"><span data-stu-id="272f3-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="272f3-198">管理用户对 Teams 的访问管理</span><span class="sxs-lookup"><span data-stu-id="272f3-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="272f3-199">使用 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="272f3-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="272f3-200">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="272f3-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="272f3-201">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="272f3-201">Education SKU reference</span></span>](../sku-reference-edu.md)