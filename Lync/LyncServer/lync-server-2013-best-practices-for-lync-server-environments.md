---
title: 'Lync Server 2013: Lync Server 环境的最佳做法'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="a26a0-102">Lync Server 2013 环境的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a26a0-102">Best practices for Lync Server 2013 environments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a26a0-103">_**主题上次修改时间:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="a26a0-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="a26a0-104">应将以下常规原则应用于系统的日常操作:</span><span class="sxs-lookup"><span data-stu-id="a26a0-104">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="a26a0-105">**了解和使用 mof**   mof 是最佳做法、原则和模型的集合, 提供有关 IT 资产管理的技术指导 (如每天 Lync Server 2013 操作)。</span><span class="sxs-lookup"><span data-stu-id="a26a0-105">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="a26a0-106">遵循 MOF 指南可帮助你为 Microsoft 产品实现任务关键型生产系统的可靠性、可用性、支持性和可管理性。</span><span class="sxs-lookup"><span data-stu-id="a26a0-106">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="a26a0-107">有关详细信息, 请参阅[Microsoft 操作框架 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)。</span><span class="sxs-lookup"><span data-stu-id="a26a0-107">For more information, see [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="a26a0-108">**了解 lync server 2013**   的最佳做法我们建议你实施实践和经验证的过程来管理 lync server 2013。</span><span class="sxs-lookup"><span data-stu-id="a26a0-108">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="a26a0-109">通过使用已尝试、经过测试和记录的方法管理操作, 可能比开发自己的方法更高效。</span><span class="sxs-lookup"><span data-stu-id="a26a0-109">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="a26a0-110">**将操作分为每天、每周和每月进程**   记录您定期执行的所需操作任务。</span><span class="sxs-lookup"><span data-stu-id="a26a0-110">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="a26a0-111">记录如何执行任务有助于确保你的信息在操作环境中发生更改时 (如部署新技术或发生人员更改时) 保留。</span><span class="sxs-lookup"><span data-stu-id="a26a0-111">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="a26a0-112">我们建议将操作任务分为每天、每周和每月执行任务的可管理工作负荷。</span><span class="sxs-lookup"><span data-stu-id="a26a0-112">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="a26a0-113">每日任务将重点关注系统的运行, 每月任务的重点都将更详细地介绍了如何确保系统长期运行。</span><span class="sxs-lookup"><span data-stu-id="a26a0-113">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="a26a0-114">此文档可以在仅使用企业语音部署即时消息/状态 (IM/P) 组件或 IM/P 的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="a26a0-114">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="a26a0-115">当任务或核对清单项目特定于企业语音时, 请注意这一点, 如果你的环境不包括企业语音, 则可以跳过该部分。</span><span class="sxs-lookup"><span data-stu-id="a26a0-115">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="a26a0-116">**部署运行 Lync server 2013**   所需的工具许多工具可用于帮助解决问题、自动执行任务和帮助监视和维护 Lync server 2013 环境。</span><span class="sxs-lookup"><span data-stu-id="a26a0-116">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="a26a0-117">为你的组织定义一组标准工具, 以便操作团队执行的任务准确、高效、一致且以可控方式执行。</span><span class="sxs-lookup"><span data-stu-id="a26a0-117">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="a26a0-118">你还应实现进程来跟踪事件和主要配置更改。</span><span class="sxs-lookup"><span data-stu-id="a26a0-118">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="a26a0-119">参考</span><span class="sxs-lookup"><span data-stu-id="a26a0-119">Reference</span></span>

<span data-ttu-id="a26a0-120">对于读者尚未熟悉服务器管理基础知识的好处, 我们提供了服务器管理做法的概述。</span><span class="sxs-lookup"><span data-stu-id="a26a0-120">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="a26a0-121">读者已熟悉服务器管理, 可能会选择跳过本部分。</span><span class="sxs-lookup"><span data-stu-id="a26a0-121">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="a26a0-122">最佳做法是基于 IT 专业人士在许多环境中获得的知识和体验而提供的建议。</span><span class="sxs-lookup"><span data-stu-id="a26a0-122">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="a26a0-123">它们提供了您的 Lync Server 管理员每天必须执行的典型任务的标准过程, 并列出了用于管理 Lync 服务器环境的工具。</span><span class="sxs-lookup"><span data-stu-id="a26a0-123">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="a26a0-124">Lync 管理员的典型任务包括以下几项:</span><span class="sxs-lookup"><span data-stu-id="a26a0-124">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="a26a0-125">**容量和可用性管理**   定义了如何以及测量哪些内容来预测未来容量需求并报告系统的容量、可靠性和可用性。</span><span class="sxs-lookup"><span data-stu-id="a26a0-125">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="a26a0-126">必须验证运行 Lync Server 的服务器是否已调整大小以处理系统上的负载, 并且计划外停机保留在服务级别协议 (SLA) 中定义的级别下。</span><span class="sxs-lookup"><span data-stu-id="a26a0-126">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="a26a0-127">此外, 你必须升级硬件才能继续满足定义的要求。</span><span class="sxs-lookup"><span data-stu-id="a26a0-127">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="a26a0-128">**更改管理和配置管理**   控制对 IT 系统进行更改的方式。</span><span class="sxs-lookup"><span data-stu-id="a26a0-128">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="a26a0-129">这应包括测试、应用程序反馈和应急计划、文档中的所有更改以及在出现问题时进行管理的批准。</span><span class="sxs-lookup"><span data-stu-id="a26a0-129">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="a26a0-130">保留你的软件和硬件资产及其配置的记录。</span><span class="sxs-lookup"><span data-stu-id="a26a0-130">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="a26a0-131">**系统管理**   概述了用于执行管理任务 (如数据库管理和网站管理) 的标准方法。</span><span class="sxs-lookup"><span data-stu-id="a26a0-131">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="a26a0-132">**安全管理**   具有可保护 IT 基础结构的数据机密性、数据完整性和数据可用性的详细策略和计划。</span><span class="sxs-lookup"><span data-stu-id="a26a0-132">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="a26a0-133">这包括与维护和调整 IT 安全基础结构相关的日常活动和任务。</span><span class="sxs-lookup"><span data-stu-id="a26a0-133">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="a26a0-134">**系统疑难解答**   用于处理意外问题的大纲方法, 包括防止将来出现类似问题的步骤。</span><span class="sxs-lookup"><span data-stu-id="a26a0-134">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="a26a0-135">**服务级别协议**   维护 IT 系统性能的一组目标, 并根据这些目标定期测量性能。</span><span class="sxs-lookup"><span data-stu-id="a26a0-135">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="a26a0-136">**文档**   文档标准过程 (如配置信息和经验教训), 并使其可供需要它们的教职员工成员使用。</span><span class="sxs-lookup"><span data-stu-id="a26a0-136">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="a26a0-137">对配置进行更改后, 请相应地更新文档。</span><span class="sxs-lookup"><span data-stu-id="a26a0-137">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="a26a0-138">相关部分</span><span class="sxs-lookup"><span data-stu-id="a26a0-138">Related Sections</span></span>

<span data-ttu-id="a26a0-139">继续之前, 请查看以下有关系统操作的主题:</span><span class="sxs-lookup"><span data-stu-id="a26a0-139">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="a26a0-140">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="a26a0-140">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="a26a0-141">Lync Server 2013 中的更改管理</span><span class="sxs-lookup"><span data-stu-id="a26a0-141">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="a26a0-142">Lync Server 2013 中的配置管理</span><span class="sxs-lookup"><span data-stu-id="a26a0-142">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="a26a0-143">Lync Server 2013 中的系统管理</span><span class="sxs-lookup"><span data-stu-id="a26a0-143">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="a26a0-144">Lync Server 2013 中的服务级别协议</span><span class="sxs-lookup"><span data-stu-id="a26a0-144">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="a26a0-145">Lync Server 2013 中的文档</span><span class="sxs-lookup"><span data-stu-id="a26a0-145">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="a26a0-146">Lync Server 2013 中的标准过程</span><span class="sxs-lookup"><span data-stu-id="a26a0-146">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="a26a0-147">Lync Server 2013 中的紧急过程</span><span class="sxs-lookup"><span data-stu-id="a26a0-147">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a26a0-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a26a0-148">See Also</span></span>


[<span data-ttu-id="a26a0-149">Microsoft 操作框架4。0</span><span class="sxs-lookup"><span data-stu-id="a26a0-149">Microsoft Operations Framework 4.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

