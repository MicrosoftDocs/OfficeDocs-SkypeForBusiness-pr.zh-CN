---
title: Lync Server 2013： Lync Server 环境的最佳实践
description: Lync Server 2013： Lync Server 环境的最佳实践。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552208"
---
# <a name="best-practices-for-lync-server-2013-environments"></a><span data-ttu-id="d21ef-103">Lync Server 2013 环境的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d21ef-103">Best practices for Lync Server 2013 environments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d21ef-104">_**上次修改的主题：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="d21ef-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="d21ef-105">应将以下常规原则应用于系统的日常操作：</span><span class="sxs-lookup"><span data-stu-id="d21ef-105">The following general principles should be applied to ongoing operations of your system:</span></span>

  - <span data-ttu-id="d21ef-106">**了解并利用 MOF**    MOF 是最佳做法、原则和模型的集合，为组织提供有关 IT 资产管理的技术指导，例如每日 Lync Server 2013 操作。</span><span class="sxs-lookup"><span data-stu-id="d21ef-106">**Understand and utilize MOF**   MOF is a collection of best practices, principles, and models that provide organizations technical guidance about the management of IT assets, such as daily Lync Server 2013 operations.</span></span> <span data-ttu-id="d21ef-107">遵循 MOF 指南可帮助您实现 Microsoft 产品的任务关键型生产系统可靠性、可用性、可支持性和可管理性。</span><span class="sxs-lookup"><span data-stu-id="d21ef-107">Following MOF guidelines can help you achieve mission-critical production system reliability, availability, supportability, and manageability for Microsoft products.</span></span> <span data-ttu-id="d21ef-108">有关详细信息，请参阅 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)。</span><span class="sxs-lookup"><span data-stu-id="d21ef-108">For more information, see [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939).</span></span>

  - <span data-ttu-id="d21ef-109">**了解 Lync Server 2013**     的最佳实践我们建议您实施实践和经验证的过程来管理 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d21ef-109">**Learn about best practices for Lync Server 2013**   We recommend that you implement practical and proven procedures to manage Lync Server 2013.</span></span> <span data-ttu-id="d21ef-110">通过使用已尝试的、经过测试和记录的方法来管理操作，可能比开发自己的方法效率更高。</span><span class="sxs-lookup"><span data-stu-id="d21ef-110">By using tried, tested, and documented methods of managing operations may be more efficient than developing your own methods.</span></span>

  - <span data-ttu-id="d21ef-111">将**操作分为每天、每周和每月进程**    记录您定期执行的必需的操作任务。</span><span class="sxs-lookup"><span data-stu-id="d21ef-111">**Separate operations into daily, weekly, and monthly processes**   Document the required operational tasks that you'll regularly perform.</span></span> <span data-ttu-id="d21ef-112">记录如何执行任务有助于确保在操作环境发生更改时（如部署新技术或发生人员更改时）保留信息。</span><span class="sxs-lookup"><span data-stu-id="d21ef-112">Documenting how you perform tasks helps make sure that your information is preserved when there is a change in your operational environment such as when new technologies are deployed or staff changes occur.</span></span> <span data-ttu-id="d21ef-113">我们建议将操作任务分为每天、每周和每月执行任务的可管理工作负载。</span><span class="sxs-lookup"><span data-stu-id="d21ef-113">We recommend that operational tasks be separated into manageable workloads where tasks are performed daily, weekly, and monthly.</span></span> <span data-ttu-id="d21ef-114">每日任务将重点放在系统功能上，每月任务将重点放在确保系统长期运行状况的详细信息中。</span><span class="sxs-lookup"><span data-stu-id="d21ef-114">Daily tasks would focus efforts on the functioning of a system, and monthly tasks would focus more on ensuring the long-term health of a system.</span></span>
    
    <span data-ttu-id="d21ef-115">此文档可在仅使用企业语音部署即时消息/状态 (IM/P) 组件或 IM/P 的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="d21ef-115">This document can be used in environments deploying only instant messaging/presence (IM/P) components or IM/P with Enterprise Voice.</span></span> <span data-ttu-id="d21ef-116">当任务或检查表项目特定于企业语音时，会提到这一点，如果您的环境不包含企业语音，则可以跳过该部分。</span><span class="sxs-lookup"><span data-stu-id="d21ef-116">When tasks or checklist items are specific to Enterprise Voice, this is mentioned and if your environment does not include Enterprise Voice the portion may be skipped.</span></span>

  - <span data-ttu-id="d21ef-117">**部署运行 Lync Server 2013**     所需的工具许多工具可用于帮助解决问题、自动执行任务并帮助监视和维护 Lync Server 2013 环境。</span><span class="sxs-lookup"><span data-stu-id="d21ef-117">**Deploy the tools that are required for operating Lync Server 2013**   Many tools are available to help troubleshoot issues, automate tasks, and help monitor and maintain the Lync Server 2013 environment.</span></span> <span data-ttu-id="d21ef-118">为您的组织定义一组标准工具，以便可以准确、高效、一致且以可控方式执行操作团队执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d21ef-118">Define a standard set of tools for your organization so the tasks that are performed by the operations team are performed accurately, efficiently, consistently, and in a controlled manner.</span></span> <span data-ttu-id="d21ef-119">您还应实施流程来跟踪事件和主要配置更改。</span><span class="sxs-lookup"><span data-stu-id="d21ef-119">You should also implement processes to track incidents and major configuration changes.</span></span>

<div>

## <a name="reference"></a><span data-ttu-id="d21ef-120">参考</span><span class="sxs-lookup"><span data-stu-id="d21ef-120">Reference</span></span>

<span data-ttu-id="d21ef-121">对于读者尚未熟悉服务器管理基础知识的优势，我们提供了服务器管理实践的概述。</span><span class="sxs-lookup"><span data-stu-id="d21ef-121">For the benefit of readers not already familiar with the basics of server management in general, we provide an overview of server management practices.</span></span> <span data-ttu-id="d21ef-122">阅读者已熟悉服务器管理可能会选择跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="d21ef-122">Readers already familiar with server management may choose to skip this section.</span></span>

<span data-ttu-id="d21ef-123">最佳实践是基于 IT 专业人员在多种环境中获得的知识和体验的建议。</span><span class="sxs-lookup"><span data-stu-id="d21ef-123">Best practices are recommendations that are based on the knowledge and experience that IT professionals have gained across many environments.</span></span> <span data-ttu-id="d21ef-124">它们提供了有关您的 Lync Server 管理员每天都必须执行的典型任务的标准过程，并列出了用于管理 Lync Server 环境的工具。</span><span class="sxs-lookup"><span data-stu-id="d21ef-124">They provide standard procedures for typical tasks that your Lync Server administrators must perform daily, and list the tools that they should use to manage a Lync Server environment.</span></span>

<span data-ttu-id="d21ef-125">Lync 管理员的典型任务包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="d21ef-125">Typical tasks for Lync administrators include the following:</span></span>

  - <span data-ttu-id="d21ef-126">**容量和可用性管理**    定义如何以及如何测量以预测未来容量需求并报告系统的容量、可靠性和可用性。</span><span class="sxs-lookup"><span data-stu-id="d21ef-126">**Capacity and Availability Management**   Define how and what to measure to predict future capacity requirements and to report about the capacity, reliability, and availability of your systems.</span></span> <span data-ttu-id="d21ef-127">必须验证运行 Lync Server 的服务器是否已调整大小以处理系统上的负载，并且未计划的停机时间保留在服务级别协议 (SLA) 中定义的级别下。</span><span class="sxs-lookup"><span data-stu-id="d21ef-127">You must verify that servers that are running Lync Server are sized to handle the load on the system, and that unplanned downtime is kept under the levels defined in the service level agreement (SLA).</span></span> <span data-ttu-id="d21ef-128">此外，还必须升级硬件以继续满足定义的要求。</span><span class="sxs-lookup"><span data-stu-id="d21ef-128">Additionally, you'll have to upgrade hardware to continue to meet the defined requirements.</span></span>

  - <span data-ttu-id="d21ef-129">**更改管理和配置管理**    控制对 IT 系统进行更改的方式。</span><span class="sxs-lookup"><span data-stu-id="d21ef-129">**Change Management and Configuration Management**   Control how changes are made to IT systems.</span></span> <span data-ttu-id="d21ef-130">这应包括测试、应用程序反馈和应急计划、所有更改的文档以及在问题发生时的管理审批。</span><span class="sxs-lookup"><span data-stu-id="d21ef-130">This should include testing, application feedback and contingency plans, documentation of all changes, and approval from management if issues occur.</span></span> <span data-ttu-id="d21ef-131">保留您的软件和硬件资产及其配置的记录。</span><span class="sxs-lookup"><span data-stu-id="d21ef-131">Keep a record of your software and hardware assets and their configurations.</span></span>

  - <span data-ttu-id="d21ef-132">**系统管理**    概述用于执行管理任务（如数据库管理和网站管理）的标准方法。</span><span class="sxs-lookup"><span data-stu-id="d21ef-132">**System Administration**   Outline standard methods for doing administrative tasks such as database administration and site administration.</span></span>

  - <span data-ttu-id="d21ef-133">**安全管理**    具有详细的策略和规划，可保护 IT 基础结构的数据机密性、数据完整性和数据可用性。</span><span class="sxs-lookup"><span data-stu-id="d21ef-133">**Security Administration**   Have a detailed policy and plan that protects data confidentiality, data integrity, and data availability of the IT infrastructure.</span></span> <span data-ttu-id="d21ef-134">这包括与维护和调整 IT 安全基础结构相关的日常活动和任务。</span><span class="sxs-lookup"><span data-stu-id="d21ef-134">This includes day-to-day activities and tasks that are related to maintaining and adjusting the IT security infrastructure.</span></span>

  - <span data-ttu-id="d21ef-135">**系统故障排除**    用于处理意外问题的大纲方法，包括防止将来出现类似问题的步骤。</span><span class="sxs-lookup"><span data-stu-id="d21ef-135">**System Troubleshooting**   Outline methods for dealing with unexpected issues, including steps to prevent similar issues in the future.</span></span>

  - <span data-ttu-id="d21ef-136">**服务级别协议**    维护 IT 系统性能的一组目标，并定期针对这些目标评估性能。</span><span class="sxs-lookup"><span data-stu-id="d21ef-136">**Service Level Agreements**   Maintain a set of goals for the performance of the IT systems and regularly measure performance against these goals.</span></span>

  - <span data-ttu-id="d21ef-137">**文档**    记录标准过程（如配置信息和已学习的经验教训），并使其可供需要它们的教职员工成员使用。</span><span class="sxs-lookup"><span data-stu-id="d21ef-137">**Documentation**   Document standard procedures, such as configuration information and lessons learned, and make them available to the staff members that need them.</span></span> <span data-ttu-id="d21ef-138">在对配置进行更改后，请相应地更新文档。</span><span class="sxs-lookup"><span data-stu-id="d21ef-138">As changes to the configuration are made, update the documentation accordingly.</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d21ef-139">相关部分</span><span class="sxs-lookup"><span data-stu-id="d21ef-139">Related Sections</span></span>

<span data-ttu-id="d21ef-140">在继续之前，请查看以下有关系统操作的主题：</span><span class="sxs-lookup"><span data-stu-id="d21ef-140">Review the following topics concerning system operations before proceeding:</span></span>

  - [<span data-ttu-id="d21ef-141">Lync Server 2013 中的容量和可用性管理</span><span class="sxs-lookup"><span data-stu-id="d21ef-141">Capacity and availability management in Lync Server 2013</span></span>](lync-server-2013-capacity-and-availability-management.md)

  - [<span data-ttu-id="d21ef-142">Lync Server 2013 中的更改管理</span><span class="sxs-lookup"><span data-stu-id="d21ef-142">Change management in Lync Server 2013</span></span>](lync-server-2013-change-management.md)

  - [<span data-ttu-id="d21ef-143">Lync Server 2013 中的配置管理</span><span class="sxs-lookup"><span data-stu-id="d21ef-143">Configuration management in Lync Server 2013</span></span>](lync-server-2013-configuration-management.md)

  - [<span data-ttu-id="d21ef-144">Lync Server 2013 中的系统管理</span><span class="sxs-lookup"><span data-stu-id="d21ef-144">System administration in Lync Server 2013</span></span>](lync-server-2013-system-administration.md)

  - [<span data-ttu-id="d21ef-145">Lync Server 2013 中的服务级别协议</span><span class="sxs-lookup"><span data-stu-id="d21ef-145">Service level agreements in Lync Server 2013</span></span>](lync-server-2013-service-level-agreements.md)

  - [<span data-ttu-id="d21ef-146">Lync Server 2013 中的文档</span><span class="sxs-lookup"><span data-stu-id="d21ef-146">Documentation in Lync Server 2013</span></span>](lync-server-2013-documentation.md)

  - [<span data-ttu-id="d21ef-147">Lync Server 2013 中的标准过程</span><span class="sxs-lookup"><span data-stu-id="d21ef-147">Standard procedures in Lync Server 2013</span></span>](lync-server-2013-standard-procedures.md)

  - [<span data-ttu-id="d21ef-148">Lync Server 2013 中的紧急步骤</span><span class="sxs-lookup"><span data-stu-id="d21ef-148">Emergency procedures in Lync Server 2013</span></span>](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d21ef-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d21ef-149">See Also</span></span>


[<span data-ttu-id="d21ef-150">Microsoft Operations Framework 4。0</span><span class="sxs-lookup"><span data-stu-id="d21ef-150">Microsoft Operations Framework 4.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

