---
title: "管理对 Microsoft Teams 的用户访问 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何基于每个用户启用或禁用用户级别访问。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5bf8a487a7931ff91e754c1e84839b75535ca3c9
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="e5cdf-103">管理对 Microsoft Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="e5cdf-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="e5cdf-104">在用户级别上，可以通过分配或删除 Microsoft Teams 产品许可证来基于每个用户启用或禁用对 Microsoft Teams 的访问。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="e5cdf-105">当前，除了许可外，没有用于按单个用户级别开启或关闭 Microsoft Teams 或一部分 Microsoft Teams 功能的策略选项。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>



> [!NOTE]
><span data-ttu-id="e5cdf-106">Microsoft 建议为公司中的所有用户启用 Microsoft Teams，以便可以根据项目和其他动态计划自然地组成团队。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-106">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="e5cdf-107">即使你只是决定试点，为所有用户启用 Microsoft Teams 可能仍然很有用，但只有用户试点组可以使用它进行通信。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-107">Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

<span data-ttu-id="e5cdf-108">Microsoft Teams 用户级别许可证直接通过 Office 365 管理中心用户管理界面进行管理。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-108">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="e5cdf-109">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-109">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="e5cdf-110">管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-110">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="e5cdf-111">为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-111">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="e5cdf-112">管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-112">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="e5cdf-114">可以随时禁用 Microsoft Teams 用户许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-114">A Microsoft Teams user license can be disabled at any time.</span></span> <span data-ttu-id="e5cdf-115">禁用许可证后，将阻止用户访问 Microsoft Teams，用户将无法再在 Office 365 应用启动程序和主页上看到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-115">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="e5cdf-117">除了使用 Office 365 管理中心外，Office 365 管理员还可以使用 Office 365 PowerShell 分配和删除许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-117">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses.</span></span> <span data-ttu-id="e5cdf-118">要为用户分配许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e5cdf-118">To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="e5cdf-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="e5cdf-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="e5cdf-120">以下示例将 litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) 许可计划中的许可证分配给未授权用户 belindan@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="e5cdf-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="e5cdf-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="e5cdf-122">有关更多详细信息和示例，请参阅[*使用 Office 365 PowerShell 为用户帐户分配许可证*](https://go.microsoft.com/fwlink/?linkid=855755)。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="e5cdf-123">要从现有用户帐户删除许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e5cdf-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="e5cdf-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="e5cdf-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="e5cdf-125">以下示例从用户帐户 BelindaN@litwareinc.com 删除 litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) 许可证。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="e5cdf-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="e5cdf-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="e5cdf-127">有关更多详细信息和示例，请参阅[*使用 Office 365 PowerShell 从用户帐户删除许可证*](https://go.microsoft.com/fwlink/?linkid=855756)。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="e5cdf-129">决策点</span><span class="sxs-lookup"><span data-stu-id="e5cdf-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="e5cdf-130">贵组织在组织中上线 Microsoft Teams 的计划是什么？</span><span class="sxs-lookup"><span data-stu-id="e5cdf-130">What is your organization’s plan for Microsoft Teams onboarding across the organization?</span></span>  <span data-ttu-id="e5cdf-131">（试点或开放）</span><span class="sxs-lookup"><span data-stu-id="e5cdf-131">(Pilot or Open)</span></span></li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="e5cdf-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5cdf-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="e5cdf-134">如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="e5cdf-135">根据决定，采取相应步骤来确保仅允许的试点用户可以访问 Microsoft Teams（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="e5cdf-136">在下面记录用于规定将有权（无权）访问 Microsoft Teams 的用户的准则。</span><span class="sxs-lookup"><span data-stu-id="e5cdf-136">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
