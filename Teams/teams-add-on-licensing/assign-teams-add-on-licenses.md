---
title: 向用户分配团队附加许可证
author: LanaChin
ms.author: v-lanac
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
description: 了解如何向用户分配 "音频会议"、"电话系统" 和 "通话计划" 等功能的团队加载项许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868579"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="d9f42-103">向用户分配团队附加许可证</span><span class="sxs-lookup"><span data-stu-id="d9f42-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="d9f42-104">加载项许可证是特定团队功能（如音频会议、电话系统和通话计划）的许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="d9f42-105">本文介绍如何将加载项许可证分配给单个用户以及批量用户的大型用户组。</span><span class="sxs-lookup"><span data-stu-id="d9f42-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f42-106">请参阅适用于使用加载项许可证的团队功能的[团队加载项许可](microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="d9f42-107">你还可以找到有关需要购买哪些许可证以及如何购买许可证的信息（取决于你的计划），以便用户可以获得音频会议、免费电话号码等功能，以及呼叫组织外部电话号码的功能。</span><span class="sxs-lookup"><span data-stu-id="d9f42-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="d9f42-108">确定所需的用户功能后，为他们分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="d9f42-109">你可以使用 Microsoft 365 管理中心或 PowerShell 将许可证分配给你的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="d9f42-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="d9f42-110">您必须是全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="d9f42-111">在分配电话系统、呼叫计划和通讯信用许可证之前需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="d9f42-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="d9f42-112">开始之前，请查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="d9f42-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="d9f42-113">如果您使用的是混合用户的本地公共交换电话网络（PSTN）连接，则只需分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="d9f42-114">不要分配呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="d9f42-115">由于 Microsoft 365 和 Microsoft 团队之间的延迟，在分配许可证后，可能需要长达24小时才能向用户分配呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="d9f42-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="d9f42-116">如果在24小时后未向用户分配呼叫计划，[请联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="d9f42-117">如果尚未购买正确数量的许可证，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d9f42-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="d9f42-118">如果您需要购买更多通话计划许可证，请选择购买更多电话的选项。</span><span class="sxs-lookup"><span data-stu-id="d9f42-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="d9f42-119">即使你的用户已分配有企业版 E5 许可证，你仍然需要将[信用点数](../what-are-communications-credits.md)许可证分配给他们，前提是他们需要从 PSTN 发出或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="d9f42-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="d9f42-120">向用户分配呼叫计划或通讯信用许可证后，您需要为您的组织获取电话号码，然后将这些号码分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d9f42-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="d9f42-121">有关分步说明，请参阅[设置呼叫计划](../set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d9f42-122">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="d9f42-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d9f42-123">使用 Microsoft 365 管理中心将许可证分配给单个用户或一次一组小型用户。</span><span class="sxs-lookup"><span data-stu-id="d9f42-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="d9f42-124">你可以在 "**许可证**" 页面（一次最多20个用户）或 "**活动用户**" 页面分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="d9f42-125">你选择的方法取决于你是要为特定用户管理产品许可证还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d9f42-126">有关分步说明，请参阅[向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="d9f42-127">如果需要为大量用户（如成百上千用户）分配许可证，请[在 Azure Active Directory （AZURE AD）中使用 Powershell 或基于组的许可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="d9f42-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9f42-128">Using PowerShell</span></span>

<span data-ttu-id="d9f42-129">使用 PowerShell 批量向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d9f42-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="d9f42-130">若要了解详细信息，请参阅[使用 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="d9f42-131">示例脚本</span><span class="sxs-lookup"><span data-stu-id="d9f42-131">Example script</span></span>

<span data-ttu-id="d9f42-132">下面是如何使用脚本向用户分配许可证的示例。</span><span class="sxs-lookup"><span data-stu-id="d9f42-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="d9f42-133">[为 IT 专业人士 RTW 安装64位版本的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/p/?LinkId=286152)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="d9f42-134">安装适用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块：</span><span class="sxs-lookup"><span data-stu-id="d9f42-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="d9f42-135">打开提升权限的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="d9f42-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="d9f42-136">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d9f42-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="d9f42-137">如果系统提示您安装 NuGet 提供程序，请键入 " **Y**"，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d9f42-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="d9f42-138">如果系统提示您从 PSGallery 安装模块，请键入**Y**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d9f42-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="d9f42-139">在 Windows PowerShell 命令提示符处，运行以下脚本以向你的用户分配许可证，其中 \<CompanyName:License> 是你的组织名称和要分配的许可证的标识符。</span><span class="sxs-lookup"><span data-stu-id="d9f42-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="d9f42-140">例如，litwareinc： MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="d9f42-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="d9f42-141">标识符与许可证的友好名称不同。</span><span class="sxs-lookup"><span data-stu-id="d9f42-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="d9f42-142">例如，音频会议的标识符是 MCOMEETADV。</span><span class="sxs-lookup"><span data-stu-id="d9f42-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="d9f42-143">若要了解详细信息，请参阅[产品名称和 SKU 标识符以获取许可](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="d9f42-144">例如，要分配 Microsoft 365 企业版1和音频会议许可证，请在脚本中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d9f42-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="d9f42-145">若要分配 Microsoft Business Voice （无需通话计划）许可证，请在脚本中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="d9f42-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="d9f42-146">用于授权的产品名称和 SKU 标识符</span><span class="sxs-lookup"><span data-stu-id="d9f42-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="d9f42-147">下面是在使用 PowerShell 管理团队中的许可证时，可用作参考的产品名称及其相应 SKU 部件名称的部分列表。</span><span class="sxs-lookup"><span data-stu-id="d9f42-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="d9f42-148">若要了解详细信息，请参阅[通过 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[产品名称和服务计划标识符以获得许可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)和[教育 SKU 参考](../sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f42-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="d9f42-149">产品名称</span><span class="sxs-lookup"><span data-stu-id="d9f42-149">Product name</span></span>| <span data-ttu-id="d9f42-150">SKU 部件名称</span><span class="sxs-lookup"><span data-stu-id="d9f42-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d9f42-151">Microsoft 企业版 E5 （带电话系统）</span><span class="sxs-lookup"><span data-stu-id="d9f42-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="d9f42-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d9f42-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d9f42-153">Microsoft 企业版 E5 （不带音频会议）</span><span class="sxs-lookup"><span data-stu-id="d9f42-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="d9f42-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="d9f42-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="d9f42-155">Microsoft 企业版 E5 （带音频会议）</span><span class="sxs-lookup"><span data-stu-id="d9f42-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="d9f42-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d9f42-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d9f42-157">Microsoft 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="d9f42-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="d9f42-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d9f42-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="d9f42-159">Microsoft 企业版 E1</span><span class="sxs-lookup"><span data-stu-id="d9f42-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="d9f42-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d9f42-160">STANDARDPACK</span></span> |
| <span data-ttu-id="d9f42-161">Microsoft 365 商业基础版</span><span class="sxs-lookup"><span data-stu-id="d9f42-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="d9f42-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="d9f42-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="d9f42-163">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="d9f42-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="d9f42-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="d9f42-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="d9f42-165">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="d9f42-165">Microsoft 365 Business</span></span> | <span data-ttu-id="d9f42-166">SPB</span><span class="sxs-lookup"><span data-stu-id="d9f42-166">SPB</span></span>|
| <span data-ttu-id="d9f42-167">Microsoft 商业语音（加拿大）</span><span class="sxs-lookup"><span data-stu-id="d9f42-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="d9f42-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="d9f42-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="d9f42-169">Microsoft 商业语音（英国）</span><span class="sxs-lookup"><span data-stu-id="d9f42-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="d9f42-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="d9f42-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="d9f42-171">Microsoft 商业语音（美国）</span><span class="sxs-lookup"><span data-stu-id="d9f42-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="d9f42-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="d9f42-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="d9f42-173">Microsoft 商业语音（无需通话计划）</span><span class="sxs-lookup"><span data-stu-id="d9f42-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="d9f42-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="d9f42-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="d9f42-175">适用于美国的 Microsoft Business Voice （无通话计划）</span><span class="sxs-lookup"><span data-stu-id="d9f42-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="d9f42-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="d9f42-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="d9f42-177">音频会议</span><span class="sxs-lookup"><span data-stu-id="d9f42-177">Audio Conferencing</span></span> | <span data-ttu-id="d9f42-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="d9f42-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="d9f42-179">每分钟支付的音频会议（即付即用）</span><span class="sxs-lookup"><span data-stu-id="d9f42-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="d9f42-180">*需要设置和启用通信信用点数。*</span><span class="sxs-lookup"><span data-stu-id="d9f42-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="d9f42-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="d9f42-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="d9f42-182">电话系统</span><span class="sxs-lookup"><span data-stu-id="d9f42-182">Phone System</span></span> | <span data-ttu-id="d9f42-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="d9f42-183">MCOEV</span></span> |
| <span data-ttu-id="d9f42-184">国内和国际通话计划</span><span class="sxs-lookup"><span data-stu-id="d9f42-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="d9f42-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="d9f42-185">MCOPSTN2</span></span> |
| <span data-ttu-id="d9f42-186">国内呼叫计划（每个用户每月每月3000分钟，对于欧盟国家/地区，每个用户每月1200分钟）</span><span class="sxs-lookup"><span data-stu-id="d9f42-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="d9f42-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="d9f42-187">MCOPSTN1</span></span> |
| <span data-ttu-id="d9f42-188">国内呼叫计划（每个国家/地区每个用户/月120分钟）</span><span class="sxs-lookup"><span data-stu-id="d9f42-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d9f42-189">*此计划在美国不可用。*</span><span class="sxs-lookup"><span data-stu-id="d9f42-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="d9f42-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="d9f42-190">MCOPSTN5</span></span> |
| <span data-ttu-id="d9f42-191">国内呼叫计划（每个国家/地区每个用户/月240分钟）</span><span class="sxs-lookup"><span data-stu-id="d9f42-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d9f42-192">*此计划在美国不可用。*</span><span class="sxs-lookup"><span data-stu-id="d9f42-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="d9f42-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="d9f42-193">MCOPSTN6</span></span> |
| <span data-ttu-id="d9f42-194">通信点数</span><span class="sxs-lookup"><span data-stu-id="d9f42-194">Communications Credits</span></span> | <span data-ttu-id="d9f42-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="d9f42-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d9f42-196">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9f42-196">Related topics</span></span>

- [<span data-ttu-id="d9f42-197">Teams 附加许可</span><span class="sxs-lookup"><span data-stu-id="d9f42-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d9f42-198">管理用户对 Teams 的访问管理</span><span class="sxs-lookup"><span data-stu-id="d9f42-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="d9f42-199">通过 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="d9f42-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d9f42-200">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="d9f42-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d9f42-201">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="d9f42-201">Education SKU reference</span></span>](../sku-reference-edu.md)