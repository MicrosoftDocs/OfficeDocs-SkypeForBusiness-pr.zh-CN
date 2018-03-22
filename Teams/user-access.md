---
title: 管理对 Microsoft Teams 的用户访问
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 了解如何基于每个用户启用或禁用用户级别访问。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="5764d-103">管理对 Microsoft Teams 的用户访问</span><span class="sxs-lookup"><span data-stu-id="5764d-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5764d-104">在用户级别中，可以启用或禁用基于每个用户分配或删除 Microsoft 小组产品许可证访问 Microsoft 小组。</span><span class="sxs-lookup"><span data-stu-id="5764d-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="5764d-105">目前，没有为打开团队或小组功能的子集或关闭外部授权单个用户级别策略选项。</span><span class="sxs-lookup"><span data-stu-id="5764d-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="5764d-106">Microsoft 建议启用团队为公司内所有用户，以便团队可以为项目和其他动态计划长足发展形成。</span><span class="sxs-lookup"><span data-stu-id="5764d-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="5764d-107">即使被确定为试点项目，它仍可能有助于使团队对所有的用户，启用，但只针对与试验组的用户的通信。</span><span class="sxs-lookup"><span data-stu-id="5764d-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-directly-through-the-office-365-admin-center"></a><span data-ttu-id="5764d-108">直接通过 Office 365 管理中心管理</span><span class="sxs-lookup"><span data-stu-id="5764d-108">Manage directly through the Office 365 admin center</span></span>

<span data-ttu-id="5764d-109">直接通过 Office 365 管理中心用户管理界面管理团队用户级别的许可证。</span><span class="sxs-lookup"><span data-stu-id="5764d-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="5764d-110">管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="5764d-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="5764d-111">管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="5764d-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="5764d-112">为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="5764d-112">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="5764d-113">管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="5764d-113">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="5764d-115">可随时禁用团队用户许可证。</span><span class="sxs-lookup"><span data-stu-id="5764d-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="5764d-116">一旦许可证被禁用，将阻止用户访问 Microsoft 小组的权限和用户将不再能够看到团队中的 Office 365 提供应用程序启动程序和主页。</span><span class="sxs-lookup"><span data-stu-id="5764d-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="5764d-118">通过 PowerShell 管理</span><span class="sxs-lookup"><span data-stu-id="5764d-118">Manage via PowerShell</span></span>

<span data-ttu-id="5764d-119">正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。</span><span class="sxs-lookup"><span data-stu-id="5764d-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="5764d-120">Microsoft Teams 的服务计划名称为 TEAMS1。</span><span class="sxs-lookup"><span data-stu-id="5764d-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="5764d-121">（有关详细信息，请参阅[通过 Office 365 PowerShell 禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)。）</span><span class="sxs-lookup"><span data-stu-id="5764d-121">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="5764d-122">**示例：**下面只是一个快速示例上特定的许可证类型中的每个人，您就会禁用团队。</span><span class="sxs-lookup"><span data-stu-id="5764d-122">**Sample:** Below is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="5764d-123">你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。</span><span class="sxs-lookup"><span data-stu-id="5764d-123">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="5764d-124">要显示贵组织中具有的订阅类型，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="5764d-124">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="5764d-125">填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5764d-125">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="5764d-126">若要禁用团队使用命名计划活动的许可证的所有用户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5764d-126">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="5764d-128">决策点</span><span class="sxs-lookup"><span data-stu-id="5764d-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="5764d-129">为团队服务的组织的计划整个组织是什么？</span><span class="sxs-lookup"><span data-stu-id="5764d-129">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="5764d-130">（试点或开放）</span><span class="sxs-lookup"><span data-stu-id="5764d-130">(Pilot or Open)</span></span></li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="5764d-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5764d-132">Next Steps</span></span>         |<ul><li><span data-ttu-id="5764d-133">如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</span><span class="sxs-lookup"><span data-stu-id="5764d-133">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="5764d-134">根据决定，采取步骤以确保只试验用户有权访问团队 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="5764d-134">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="5764d-135">文档的准则为哪些用户会 （或不会） 有权访问团队。</span><span class="sxs-lookup"><span data-stu-id="5764d-135">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a><span data-ttu-id="5764d-136">通过 Office Sku 级交换机管理</span><span class="sxs-lookup"><span data-stu-id="5764d-136">Manage via Office Sku level switch</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  <span data-ttu-id="5764d-137">使用具有全局管理员权限的帐户登录 [Office 365 管理中心](https://go.microsoft.com/fwlink/?linkid=854614)。</span><span class="sxs-lookup"><span data-stu-id="5764d-137">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="5764d-138">转至“**设置**” > “**服务和外接程序**”。</span><span class="sxs-lookup"><span data-stu-id="5764d-138">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="5764d-139">Office 365 管理中心中的“设置”部分（选择了“服务和外接程序”）屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="5764d-139">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="5764d-140">在“服务和外接程序”页面上，单击**“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="5764d-140">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![选择了“Microsoft Teams”的“服务和外接程序”页面屏幕截图。](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="5764d-142">要为组织启用 Teams，请使用许可证选取器，并选择每个许可证，然后将切换设置为**“开启”**，并单击**“保存”**。</span><span class="sxs-lookup"><span data-stu-id="5764d-142">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![Microsoft Teams 设置页面屏幕截图，显示切换设置为“开启”以启用 Microsoft Teams。](media/Services-and-addins-control-Microsoft-Teams.PNG)
