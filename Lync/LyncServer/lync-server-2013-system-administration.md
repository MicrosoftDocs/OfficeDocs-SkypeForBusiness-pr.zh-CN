---
title: 'Lync Server 2013: 系统管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="d60a5-102">Lync Server 2013 中的系统管理</span><span class="sxs-lookup"><span data-stu-id="d60a5-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d60a5-103">_**主题上次修改时间:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="d60a5-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="d60a5-104">系统管理包括日常管理任务 (计划和按需), 使 IT 系统保持平稳运行是必需的。</span><span class="sxs-lookup"><span data-stu-id="d60a5-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="d60a5-105">通常情况下, 系统管理任务由书面过程覆盖。</span><span class="sxs-lookup"><span data-stu-id="d60a5-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="d60a5-106">这些过程有助于确保所有支持人员都使用相同的标准工具和方法。</span><span class="sxs-lookup"><span data-stu-id="d60a5-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="d60a5-107">在 Lync 环境中, 典型的系统管理任务包括备份和存档池、监视日志、创建和管理用户以及更新防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="d60a5-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="d60a5-108">系统疑难解答</span><span class="sxs-lookup"><span data-stu-id="d60a5-108">System troubleshooting</span></span>

<span data-ttu-id="d60a5-109">组织必须准备好处理意外问题, 并且应该有一个过程来从报告问题的位置管理问题, 直到其解决。</span><span class="sxs-lookup"><span data-stu-id="d60a5-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="d60a5-110">有关诊断问题的支持人员的信息应在将来记录和使用, 以避免不必要的重复工作。</span><span class="sxs-lookup"><span data-stu-id="d60a5-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="d60a5-111">系统故障排除过程</span><span class="sxs-lookup"><span data-stu-id="d60a5-111">System troubleshooting process</span></span>

<span data-ttu-id="d60a5-112">下图显示了系统疑难解答过程以及与其他操作角色的交互。</span><span class="sxs-lookup"><span data-stu-id="d60a5-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="d60a5-113">**系统疑难解答流程图**</span><span class="sxs-lookup"><span data-stu-id="d60a5-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="d60a5-114">![系统疑难解答流程图](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系统疑难解答流程图")</span><span class="sxs-lookup"><span data-stu-id="d60a5-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="d60a5-115">**对此任务进行分类和设置优先级**   通常由服务台执行。</span><span class="sxs-lookup"><span data-stu-id="d60a5-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="d60a5-116">例如, 问题可能会被分组为软件问题或硬件问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="d60a5-117">然后, 该问题将路由到相应的支持团队进行调查。</span><span class="sxs-lookup"><span data-stu-id="d60a5-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="d60a5-118">确定问题优先级的规则以及响应时间和解决时间的规则通常在 SLA 中定义。</span><span class="sxs-lookup"><span data-stu-id="d60a5-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="d60a5-119">**调查和诊断**   相应的支持团队诊断问题并建议更改以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="d60a5-120">如果解决方案非常简单, 并且不需要更改控制, 则可以立即应用该解决方案。</span><span class="sxs-lookup"><span data-stu-id="d60a5-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="d60a5-121">如果解决方案不是很简单, 则应引发更改请求, 并且建议的工作应由更改管理过程进行管理, 这些过程通常位于 "快速跟踪" 过程下方。</span><span class="sxs-lookup"><span data-stu-id="d60a5-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="d60a5-122">应使用配置管理过程记录所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d60a5-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="d60a5-123">**关闭并录制**   测试分辨率后, 应关闭问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="d60a5-124">如果有从问题中学到的课程, 则应在知识库中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="d60a5-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="d60a5-125">**查看和趋势分析**   定期检查最近的问题, 以确定问题趋势。</span><span class="sxs-lookup"><span data-stu-id="d60a5-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="d60a5-126">例如, 如果用户经常遇到一些对其 Lync 网站的登录速度较慢的问题, 则可能是网络带宽问题造成的。</span><span class="sxs-lookup"><span data-stu-id="d60a5-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="d60a5-127">解决问题的时间和对系统可用性的任何停机的影响都应进行检查, 并与 SLA 进行比较。</span><span class="sxs-lookup"><span data-stu-id="d60a5-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="d60a5-128">与客户 liaises 服务问题 (如客户经理) 的人员应了解任何重大问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="d60a5-129">问题管理工具</span><span class="sxs-lookup"><span data-stu-id="d60a5-129">Issue management tools</span></span>

<span data-ttu-id="d60a5-130">服务台工具使教职员工能够记录、分类和优先处理新问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="d60a5-131">然后, 工具将通过调查和诊断提供工作流流程来管理问题服务请求, 这种情况通常由多个支持团队提供。</span><span class="sxs-lookup"><span data-stu-id="d60a5-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="d60a5-132">工具 (通常提供有关分辨率时间和历史趋势的报表) 也可能包含知识库数据库, 可用于搜索过去的问题。</span><span class="sxs-lookup"><span data-stu-id="d60a5-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="d60a5-133">Microsoft 知识库是 Microsoft 所遇到的支持问题的有用记录。</span><span class="sxs-lookup"><span data-stu-id="d60a5-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="d60a5-134">有关详细信息, 请参阅 Microsoft 支持网站 (<http://go.microsoft.com/fwlink/?linkid=14898>)。</span><span class="sxs-lookup"><span data-stu-id="d60a5-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="d60a5-135">第三方软件通常需要自定义以满足组织的需求, 例如团队的组织、报告要求和 SLA 所需的度量。</span><span class="sxs-lookup"><span data-stu-id="d60a5-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="d60a5-136">集中管理和分散式管理</span><span class="sxs-lookup"><span data-stu-id="d60a5-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="d60a5-137">执行系统管理任务的角色和职责取决于组织关注的是集中式模型、分散模型还是两者的组合。</span><span class="sxs-lookup"><span data-stu-id="d60a5-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="d60a5-138">**集中式模型**   在集中式模型中, 一个或多个管理组保持对整个 Lync 服务器环境的完全控制。</span><span class="sxs-lookup"><span data-stu-id="d60a5-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="d60a5-139">此管理模型类似于一个数据中心, 其中的所有管理任务均由单个信息技术组执行。</span><span class="sxs-lookup"><span data-stu-id="d60a5-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="d60a5-140">应根据经验和专业知识定义团队中的角色和职责。</span><span class="sxs-lookup"><span data-stu-id="d60a5-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="d60a5-141">**分散式模型**   分散的组织位于多个地理位置, 并且在不同位置有运行的 Lync 服务器服务器和团队。</span><span class="sxs-lookup"><span data-stu-id="d60a5-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="d60a5-142">例如, 可能有本地管理人员和一个或多个运行 Lync Server 2013 的服务器用于每个国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d60a5-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="d60a5-143">或者, 可能有运行 Lync Server 2013 的服务器池和北美和欧洲的管理团队。</span><span class="sxs-lookup"><span data-stu-id="d60a5-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="d60a5-144">有时, 你可能希望管理员仅负责自己的地理区域, 并限制管理其他区域中的资源的权限。</span><span class="sxs-lookup"><span data-stu-id="d60a5-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="d60a5-145">Lync 服务器还允许你通过使用基于角色的访问控制 (RBAC) 将特定的管理任务委派给特定人员或组。</span><span class="sxs-lookup"><span data-stu-id="d60a5-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="d60a5-146">RBAC 允许管理员向其他管理员委派特定的用户权利和权限, 以执行可能的管理任务的子集。</span><span class="sxs-lookup"><span data-stu-id="d60a5-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="d60a5-147">通过使用 RBAC, 用户执行特定管理任务的能力取决于分配给用户的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d60a5-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="d60a5-148">RBAC 提供用户可以根据用户所属的 RBAC 角色运行的 cmdlet 的列表。</span><span class="sxs-lookup"><span data-stu-id="d60a5-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

