---
title: 使用 Microsoft 团队的网络 Planner
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: 了解如何使用网络规划器确定 Microsoft 团队的网络要求。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aaf2c2c7242c594d67af131d3a15224ddf16419c
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2019
ms.locfileid: "35214820"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="757e2-103">使用 Microsoft 团队的网络 Planner</span><span class="sxs-lookup"><span data-stu-id="757e2-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="757e2-104">欢迎使用网络 Planner。</span><span class="sxs-lookup"><span data-stu-id="757e2-104">Welcome to the Network Planner.</span></span> <span data-ttu-id="757e2-105">通过以下几个步骤, 网络规划器可以帮助你确定和组织在你的组织中连接 Microsoft 团队用户的网络要求。</span><span class="sxs-lookup"><span data-stu-id="757e2-105">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="757e2-106">当你提供网络详细信息和团队使用情况时, 网络 Planner 会计算你的网络要求, 以便在组织的物理位置部署团队和云语音。</span><span class="sxs-lookup"><span data-stu-id="757e2-106">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![网络 Planner 的屏幕截图](media/network-planner.png)

<span data-ttu-id="757e2-108">网络 Planner 允许您:</span><span class="sxs-lookup"><span data-stu-id="757e2-108">Network Planner allows you to:</span></span>

- <span data-ttu-id="757e2-109">使用网站和 Microsoft 推荐的角色 (office 工作人员、远程工作人员和团队室系统) 创建组织的表示形式。</span><span class="sxs-lookup"><span data-stu-id="757e2-109">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="757e2-110">根据团队最佳使用方案和典型使用模式中的数据开发了推荐的角色。</span><span class="sxs-lookup"><span data-stu-id="757e2-110">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="757e2-111">但是, 除了三个推荐的角色外, 你还可以创建最多三个自定义角色。</span><span class="sxs-lookup"><span data-stu-id="757e2-111">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="757e2-112">生成报表并计算团队使用情况的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="757e2-112">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="757e2-113">创建自定义角色</span><span class="sxs-lookup"><span data-stu-id="757e2-113">Create a custom persona</span></span>

<span data-ttu-id="757e2-114">请按照以下步骤创建自定义角色:</span><span class="sxs-lookup"><span data-stu-id="757e2-114">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="757e2-115">转到 Microsoft 团队管理中心中的网络 Planner。</span><span class="sxs-lookup"><span data-stu-id="757e2-115">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="757e2-116">在 "**角色**" 选项卡上, 单击 " **+ 自定义角色**"。</span><span class="sxs-lookup"><span data-stu-id="757e2-116">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="757e2-117">在 "**新建自定义角色**" 窗格中, 为新角色添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="757e2-117">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="757e2-118">选择此角色将在组织内使用的权限。</span><span class="sxs-lookup"><span data-stu-id="757e2-118">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="757e2-119">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="757e2-119">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="757e2-120">构建你的计划</span><span class="sxs-lookup"><span data-stu-id="757e2-120">Build your plan</span></span>

<span data-ttu-id="757e2-121">请按照以下步骤开始构建你的网络计划:</span><span class="sxs-lookup"><span data-stu-id="757e2-121">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="757e2-122">转到 Microsoft 团队管理中心中的网络 Planner。</span><span class="sxs-lookup"><span data-stu-id="757e2-122">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="757e2-123">在 "**网络计划**" 选项卡上, 单击 "**添加网络计划**"。</span><span class="sxs-lookup"><span data-stu-id="757e2-123">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="757e2-124">输入网络计划的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="757e2-124">Enter a name and description for your network plan.</span></span> <span data-ttu-id="757e2-125">"网络计划" 将显示在可用计划列表中。</span><span class="sxs-lookup"><span data-stu-id="757e2-125">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="757e2-126">单击计划名称以选择新计划。</span><span class="sxs-lookup"><span data-stu-id="757e2-126">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="757e2-127">添加网站以创建组织的网络设置的表示形式。</span><span class="sxs-lookup"><span data-stu-id="757e2-127">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="757e2-128">根据您所在组织的网络, 您可能希望使用网站来表示建筑物、办公地点或其他内容。</span><span class="sxs-lookup"><span data-stu-id="757e2-128">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="757e2-129">网站可能通过 WAN 连接, 以允许共享 internet 和/或 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="757e2-129">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="757e2-130">为获得最佳结果, 请先创建具有本地连接的网站, 然后再创建远程连接到 internet 或 PSTN 的网站。</span><span class="sxs-lookup"><span data-stu-id="757e2-130">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="757e2-131">要创建网站, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="757e2-131">To create a site:</span></span>

    1. <span data-ttu-id="757e2-132">为您的网站添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="757e2-132">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="757e2-133">在 "**网络设置**" 下, 添加该站点上的网络用户数 (必需)。</span><span class="sxs-lookup"><span data-stu-id="757e2-133">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="757e2-134">添加网络详细信息: 支持 WAN 的、WAN 容量、internet 出口 (**本地**或**远程**) 以及 PSTN 出口 (无、本地或远程)。</span><span class="sxs-lookup"><span data-stu-id="757e2-134">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="757e2-135">你必须添加 WAN 和 internet 容量数字, 才能在生成报告时查看特定的带宽建议。</span><span class="sxs-lookup"><span data-stu-id="757e2-135">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="757e2-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="757e2-136">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="757e2-137">创建报表</span><span class="sxs-lookup"><span data-stu-id="757e2-137">Create a report</span></span>

<span data-ttu-id="757e2-138">添加所有网站后, 您可以创建报表, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="757e2-138">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="757e2-139">在 "**报表**" 选项卡上, 单击 "**开始报表**"。</span><span class="sxs-lookup"><span data-stu-id="757e2-139">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="757e2-140">对于创建的每个网站, 在可用的角色间分配用户数。</span><span class="sxs-lookup"><span data-stu-id="757e2-140">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="757e2-141">如果您使用 Microsoft 推荐的角色, 该号码将自动分发 (80% 的 office 工作人员和 20% 的远程工作人员)。</span><span class="sxs-lookup"><span data-stu-id="757e2-141">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="757e2-142">完成分发后, 单击 "**生成报表**"。</span><span class="sxs-lookup"><span data-stu-id="757e2-142">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="757e2-143">生成的报表将显示多个不同视图中的带宽要求, 以便你可以清楚地了解输出:</span><span class="sxs-lookup"><span data-stu-id="757e2-143">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="757e2-144">具有单个计算的表将显示每个允许的活动的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="757e2-144">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="757e2-145">其他视图将显示具有建议的整体带宽需求。</span><span class="sxs-lookup"><span data-stu-id="757e2-145">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="757e2-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="757e2-146">Click **Save**.</span></span> <span data-ttu-id="757e2-147">报表将在 "报表" 列表中提供, 供以后查看。</span><span class="sxs-lookup"><span data-stu-id="757e2-147">Your report will be available on the reports list for later viewing.</span></span>
