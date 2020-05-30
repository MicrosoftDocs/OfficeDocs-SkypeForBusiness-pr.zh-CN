---
title: 管理你的组织的倒班应用
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中的一线工作人员的团队中设置和管理倒班应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416882"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="d4ab6-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="d4ab6-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4ab6-104">2020年6月30日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="d4ab6-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d4ab6-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d4ab6-107">StaffHub 将在2020年6月30日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="d4ab6-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="d4ab6-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="d4ab6-110">倒班概述</span><span class="sxs-lookup"><span data-stu-id="d4ab6-110">Overview of Shifts</span></span>

<span data-ttu-id="d4ab6-111">Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动，为团队提供快速、有效的时间管理和沟通。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="d4ab6-112">倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="d4ab6-113">经理负责创建、更新和管理团队的倒班计划。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="d4ab6-114">他们可以向一个人发送消息（"在地面上有溢出"）或整个团队（"区域 GM 在20分钟内送达"）。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="d4ab6-115">他们还可以发送策略文档、新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="d4ab6-116">员工查看他们的即将到来的班次，可查看当天安排的其他人、请求交换或提供班次，以及请求下班时间。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="d4ab6-117">请务必知道当前班次不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="d4ab6-118">这意味着在团队中启用来宾访问时，无法将团队中的来宾添加到或使用倒班计划。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="d4ab6-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="d4ab6-119">Availability of Shifts</span></span>

<span data-ttu-id="d4ab6-120">倒班在所有企业版 Sku 可用，其中有团队可用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="d4ab6-121">倒班数据的位置</span><span class="sxs-lookup"><span data-stu-id="d4ab6-121">Location of Shifts data</span></span>

<span data-ttu-id="d4ab6-122">倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="d4ab6-123">有关存储数据的位置的详细信息，请参阅[我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="d4ab6-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="d4ab6-124">设置倒班</span><span class="sxs-lookup"><span data-stu-id="d4ab6-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="d4ab6-125">启用或禁用组织中的班次</span><span class="sxs-lookup"><span data-stu-id="d4ab6-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="d4ab6-126">默认情况下，将为组织中的所有团队用户启用倒班。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="d4ab6-127">你可以在 Microsoft 团队管理中心的 "[管理应用](../../manage-apps.md)" 页面上，关闭或打开组织级别的应用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="d4ab6-128">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="d4ab6-129">在应用列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d4ab6-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="d4ab6-130">若要为你的组织关闭班次，请搜索 "倒班" 应用，选择它，然后单击 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="d4ab6-131">若要为你的组织启用倒班，请搜索 "倒班" 应用，选择它，然后单击 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="d4ab6-132">启用或禁用组织中特定用户的班次</span><span class="sxs-lookup"><span data-stu-id="d4ab6-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="d4ab6-133">若要允许或阻止组织中的特定用户使用倒班，请确保在 "[管理应用](../../manage-apps.md)" 页面上为你的组织启用了班次，然后创建自定义应用权限策略并将其分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="d4ab6-134">若要了解详细信息，请参阅[管理团队中的应用权限策略](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="d4ab6-135">使用 FirstlineWorker 应用设置策略固定对团队的倒班</span><span class="sxs-lookup"><span data-stu-id="d4ab6-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="d4ab6-136">应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="d4ab6-137">策略中设置的应用将固定到应用程序栏，应用栏 &mdash; 位于团队桌面客户端和团队移动客户端的底部， &mdash; 用户可在其中快速轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="d4ab6-138">团队包括一个内置的 FirstlineWorker 应用设置策略，可分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="d4ab6-139">默认情况下，该策略包括活动、班次、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="d4ab6-140">若要查看 FirstlineWorker 策略，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **应用" 设置策略**。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="d4ab6-141">![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="d4ab6-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-users"></a><span data-ttu-id="d4ab6-142">将 FirstlineWorker 策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="d4ab6-142">Assign the FirstlineWorker policy to users</span></span>

<span data-ttu-id="d4ab6-143">若要向一个用户分配 FirstlineWorker 应用设置策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4ab6-143">To assign the FirstlineWorker app setup policy to one user:</span></span>

1. <span data-ttu-id="d4ab6-144">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d4ab6-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d4ab6-145">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d4ab6-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d4ab6-146">在 "**应用设置策略**" 下，选择 " **FirstlineWorker**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-146">Under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>

<span data-ttu-id="d4ab6-147">要一次为多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4ab6-147">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d4ab6-148">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d4ab6-149">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-149">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d4ab6-150">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-150">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d4ab6-151">单击 "**应用设置策略**" 下的 "**编辑设置**"，选择 " **FirstlineWorker**"，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-151">Click **Edit settings**, under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>  

<span data-ttu-id="d4ab6-152">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4ab6-152">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d4ab6-153">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **设置策略**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d4ab6-154">通过单击策略名称的左侧，选择 FirstlineWorker 策略。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-154">Select the FirstlineWorker policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d4ab6-155">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-155">Select **Manage users**.</span></span>
4. <span data-ttu-id="d4ab6-156">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d4ab6-157">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-157">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d4ab6-158">添加完用户后，选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-158">After you finish adding users, select **Apply**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="d4ab6-159">将 FirstlineWorker 应用设置策略分配给组的用户成员</span><span class="sxs-lookup"><span data-stu-id="d4ab6-159">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="d4ab6-160">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块，将 FirstlineWorker 应用设置策略分配给组的用户成员（如安全组）。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-160">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="d4ab6-161">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](../../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="d4ab6-162">在此示例中，我们将 FirstlineWorker 应用设置策略分配给 Contoso 一线团队组的所有用户成员。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-162">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="d4ab6-163">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="d4ab6-164">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-164">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="d4ab6-165">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-165">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d4ab6-166">将 FirstlineWorker 应用设置策略分配给该组的所有用户成员。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-166">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="d4ab6-167">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="d4ab6-168">在审核日志中搜索倒班事件</span><span class="sxs-lookup"><span data-stu-id="d4ab6-168">Search the audit log for Shifts events</span></span>

<span data-ttu-id="d4ab6-169">**（处于预览阶段）**</span><span class="sxs-lookup"><span data-stu-id="d4ab6-169">**(in preview)**</span></span>

<span data-ttu-id="d4ab6-170">您可以在您的组织中搜索 "审核日志" 以查看倒班活动。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-170">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="d4ab6-171">若要了解有关如何搜索审核日志和查看审核日志中记录的[班次活动](../../audit-log-events.md#shifts-in-teams-activities)列表的详细信息，请参阅[在审核日志中搜索团队中的事件](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-171">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="d4ab6-172">在搜索审核日志之前，必须先在[安全 & 合规中心](https://protection.office.com)启用审核。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d4ab6-173">若要了解详细信息，请参阅[打开或关闭审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-173">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="d4ab6-174">请记住，审核数据仅在你打开审核的位置可用。</span><span class="sxs-lookup"><span data-stu-id="d4ab6-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4ab6-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="d4ab6-175">Related topics</span></span>

- [<span data-ttu-id="d4ab6-176">倒班一线工作者的帮助</span><span class="sxs-lookup"><span data-stu-id="d4ab6-176">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="d4ab6-177">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="d4ab6-177">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
