---
title: 使用 Microsoft 团队的网络 planner
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理员可以了解如何使用网络规划器确定 Microsoft 团队的网络要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611796"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="e56b6-103">使用 Microsoft 团队的网络 planner</span><span class="sxs-lookup"><span data-stu-id="e56b6-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="e56b6-104">网络规划器是团队管理中心提供的新工具。</span><span class="sxs-lookup"><span data-stu-id="e56b6-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="e56b6-105">可通过 **规划**  >  **网络 planner** 找到它。</span><span class="sxs-lookup"><span data-stu-id="e56b6-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="e56b6-106">通过以下几个步骤，网络规划器可以帮助你确定和组织在你的组织中连接 Microsoft 团队用户的网络要求。</span><span class="sxs-lookup"><span data-stu-id="e56b6-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="e56b6-107">当你提供网络详细信息和团队使用情况时，网络 Planner 会计算你的网络要求，以便在组织的物理位置部署团队和云语音。</span><span class="sxs-lookup"><span data-stu-id="e56b6-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![网络 planner 的屏幕截图](media/network-planner.png)

<span data-ttu-id="e56b6-109">网络 planner 允许您：</span><span class="sxs-lookup"><span data-stu-id="e56b6-109">Network planner allows you to:</span></span>

- <span data-ttu-id="e56b6-110">使用网站和 Microsoft 推荐的角色 (office 工作人员、远程工作人员和团队间系统) 来创建组织的表示形式。</span><span class="sxs-lookup"><span data-stu-id="e56b6-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e56b6-111">根据团队最佳使用方案和典型使用模式中的数据开发了推荐的角色。</span><span class="sxs-lookup"><span data-stu-id="e56b6-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="e56b6-112">但是，除了三个推荐的角色外，你还可以创建最多三个自定义角色。</span><span class="sxs-lookup"><span data-stu-id="e56b6-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="e56b6-113">生成报表并计算团队使用情况的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="e56b6-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="e56b6-114">若要使用网络 planner，您必须是全局管理员、团队服务管理员或团队通信管理员。</span><span class="sxs-lookup"><span data-stu-id="e56b6-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="e56b6-115">创建自定义角色</span><span class="sxs-lookup"><span data-stu-id="e56b6-115">Create a custom persona</span></span>

<span data-ttu-id="e56b6-116">请按照以下步骤创建自定义角色：</span><span class="sxs-lookup"><span data-stu-id="e56b6-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="e56b6-117">转到 Microsoft 团队管理中心中的网络 planner。</span><span class="sxs-lookup"><span data-stu-id="e56b6-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="e56b6-118">在 " **角色** " 选项卡上，单击 " **+ 自定义角色**"。</span><span class="sxs-lookup"><span data-stu-id="e56b6-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="e56b6-119">在 " **新建自定义角色** " 窗格中，为新角色添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e56b6-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="e56b6-120">选择此角色将在组织内使用的权限。</span><span class="sxs-lookup"><span data-stu-id="e56b6-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="e56b6-121">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e56b6-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="e56b6-122">构建你的计划</span><span class="sxs-lookup"><span data-stu-id="e56b6-122">Build your plan</span></span>

<span data-ttu-id="e56b6-123">请按照以下步骤开始构建你的网络计划：</span><span class="sxs-lookup"><span data-stu-id="e56b6-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="e56b6-124">转到 Microsoft 团队管理中心中的网络 planner。</span><span class="sxs-lookup"><span data-stu-id="e56b6-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="e56b6-125">在 " **网络计划** " 选项卡上，单击 " **添加网络计划**"。</span><span class="sxs-lookup"><span data-stu-id="e56b6-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="e56b6-126">输入网络计划的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e56b6-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="e56b6-127">"网络计划" 将显示在可用计划列表中。</span><span class="sxs-lookup"><span data-stu-id="e56b6-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="e56b6-128">单击计划名称以选择新计划。</span><span class="sxs-lookup"><span data-stu-id="e56b6-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="e56b6-129">添加网站以创建组织的网络设置的表示形式。</span><span class="sxs-lookup"><span data-stu-id="e56b6-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="e56b6-130">根据您所在组织的网络，您可能希望使用网站来表示建筑物、办公地点或其他内容。</span><span class="sxs-lookup"><span data-stu-id="e56b6-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="e56b6-131">网站可能通过 WAN 连接，以允许共享 internet 和/或 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="e56b6-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="e56b6-132">为获得最佳结果，请先创建具有本地连接的网站，然后再创建远程连接到 internet 或 PSTN 的网站。</span><span class="sxs-lookup"><span data-stu-id="e56b6-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="e56b6-133">要创建网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e56b6-133">To create a site:</span></span>

    1. <span data-ttu-id="e56b6-134">为您的网站添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e56b6-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="e56b6-135">在 " **网络设置**" 下，将该网站上的网络用户数量添加 (必需的) 。</span><span class="sxs-lookup"><span data-stu-id="e56b6-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="e56b6-136">添加网络详细信息：支持 WAN、WAN 容量、internet 出口 (**本地** 或 **远程**) 以及 PSTN 出局 (无、本地或远程) 。</span><span class="sxs-lookup"><span data-stu-id="e56b6-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="e56b6-137">你必须添加 WAN 和 internet 容量数字，才能在生成报告时查看特定的带宽建议。</span><span class="sxs-lookup"><span data-stu-id="e56b6-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="e56b6-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e56b6-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="e56b6-139">创建报表</span><span class="sxs-lookup"><span data-stu-id="e56b6-139">Create a report</span></span>

<span data-ttu-id="e56b6-140">添加所有网站后，您可以创建报表，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e56b6-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="e56b6-141">在 " **报表** " 选项卡上，单击 " **开始报表**"。</span><span class="sxs-lookup"><span data-stu-id="e56b6-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="e56b6-142">对于创建的每个网站，在可用的角色间分配用户数。</span><span class="sxs-lookup"><span data-stu-id="e56b6-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="e56b6-143">如果你使用 Microsoft 推荐的角色，该数字将自动分发 (80% office 工作线程和20% 的远程工作) 。</span><span class="sxs-lookup"><span data-stu-id="e56b6-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="e56b6-144">完成分发后，单击 " **生成报表**"。</span><span class="sxs-lookup"><span data-stu-id="e56b6-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="e56b6-145">生成的报表将显示多个不同视图中的带宽要求，以便你可以清楚地了解输出：</span><span class="sxs-lookup"><span data-stu-id="e56b6-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="e56b6-146">具有单个计算的表将显示每个允许的活动的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="e56b6-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="e56b6-147">其他视图将显示具有建议的整体带宽需求。</span><span class="sxs-lookup"><span data-stu-id="e56b6-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="e56b6-148">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e56b6-148">Click **Save**.</span></span> <span data-ttu-id="e56b6-149">报表将在 "报表" 列表中提供，供以后查看。</span><span class="sxs-lookup"><span data-stu-id="e56b6-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e56b6-150">示例方案</span><span class="sxs-lookup"><span data-stu-id="e56b6-150">Example scenario</span></span>

<span data-ttu-id="e56b6-151">有关如何使用网络计划程序设置网络计划并使用这些步骤生成报表的示例，请下载 [网络 planner How-To PowerPoint 幻灯片](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) "仅 (英语") 。</span><span class="sxs-lookup"><span data-stu-id="e56b6-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
