---
title: 向学校的大型用户组分配策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 "批处理策略分配" 为远程学校（teleschool、长途）批量为您的教育机构中的大型用户分配策略。
f1keywords: ''
ms.openlocfilehash: e95c6b035298ce583a0ad34a030f2086b7c12ff3
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583330"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="33f3e-103">向学校的大型用户组分配策略</span><span class="sxs-lookup"><span data-stu-id="33f3e-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="33f3e-104">您是否需要为学生和教育部门提供对 Microsoft 团队中的不同功能的访问权限？</span><span class="sxs-lookup"><span data-stu-id="33f3e-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="33f3e-105">你可以按许可证类型快速标识组织中的用户，然后为其分配相应的策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="33f3e-106">本教程介绍如何使用批量[策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)来批量向用户分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="33f3e-107">请记住，在团队中，用户将自动获取团队策略类型的全局（组织范围默认）策略，除非你创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="33f3e-108">由于学生填充通常是最大的一组用户，并且通常会收到限制性最严格的设置，因此我们建议你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33f3e-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="33f3e-109">编辑和应用全局（组织范围默认）策略以限制学生的功能。</span><span class="sxs-lookup"><span data-stu-id="33f3e-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="33f3e-110">创建允许核心功能（如私人聊天和会议计划）的自定义策略，并向您的员工和教育部门分配策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="33f3e-111">请记住，全局策略将应用于你的学校中的所有用户，直到你创建自定义策略并将其分配给你的员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="33f3e-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="33f3e-112">在本教程中，学生将获得全局会议策略，并使用 PowerShell 将名为 EducatorMeetingPolicy 的自定义会议策略分配给教职员工和教育批量。</span><span class="sxs-lookup"><span data-stu-id="33f3e-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="33f3e-113">我们假定你已编辑全局策略，以便为学生自定义会议设置，并创建定义教职员工和教育版会议体验的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![团队管理中心中的 "会议策略" 页面的屏幕截图](media/edu-batch-policy-assignment.png)

<span data-ttu-id="33f3e-115">请按照以下步骤批量向员工和教育部门分配自定义会议策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="33f3e-116">连接到适用于 Graph 模块和团队 PowerShell 模块的 Azure AD PowerShell</span><span class="sxs-lookup"><span data-stu-id="33f3e-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="33f3e-117">在执行本文中的步骤之前，你需要安装并连接到 Azure AD PowerShell for Graph 模块（以通过其分配的许可证标识用户）和 Microsoft 团队 PowerShell 模块的预发布版本（将策略分配给这些用户）。</span><span class="sxs-lookup"><span data-stu-id="33f3e-117">Before you perform the steps in this article, you’ll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the pre-release version of the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="33f3e-118">安装并连接到 Azure AD PowerShell for Graph 模块</span><span class="sxs-lookup"><span data-stu-id="33f3e-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="33f3e-119">打开提升了权限的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell），然后运行以下命令来安装适用于 Graph 模块的 Azure Active Directory PowerShell。</span><span class="sxs-lookup"><span data-stu-id="33f3e-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module AzureAD
```

<span data-ttu-id="33f3e-120">运行以下操作以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="33f3e-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="33f3e-121">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33f3e-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="33f3e-122">若要了解详细信息，请参阅[连接到 Azure Active Directory PowerShell For Graph 模块](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="33f3e-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/eoffice365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="33f3e-123">安装并连接到团队 PowerShell 模块的预发布版本</span><span class="sxs-lookup"><span data-stu-id="33f3e-123">Install and connect to the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="33f3e-124">你需要的 cmdlet 位于团队 PowerShell 模块的预发布版本中。</span><span class="sxs-lookup"><span data-stu-id="33f3e-124">The cmdlets you'll need are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="33f3e-125">按照[安装和连接到 Microsoft 团队 powershell 模块](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)中的步骤，首先卸载团队 powershell 模块的一般可用版本（如果已安装），然后从 PowerShell 测试库安装该模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="33f3e-125">Follow the steps in [Install and connect to the Microsoft Teams PowerShell module](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="33f3e-126">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="33f3e-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="33f3e-127">出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33f3e-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="33f3e-128">标识您的用户</span><span class="sxs-lookup"><span data-stu-id="33f3e-128">Identify your users</span></span>

<span data-ttu-id="33f3e-129">首先，运行以下操作以通过许可证类型标识你的员工和教师。</span><span class="sxs-lookup"><span data-stu-id="33f3e-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="33f3e-130">这将告诉你组织中使用的 Sku。</span><span class="sxs-lookup"><span data-stu-id="33f3e-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="33f3e-131">然后，您可以识别已分配教职员 SKU 的职员和教师。</span><span class="sxs-lookup"><span data-stu-id="33f3e-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

<span data-ttu-id="33f3e-132">返回：</span><span class="sxs-lookup"><span data-stu-id="33f3e-132">Which returns:</span></span>

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="33f3e-133">在此示例中，输出显示教职员许可证 SkuId 为 "e97c048c-37a4-45fb-ab50-922fbf07a370"。</span><span class="sxs-lookup"><span data-stu-id="33f3e-133">In this example, the output shows that the Faculty license SkuId is “e97c048c-37a4-45fb-ab50-922fbf07a370”.</span></span>

> [!NOTE]
> <span data-ttu-id="33f3e-134">若要查看教育 Sku 和 SKU Id 的列表，请参阅[教育 sku 参考](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="33f3e-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="33f3e-135">接下来，我们运行以下内容来确定拥有此许可证的用户，并将它们一起收集。</span><span class="sxs-lookup"><span data-stu-id="33f3e-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains “e97c048c-37a4-45fb-ab50-922fbf07a370”)
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="33f3e-136">批量分配策略</span><span class="sxs-lookup"><span data-stu-id="33f3e-136">Assign a policy in bulk</span></span>

<span data-ttu-id="33f3e-137">现在，我们会批量向用户分配适当的策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="33f3e-138">你可以为其分配或更新策略的最大用户数为每次20000。</span><span class="sxs-lookup"><span data-stu-id="33f3e-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="33f3e-139">例如，如果您有超过20000的员工和教育版，则需要提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="33f3e-139">For example, if you have more than 20,000 staff and educators, you’ll need to submit multiple batches.</span></span>

<span data-ttu-id="33f3e-140">运行以下操作，将名为 EducatorMeetingPolicy 的会议策略分配给你的员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="33f3e-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="33f3e-141">若要批量分配不同的策略类型（如 TeamsMessagingPolicy），你需要更改```PolicyType```为你分配的策略和```PolicyName```策略名称。</span><span class="sxs-lookup"><span data-stu-id="33f3e-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you’ll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="33f3e-142">获取批量作业的状态</span><span class="sxs-lookup"><span data-stu-id="33f3e-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="33f3e-143">每个批量分配都将返回一个操作 ID，您可以使用该 ID 跟踪策略分配的进度，或标识可能出现的任何失败。</span><span class="sxs-lookup"><span data-stu-id="33f3e-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="33f3e-144">例如，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="33f3e-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="33f3e-145">若要查看批处理操作中每个用户的作业状态，请运行以下。</span><span class="sxs-lookup"><span data-stu-id="33f3e-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="33f3e-146">每个用户的详细信息都```UserState```在该属性中。</span><span class="sxs-lookup"><span data-stu-id="33f3e-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="33f3e-147">如果用户超过20000个用户，则批量分配策略</span><span class="sxs-lookup"><span data-stu-id="33f3e-147">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="33f3e-148">首先，运行以下内容查看您拥有的职员和教育人数：</span><span class="sxs-lookup"><span data-stu-id="33f3e-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="33f3e-149">请运行以下操作以指定第一个20000，然后再指定下一个20000，依此类推，而不是提供整个用户 Id 列表。</span><span class="sxs-lookup"><span data-stu-id="33f3e-149">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

<span data-ttu-id="33f3e-150">你可以更改用户 Id 的范围，直到到达用户的完整列表。</span><span class="sxs-lookup"><span data-stu-id="33f3e-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="33f3e-151">例如，输入```$faculty[0..19999```第一个批处理，为第二```$faculty[20000..39999```个批次使用，为```$faculty[40000..59999```第三个批处理输入，依此类推。</span><span class="sxs-lookup"><span data-stu-id="33f3e-151">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="33f3e-152">获取分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="33f3e-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="33f3e-153">运行以下操作，查看分配给特定用户的所有策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="33f3e-154">下面的示例演示如何获取分配给 hannah@contoso.com 的策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="33f3e-155">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="33f3e-155">FAQ</span></span>

<span data-ttu-id="33f3e-156">**我想要确保学生、教职员工和教育版的所有用户都自动获得分配的许可证。如何执行此操作？**</span><span class="sxs-lookup"><span data-stu-id="33f3e-156">**I want to make sure that all users that are students, staff, and educators automatically get licenses assigned. How can I do that?**</span></span>

<span data-ttu-id="33f3e-157">团队产品团队正在执行工作以支持向安全组分配策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="33f3e-158">此时，你将能够为学生和教师创建组，然后为这些组创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-158">At that time, you’ll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="33f3e-159">请注意，显式用户分配（如使用本教程分配的策略）将覆盖从组继承的策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-159">Note that explicit user assignments (such as the policies that you’ve assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="33f3e-160">如果支持此功能，我们将提供更多有关如何使用策略分配到组和更新用户的说明，以确保他们获得继承的组策略。</span><span class="sxs-lookup"><span data-stu-id="33f3e-160">When this feature is supported, we’ll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="33f3e-161">**我不熟悉 PowerShell for 团队。在哪里可以了解更多信息？**</span><span class="sxs-lookup"><span data-stu-id="33f3e-161">**I’m not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="33f3e-162">请参阅[团队 Powershell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="33f3e-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="33f3e-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="33f3e-163">Related topics</span></span>

- [<span data-ttu-id="33f3e-164">为用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33f3e-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="33f3e-165">新-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="33f3e-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="33f3e-166">CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="33f3e-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="33f3e-167">CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="33f3e-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)