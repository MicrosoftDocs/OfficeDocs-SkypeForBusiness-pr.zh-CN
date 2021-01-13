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
description: 了解如何通过向组织中用户分配或删除 Teams 许可证来管理用户对 Teams 的访问权限。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4fdfddfe43fd977099a02df61bb74146afcb05d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804402"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="8e2b5-103">管理用户对 Teams 的访问管理</span><span class="sxs-lookup"><span data-stu-id="8e2b5-103">Manage user access to Teams</span></span>

<span data-ttu-id="8e2b5-104">通过分配或删除 Microsoft Teams 产品许可证，在用户级别管理对 Teams 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="8e2b5-105">除了匿名加入 Teams 会议外，组织中的每个用户必须具有 Teams 许可证才能使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="8e2b5-106">可以在新建用户帐户时为新用户分配 Teams 许可证，也可以为具有现有帐户的用户分配 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="8e2b5-107">默认情况下，将许可计划 (例如 Microsoft 365 企业版 E3 或 Microsoft 365 商业高级版) 分配给用户时，将自动分配 Teams 许可证，并且为 Teams 启用该用户。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="8e2b5-108">你随时可以通过删除或分配许可证来为用户禁用或启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="8e2b5-109">使用从 Teams 管理中心管理的消息策略来控制 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams</a>中的用户可以使用哪些聊天和频道消息传送功能。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="8e2b5-110">可以使用默认策略，或为组织成员创建一个或多个自定义消息传送策略。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="8e2b5-111">若要了解有关详细信息，请阅读["在 Teams 中管理消息传送策略"。](messaging-policies-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8e2b5-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="8e2b5-112">在 Microsoft 365 管理中心中或通过使用 PowerShell 管理 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="8e2b5-113">只有全局管理员或用户管理管理员才能管理许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="8e2b5-114">我们建议为所有用户启用 Teams，以便可以针对项目和其他动态计划有组织地组建团队。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="8e2b5-115">即使正在运行试点，让所有用户都启用 Teams 可能也很有帮助，但仅面向试点用户组的通信。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8e2b5-116">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="8e2b5-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="8e2b5-117">Teams 用户级许可证直接通过 Microsoft 365 管理中心用户管理界面进行管理。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="8e2b5-118">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8e2b5-119">管理员必须具有全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="8e2b5-120">使用 Microsoft 365 管理中心一次管理单个用户或少量用户的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="8e2b5-121">可以在"许可证"页面上管理Teams 许可证 (最多同时为 20 个用户管理) **活动用户**"页面。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="8e2b5-122">选择的方法取决于是管理特定用户的产品许可证，还是管理特定产品的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="8e2b5-123">如果需要为大量用户（如数百或数千个用户）管理 Teams 许可证，请使用[Azure Active Directory ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) (Azure AD) 中的[PowerShell](#using-powershell)或基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="8e2b5-124">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-124">Assign a Teams license</span></span>

<span data-ttu-id="8e2b5-125">根据是使用"许可证"页还是"活动用户" **页面** ，步骤 **会** 有所不同。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="8e2b5-126">有关分步说明，请参阅"[向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="8e2b5-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![为用户启用 Teams 许可证的屏幕截图](media/assign-teams-licenses-1.png)    | ![为用户启用 Teams 许可证的屏幕截图](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="8e2b5-129">删除 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-129">Remove a Teams license</span></span>

<span data-ttu-id="8e2b5-130">从用户删除 Teams 许可证时，将为该用户禁用 Teams，他们将不再在应用启动器或主页中看到 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="8e2b5-131">有关详细步骤，请参阅["取消分配用户的许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="8e2b5-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![已针对用户禁用 Teams 许可证的屏幕截图](media/remove-teams-licenses-1.png)    | ![已针对用户禁用 Teams 许可证的屏幕截图](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="8e2b5-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e2b5-134">Using PowerShell</span></span>

<span data-ttu-id="8e2b5-135">使用 PowerShell 批量管理用户的 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="8e2b5-136">通过 PowerShell 启用和禁用 Teams 的方式与为任何其他服务计划许可证启用和禁用 Teams 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="8e2b5-137">需要 Teams 服务计划的标识符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e2b5-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="8e2b5-138">Microsoft Teams：TEAMS1</span><span class="sxs-lookup"><span data-stu-id="8e2b5-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="8e2b5-139">Microsoft Teams for GCC：TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="8e2b5-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="8e2b5-140">Microsoft Teams for DoD：TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="8e2b5-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="8e2b5-141">批量分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="8e2b5-142">有关详细步骤，请参阅使用 [PowerShell 将许可证分配给用户帐户](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="8e2b5-143">批量删除 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="8e2b5-144">有关详细步骤，请参阅"[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)禁用对服务的访问"和"分配用户许可证时禁用[对服务的访问权限"。](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="8e2b5-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="8e2b5-145">示例</span><span class="sxs-lookup"><span data-stu-id="8e2b5-145">Example</span></span> 

<span data-ttu-id="8e2b5-146">以下示例演示了如何使用 [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet 为具有特定许可计划的用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="8e2b5-147">例如，按照以下步骤首先为具有特定许可计划的所有用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="8e2b5-148">然后，为应有权访问 Teams 的每个用户启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e2b5-149">除非 [在自定义脚本中显式标识，否则 New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet 将启用以前禁用的所有服务。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="8e2b5-150">例如，如果要同时禁用 Exchange 和 Sway，同时禁用 Teams，则需要在脚本中包括此功能，否则将为标识的用户启用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="8e2b5-151">运行以下命令，显示组织中所有可用的许可计划。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="8e2b5-152">若要了解有关详细信息，请参阅["使用 PowerShell 查看许可证和服务"。](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8e2b5-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="8e2b5-153">运行以下命令，组织名称和在上一步中检索到的许可计划的 \<CompanyName:License> 标识符位于何处。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="8e2b5-154">例如，ContosoSchool：ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="8e2b5-155">运行以下命令，为拥有许可计划有效许可证的所有用户禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="8e2b5-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="8e2b5-156">在组织级别管理团队</span><span class="sxs-lookup"><span data-stu-id="8e2b5-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="8e2b5-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="8e2b5-157">Related topics</span></span>

- [<span data-ttu-id="8e2b5-158">Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="8e2b5-159">分配 Teams 附加许可证</span><span class="sxs-lookup"><span data-stu-id="8e2b5-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="8e2b5-160">使用 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="8e2b5-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="8e2b5-161">用于许可的产品名称和服务计划标识符</span><span class="sxs-lookup"><span data-stu-id="8e2b5-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="8e2b5-162">教育 SKU 参考</span><span class="sxs-lookup"><span data-stu-id="8e2b5-162">Education SKU reference</span></span>](sku-reference-edu.md)
