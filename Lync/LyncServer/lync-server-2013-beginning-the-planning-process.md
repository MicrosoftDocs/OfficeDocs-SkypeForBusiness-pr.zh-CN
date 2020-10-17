---
title: Lync Server 2013：开始规划过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513035"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="339a9-102">开始 Lync Server 2013 的规划过程</span><span class="sxs-lookup"><span data-stu-id="339a9-102">Beginning the planning process for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="339a9-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="339a9-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="339a9-104">尽管在规划本地统一通信部署可能看起来 intimidating，Lync Server 提供了两个有用的工具来帮助您：</span><span class="sxs-lookup"><span data-stu-id="339a9-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="339a9-105">**规划工具** 是一个向导，它提供有关您的组织、您要启用的 Lync Server 功能以及容量规划需求的一系列问题。</span><span class="sxs-lookup"><span data-stu-id="339a9-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="339a9-106">然后，它根据你的回答创建建议的部署拓扑，并生成此部署的 Microsoft Visio 关系图。</span><span class="sxs-lookup"><span data-stu-id="339a9-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="339a9-107">**拓扑生成器** 是 Lync Server 的安装组件。</span><span class="sxs-lookup"><span data-stu-id="339a9-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="339a9-108">您可以使用拓扑生成器来创建、调整和发布规划的拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="339a9-109">该工具还可以在开始安装服务器之前验证您的拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="339a9-110">在单独的服务器上安装 Lync Server 时，服务器会在安装过程中读取已发布的拓扑，并且安装程序将在拓扑中按照指示的方式部署服务器。</span><span class="sxs-lookup"><span data-stu-id="339a9-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="339a9-111">Lync Server 规划工具</span><span class="sxs-lookup"><span data-stu-id="339a9-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="339a9-112">规划工具将获取工具中问题的答案，并根据 Lync Server 指南和最佳实践生成拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="339a9-113">它还根据您的回答提供了多个部署视图。</span><span class="sxs-lookup"><span data-stu-id="339a9-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="339a9-114">它同时显示了所有网站 (的全局视图，包括中央网站和分支网站) ，以及显示每个网站上的服务器和其他组件的详细视图。</span><span class="sxs-lookup"><span data-stu-id="339a9-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="339a9-115">运行规划工具不会向您提交任何特定部署，也不会启动任何进程。</span><span class="sxs-lookup"><span data-stu-id="339a9-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="339a9-116">事实上，即使在您有一个固定计划之前运行规划工具，也可能是了解您在规划过程中需要考虑的问题种类的一种非常有益的方法。</span><span class="sxs-lookup"><span data-stu-id="339a9-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="339a9-117">您可以多次运行规划工具，以不同的方式回答问题，并比较结果。</span><span class="sxs-lookup"><span data-stu-id="339a9-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="339a9-118">如果你的设计最常用，但你需要对进行更改，则可以返回到规划工具，加载设计，然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="339a9-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="339a9-119">完成规划工具一次大约需要15分钟时间。</span><span class="sxs-lookup"><span data-stu-id="339a9-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="339a9-120">在您满意后，您可以使用规划工具创建规划的部署的关系图。</span><span class="sxs-lookup"><span data-stu-id="339a9-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="339a9-121">在拓扑生成器中创建部署时，可以使用此关系图。</span><span class="sxs-lookup"><span data-stu-id="339a9-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="339a9-122">此版本的 Lync Server 2013 中包含的规划工具是预发布版本。</span><span class="sxs-lookup"><span data-stu-id="339a9-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="339a9-123">请注意，规划工具中的容量规划数量是初步的，并且在最终版本中不受支持。</span><span class="sxs-lookup"><span data-stu-id="339a9-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="339a9-124">Lync Server 拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="339a9-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="339a9-125">在确定了部署计划后，使用拓扑生成器开始部署。</span><span class="sxs-lookup"><span data-stu-id="339a9-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="339a9-126">完成后，使用拓扑生成器验证拓扑，然后，如果它通过，则可以发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="339a9-127">发布拓扑时，Lync Server 会将拓扑放到中央管理存储中，如果目前尚不存在，则会创建该拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="339a9-128">当您在部署中的每台服务器上安装 Lync Server 时，服务器将从中央管理存储读取拓扑，并自行安装以适应其在您的部署中的角色。</span><span class="sxs-lookup"><span data-stu-id="339a9-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="339a9-129">或者，如果您非常熟悉 Lync Server，并且需要更少的说明性指导，则可以跳过规划工具并使用拓扑生成器中的向导进行部署的初始设计，还可以使用验证和发布步骤。</span><span class="sxs-lookup"><span data-stu-id="339a9-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="339a9-130">使用拓扑生成器来规划和发布拓扑是必需的步骤。</span><span class="sxs-lookup"><span data-stu-id="339a9-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="339a9-131">您不能绕过拓扑生成器并在部署中的服务器上单独安装 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="339a9-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="339a9-132">每台服务器必须从中央管理存储中已验证的已发布拓扑中读取拓扑。</span><span class="sxs-lookup"><span data-stu-id="339a9-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="339a9-133">High-Level 规划过程</span><span class="sxs-lookup"><span data-stu-id="339a9-133">High-Level Planning Process</span></span>

<span data-ttu-id="339a9-134">我们建议使用以下常规过程来规划 Lync Server 部署，同时使用文档和规划工具。</span><span class="sxs-lookup"><span data-stu-id="339a9-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="339a9-135">如果您熟悉 Lync Server 的早期版本，请阅读 [lync server 2013 中的新功能](lync-server-2013-new-features.md) ，以熟悉 lync server 2013 中的新功能和要求。</span><span class="sxs-lookup"><span data-stu-id="339a9-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="339a9-136">阅读本文档的本部分中的其他主题： [规划 Lync server 2013 之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)、 [lync server 2013 的初始规划决定](lync-server-2013-initial-planning-decisions.md)以及 [lync server 2013 的客户端](lync-server-2013-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="339a9-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="339a9-137">请注意 [Lync Server 2013 中的参考拓扑中](lync-server-2013-reference-topologies.md)所示的规划决策。</span><span class="sxs-lookup"><span data-stu-id="339a9-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="339a9-138">现在，您更熟悉 Lync Server 功能以及必须回答的问题种类，请运行规划工具并查看生成的拓扑及其详细信息。</span><span class="sxs-lookup"><span data-stu-id="339a9-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="339a9-139">确保拓扑符合组织的独特要求。</span><span class="sxs-lookup"><span data-stu-id="339a9-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="339a9-140">如果有您感兴趣或需要了解的特定工作负荷或功能，请阅读 [规划 Lync Server 2013](lync-server-2013-planning.md)的相应部分。</span><span class="sxs-lookup"><span data-stu-id="339a9-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="339a9-141">再次运行规划工具。</span><span class="sxs-lookup"><span data-stu-id="339a9-141">Run the Planning Tool again.</span></span> <span data-ttu-id="339a9-142">您可以从在步骤3中创建的部署开始，并修改结果，也可以从头开始。</span><span class="sxs-lookup"><span data-stu-id="339a9-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="339a9-143">如果需要，请第三次运行规划工具并重复此操作，直到您对输出结果感到满意。</span><span class="sxs-lookup"><span data-stu-id="339a9-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="339a9-144">完成拓扑计划后，请使用规划工具创建并打印您的拓扑的 Visio 图表。</span><span class="sxs-lookup"><span data-stu-id="339a9-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="339a9-145">在使用拓扑生成器来输入拓扑时，可以使用此打印输出。</span><span class="sxs-lookup"><span data-stu-id="339a9-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="339a9-146">在开始部署之前，请阅读 [确定 Lync server 2013 的系统要求](lync-server-2013-determining-your-system-requirements.md) ，并 [确定 lync server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md) ，以熟悉 lync server 的先决条件和必要的基础结构。</span><span class="sxs-lookup"><span data-stu-id="339a9-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="339a9-147">此外，请务必阅读适用于计划部署的工作负荷和功能的所有 [规划的 Lync Server 2013](lync-server-2013-planning.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="339a9-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="339a9-148">从以前的版本迁移</span><span class="sxs-lookup"><span data-stu-id="339a9-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="339a9-149">如果要从以前的版本迁移到 Lync Server，请参阅 [迁移](migration.md) 文档以获取有关迁移和部署的特定说明。</span><span class="sxs-lookup"><span data-stu-id="339a9-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

