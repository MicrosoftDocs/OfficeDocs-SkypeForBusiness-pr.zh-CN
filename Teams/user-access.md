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
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何通过向组织中的用户分配或删除团队许可证来管理用户对团队的访问权限。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521379"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="01548-103">管理用户对 Teams 的访问管理</span><span class="sxs-lookup"><span data-stu-id="01548-103">Manage user access to Teams</span></span>

<span data-ttu-id="01548-104">通过分配或删除 Microsoft 团队产品许可证，可在用户级别管理对团队的访问。</span><span class="sxs-lookup"><span data-stu-id="01548-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="01548-105">组织中的每个用户都必须拥有一个团队许可证，然后他们才能使用团队。</span><span class="sxs-lookup"><span data-stu-id="01548-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="01548-106">当创建新用户帐户或使用现有帐户向用户分配新用户帐户时，您可以为新用户分配团队许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="01548-107">默认情况下，当 (授权计划时，将为用户分配 Microsoft 365 企业版 E3 或 Microsoft 365 Business Premium) ，将自动分配团队许可证，并为团队启用用户。</span><span class="sxs-lookup"><span data-stu-id="01548-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="01548-108">你可以随时删除或分配许可证，为用户禁用或启用团队。</span><span class="sxs-lookup"><span data-stu-id="01548-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="01548-109">使用邮件策略从 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">团队管理中心</a>进行管理，以控制团队中的用户可以使用哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="01548-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="01548-110">你可以使用默认策略或为组织中的人员创建一个或多个自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="01548-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="01548-111">若要了解详细信息，请阅读 [团队中的 "管理消息策略](messaging-policies-in-teams.md)"。</span><span class="sxs-lookup"><span data-stu-id="01548-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="01548-112">可在 Microsoft 365 管理中心或通过使用 PowerShell 管理团队许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="01548-113">您必须是全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="01548-114">我们建议你为所有用户启用团队，以便团队可以为项目和其他动态计划 organically。</span><span class="sxs-lookup"><span data-stu-id="01548-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="01548-115">即使你正在运行试验，仍可让团队为所有用户启用团队，但仅将目标与用户的试点组通信。</span><span class="sxs-lookup"><span data-stu-id="01548-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="01548-116">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="01548-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="01548-117">团队用户级许可证通过 Microsoft 365 管理中心用户管理界面直接管理。</span><span class="sxs-lookup"><span data-stu-id="01548-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="01548-118">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="01548-119">管理员必须具有全局管理员权限或用户管理管理员权限才能管理 Microsoft 团队许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="01548-120">使用 Microsoft 365 管理中心管理单个用户或一次小型用户组的团队许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="01548-121">您可以在 "许可证" 页面上管理多达20个用户的 " **许可证** " 页面 (，) 或 " **活动用户** " 页面。</span><span class="sxs-lookup"><span data-stu-id="01548-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="01548-122">你选择的方法取决于你是要为特定用户管理产品许可证还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="01548-123">如果需要管理大量用户（如成百上千用户）的团队许可证，请 [使用](#using-powershell) [azure Active Directory 中的 Powershell 或基于组的许可 (azure AD) ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="01548-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="01548-124">分配团队许可证</span><span class="sxs-lookup"><span data-stu-id="01548-124">Assign a Teams license</span></span>

<span data-ttu-id="01548-125">根据您使用的是 " **许可证** " 页面还是 " **活动用户** " 页面，这些步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="01548-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="01548-126">有关分步说明，请参阅 [向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="01548-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![为用户启用的团队许可证的屏幕截图](media/assign-teams-licenses-1.png)    | ![为用户启用的团队许可证的屏幕截图](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="01548-129">删除团队许可证</span><span class="sxs-lookup"><span data-stu-id="01548-129">Remove a Teams license</span></span>

<span data-ttu-id="01548-130">从用户删除团队许可证时，将对该用户禁用团队，并且他们将不再在应用启动器或主页中看到团队。</span><span class="sxs-lookup"><span data-stu-id="01548-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="01548-131">有关详细步骤，请参阅 [取消分配给用户的许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="01548-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![已针对用户禁用的团队许可证的屏幕截图](media/remove-teams-licenses-1.png)    | ![已针对用户禁用的团队许可证的屏幕截图](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="01548-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="01548-134">Using PowerShell</span></span>

<span data-ttu-id="01548-135">使用 PowerShell 批量管理用户的团队许可证。</span><span class="sxs-lookup"><span data-stu-id="01548-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="01548-136">通过 PowerShell 启用和禁用团队的方式与任何其他服务计划许可证的方式相同。</span><span class="sxs-lookup"><span data-stu-id="01548-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="01548-137">你将需要团队服务计划的标识符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01548-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="01548-138">Microsoft 团队： TEAMS1</span><span class="sxs-lookup"><span data-stu-id="01548-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="01548-139">适用于 GCC 的 Microsoft 团队： TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="01548-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="01548-140">适用于 DoD 的 Microsoft 团队： TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="01548-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="01548-141">批量分配团队许可证</span><span class="sxs-lookup"><span data-stu-id="01548-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="01548-142">有关详细步骤，请参阅 [使用 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="01548-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="01548-143">批量删除团队许可证</span><span class="sxs-lookup"><span data-stu-id="01548-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="01548-144">有关详细步骤，请参阅 [使用 PowerShell 禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) ，并 [在分配用户许可证时禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="01548-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="01548-145">示例</span><span class="sxs-lookup"><span data-stu-id="01548-145">Example</span></span> 

<span data-ttu-id="01548-146">下面是如何使用 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 和 [MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet 为具有特定授权计划的用户禁用团队的示例。</span><span class="sxs-lookup"><span data-stu-id="01548-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="01548-147">例如，请按照以下步骤操作，首先针对具有特定授权计划的所有用户禁用团队。</span><span class="sxs-lookup"><span data-stu-id="01548-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="01548-148">然后为应该有权访问团队的每个单独用户启用团队。</span><span class="sxs-lookup"><span data-stu-id="01548-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01548-149">除非在自定义脚本中明确标识，否则 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet 将启用之前已禁用的所有服务。</span><span class="sxs-lookup"><span data-stu-id="01548-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="01548-150">例如，如果你希望同时禁用 Exchange 和 Sway 同时禁用团队，你需要在脚本中包含此内容，或者将为你标识的用户启用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="01548-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="01548-151">运行以下命令以显示你的组织中的所有可用授权计划。</span><span class="sxs-lookup"><span data-stu-id="01548-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="01548-152">若要了解详细信息，请参阅 [通过 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="01548-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="01548-153">运行以下命令，其中 \<CompanyName:License> 是你的组织名称和你在之前步骤中检索的授权计划的标识符。</span><span class="sxs-lookup"><span data-stu-id="01548-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="01548-154">例如，ContosoSchool： ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="01548-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="01548-155">运行以下命令，为具有许可计划的活动许可证的所有用户禁用团队。</span><span class="sxs-lookup"><span data-stu-id="01548-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="01548-156">管理组织级别的团队</span><span class="sxs-lookup"><span data-stu-id="01548-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="01548-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="01548-157">Related topics</span></span>

- [<span data-ttu-id="01548-158">团队附加设备许可证</span><span class="sxs-lookup"><span data-stu-id="01548-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="01548-159">分配团队附加设备许可证</span><span class="sxs-lookup"><span data-stu-id="01548-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="01548-160">通过 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="01548-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="01548-161">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="01548-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="01548-162">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="01548-162">Education SKU reference</span></span>](sku-reference-edu.md)