---
title: 在 Microsoft Teams 管理中心的活动日志中查看策略分配
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心的活动日志中查看策略分配活动。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821312"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="3600b-103">在活动日志中查看策略分配</span><span class="sxs-lookup"><span data-stu-id="3600b-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="3600b-104">在 Microsoft Teams 管理中心向用户分配策略时，可以在活动日志中查看这些策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="3600b-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="3600b-105">活动日志显示过去 30 天内通过 Microsoft Teams 管理中心向超过 20 个用户批处理的策略分配。</span><span class="sxs-lookup"><span data-stu-id="3600b-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="3600b-106">请记住，活动日志不会通过 Microsoft Teams 管理中心向少于 20 名用户的批次显示策略包分配、策略分配，也不通过 PowerShell 显示策略分配。</span><span class="sxs-lookup"><span data-stu-id="3600b-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

!["活动日志"页的屏幕截图](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="3600b-108">在活动日志中查看策略分配活动</span><span class="sxs-lookup"><span data-stu-id="3600b-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="3600b-109">在活动日志中查看策略分配：</span><span class="sxs-lookup"><span data-stu-id="3600b-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="3600b-110">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"** 仪表板"，然后在"活动日志"下选择 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="3600b-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="3600b-111">可以查看所有策略分配或按状态筛选列表，以只显示未启动、正在进行或已完成 **的分配**。 </span><span class="sxs-lookup"><span data-stu-id="3600b-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="3600b-112">你将看到有关每个作业的以下信息：</span><span class="sxs-lookup"><span data-stu-id="3600b-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="3600b-113">**名称**：策略分配的名称。</span><span class="sxs-lookup"><span data-stu-id="3600b-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="3600b-114">单击该链接可查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="3600b-114">Click the link to view more details.</span></span> <span data-ttu-id="3600b-115">这包括策略分配到的用户数，以及已完成、进行中和未启动的分配数。</span><span class="sxs-lookup"><span data-stu-id="3600b-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="3600b-116">还将看到批处理中的用户列表，以及每个用户的状态和结果。</span><span class="sxs-lookup"><span data-stu-id="3600b-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="3600b-117">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="3600b-117">Here's an example:</span></span>

        ![屏幕截图](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="3600b-119">**已提交**：提交策略分配的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3600b-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="3600b-120">**完成时间**：策略分配的完成日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3600b-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="3600b-121">**影响**：批中的用户数。</span><span class="sxs-lookup"><span data-stu-id="3600b-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="3600b-122">**总体状态**：策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="3600b-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="3600b-123">还可以从"用户"页访问 **活动** 日志。</span><span class="sxs-lookup"><span data-stu-id="3600b-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="3600b-124">单击" **应用** "提交批量策略分配后，页面顶部将会显示一个横幅。</span><span class="sxs-lookup"><span data-stu-id="3600b-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="3600b-125">单击 **横幅中的活动** 日志链接。</span><span class="sxs-lookup"><span data-stu-id="3600b-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3600b-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="3600b-126">Related topics</span></span>

- [<span data-ttu-id="3600b-127">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3600b-127">Assign policies to users</span></span>](assign-policies.md)
