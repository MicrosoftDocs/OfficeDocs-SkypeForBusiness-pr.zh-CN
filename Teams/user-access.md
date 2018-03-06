---
title: "管理对 Microsoft Teams 的用户访问"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "了解如何基于每个用户启用或禁用用户级别访问。"
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd2c7490c837e34e242feed295e63a7ebac11dc6
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="bc169-103">管理对 Microsoft Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="bc169-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="bc169-104">在用户级别上，可以通过分配或删除 Microsoft Teams 产品许可证来基于每个用户启用或禁用对 Microsoft Teams 的访问。</span><span class="sxs-lookup"><span data-stu-id="bc169-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="bc169-105">当前，除了许可外，没有用于按单个用户级别开启或关闭 Microsoft Teams 或一部分 Microsoft Teams 功能的策略选项。</span><span class="sxs-lookup"><span data-stu-id="bc169-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>



> [!NOTE]
><span data-ttu-id="bc169-106">Microsoft 建议为公司中的所有用户启用 Microsoft Teams，以便可以根据项目和其他动态计划自然地组成团队。</span><span class="sxs-lookup"><span data-stu-id="bc169-106">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="bc169-107">即使你只是决定试点，为所有用户启用 Microsoft Teams 可能仍然很有用，但只有用户试点组可以使用它进行通信。</span><span class="sxs-lookup"><span data-stu-id="bc169-107">Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

<span data-ttu-id="bc169-108">Microsoft Teams 用户级别许可证直接通过 Office 365 管理中心用户管理界面进行管理。</span><span class="sxs-lookup"><span data-stu-id="bc169-108">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="bc169-109">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-109">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="bc169-110">管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-110">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="bc169-111">为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bc169-111">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="bc169-112">管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-112">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="bc169-114">可以随时禁用 Microsoft Teams 用户许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-114">A Microsoft Teams user license can be disabled at any time.</span></span> <span data-ttu-id="bc169-115">禁用许可证后，将阻止用户访问 Microsoft Teams，用户将无法再在 Office 365 应用启动程序和主页上看到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bc169-115">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="bc169-117">除了使用 Office 365 管理中心外，Office 365 管理员还可以使用 Office 365 PowerShell 分配和删除许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-117">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses.</span></span> <span data-ttu-id="bc169-118">要为用户分配许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bc169-118">To assign a license to a user, use the following syntax:</span></span>

```
Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"
```

<span data-ttu-id="bc169-119">以下示例将 litwareinc:ENTERPRISEPACK（Office 365 企业版 E3）许可计划中的许可证分配给未授权用户 belindan@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="bc169-119">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

```
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="bc169-120">有关更多详细信息和示例，请参阅[使用 Office 365 PowerShell 为用户帐户分配许可证](https://go.microsoft.com/fwlink/?linkid=855755)。</span><span class="sxs-lookup"><span data-stu-id="bc169-120">For more details and examples, see [Assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="bc169-121">要从现有用户帐户删除许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bc169-121">To remove licenses from an existing user account, use the following syntax:</span></span>

```
Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"
```

<span data-ttu-id="bc169-122">以下示例从用户帐户 BelindaN@litwareinc.com 删除 litwareinc:ENTERPRISEPACK（Office 365 企业版 E3）许可证。</span><span class="sxs-lookup"><span data-stu-id="bc169-122">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

```
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="bc169-123">有关更多详细信息和示例，请参阅[使用 Office 365 PowerShell 从用户帐户删除许可证](https://go.microsoft.com/fwlink/?linkid=855756)。</span><span class="sxs-lookup"><span data-stu-id="bc169-123">For more details and examples, see [Remove licenses from user accounts with office 365 PowerShell](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="bc169-125">决策点</span><span class="sxs-lookup"><span data-stu-id="bc169-125">Decision Point</span></span>         |<ul><li><span data-ttu-id="bc169-126">贵组织在组织中上线 Microsoft Teams 的计划是什么？</span><span class="sxs-lookup"><span data-stu-id="bc169-126">What is your organization’s plan for Microsoft Teams onboarding across the organization?</span></span>  <span data-ttu-id="bc169-127">（试点或开放）</span><span class="sxs-lookup"><span data-stu-id="bc169-127">(Pilot or Open)</span></span></li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="bc169-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bc169-129">Next Steps</span></span>         |<ul><li><span data-ttu-id="bc169-130">如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</span><span class="sxs-lookup"><span data-stu-id="bc169-130">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="bc169-131">根据决定，采取相应步骤来确保仅允许的试点用户可以访问 Microsoft Teams（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="bc169-131">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="bc169-132">记录用于规定将有权（或无权）访问 Microsoft Teams 的用户的准则。</span><span class="sxs-lookup"><span data-stu-id="bc169-132">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
