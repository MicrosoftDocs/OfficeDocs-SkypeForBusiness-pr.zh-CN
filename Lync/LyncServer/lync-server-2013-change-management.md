---
title: Lync Server 2013：更改管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de514dee1b9e185e880660be656b493ae520340
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a><span data-ttu-id="b2da6-102">Lync Server 2013 中的更改管理</span><span class="sxs-lookup"><span data-stu-id="b2da6-102">Change management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2da6-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="b2da6-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="b2da6-104">对 IT 环境的更改是不可避免的。</span><span class="sxs-lookup"><span data-stu-id="b2da6-104">Changes to the IT environment are unavoidable.</span></span> <span data-ttu-id="b2da6-105">更改包括新技术、系统、应用程序、硬件、工具、过程和角色和职责方面的更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-105">Changes include new technologies, systems, applications, hardware, tools, processes, and changes in roles and responsibilities.</span></span> <span data-ttu-id="b2da6-106">有效的更改管理系统允许您快速引入 IT 环境的更改，并减少服务中断。</span><span class="sxs-lookup"><span data-stu-id="b2da6-106">An effective change management system lets you introduce changes to the IT environment quickly and with minimal service disruption.</span></span> <span data-ttu-id="b2da6-107">变更管理系统将更改系统所涉及的团队汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="b2da6-107">A change management system brings together the teams involved in changing a system.</span></span> <span data-ttu-id="b2da6-108">例如，决定利用 Office Web Apps。</span><span class="sxs-lookup"><span data-stu-id="b2da6-108">For example, deciding to take advantage of the Office Web Apps.</span></span> <span data-ttu-id="b2da6-109">这是一个集成的 Lync Service 应用程序，使用户能够在浏览器中读取和编辑文档。</span><span class="sxs-lookup"><span data-stu-id="b2da6-109">This is an integrated Lync Service application that enables users to read and edit documents in a browser.</span></span> <span data-ttu-id="b2da6-110">此服务的实现在投入生产后，需要多个团队的参与：</span><span class="sxs-lookup"><span data-stu-id="b2da6-110">The implementation of this service, after you have gone into production, requires the involvement of several teams:</span></span>

  - <span data-ttu-id="b2da6-111">**测试团队**   此团队加载-在测试服务器上测试 Office Web Apps，该过程提供有关生产服务器的预期使用模式和预期性能的信息。</span><span class="sxs-lookup"><span data-stu-id="b2da6-111">**Test Team**   This team load-tests the Office Web Apps on a test server, in the process providing information about the expected usage patterns and expected performance of the production servers.</span></span>

  - <span data-ttu-id="b2da6-112">**Lync 管理员**   此团队确定部署策略并在可能的情况下将安装脚本。</span><span class="sxs-lookup"><span data-stu-id="b2da6-112">**Lync Administrators**   This team determines the deployment strategy and scripts the installation where it was possible.</span></span> <span data-ttu-id="b2da6-113">团队负责确保更改已部署在生产环境中，并且负责在以后进行管理。</span><span class="sxs-lookup"><span data-stu-id="b2da6-113">The team is responsible for making sure that the change is deployed on the production environment, and it is responsible for administration afterward.</span></span> <span data-ttu-id="b2da6-114">团队必须了解更改的影响，并在将更改投入生产之前将其纳入过程中</span><span class="sxs-lookup"><span data-stu-id="b2da6-114">The team must understand the effect of the changes and incorporate them in procedures before the changes are put into production</span></span>

  - <span data-ttu-id="b2da6-115">**网络团队**   此团队负责对防火墙规则的更改，这些规则允许从 Internet 访问内部 Lync 池服务器。</span><span class="sxs-lookup"><span data-stu-id="b2da6-115">**Network Team**   This team is responsible for changes to firewall rules that allow access from the Internet to the internal Lync pool servers.</span></span> <span data-ttu-id="b2da6-116">团队还负责与 Lync 管理员合作，以确保可用带宽能够支持额外负载。</span><span class="sxs-lookup"><span data-stu-id="b2da6-116">The team is also responsible in working with the Lync administrators for making sure that the available bandwidth can support the additional load.</span></span>

  - <span data-ttu-id="b2da6-117">**安全团队**   此团队将评估安全性并将风险降至最低。</span><span class="sxs-lookup"><span data-stu-id="b2da6-117">**Security Team**   This team assesses security and minimizes risks.</span></span> <span data-ttu-id="b2da6-118">安全团队必须查看已知的漏洞并帮助确保最大限度地降低安全风险。</span><span class="sxs-lookup"><span data-stu-id="b2da6-118">The security team must review known vulnerabilities and help ensure that security risks are minimized.</span></span>

  - <span data-ttu-id="b2da6-119">**用户验收团队**   此团队由愿意测试系统并提供改进反馈的用户组成。</span><span class="sxs-lookup"><span data-stu-id="b2da6-119">**User Acceptance Team**   This team is composed of users who are willing to test the system and offer feedback for improvements.</span></span>

<span data-ttu-id="b2da6-120">变更管理过程定义每个团队的责任，并安排要执行的工作，并在需要时纳入检查和测试。</span><span class="sxs-lookup"><span data-stu-id="b2da6-120">The change management process defines the responsibilities of each team and schedules the work to be performed, incorporating checks and tests where they are required.</span></span> <span data-ttu-id="b2da6-121">更改控件将因更改的复杂性和预期效果而异。</span><span class="sxs-lookup"><span data-stu-id="b2da6-121">Change controls will vary depending on the complexity and expected effect of a change.</span></span> <span data-ttu-id="b2da6-122">它们可能因次要更改的自动审批、将评审会议更改为完整项目级评审而异。</span><span class="sxs-lookup"><span data-stu-id="b2da6-122">They can vary from automatic approval of minor changes, to change review meetings, to full project-level reviews.</span></span> <span data-ttu-id="b2da6-123">为了更好地说明这一点，本节将对更改组进行讨论。</span><span class="sxs-lookup"><span data-stu-id="b2da6-123">To explain this better, the groups of changes are discussed in this section.</span></span>

  - <span data-ttu-id="b2da6-124">**主要更改**   主要更改对系统有全局影响，可能需要来自不同团队的输入。</span><span class="sxs-lookup"><span data-stu-id="b2da6-124">**Major Changes**   Major changes have a global effect on the system and may require input from various teams.</span></span> <span data-ttu-id="b2da6-125">升级到 Lync Server 2013 的一个示例。</span><span class="sxs-lookup"><span data-stu-id="b2da6-125">An example of this is upgrading to Lync Server 2013.</span></span> <span data-ttu-id="b2da6-126">主要更改会影响许多团队和可能不同的系统。</span><span class="sxs-lookup"><span data-stu-id="b2da6-126">Major changes affect many teams and perhaps different systems.</span></span> <span data-ttu-id="b2da6-127">更改管理过程可能包含一个或多个变更评审会议，以通知团队将参与更改或受更改影响。</span><span class="sxs-lookup"><span data-stu-id="b2da6-127">The change management process will probably include one or more change review meetings to inform the teams that will be involved in the change or be affected by the change.</span></span>

  - <span data-ttu-id="b2da6-128">**重大更改**   重大更改需要大量的资源来进行规划、构建和实施。</span><span class="sxs-lookup"><span data-stu-id="b2da6-128">**Significant Changes**   Significant changes require significant resources to plan, build, and implement.</span></span> <span data-ttu-id="b2da6-129">应引入相应的更改控件，以帮助确保能够理解更改的效果，测试部署过程，并且回滚和应变计划已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="b2da6-129">Appropriate change controls should be introduced to help make ensure that the effect of the change is understood, deployment procedures are tested, and the rollback and contingency plans are ready.</span></span> <span data-ttu-id="b2da6-130">一个重大更改的示例是部署新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="b2da6-130">An example of a significant change is deploying a new cumulative update.</span></span>

  - <span data-ttu-id="b2da6-131">**次要更改**   微小更改不会显著影响 IT 环境，例如，通过 Microsoft Lync Server 2013 控制面板更改某些 Lync 策略。</span><span class="sxs-lookup"><span data-stu-id="b2da6-131">**Minor Changes**   Minor changes do not significantly affect the IT environment, for example, changing certain Lync policies via the Microsoft Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="b2da6-132">**标准更改**   ：定期执行标准更改，并对其进行充分了解和记录。</span><span class="sxs-lookup"><span data-stu-id="b2da6-132">**Standard Changes**   Standard changes are performed regularly and are well understood and documented.</span></span> <span data-ttu-id="b2da6-133">更改管理过程应检查对过程所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-133">The change management process should review all changes to the procedures.</span></span> <span data-ttu-id="b2da6-134">与创建内容数据库或添加用户相比，常规更改不需要使用它。</span><span class="sxs-lookup"><span data-stu-id="b2da6-134">It should not be needed for routine changes like creating a content database or adding a user.</span></span>

<span data-ttu-id="b2da6-135">下面的更改管理示例检查不同的团队如何交互以及在部署新 service pack 时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b2da6-135">The following example of change management examines how different teams interact and the actions that are performed when a new service pack is deployed.</span></span> <span data-ttu-id="b2da6-136">这些操作通过更改管理过程进行组织和管理。</span><span class="sxs-lookup"><span data-stu-id="b2da6-136">These actions are organized and managed by the change management process.</span></span>

  - <span data-ttu-id="b2da6-137">**提出更改请求**   安全团队已评估了最新的 service pack，并确认它可解决生产系统中可能存在的漏洞。</span><span class="sxs-lookup"><span data-stu-id="b2da6-137">**Raise a change request**   The security team has assessed the latest service pack and confirmed that it resolves a possible vulnerability in the production system.</span></span> <span data-ttu-id="b2da6-138">团队引发更改请求，以将新的累积更新应用于运行 Lync Server 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="b2da6-138">The team raises a change request to have the new cumulative update applied to all servers that are running Lync Server.</span></span>

  - <span data-ttu-id="b2da6-139">**Service pack 发行说明回顾**   ： Lync 管理员团队审阅 service pack 发行说明，以确定对系统的影响。</span><span class="sxs-lookup"><span data-stu-id="b2da6-139">**Service pack release notes review**   The Lync administrator team reviews the service pack release notes to identify the effect on the system.</span></span>

  - <span data-ttu-id="b2da6-140">**执行一系列实验室测试时**   ，Lync 管理员团队必须在测试环境中的服务器上执行测试更新，以确定是否可以成功应用 service pack，而不会影响任何已安装的应用程序和服务器系统。</span><span class="sxs-lookup"><span data-stu-id="b2da6-140">**A series of lab tests is performed**   The Lync administrator team must perform test updates on a server in a test environment to decide whether the service pack can be applied successfully without affecting any of the installed applications and server systems.</span></span> <span data-ttu-id="b2da6-141">如果在生产环境中有与 Lync Server 交互的第三方或内部创建的应用程序，则还应对这些应用程序进行测试。</span><span class="sxs-lookup"><span data-stu-id="b2da6-141">If there are third-party or internally created applications that interface with Lync Server in a production environment, these should be also tested.</span></span> <span data-ttu-id="b2da6-142">这些测试还可用于估计执行升级所需的时间。</span><span class="sxs-lookup"><span data-stu-id="b2da6-142">These tests can also be used to estimate the time that is required to perform the upgrades.</span></span>

  - <span data-ttu-id="b2da6-143">**通知用户发生中断时**   ，Lync 管理员团队、通信团队或用户帮助台会通知所有受影响的用户有关计划的维护周期以及服务将不可用的时间。</span><span class="sxs-lookup"><span data-stu-id="b2da6-143">**Users are informed of the outage**   The Lync administrator team, communications team, or user help desk informs all affected users about the planned maintenance cycle and how long the service will be unavailable.</span></span>

  - <span data-ttu-id="b2da6-144">**在升级之前执行 lync 的完整备份**   。在升级之前，lync 管理员团队必须验证是否存在可用于还原为原始系统状态的有效备份（如果 service pack 安装失败）。</span><span class="sxs-lookup"><span data-stu-id="b2da6-144">**A full backup of Lync is performed before the upgrade**   The Lync administrator team must verify that there is a valid backup that can be used to revert to the original system state if the service pack installation fails.</span></span> <span data-ttu-id="b2da6-145">建议将备份还原到备用服务器，以使此系统在出现问题时易于使用。</span><span class="sxs-lookup"><span data-stu-id="b2da6-145">We recommend that the backup be restored to a standby server to have this system readily available if there are issues.</span></span>

  - <span data-ttu-id="b2da6-146">**部署累积更新时**   ，Lync 管理员团队会在计划的维护周期内执行安装。</span><span class="sxs-lookup"><span data-stu-id="b2da6-146">**The cumulative update is deployed**   The Lync administrator team does the installation during the planned maintenance cycle.</span></span>

<div>

## <a name="managing-the-timing-of-changes"></a><span data-ttu-id="b2da6-147">管理更改的计时</span><span class="sxs-lookup"><span data-stu-id="b2da6-147">Managing the timing of changes</span></span>

<span data-ttu-id="b2da6-148">我们建议您实施计划更改过程以避免工作的重叠部分中断。</span><span class="sxs-lookup"><span data-stu-id="b2da6-148">We recommend that you implement a procedure for scheduling changes to avoid disruptions in overlapping sections of your work.</span></span> <span data-ttu-id="b2da6-149">例如，两个团队可能都在规划对系统的微小更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-149">For example, two teams may both be planning a minor change to a system.</span></span> <span data-ttu-id="b2da6-150">一个团队可能会在另一个团队将旧版用户迁移到该池中时对池应用累积更新。</span><span class="sxs-lookup"><span data-stu-id="b2da6-150">One team may be applying a cumulative update on a pool while another team is migrating legacy users into that pool.</span></span> <span data-ttu-id="b2da6-151">其他团队正在规划的更改不会影响任何团队，并且每个团队可能都不一定知道其他团队正在规划的更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-151">Neither team is affected by the changes that the other team is planning, and each team may not necessarily know about changes that the other team is planning.</span></span> <span data-ttu-id="b2da6-152">如果同时发生这两个更改，则可能会在实施更改时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="b2da6-152">If both changes occurred at the same time, there might be issues implementing the changes.</span></span> <span data-ttu-id="b2da6-153">此外，如果在应用更改后存在问题，例如，如果用户迁移失败，可能很难决定应回滚的更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-153">Also, if there are issues after the changes were applied, for example, if the user migration fails, it may be difficult to decide which change should be rolled back.</span></span> <span data-ttu-id="b2da6-154">应在 IT 和管理之间设置定期维护期间，以测试更改并接受这些更改。</span><span class="sxs-lookup"><span data-stu-id="b2da6-154">There should be regular maintenance periods set up between IT and management to test the changes and accept them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

