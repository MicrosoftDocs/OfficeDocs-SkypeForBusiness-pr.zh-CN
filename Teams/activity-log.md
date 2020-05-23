---
title: 在 Microsoft 团队管理中心的活动日志中查看你的策略分配
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft 团队管理中心的活动日志中查看策略分配活动。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350067"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="7e4aa-103">查看活动日志中的策略分配</span><span class="sxs-lookup"><span data-stu-id="7e4aa-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="7e4aa-104">向 Microsoft 团队管理中心中的用户分配策略时，可以在活动日志中查看这些策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="7e4aa-105">活动日志显示过去30天内通过 Microsoft 团队管理中心向超过20名用户批处理的策略分配。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="7e4aa-106">请注意，活动日志未显示策略程序包分配、策略分配，可通过 Microsoft 团队管理中心的用户数少于20个用户，或通过 PowerShell 进行策略分配。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![活动日志页的屏幕截图](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="7e4aa-108">在活动日志中查看策略分配活动</span><span class="sxs-lookup"><span data-stu-id="7e4aa-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="7e4aa-109">要查看活动日志中的策略分配，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7e4aa-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="7e4aa-110">在 Microsoft 团队管理中心的左侧导航中，转到**仪表板**，然后在 "**活动日志**" 下，选择 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="7e4aa-111">你可以查看所有策略分配或按状态筛选列表，以仅显示**未开始**、**正在进行**或**已完成**的作业。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="7e4aa-112">你将看到有关每个作业的以下信息：</span><span class="sxs-lookup"><span data-stu-id="7e4aa-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="7e4aa-113">**名称**：策略分配的名称。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="7e4aa-114">单击链接以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-114">Click the link to view more details.</span></span> <span data-ttu-id="7e4aa-115">其中包括分配了该策略的用户数以及已完成的作业数、正在进行的作业数以及未开始的作业数。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="7e4aa-116">你还将看到批中的用户列表，以及每个用户的状态和结果。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="7e4aa-117">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="7e4aa-117">Here's an example:</span></span>

        ![的屏幕截图](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="7e4aa-119">已**提交**：提交策略分配的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="7e4aa-120">**完成时间**：策略分配完成的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="7e4aa-121">**影响**：批处理中的用户数。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="7e4aa-122">**总体状态**：策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="7e4aa-123">您也可以从 "**用户**" 页面访问活动日志。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="7e4aa-124">单击 "**应用**" 以提交批量策略分配后，将在页面顶部看到横幅。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="7e4aa-125">单击横幅中的 "**活动日志**" 链接。</span><span class="sxs-lookup"><span data-stu-id="7e4aa-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e4aa-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e4aa-126">Related topics</span></span>

- [<span data-ttu-id="7e4aa-127">为用户分配策略</span><span class="sxs-lookup"><span data-stu-id="7e4aa-127">Assign policies to users</span></span>](assign-policies.md)
