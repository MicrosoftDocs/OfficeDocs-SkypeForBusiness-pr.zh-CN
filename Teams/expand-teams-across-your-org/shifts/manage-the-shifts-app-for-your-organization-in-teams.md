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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7dbe54c0f7239653b8f36179e57ab83510e0a5a1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232264"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="544ee-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="544ee-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="544ee-104">2019年10月1日生效, Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="544ee-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="544ee-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="544ee-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="544ee-106">今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="544ee-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="544ee-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="544ee-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="544ee-108">任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="544ee-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="544ee-109">若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="544ee-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="544ee-110">倒班概述</span><span class="sxs-lookup"><span data-stu-id="544ee-110">Overview of Shifts</span></span>
<span data-ttu-id="544ee-111">Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动, 为团队提供快速、有效的时间管理和沟通。</span><span class="sxs-lookup"><span data-stu-id="544ee-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="544ee-112">倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。</span><span class="sxs-lookup"><span data-stu-id="544ee-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="544ee-113">经理负责创建、更新和管理团队的倒班计划。</span><span class="sxs-lookup"><span data-stu-id="544ee-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="544ee-114">他们可以向一个人发送消息 ("在地面上有溢出") 或整个团队 ("区域 GM 在20分钟内送达")。</span><span class="sxs-lookup"><span data-stu-id="544ee-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="544ee-115">他们还可以发送策略文档、新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="544ee-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="544ee-116">员工查看他们的即将到来的班次, 可查看当天安排的其他人、请求交换或提供班次, 以及请求下班时间。</span><span class="sxs-lookup"><span data-stu-id="544ee-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="544ee-117">请务必知道当前班次不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="544ee-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="544ee-118">这意味着在团队中启用来宾访问时, 无法将团队中的来宾添加到或使用倒班计划。</span><span class="sxs-lookup"><span data-stu-id="544ee-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="544ee-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="544ee-119">Availability of Shifts</span></span>

<span data-ttu-id="544ee-120">倒班在所有包含团队的 Office 365 订阅中均可用, 有几个例外。</span><span class="sxs-lookup"><span data-stu-id="544ee-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="544ee-121">例外情况是美国政府云社区 (GCC) 和团队免费。</span><span class="sxs-lookup"><span data-stu-id="544ee-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="544ee-122">班次在 Office 365 中不可用。美国政府或团队免费服务。</span><span class="sxs-lookup"><span data-stu-id="544ee-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="544ee-123">若要了解有关团队授权的详细信息, 包括包含团队的 Office 365 订阅的列表, 请参阅[团队的 office 365 许可](../../Office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="544ee-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="544ee-124">倒班数据的位置</span><span class="sxs-lookup"><span data-stu-id="544ee-124">Location of Shifts data</span></span>

<span data-ttu-id="544ee-125">倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="544ee-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="544ee-126">有关存储数据的位置的详细信息, 请参阅[我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="544ee-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="544ee-127">设置倒班</span><span class="sxs-lookup"><span data-stu-id="544ee-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="544ee-128">启用或禁用组织中的班次</span><span class="sxs-lookup"><span data-stu-id="544ee-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="544ee-129">默认情况下, 将为组织中的所有团队用户启用倒班。</span><span class="sxs-lookup"><span data-stu-id="544ee-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="544ee-130">你可以通过在 Microsoft 团队管理中心的应用权限策略中使用组织范围内的设置来关闭或打开应用组织。</span><span class="sxs-lookup"><span data-stu-id="544ee-130">You can turn off or turn on the app org-wide by using org-wide settings in app permission policies in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="544ee-131">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="544ee-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies** .</span></span>
2. <span data-ttu-id="544ee-132">单击 "**组织范围的设置**"。</span><span class="sxs-lookup"><span data-stu-id="544ee-132">Click **Org-wide settings**.</span></span>
3. <span data-ttu-id="544ee-133">在 "**组织范围设置**" 面板的 "已**阻止的应用**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="544ee-133">In the **Org-wide settings** panel, under **Blocked apps**, do one of the following:</span></span>

    - <span data-ttu-id="544ee-134">若要为你的组织关闭班次, 请搜索 "倒班" 应用, 然后单击 "**添加**" 以将其添加到 "阻止的应用" 列表。</span><span class="sxs-lookup"><span data-stu-id="544ee-134">To turn off Shifts for your organization, search for the Shifts app, and click **Add** to add it to the blocked apps list.</span></span>
    - <span data-ttu-id="544ee-135">若要为你的组织启用班次, 请从 "阻止的应用" 列表中删除 "倒班" 应用。</span><span class="sxs-lookup"><span data-stu-id="544ee-135">To turn on Shifts for your organization, remove the Shifts app from the blocked apps list.</span></span>
4. <span data-ttu-id="544ee-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="544ee-136">Click **Save**.</span></span> 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="544ee-137">启用或禁用组织中特定用户的班次</span><span class="sxs-lookup"><span data-stu-id="544ee-137">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="544ee-138">若要允许或阻止组织中的特定用户使用倒班, 请确保在组织范围的设置中为你的组织启用了倒班, 然后创建自定义应用权限策略并将其分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="544ee-138">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization in org-wide settings, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="544ee-139">若要了解详细信息, 请参阅[管理团队中的应用权限策略](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="544ee-139">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="544ee-140">使用 FirstlineWorker 应用设置策略固定对团队的倒班</span><span class="sxs-lookup"><span data-stu-id="544ee-140">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="544ee-141">应用设置策略允许你自定义团队, 以突出显示你的组织中的用户最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="544ee-141">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="544ee-142">策略中设置的应用将固定到应用程序栏,&mdash;应用栏位于团队桌面客户端和团队移动客户&mdash;端的底部, 用户可在其中快速轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="544ee-142">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="544ee-143">团队包括一个内置的 FirstlineWorker 应用设置策略, 可分配给你的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="544ee-143">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="544ee-144">默认情况下, 该策略包括活动、班次、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="544ee-144">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="544ee-145">若要查看 FirstlineWorker 策略, 请在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队应用** > **应用" 设置策略**。</span><span class="sxs-lookup"><span data-stu-id="544ee-145">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="544ee-146">![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="544ee-146">![Screen shot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screen shot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="544ee-147">将 FirstlineWorker 策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="544ee-147">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="544ee-148">在 Microsoft 团队管理中心的左侧导航中, 转到 "**用户**", 然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="544ee-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="544ee-149">在 "**分配的策略**" 旁边, 选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="544ee-149">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="544ee-150">在 "**团队应用设置策略**" 下, 选择 " **FirstlineWorker**", 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="544ee-150">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="544ee-151">将 FirstlineWorker 应用设置策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="544ee-151">Assign the FirstlineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="544ee-152">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块, 将 FirstlineWorker 应用设置策略分配给组中的用户 (如安全组)。</span><span class="sxs-lookup"><span data-stu-id="544ee-152">You can assign the FirstlineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="544ee-153">有关使用 PowerShell 管理团队的详细信息, 请参阅[团队 PowerShell 概述](../../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="544ee-153">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="544ee-154">在此示例中, 我们将 FirstlineWorker 应用设置策略分配给 Contoso 一线团队组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="544ee-154">In this example, we assign the FirstlineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="544ee-155">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤, 确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="544ee-155">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="544ee-156">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="544ee-156">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="544ee-157">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="544ee-157">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="544ee-158">将组中的所有用户分配到 FirstlineWorker 应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="544ee-158">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="544ee-159">此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="544ee-159">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="544ee-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="544ee-160">Related topics</span></span>
- [<span data-ttu-id="544ee-161">倒班一线工作者的帮助</span><span class="sxs-lookup"><span data-stu-id="544ee-161">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
