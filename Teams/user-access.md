---
title: 管理对 Microsoft Teams 的用户访问
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何基于每个用户启用或禁用用户级别访问。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205829"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="70d2a-103">管理对 Microsoft Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="70d2a-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="70d2a-104">在用户级别，可以启用或禁用基于每个用户分配或删除的 Microsoft 团队产品许可证的 Microsoft 团队访问。</span><span class="sxs-lookup"><span data-stu-id="70d2a-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="70d2a-105">邮件策略，从工作组管理中心托管用于控制哪些聊天和消息功能的通道供团队中的用户。</span><span class="sxs-lookup"><span data-stu-id="70d2a-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="70d2a-106">您可以使用默认策略，或在组织中的人员创建一个或多个自定义的邮件策略。</span><span class="sxs-lookup"><span data-stu-id="70d2a-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="70d2a-107">若要了解详细信息，请阅读[管理团队中的邮件策略](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="70d2a-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="70d2a-108">Microsoft 建议，您打开团队公司中的所有用户，以便团队可以该库格式正确的项目和其他动态计划。</span><span class="sxs-lookup"><span data-stu-id="70d2a-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="70d2a-109">即使您决定为试点，它可能仍会有所帮助保持团队启用所有用户，但仅具有与试点的用户组的通信。</span><span class="sxs-lookup"><span data-stu-id="70d2a-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="70d2a-110">通过在 Office 365 管理中心管理团队</span><span class="sxs-lookup"><span data-stu-id="70d2a-110">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="70d2a-111">直接通过 Office 365 admin center 用户管理界面进行管理团队用户级许可证。</span><span class="sxs-lookup"><span data-stu-id="70d2a-111">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="70d2a-112">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="70d2a-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="70d2a-113">管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="70d2a-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="70d2a-114">为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="70d2a-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="70d2a-115">管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="70d2a-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="70d2a-117">可以随时禁用团队用户许可证。</span><span class="sxs-lookup"><span data-stu-id="70d2a-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="70d2a-118">一旦被禁用许可证，将阻止向 Microsoft 工作组的用户访问，用户将不再能够看到团队中的 Office 365 应用程序启动器和主页。</span><span class="sxs-lookup"><span data-stu-id="70d2a-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="70d2a-120">通过 PowerShell 自定义管理</span><span class="sxs-lookup"><span data-stu-id="70d2a-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70d2a-121">新 MsolLicenseOptions 将启用以前被禁用，除非的所有服务 explictitly identitied 中自定义脚本。</span><span class="sxs-lookup"><span data-stu-id="70d2a-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="70d2a-122">作为示例，如果您想要保留这两个 Exchange & Sway 此外禁用团队时禁用您将需要包括此脚本或两个 Exchange & Sway 将变为启用您已确定这些用户。</span><span class="sxs-lookup"><span data-stu-id="70d2a-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="70d2a-123">如果您希望执行利用 GUI 管理此功能，请参阅： [Office 365 许可报告和管理工具-删除许可证分配批量](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="70d2a-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="70d2a-124">正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="70d2a-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="70d2a-125">Microsoft Teams 的服务计划名称为 TEAMS1。</span><span class="sxs-lookup"><span data-stu-id="70d2a-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="70d2a-126">对于 GCC 服务计划名称是 TEAMS_GOV。</span><span class="sxs-lookup"><span data-stu-id="70d2a-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="70d2a-127">对于 GCC 高服务计划名称是 TEAMS_GCCHIGH。</span><span class="sxs-lookup"><span data-stu-id="70d2a-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="70d2a-128">对于 DoD 服务计划名称是 TEAMS_DOD (请参阅[禁止访问服务与 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)的详细信息。)</span><span class="sxs-lookup"><span data-stu-id="70d2a-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="70d2a-129">**示例：** 下面是只在特定许可证类型中的所有人，您就会禁用团队的快速示例。</span><span class="sxs-lookup"><span data-stu-id="70d2a-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="70d2a-130">你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。</span><span class="sxs-lookup"><span data-stu-id="70d2a-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="70d2a-131">要显示贵组织中具有的订阅类型，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="70d2a-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="70d2a-132">填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="70d2a-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="70d2a-133">若要禁用团队的所有用户与您命名计划的活动许可证，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="70d2a-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="70d2a-135">决策点</span><span class="sxs-lookup"><span data-stu-id="70d2a-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="70d2a-136">什么是整个组织内的组织规划团队入职培训？</span><span class="sxs-lookup"><span data-stu-id="70d2a-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="70d2a-137">（试点或开放）</span><span class="sxs-lookup"><span data-stu-id="70d2a-137">(Pilot or Open)</span></span></li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="70d2a-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="70d2a-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="70d2a-140">如果您希望通过许可，这样或目标通信，如果决定通过关闭试验入职培训。</span><span class="sxs-lookup"><span data-stu-id="70d2a-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="70d2a-141">决策，根据需要步骤以确保仅试验用户有权访问工作组 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="70d2a-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="70d2a-142">文档的准则为哪些用户将 （或不会） 有权访问团队。</span><span class="sxs-lookup"><span data-stu-id="70d2a-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="70d2a-143">管理 Office 365 租户级别的团队</span><span class="sxs-lookup"><span data-stu-id="70d2a-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

