---
title: 管理对 Microsoft Teams 的用户访问
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何通过向组织中的用户分配或删除团队许可证来管理用户对团队的访问权限。
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042269"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="a0db3-103">管理用户对 Teams 的访问管理</span><span class="sxs-lookup"><span data-stu-id="a0db3-103">Manage user access to Teams</span></span>

<span data-ttu-id="a0db3-104">通过分配或删除 Microsoft 团队产品许可证，可在用户级别管理对团队的访问。</span><span class="sxs-lookup"><span data-stu-id="a0db3-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="a0db3-105">组织中的每个用户都必须拥有一个团队许可证，然后他们才能使用团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="a0db3-106">当创建新用户帐户或使用现有帐户向用户分配新用户帐户时，您可以为新用户分配团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="a0db3-107">默认情况下，当向用户分配了授权计划（例如 Microsoft 365 企业版 E3 或 Microsoft 365 Business Premium）时，将自动分配团队许可证，并为团队启用用户。</span><span class="sxs-lookup"><span data-stu-id="a0db3-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="a0db3-108">你可以随时删除或分配许可证，为用户禁用或启用团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="a0db3-109">可在 Microsoft 365 管理中心或通过使用 PowerShell 管理团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-109">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="a0db3-110">您必须是全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-110">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="a0db3-111">我们建议你为所有用户启用团队，以便团队可以为项目和其他动态计划 organically。</span><span class="sxs-lookup"><span data-stu-id="a0db3-111">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="a0db3-112">即使你正在运行试验，仍可让团队为所有用户启用团队，但仅将目标与用户的试点组通信。</span><span class="sxs-lookup"><span data-stu-id="a0db3-112">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="a0db3-113">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="a0db3-113">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="a0db3-114">使用 Microsoft 365 管理中心管理单个用户或一次小型用户组的团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-114">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="a0db3-115">可以在 "**许可证**" 页面上管理团队许可证（同时适用于最多20个用户）或 "**活动用户**" 页面。</span><span class="sxs-lookup"><span data-stu-id="a0db3-115">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="a0db3-116">你选择的方法取决于你是要为特定用户管理产品许可证还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-116">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="a0db3-117">如果需要管理大量用户（如成百上千用户）的团队许可证，请[在 Azure Active Directory （AZURE AD）中](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)[使用 Powershell](#using-powershell)或基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="a0db3-117">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="a0db3-118">分配团队许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-118">Assign a Teams license</span></span>

<span data-ttu-id="a0db3-119">根据您使用的是 "**许可证**" 页面还是 "**活动用户**" 页面，这些步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="a0db3-119">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="a0db3-120">有关分步说明，请参阅[向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="a0db3-120">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![为用户启用的团队许可证的屏幕截图](media/assign-teams-licenses-1.png)    | ![为用户启用的团队许可证的屏幕截图](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="a0db3-123">删除团队许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-123">Remove a Teams license</span></span>

<span data-ttu-id="a0db3-124">从用户删除团队许可证时，将对该用户禁用团队，并且他们将不再在应用启动器或主页中看到团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-124">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="a0db3-125">有关详细步骤，请参阅[取消分配给用户的许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="a0db3-125">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![已针对用户禁用的团队许可证的屏幕截图](media/remove-teams-licenses-1.png)    | ![已针对用户禁用的团队许可证的屏幕截图](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="a0db3-128">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0db3-128">Using PowerShell</span></span>

<span data-ttu-id="a0db3-129">使用 PowerShell 批量管理用户的团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0db3-129">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="a0db3-130">通过 PowerShell 启用和禁用团队的方式与任何其他服务计划许可证的方式相同。</span><span class="sxs-lookup"><span data-stu-id="a0db3-130">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="a0db3-131">你将需要团队服务计划的标识符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0db3-131">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="a0db3-132">Microsoft 团队： TEAMS1</span><span class="sxs-lookup"><span data-stu-id="a0db3-132">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="a0db3-133">适用于 GCC 的 Microsoft 团队： TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="a0db3-133">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="a0db3-134">适用于 DoD 的 Microsoft 团队： TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="a0db3-134">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="a0db3-135">批量分配团队许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-135">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="a0db3-136">有关详细步骤，请参阅[使用 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0db3-136">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="a0db3-137">批量删除团队许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-137">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="a0db3-138">有关详细步骤，请参阅[使用 PowerShell 禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)，并[在分配用户许可证时禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="a0db3-138">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="a0db3-139">示例</span><span class="sxs-lookup"><span data-stu-id="a0db3-139">Example</span></span> 

<span data-ttu-id="a0db3-140">下面是如何使用[MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions)和[MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet 为具有特定授权计划的用户禁用团队的示例。</span><span class="sxs-lookup"><span data-stu-id="a0db3-140">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="a0db3-141">例如，请按照以下步骤操作，首先针对具有特定授权计划的所有用户禁用团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-141">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="a0db3-142">然后为应该有权访问团队的每个单独用户启用团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-142">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0db3-143">除非在自定义脚本中明确标识，否则[MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet 将启用之前已禁用的所有服务。</span><span class="sxs-lookup"><span data-stu-id="a0db3-143">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="a0db3-144">例如，如果你希望同时禁用 Exchange 和 Sway 同时禁用团队，你需要在脚本中包含此内容，或者将为你标识的用户启用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="a0db3-144">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="a0db3-145">运行以下命令以显示你的组织中的所有可用授权计划。</span><span class="sxs-lookup"><span data-stu-id="a0db3-145">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="a0db3-146">若要了解详细信息，请参阅[通过 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0db3-146">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="a0db3-147">运行以下命令，其中\<"公司名称：许可证>" 是你的组织名称，以及你在之前步骤中检索的授权计划的标识符。</span><span class="sxs-lookup"><span data-stu-id="a0db3-147">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="a0db3-148">例如，ContosoSchool： ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="a0db3-148">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="a0db3-149">运行以下命令，为具有许可计划的活动许可证的所有用户禁用团队。</span><span class="sxs-lookup"><span data-stu-id="a0db3-149">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="a0db3-150">管理组织级别的团队</span><span class="sxs-lookup"><span data-stu-id="a0db3-150">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="a0db3-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0db3-151">Related topics</span></span>

- [<span data-ttu-id="a0db3-152">团队附加设备许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-152">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="a0db3-153">分配团队附加设备许可证</span><span class="sxs-lookup"><span data-stu-id="a0db3-153">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="a0db3-154">通过 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="a0db3-154">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="a0db3-155">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="a0db3-155">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="a0db3-156">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="a0db3-156">Education SKU reference</span></span>](sku-reference-edu.md)