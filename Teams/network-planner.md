---
title: 使用网络规划器Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理员可以了解如何使用网络规划器来确定网络Microsoft Teams。
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240475"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="25baa-103">使用网络规划器Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25baa-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="25baa-104">网络规划器是一个新的工具，可在 Teams管理中心使用。</span><span class="sxs-lookup"><span data-stu-id="25baa-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="25baa-105">可以通过访问规划网络规划器  >  **找到它**。</span><span class="sxs-lookup"><span data-stu-id="25baa-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="25baa-106">只需几个步骤，网络规划器就可以帮助你确定和组织连接组织中Microsoft Teams用户的网络要求。</span><span class="sxs-lookup"><span data-stu-id="25baa-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="25baa-107">只要您提供网络的详细信息和 Teams 的使用场景，网络规划器便会计算出在您组织的所有地点部署 Teams 和云语音的网络要求。</span><span class="sxs-lookup"><span data-stu-id="25baa-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![网络规划器屏幕截图](media/network-planner.png)

<span data-ttu-id="25baa-109">网络规划器允许：</span><span class="sxs-lookup"><span data-stu-id="25baa-109">Network planner allows you to:</span></span>

- <span data-ttu-id="25baa-110">使用网站和 Microsoft 推荐角色创建组织的表示形式 (办公室工作人员、远程工作人员以及Teams聊天室) 。</span><span class="sxs-lookup"><span data-stu-id="25baa-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="25baa-111">推荐角色是根据最佳使用方案和典型Teams数据开发的。</span><span class="sxs-lookup"><span data-stu-id="25baa-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="25baa-112">但是，除了三个推荐角色外，还可以创建最多三个自定义角色。</span><span class="sxs-lookup"><span data-stu-id="25baa-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="25baa-113">生成报告并计算使用情况Teams要求。</span><span class="sxs-lookup"><span data-stu-id="25baa-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="25baa-114">若要使用网络规划器，你必须是全局管理员、Teams管理员或Teams管理员。</span><span class="sxs-lookup"><span data-stu-id="25baa-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="25baa-115">创建自定义角色</span><span class="sxs-lookup"><span data-stu-id="25baa-115">Create a custom persona</span></span>

<span data-ttu-id="25baa-116">按照以下步骤创建自定义角色：</span><span class="sxs-lookup"><span data-stu-id="25baa-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="25baa-117">转到管理中心内Microsoft Teams规划器。</span><span class="sxs-lookup"><span data-stu-id="25baa-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="25baa-118">在"**角色"选项卡上**，单击 **"+ 自定义角色"。**</span><span class="sxs-lookup"><span data-stu-id="25baa-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="25baa-119">在 **"新建自定义角色"** 窗格中，添加新角色的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="25baa-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="25baa-120">选择此角色将在组织中使用的权限。</span><span class="sxs-lookup"><span data-stu-id="25baa-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="25baa-121">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="25baa-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="25baa-122">构建计划</span><span class="sxs-lookup"><span data-stu-id="25baa-122">Build your plan</span></span>

<span data-ttu-id="25baa-123">请按照以下步骤开始构建网络计划：</span><span class="sxs-lookup"><span data-stu-id="25baa-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="25baa-124">转到管理中心内Microsoft Teams规划器。</span><span class="sxs-lookup"><span data-stu-id="25baa-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="25baa-125">在"**网络计划"** 选项卡上，单击 **"添加网络计划"。**</span><span class="sxs-lookup"><span data-stu-id="25baa-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="25baa-126">输入网络计划的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="25baa-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="25baa-127">网络计划将显示在可用计划列表中。</span><span class="sxs-lookup"><span data-stu-id="25baa-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="25baa-128">单击计划名称以选择新计划。</span><span class="sxs-lookup"><span data-stu-id="25baa-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="25baa-129">添加网站以创建组织网络设置的表示形式。</span><span class="sxs-lookup"><span data-stu-id="25baa-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="25baa-130">根据组织的网络，你可能希望使用网站来表示建筑物、办公室位置或其他内容。</span><span class="sxs-lookup"><span data-stu-id="25baa-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="25baa-131">站点可能通过 WAN 进行连接，以允许共享 Internet 和/或 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="25baa-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="25baa-132">为获得最佳结果，请创建具有本地连接的网站，然后再创建远程连接到 Internet 或 PSTN 的网站。</span><span class="sxs-lookup"><span data-stu-id="25baa-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="25baa-133">创建网站：</span><span class="sxs-lookup"><span data-stu-id="25baa-133">To create a site:</span></span>

    1. <span data-ttu-id="25baa-134">为网站添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="25baa-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="25baa-135">在 **"网络** 设置"下，添加该站点中所需的 (用户) 。</span><span class="sxs-lookup"><span data-stu-id="25baa-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="25baa-136">添加网络详细信息：启用 WAN、WAN 容量、Internet 出口 (**本地** 或远程 **) ，** 以及 PSTN (无、本地或远程) 。</span><span class="sxs-lookup"><span data-stu-id="25baa-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="25baa-137">必须添加 WAN 和 Internet 容量编号，在生成报告时查看特定的带宽建议。</span><span class="sxs-lookup"><span data-stu-id="25baa-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="25baa-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="25baa-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="25baa-139">创建报表</span><span class="sxs-lookup"><span data-stu-id="25baa-139">Create a report</span></span>

<span data-ttu-id="25baa-140">添加所有网站后，可以创建报表，如下所示。</span><span class="sxs-lookup"><span data-stu-id="25baa-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="25baa-141">在"**报表"选项卡** 上，单击 **"启动报表"。**</span><span class="sxs-lookup"><span data-stu-id="25baa-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="25baa-142">对于您创建的每个网站，跨可用角色分配用户数。</span><span class="sxs-lookup"><span data-stu-id="25baa-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="25baa-143">如果使用 Microsoft 推荐的角色，该数字将自动 (80% 的办公人员以及 20% 的远程) 。</span><span class="sxs-lookup"><span data-stu-id="25baa-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="25baa-144">完成分发后，单击"生成 **报表"。**</span><span class="sxs-lookup"><span data-stu-id="25baa-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="25baa-145">生成的报告将在多个不同的视图中显示带宽要求，以便可以清楚地了解输出：</span><span class="sxs-lookup"><span data-stu-id="25baa-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="25baa-146">包含单个计算的表将显示每个允许活动的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="25baa-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="25baa-147">其他视图会显示总体带宽需求以及建议。</span><span class="sxs-lookup"><span data-stu-id="25baa-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="25baa-148">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="25baa-148">Click **Save**.</span></span> <span data-ttu-id="25baa-149">报表将在报表列表中提供，供以后查看。</span><span class="sxs-lookup"><span data-stu-id="25baa-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="25baa-150">应用场景示例</span><span class="sxs-lookup"><span data-stu-id="25baa-150">Example scenario</span></span>

<span data-ttu-id="25baa-151">有关如何使用网络规划器设置网络计划并使用这些步骤生成报表的示例，请仅下载"网络规划器How-To PowerPoint[幻灯片](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (英语) 。</span><span class="sxs-lookup"><span data-stu-id="25baa-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
