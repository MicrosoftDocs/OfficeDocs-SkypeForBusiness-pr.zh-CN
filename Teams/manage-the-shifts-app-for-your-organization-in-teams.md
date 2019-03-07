---
title: 在 Microsoft Teams 中为组织管理 Shifts 应用
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何设置和管理组织中的 firstline 工作者团队中的班次应用程序。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd05bf1485460bfd94ca3b33c5134084176e1fe
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462875"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="6e69d-103">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="6e69d-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e69d-104">有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。</span><span class="sxs-lookup"><span data-stu-id="6e69d-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6e69d-105">我们正在构建 StaffHub 功能，包括时间表和任务管理功能，向 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="6e69d-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="6e69d-106">Firstline 工作人员的其他功能将推出向工作组随着时间的推移。</span><span class="sxs-lookup"><span data-stu-id="6e69d-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="6e69d-107">若要了解详细信息，请参阅[Microsoft StaffHub 要停用](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0)。</span><span class="sxs-lookup"><span data-stu-id="6e69d-107">To learn more, see [Microsoft StaffHub to be retired](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="6e69d-108">班次的概述</span><span class="sxs-lookup"><span data-stu-id="6e69d-108">Overview of Shifts</span></span>
<span data-ttu-id="6e69d-109">引进应用程序中的 Microsoft 团队保持 firstline 工作者连接和同步。它是移动首先生成 fast 和有效时间管理和团队的通信。</span><span class="sxs-lookup"><span data-stu-id="6e69d-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="6e69d-110">引进允许 firstline 工作者和经理使用其移动设备管理计划并保持联系。</span><span class="sxs-lookup"><span data-stu-id="6e69d-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="6e69d-111">管理员创建、 更新和管理团队 shift 计划。</span><span class="sxs-lookup"><span data-stu-id="6e69d-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="6e69d-112">他们可以向一个人发送邮件 （"没有防泼上讲席"） 或整个团队 （"区域 GM 到达 20 分钟"）。</span><span class="sxs-lookup"><span data-stu-id="6e69d-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="6e69d-113">他们还可以发送策略文档、 新闻公告和视频。</span><span class="sxs-lookup"><span data-stu-id="6e69d-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="6e69d-114">员工查看其即将开始的引进、 可以查看其他还有谁已安排在一天、 请求交换或提供 shift 键，并关闭请求的时间。</span><span class="sxs-lookup"><span data-stu-id="6e69d-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="6e69d-115">务必要了解的引进当前不支持来宾用户。</span><span class="sxs-lookup"><span data-stu-id="6e69d-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="6e69d-116">这意味着来宾团队无法添加到或团队中开启来宾访问时，使用 shift 计划。</span><span class="sxs-lookup"><span data-stu-id="6e69d-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="6e69d-117">班次的可用性</span><span class="sxs-lookup"><span data-stu-id="6e69d-117">Availability of Shifts</span></span>

<span data-ttu-id="6e69d-118">引进可用于所有 Office 365 订阅包括团队，与几个例外。</span><span class="sxs-lookup"><span data-stu-id="6e69d-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="6e69d-119">例外情况是美国政府云社区 (GCC) 和团队免费。</span><span class="sxs-lookup"><span data-stu-id="6e69d-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="6e69d-120">Office 365 美国政府引进不可或团队忙产品。</span><span class="sxs-lookup"><span data-stu-id="6e69d-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="6e69d-121">进一步了解许可团队，包括 Office 365 订阅的列表，包括团队，请参阅[Office 365 许可团队](Office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="6e69d-121">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="6e69d-122">引进数据的位置</span><span class="sxs-lookup"><span data-stu-id="6e69d-122">Location of Shifts data</span></span>

<span data-ttu-id="6e69d-123">北美、 西欧和亚太地区中的数据中心中的 Azure 中当前存储引进数据。</span><span class="sxs-lookup"><span data-stu-id="6e69d-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="6e69d-124">有关存储数据的详细信息，请参阅[其中是我的数据](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="6e69d-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="6e69d-125">设置引进</span><span class="sxs-lookup"><span data-stu-id="6e69d-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="6e69d-126">启用或禁用组织中的变化</span><span class="sxs-lookup"><span data-stu-id="6e69d-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="6e69d-127">默认情况下，为您的组织中的所有工作组用户启用引进。</span><span class="sxs-lookup"><span data-stu-id="6e69d-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="6e69d-128">您可以关闭或打开 Microsoft 365 管理中心中的组织的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e69d-128">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="6e69d-129">登录到 Microsoft 365 管理中心，使用您的 Office 365 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="6e69d-129">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="6e69d-130">转到**设置** > **服务 & 加载项** > **Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="6e69d-130">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="6e69d-131">**租户范围的设置**下选择**应用程序**，然后在**默认应用程序**，清除或选择**班次**复选框，以关闭或打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e69d-131">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="6e69d-132">![默认应用程序部分的屏幕截图](media/firstline-worker-enable-disable-shifts.png "Microsoft 365 管理中心内，显示的应用程序，包括引进应用程序列表中的默认应用程序部分的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="6e69d-132">![Screen shot of the Default Apps section](media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="6e69d-133">使用 pin 引进向工作组到 FirstLineWorker 应用程序安装程序策略</span><span class="sxs-lookup"><span data-stu-id="6e69d-133">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="6e69d-134">应用程序设置策略允许您自定义团队以突出显示您的组织中的用户的最重要的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e69d-134">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="6e69d-135">在策略中设置的应用程序固定到应用程序栏&mdash;团队桌面客户端的一侧和底部的团队移动客户端的栏&mdash;其中用户可以快速、 轻松地访问它们。</span><span class="sxs-lookup"><span data-stu-id="6e69d-135">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="6e69d-136">团队包括您可以分配给 firstline 工作者您的组织中的内置 FirstLineWorker 应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="6e69d-136">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="6e69d-137">默认情况下，该策略包括活动、 引进、 聊天和调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e69d-137">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="6e69d-138">若要查看 FirstLineWorker 策略中，Microsoft 团队管理中心的左侧窗格中，转到**团队应用程序** > **应用程序设置策略**。</span><span class="sxs-lookup"><span data-stu-id="6e69d-138">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="6e69d-139">![Microsoft 团队管理中心中的 FirstLineWorker 应用程序设置策略的屏幕截图](media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstLineWorker 应用程序设置策略的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="6e69d-139">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center](media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="6e69d-140">将 FirstLineWorker 策略分配给各个用户</span><span class="sxs-lookup"><span data-stu-id="6e69d-140">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="6e69d-141">在 Microsoft 团队管理中心的左侧导航窗格中，转到**用户**，，然后单击用户。</span><span class="sxs-lookup"><span data-stu-id="6e69d-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6e69d-142">旁边**分配策略**，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="6e69d-142">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="6e69d-143">**团队应用程序设置策略**，下选择**FirstLineWorker**，，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="6e69d-143">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="6e69d-144">将 FirstLineWorker 应用程序安装策略分配给组中的用户</span><span class="sxs-lookup"><span data-stu-id="6e69d-144">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="6e69d-145">通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块 Skype，可以向组中，如安全组的用户分配 FirstLineWorker 应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="6e69d-145">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="6e69d-146">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell Overview](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6e69d-146">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="6e69d-147">本示例中，我们为 Contoso Firstline 工作组组中的所有用户分配 FirstLineWorker 应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="6e69d-147">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="6e69d-148">请确保您首次[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤通过连接到图模块 Azure Active Directory PowerShell 和业务 PowerShell 模块的 Skype。</span><span class="sxs-lookup"><span data-stu-id="6e69d-148">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="6e69d-149">获取特定的组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="6e69d-149">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="6e69d-150">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="6e69d-150">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="6e69d-151">组中的所有用户都分配 FirstLineWorker 应用程序设置策略。</span><span class="sxs-lookup"><span data-stu-id="6e69d-151">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="6e69d-152">根据组中成员的数目，此命令可能需要几分钟才能执行。</span><span class="sxs-lookup"><span data-stu-id="6e69d-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e69d-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="6e69d-153">Related topics</span></span>
- [<span data-ttu-id="6e69d-154">切换为 firstline 工作人员和管理员的帮助</span><span class="sxs-lookup"><span data-stu-id="6e69d-154">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)