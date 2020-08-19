---
title: 政府团队政策包
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理政府组织的团队策略包。
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804008"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="58670-103">政府团队政策包</span><span class="sxs-lookup"><span data-stu-id="58670-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="58670-104">策略程序包目前在 Microsoft 365 政府版或 DoD 部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="58670-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="58670-105">概述</span><span class="sxs-lookup"><span data-stu-id="58670-105">Overview</span></span>

<span data-ttu-id="58670-106">Microsoft 团队中的 [策略包](manage-policy-packages.md) 是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="58670-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="58670-107">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="58670-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="58670-108">你可以自定义程序包中的策略设置以满足你的用户需求。</span><span class="sxs-lookup"><span data-stu-id="58670-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="58670-109">当您更改策略包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。</span><span class="sxs-lookup"><span data-stu-id="58670-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="58670-110">你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="58670-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="58670-111">策略程序包针对以下情况预定义策略，具体取决于程序包：</span><span class="sxs-lookup"><span data-stu-id="58670-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="58670-112">消息传递</span><span class="sxs-lookup"><span data-stu-id="58670-112">Messaging</span></span>
- <span data-ttu-id="58670-113">会议</span><span class="sxs-lookup"><span data-stu-id="58670-113">Meetings</span></span>
- <span data-ttu-id="58670-114">通话</span><span class="sxs-lookup"><span data-stu-id="58670-114">Calling</span></span>
- <span data-ttu-id="58670-115">应用设置</span><span class="sxs-lookup"><span data-stu-id="58670-115">App setup</span></span>
- <span data-ttu-id="58670-116">实时事件</span><span class="sxs-lookup"><span data-stu-id="58670-116">Live events</span></span>

<span data-ttu-id="58670-117">团队当前包括适用于政府的以下政策包。</span><span class="sxs-lookup"><span data-stu-id="58670-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="58670-118">Microsoft 团队管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="58670-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="58670-119">最适合用于</span><span class="sxs-lookup"><span data-stu-id="58670-119">Best used for</span></span>|<span data-ttu-id="58670-120">说明</span><span class="sxs-lookup"><span data-stu-id="58670-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="58670-121">公共安全专员</span><span class="sxs-lookup"><span data-stu-id="58670-121">Public safety officer</span></span>  |<span data-ttu-id="58670-122">政府组织中的公共安全官员</span><span class="sxs-lookup"><span data-stu-id="58670-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="58670-123">创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。</span><span class="sxs-lookup"><span data-stu-id="58670-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="58670-124">一线管理器</span><span class="sxs-lookup"><span data-stu-id="58670-124">Firstline manager</span></span>  |<span data-ttu-id="58670-125">政府组织中的一线经理</span><span class="sxs-lookup"><span data-stu-id="58670-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="58670-126">创建一组策略，并将这些设置应用到组织中的一线管理员。</span><span class="sxs-lookup"><span data-stu-id="58670-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="58670-127">一线工作人员</span><span class="sxs-lookup"><span data-stu-id="58670-127">Firstline worker</span></span>  |<span data-ttu-id="58670-128">您的政府组织中的一线工作者</span><span class="sxs-lookup"><span data-stu-id="58670-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="58670-129">创建一组策略，并将这些设置应用于您的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="58670-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![医疗保健策略程序包的屏幕截图](media/policy-packages-gov.png)

<span data-ttu-id="58670-131">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="58670-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="58670-132">例如，当您将公共安全专员策略包分配给您的组织中的用户时，将为程序包中的每个策略创建一个名为 PublicSafety_Officer 的策略。</span><span class="sxs-lookup"><span data-stu-id="58670-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医疗保健临床工作者程序包中的策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="58670-134">管理策略包</span><span class="sxs-lookup"><span data-stu-id="58670-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="58670-135">查看</span><span class="sxs-lookup"><span data-stu-id="58670-135">View</span></span>

<span data-ttu-id="58670-136">在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="58670-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="58670-137">在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包**"，选择程序包名称，然后选择 "策略名称"。</span><span class="sxs-lookup"><span data-stu-id="58670-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="58670-138">确定预定义的值是否适合你的组织，或者你是否需要根据组织的需求自定义它们以使其更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="58670-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="58670-139">自定义</span><span class="sxs-lookup"><span data-stu-id="58670-139">Customize</span></span>

<span data-ttu-id="58670-140">根据需要自定义策略包中的策略设置，以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="58670-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="58670-141">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="58670-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="58670-142">若要编辑策略包中的策略设置，请在 Microsoft 团队管理中心中，选择 "策略" 程序包，选择要编辑的策略的名称，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="58670-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="58670-143">请记住，你还可以在分配策略包后更改程序包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="58670-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="58670-144">若要了解详细信息，请参阅 [自定义策略包中的策略](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="58670-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="58670-145">分配</span><span class="sxs-lookup"><span data-stu-id="58670-145">Assign</span></span>

<span data-ttu-id="58670-146">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="58670-146">Assign the policy package to users.</span></span> <span data-ttu-id="58670-147">若要向一个或多个用户分配策略包，请单击 " **管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="58670-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="58670-148">你还可以 [使用 PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 将策略包分配给大量用户。</span><span class="sxs-lookup"><span data-stu-id="58670-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="58670-149">有关如何使用 Microsoft 团队管理中心或 PowerShell 分配策略包的步骤，请参阅 [分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="58670-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![如何在管理中心分配策略包的屏幕截图](media/policy-packages-gov-assign.png)

<span data-ttu-id="58670-151">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="58670-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58670-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="58670-152">Related topics</span></span>

[<span data-ttu-id="58670-153">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="58670-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="58670-154">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="58670-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
