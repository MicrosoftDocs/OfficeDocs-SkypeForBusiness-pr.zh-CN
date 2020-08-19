---
title: 医疗保健的团队策略程序包
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
description: 了解如何使用和管理你的医疗保健组织的团队策略包。
ms.openlocfilehash: dbbc0956f339760bedf1ce9cc2c5012cc317e152
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803965"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="60c4e-103">医疗保健的团队策略程序包</span><span class="sxs-lookup"><span data-stu-id="60c4e-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="60c4e-104">概述</span><span class="sxs-lookup"><span data-stu-id="60c4e-104">Overview</span></span>

<span data-ttu-id="60c4e-105">Microsoft 团队中的 [策略包](manage-policy-packages.md) 是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="60c4e-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="60c4e-106">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="60c4e-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="60c4e-107">你可以自定义程序包中的策略设置以满足你的用户需求。</span><span class="sxs-lookup"><span data-stu-id="60c4e-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="60c4e-108">当您更改策略包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。</span><span class="sxs-lookup"><span data-stu-id="60c4e-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="60c4e-109">你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="60c4e-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="60c4e-110">策略程序包针对以下情况预定义策略，具体取决于程序包：</span><span class="sxs-lookup"><span data-stu-id="60c4e-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="60c4e-111">消息传递</span><span class="sxs-lookup"><span data-stu-id="60c4e-111">Messaging</span></span>
- <span data-ttu-id="60c4e-112">会议</span><span class="sxs-lookup"><span data-stu-id="60c4e-112">Meetings</span></span>
- <span data-ttu-id="60c4e-113">通话</span><span class="sxs-lookup"><span data-stu-id="60c4e-113">Calling</span></span>
- <span data-ttu-id="60c4e-114">应用设置</span><span class="sxs-lookup"><span data-stu-id="60c4e-114">App setup</span></span>
- <span data-ttu-id="60c4e-115">实时事件</span><span class="sxs-lookup"><span data-stu-id="60c4e-115">Live events</span></span>

<span data-ttu-id="60c4e-116">团队当前包含以下医疗保健策略程序包。</span><span class="sxs-lookup"><span data-stu-id="60c4e-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="60c4e-117">Microsoft 团队管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="60c4e-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="60c4e-118">最适合用于</span><span class="sxs-lookup"><span data-stu-id="60c4e-118">Best used for</span></span>|<span data-ttu-id="60c4e-119">说明</span><span class="sxs-lookup"><span data-stu-id="60c4e-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="60c4e-120">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="60c4e-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="60c4e-121">医疗保健组织中的临床工作者</span><span class="sxs-lookup"><span data-stu-id="60c4e-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="60c4e-122">创建一组策略和策略设置，为临床工作者（如注册的护士、费用护理、医生和社会工作者）提供对聊天、通话、班次管理和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="60c4e-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="60c4e-123">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="60c4e-123">Healthcare information worker</span></span>  |<span data-ttu-id="60c4e-124">您的医疗保健组织中的信息工作者</span><span class="sxs-lookup"><span data-stu-id="60c4e-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="60c4e-125">创建一组策略和策略设置，提供信息工作者，如 IT 人员、informatics 员工、财务人员和合规性监察官、对聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="60c4e-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="60c4e-126">医疗保健患者聊天室</span><span class="sxs-lookup"><span data-stu-id="60c4e-126">Healthcare patient room</span></span>  |<span data-ttu-id="60c4e-127">患者聊天室设备</span><span class="sxs-lookup"><span data-stu-id="60c4e-127">Patient room devices</span></span>|<span data-ttu-id="60c4e-128">创建一组策略和策略设置，这些策略设置适用于您的医疗保健组织中的患者聊天室。</span><span class="sxs-lookup"><span data-stu-id="60c4e-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![医疗保健策略程序包的屏幕截图](media/policy-packages-healthcare.png)

<span data-ttu-id="60c4e-130">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="60c4e-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="60c4e-131">例如，当你将医疗保健临床工作人员策略包分配给你的组织中的临床医生时，将为程序包中的每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。</span><span class="sxs-lookup"><span data-stu-id="60c4e-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医疗保健临床工作者程序包中的策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="60c4e-133">管理策略包</span><span class="sxs-lookup"><span data-stu-id="60c4e-133">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="60c4e-134">查看</span><span class="sxs-lookup"><span data-stu-id="60c4e-134">View</span></span>

<span data-ttu-id="60c4e-135">在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="60c4e-135">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="60c4e-136">在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包**"，选择程序包名称，然后选择 "策略名称"。</span><span class="sxs-lookup"><span data-stu-id="60c4e-136">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="60c4e-137">确定预定义的值是否适合你的组织，或者你是否需要根据组织的需求自定义它们以使其更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="60c4e-137">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="60c4e-138">自定义</span><span class="sxs-lookup"><span data-stu-id="60c4e-138">Customize</span></span>

<span data-ttu-id="60c4e-139">根据需要自定义策略包中的策略设置，以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="60c4e-139">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="60c4e-140">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="60c4e-140">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="60c4e-141">若要编辑策略包中的策略设置，请在 Microsoft 团队管理中心中，选择 "策略" 程序包，选择要编辑的策略的名称，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="60c4e-141">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="60c4e-142">请记住，你还可以在分配策略包后更改程序包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="60c4e-142">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="60c4e-143">若要了解详细信息，请参阅 [自定义策略包中的策略](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="60c4e-143">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="60c4e-144">分配</span><span class="sxs-lookup"><span data-stu-id="60c4e-144">Assign</span></span>

<span data-ttu-id="60c4e-145">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="60c4e-145">Assign the policy package to users.</span></span> <span data-ttu-id="60c4e-146">若要向一个或多个用户分配策略包，请单击 " **管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="60c4e-146">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="60c4e-147">你还可以 [使用 PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 将策略包分配给大量用户。</span><span class="sxs-lookup"><span data-stu-id="60c4e-147">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="60c4e-148">有关如何使用 Microsoft 团队管理中心或 PowerShell 分配策略包的步骤，请参阅 [分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="60c4e-148">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="60c4e-150">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="60c4e-150">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60c4e-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="60c4e-151">Related topics</span></span>

[<span data-ttu-id="60c4e-152">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="60c4e-152">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="60c4e-153">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="60c4e-153">Assign policies to your users in Teams</span></span>](assign-policies.md)
