---
title: 管理对 Microsoft Teams 的用户访问
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何通过向组织中的用户分配或删除 Teams 许可证来管理对 Teams 的用户访问。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637724"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="4d5f9-103">管理对 Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="4d5f9-103">Manage user access to Teams</span></span>

<span data-ttu-id="4d5f9-104">你可通过分配或删除 Microsoft Teams 产品许可证，在用户级别管理对 Teams 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="4d5f9-105">除了匿名加入 Teams 会议外，组织中的每个用户都必须拥有 Teams 许可证才能使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="4d5f9-106">你可以在创建新用户帐户时为新用户分配 Teams 许可证，也可以为已有帐户的用户分配 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="4d5f9-107">默认情况下，向用户分配许可计划（例如 Microsoft 365 企业版 E3 或 Microsoft 365 商业高级版）时，将自动分配 Teams 许可证，并且将为该用户启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="4d5f9-108">你可随时通过删除或分配许可证来为用户禁用或启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="4d5f9-109">使用从 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams 管理中心</a>管理的消息传递策略来控制 Teams 中的用户可以使用哪些聊天和频道消息传递功能。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="4d5f9-110">可以使用默认策略，或者为组织中的人员创建一个或多个自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="4d5f9-111">若要了解更多详细信息，请参阅[在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="4d5f9-112">你可在 Microsoft 365 管理中心或使用 PowerShell 来管理 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="4d5f9-113">你必须成为全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="4d5f9-114">建议为所有用户启用 Teams，以便可以有组织地为项目和其他动态计划建立团队。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="4d5f9-115">即使你只是在进行试点，为所有用户启用 Teams 也仍然可能很有用，但这只针对试点用户组的通信。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="4d5f9-116">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="4d5f9-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="4d5f9-117">Teams 用户级别许可证是直接通过 Microsoft 365 管理中心用户管理界面管理的。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="4d5f9-118">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4d5f9-119">管理员必须拥有全局管理员或用户管理管理员权限，才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="4d5f9-120">使用 Microsoft 365 管理中心一次管理单个用户或小部分用户的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="4d5f9-121">你可以在 **“许可证”** 页面（同时最多支持 20 个用户）或 **“活动用户”** 页面上管理 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="4d5f9-122">选择的方法取决于你想要管理特定用户的产品许可证还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="4d5f9-123">如果你需要为大量用户（如成百上千个用户）管理 Teams 许可证，请[使用 PowerShell ](#using-powershell) 或使用[在 Azure Active Directory (Azure AD) 中基于组的许可计划](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="4d5f9-124">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-124">Assign a Teams license</span></span>

<span data-ttu-id="4d5f9-125">两者步骤有所不同，具体取决于你是使用 **“许可证”** 页面还是 **“活动用户”** 页面。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="4d5f9-126">有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![已为用户启用 Teams 许可证的屏幕截图](media/assign-teams-licenses-1.png)    | ![已为用户启用 Teams 许可证的屏幕截图](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="4d5f9-129">删除 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-129">Remove a Teams license</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d5f9-130">禁用 Teams SKU 需要大约 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-130">It takes about 24 hours for disabling a Teams SKU to take effect.</span></span>

<span data-ttu-id="4d5f9-131">从用户删除 Teams 许可证时，将针对该用户禁用 Teams，然后他们将不会再在应用启动器或主页中看到 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-131">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="4d5f9-132">有关详细步骤，请参阅[取消分配用户许可证](/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-132">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![已为用户禁用 Teams 许可证的屏幕截图](media/remove-teams-licenses-1.png)    | ![已为用户禁用 Teams 许可证的屏幕截图](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="4d5f9-135">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d5f9-135">Using PowerShell</span></span>

<span data-ttu-id="4d5f9-136">使用 PowerShell 批量管理用户的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-136">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="4d5f9-137">你可以通过 PowerShell 来启用和禁用 Teams，方法与启用和禁用任何其他服务计划许可证相同。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-137">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="4d5f9-138">你需要 Teams 服务计划的标识符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d5f9-138">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="4d5f9-139">Microsoft Teams：TEAMS1</span><span class="sxs-lookup"><span data-stu-id="4d5f9-139">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="4d5f9-140">适用于 GCC 的 Microsoft Teams：TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="4d5f9-140">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="4d5f9-141">适用于 DOD 的 Microsoft Teams：TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="4d5f9-141">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="4d5f9-142">批量分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-142">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="4d5f9-143">有关详细步骤，请参阅[使用 PowerShell 向用户帐户分配许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-143">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="4d5f9-144">批量删除 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-144">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="4d5f9-145">有关详细步骤，请参阅[使用 PowerShell 禁止访问服务](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 和 [在分配用户许可证时禁止访问服务](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-145">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="4d5f9-146">示例</span><span class="sxs-lookup"><span data-stu-id="4d5f9-146">Example</span></span> 

<span data-ttu-id="4d5f9-147">以下示例演示了如何使用 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlet 来为具有特定许可计划的用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-147">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="4d5f9-148">例如，请按照以下步骤操作，先为具有特定许可计划的所有用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-148">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="4d5f9-149">然后为应有权访问 Teams 的每位单独用户启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-149">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d5f9-150">[New-MsolLicenseOption](/powershell/module/msonline/new-msollicenseoptions) cmdlet 将启用先前禁用的所有服务，除非在自定义脚本中显式标识。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-150">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="4d5f9-151">例如，如果希望在禁用 Teams 的同时禁用 Exchange 和 Sway，则需要在脚本中包括这个，否则将同时为已标识的用户启用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-151">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="4d5f9-152">运行以下命令，显示组织中所有可用的许可计划。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-152">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="4d5f9-153">有关详细信息，请参阅[使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-153">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="4d5f9-154">运行以下命令，其中 \<CompanyName:License> 是组织名称和在前一步中为许可计划所检索的标识符。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-154">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="4d5f9-155">例如，ContosoSchool:ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-155">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="4d5f9-156">运行以下命令，对拥有许可计划有效许可证的所有用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="4d5f9-156">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="4d5f9-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d5f9-157">Related topics</span></span>

- [<span data-ttu-id="4d5f9-158">Teams 附加许可许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="4d5f9-159">分配 Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="4d5f9-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="4d5f9-160">使用 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="4d5f9-160">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="4d5f9-161">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="4d5f9-161">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="4d5f9-162">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="4d5f9-162">Education SKU reference</span></span>](sku-reference-edu.md)
