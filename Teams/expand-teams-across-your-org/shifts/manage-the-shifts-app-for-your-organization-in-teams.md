---
title: 在 Microsoft Teams 中为组织管理 Shifts 应用
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中的一线工作人员的团队中设置和管理倒班应用。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bd65376be278a3d07e5a7a8c4ba69ccd5408090
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39961607"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="018ef-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="018ef-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="018ef-104">2019年12月31日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="018ef-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="018ef-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="018ef-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="018ef-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="018ef-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="018ef-107">StaffHub 将停止为2019年12月31日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="018ef-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="018ef-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="018ef-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="018ef-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="018ef-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="018ef-110">倒班概述</span><span class="sxs-lookup"><span data-stu-id="018ef-110">Overview of Shifts</span></span>
<span data-ttu-id="018ef-111">Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动，为团队提供快速、有效的时间管理和沟通。</span><span class="sxs-lookup"><span data-stu-id="018ef-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="018ef-112">倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。</span><span class="sxs-lookup"><span data-stu-id="018ef-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="018ef-113">经理负责创建、更新和管理团队的倒班计划。</span><span class="sxs-lookup"><span data-stu-id="018ef-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="018ef-114">他们可以向一个人发送消息（"在地面上有溢出"）或整个团队（"区域 GM 在20分钟内送达"）。</span><span class="sxs-lookup"><span data-stu-id="018ef-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="018ef-115">他们还可以发送策略文档、新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="018ef-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="018ef-116">员工查看他们的即将到来的班次，可查看当天安排的其他人、请求交换或提供班次，以及请求下班时间。</span><span class="sxs-lookup"><span data-stu-id="018ef-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="018ef-117">请务必知道当前班次不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="018ef-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="018ef-118">这意味着在团队中启用来宾访问时，无法将团队中的来宾添加到或使用倒班计划。</span><span class="sxs-lookup"><span data-stu-id="018ef-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="018ef-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="018ef-119">Availability of Shifts</span></span>

<span data-ttu-id="018ef-120">倒班在所有企业版 Sku 可用，其中有团队可用。</span><span class="sxs-lookup"><span data-stu-id="018ef-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="018ef-121">倒班数据的位置</span><span class="sxs-lookup"><span data-stu-id="018ef-121">Location of Shifts data</span></span>

<span data-ttu-id="018ef-122">倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="018ef-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="018ef-123">有关存储数据的位置的详细信息，请参阅[我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="018ef-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="018ef-124">设置倒班</span><span class="sxs-lookup"><span data-stu-id="018ef-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="018ef-125">启用或禁用组织中的班次</span><span class="sxs-lookup"><span data-stu-id="018ef-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="018ef-126">默认情况下，将为组织中的所有团队用户启用倒班。</span><span class="sxs-lookup"><span data-stu-id="018ef-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="018ef-127">你可以通过在 Microsoft 团队管理中心的应用权限策略中使用组织范围内的设置来关闭或打开应用组织。</span><span class="sxs-lookup"><span data-stu-id="018ef-127">You can turn off or turn on the app org-wide by using org-wide settings in app permission policies in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="018ef-128">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="018ef-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies** .</span></span>
2. <span data-ttu-id="018ef-129">单击 "**组织范围的设置**"。</span><span class="sxs-lookup"><span data-stu-id="018ef-129">Click **Org-wide settings**.</span></span>
3. <span data-ttu-id="018ef-130">在 "**组织范围设置**" 面板的 "已**阻止的应用**" 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="018ef-130">In the **Org-wide settings** panel, under **Blocked apps**, do one of the following:</span></span>

    - <span data-ttu-id="018ef-131">若要为你的组织关闭班次，请搜索 "倒班" 应用，然后单击 "**添加**" 以将其添加到 "阻止的应用" 列表。</span><span class="sxs-lookup"><span data-stu-id="018ef-131">To turn off Shifts for your organization, search for the Shifts app, and click **Add** to add it to the blocked apps list.</span></span>
    - <span data-ttu-id="018ef-132">若要为你的组织启用班次，请从 "阻止的应用" 列表中删除 "倒班" 应用。</span><span class="sxs-lookup"><span data-stu-id="018ef-132">To turn on Shifts for your organization, remove the Shifts app from the blocked apps list.</span></span>
4. <span data-ttu-id="018ef-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="018ef-133">Click **Save**.</span></span> 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="018ef-134">启用或禁用组织中特定用户的班次</span><span class="sxs-lookup"><span data-stu-id="018ef-134">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="018ef-135">若要允许或阻止组织中的特定用户使用倒班，请确保在组织范围的设置中为你的组织启用了倒班，然后创建自定义应用权限策略并将其分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="018ef-135">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization in org-wide settings, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="018ef-136">若要了解详细信息，请参阅[管理团队中的应用权限策略](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="018ef-136">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="018ef-137">使用 FirstlineWorker 应用设置策略固定对团队的倒班</span><span class="sxs-lookup"><span data-stu-id="018ef-137">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="018ef-138">应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="018ef-138">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="018ef-139">策略中设置的应用将固定到应用程序栏，&mdash;应用栏位于团队桌面客户端和团队移动客户&mdash;端的底部，用户可在其中快速轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="018ef-139">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="018ef-140">团队包括一个内置的 FirstlineWorker 应用设置策略，可分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="018ef-140">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="018ef-141">默认情况下，该策略包括活动、班次、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="018ef-141">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="018ef-142">若要查看 FirstlineWorker 策略，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **应用" 设置策略**。</span><span class="sxs-lookup"><span data-stu-id="018ef-142">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="018ef-143">![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="018ef-143">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="018ef-144">将 FirstlineWorker 策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="018ef-144">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="018ef-145">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="018ef-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="018ef-146">在 "**分配的策略**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="018ef-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="018ef-147">在 "**团队应用设置策略**" 下，选择 " **FirstlineWorker**"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="018ef-147">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="018ef-148">将 FirstlineWorker 应用设置策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="018ef-148">Assign the FirstlineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="018ef-149">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块，将 FirstlineWorker 应用设置策略分配给组中的用户（如安全组）。</span><span class="sxs-lookup"><span data-stu-id="018ef-149">You can assign the FirstlineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="018ef-150">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](../../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="018ef-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="018ef-151">在此示例中，我们将 FirstlineWorker 应用设置策略分配给 Contoso 一线团队组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="018ef-151">In this example, we assign the FirstlineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="018ef-152">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="018ef-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="018ef-153">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="018ef-153">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="018ef-154">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="018ef-154">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="018ef-155">将组中的所有用户分配到 FirstlineWorker 应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="018ef-155">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="018ef-156">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="018ef-156">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="018ef-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="018ef-157">Related topics</span></span>
- [<span data-ttu-id="018ef-158">倒班一线工作者的帮助</span><span class="sxs-lookup"><span data-stu-id="018ef-158">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
