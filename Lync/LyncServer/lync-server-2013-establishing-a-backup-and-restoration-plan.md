---
title: Lync Server 2013：建立备份和还原计划
description: Lync Server 2013：建立备份和还原计划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555048"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="7e84b-103">为 Lync Server 2013 建立备份和还原计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-103">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e84b-104">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7e84b-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="7e84b-105">创建备份和还原计划包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7e84b-105">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="7e84b-106">制定计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-106">Developing the plan.</span></span>

  - <span data-ttu-id="7e84b-107">实施计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-107">Implementing the plan.</span></span>

  - <span data-ttu-id="7e84b-108">维护计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-108">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="7e84b-109">制定备份和还原计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-109">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="7e84b-110">在开发 Lync Server 的备份和还原策略之后，请使用它记录详细的备份和还原计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-110">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="7e84b-111">您的计划应清楚地传达有关备份数据和设置的优先级及要求。</span><span class="sxs-lookup"><span data-stu-id="7e84b-111">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="7e84b-112">您可以使用为 lync server [2013 建立备份和还原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 以及 [Lync server 2013 备份和还原工作](lync-server-2013-backup-and-restoration-worksheets.md) 表中的工作表，以促进策略的文档。</span><span class="sxs-lookup"><span data-stu-id="7e84b-112">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="7e84b-113">您的计划还应包含用于决定何时以及如何还原服务的条件。</span><span class="sxs-lookup"><span data-stu-id="7e84b-113">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="7e84b-114">在制定计划时，您需要考虑以下各项，并考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="7e84b-114">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="7e84b-115">您将如何在新硬件上恢复服务器。</span><span class="sxs-lookup"><span data-stu-id="7e84b-115">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="7e84b-116">您将如何恢复需要多个业务领域或部门采取操作的服务。</span><span class="sxs-lookup"><span data-stu-id="7e84b-116">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="7e84b-117">您如何快速获得备用服务器。</span><span class="sxs-lookup"><span data-stu-id="7e84b-117">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="7e84b-118">使用您的策略进行恢复所需的时间。</span><span class="sxs-lookup"><span data-stu-id="7e84b-118">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="7e84b-119">考虑组织对恢复时间目标 (RTO) 的要求。</span><span class="sxs-lookup"><span data-stu-id="7e84b-119">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="7e84b-120">修改本主题中的备份和还原过程，并根据需要添加和删除过程，以反映部署中的服务器和组件。</span><span class="sxs-lookup"><span data-stu-id="7e84b-120">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="7e84b-121">您还可以将适当的详细信息（如备份计划）添加到相应的过程，以确保信息不被忽略。</span><span class="sxs-lookup"><span data-stu-id="7e84b-121">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e84b-122">最好为尽可能多的步骤创建脚本，以帮助确保过程的质量和 reproducibility。</span><span class="sxs-lookup"><span data-stu-id="7e84b-122">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="7e84b-123">在您的计划中，指定负责检查计划的负责，谁负责测试和验证任何新的过程或工具，以及必须批准对计划和相关过程所做的任何更改的用户。</span><span class="sxs-lookup"><span data-stu-id="7e84b-123">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="7e84b-124">若要确保您的备份和还原计划完全符合所有已建立的目标和优先级，请在实施计划之前，获取组织中相应的业务决策制定者和技术决策制定者的批准。</span><span class="sxs-lookup"><span data-stu-id="7e84b-124">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="7e84b-125">实施备份和还原计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-125">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="7e84b-126">若要实现备份和还原计划，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7e84b-126">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="7e84b-127">测试和验证计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-127">Testing and validating the plan.</span></span>

  - <span data-ttu-id="7e84b-128">传达计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-128">Communicating the plan.</span></span>

  - <span data-ttu-id="7e84b-129">验证备份和还原操作。</span><span class="sxs-lookup"><span data-stu-id="7e84b-129">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="7e84b-130">测试和验证计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-130">Testing and Validating the Plan</span></span>

<span data-ttu-id="7e84b-131">此处介绍的过程已在实验室环境中进行了测试和验证。</span><span class="sxs-lookup"><span data-stu-id="7e84b-131">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="7e84b-132">若要确保这些或任何其他过程在您的环境中正常运行，应测试并验证您要实现的每个过程。</span><span class="sxs-lookup"><span data-stu-id="7e84b-132">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="7e84b-133">在提交您的最终审批计划之前，请先完成测试和验证。</span><span class="sxs-lookup"><span data-stu-id="7e84b-133">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="7e84b-134">传达计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-134">Communicating the Plan</span></span>

<span data-ttu-id="7e84b-135">您的备份和还原计划应清楚地说明谁实施过程和有关执行过程的分步说明。</span><span class="sxs-lookup"><span data-stu-id="7e84b-135">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="7e84b-136">应确保负责备份和还原的任何方面的人了解计划、实现方式以及角色的用途。</span><span class="sxs-lookup"><span data-stu-id="7e84b-136">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="7e84b-137">这包括有关以下方面的所有实施要求：</span><span class="sxs-lookup"><span data-stu-id="7e84b-137">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="7e84b-138">池和服务器备份。</span><span class="sxs-lookup"><span data-stu-id="7e84b-138">Pool and server backup.</span></span>

  - <span data-ttu-id="7e84b-139">还原服务。</span><span class="sxs-lookup"><span data-stu-id="7e84b-139">Restoration of service.</span></span>

<span data-ttu-id="7e84b-140">**池和服务器备份**</span><span class="sxs-lookup"><span data-stu-id="7e84b-140">**Pool and server backup**</span></span>

<span data-ttu-id="7e84b-p106">备份和还原计划应包括持续完成备份过程所需的所有信息。要传达给负责的团队成员的主要信息包括：</span><span class="sxs-lookup"><span data-stu-id="7e84b-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="7e84b-143">团队或个人 (指定为负责备份每个服务器的个人或角色) 。</span><span class="sxs-lookup"><span data-stu-id="7e84b-143">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="7e84b-144">用于备份每个服务器的特定计划。</span><span class="sxs-lookup"><span data-stu-id="7e84b-144">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="7e84b-145"> (设置、数据库和文件共享) 的每种数据类型的备份位置。</span><span class="sxs-lookup"><span data-stu-id="7e84b-145">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="7e84b-146">要使用的备份过程，包括完成每个步骤所需的工具。</span><span class="sxs-lookup"><span data-stu-id="7e84b-146">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="7e84b-147">完成备份所需的信息，如 [Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="7e84b-147">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="7e84b-148">验证方法用于帮助确保正确备份数据和设置并可用于还原，这可能包括定期审核和测试还原。</span><span class="sxs-lookup"><span data-stu-id="7e84b-148">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="7e84b-149">**服务的还原**</span><span class="sxs-lookup"><span data-stu-id="7e84b-149">**Restoration of service**</span></span>

<span data-ttu-id="7e84b-150">备份和还原计划应包含还原服务所需的所有信息，以防有一个或多个服务器遇到使服务不可用的损失。</span><span class="sxs-lookup"><span data-stu-id="7e84b-150">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="7e84b-151">要传达给负责的团队成员的主要信息包括：</span><span class="sxs-lookup"><span data-stu-id="7e84b-151">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="7e84b-152">负责确定何时需要还原服务和用于还原服务的过程的团队或人员（指定为个人或角色），以及负责实施每个还原方案的过程的团队或人员。</span><span class="sxs-lookup"><span data-stu-id="7e84b-152">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="7e84b-153">用于确定哪些还原过程最适合特定情况的条件。</span><span class="sxs-lookup"><span data-stu-id="7e84b-153">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="7e84b-154">在每个还原方案中还原服务和恢复时间目标 (RTO) 的时间估计。</span><span class="sxs-lookup"><span data-stu-id="7e84b-154">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="7e84b-155">要使用的还原过程，包括完成每个过程所需的工具。</span><span class="sxs-lookup"><span data-stu-id="7e84b-155">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="7e84b-156">还原数据和设置所需的信息。</span><span class="sxs-lookup"><span data-stu-id="7e84b-156">Information required to restore data and settings.</span></span> <span data-ttu-id="7e84b-157">工作表在 [Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="7e84b-157">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="7e84b-158">验证备份和还原操作</span><span class="sxs-lookup"><span data-stu-id="7e84b-158">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="7e84b-159">在生产环境中完成初始备份工作以及按指定的时间间隔（在您的备份和还原计划中指定）完成备份工作后，您应验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="7e84b-159">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="7e84b-160">按需进行备份。</span><span class="sxs-lookup"><span data-stu-id="7e84b-160">Backups are occurring as required.</span></span>

  - <span data-ttu-id="7e84b-161">备份的数据和设置是可访问的。</span><span class="sxs-lookup"><span data-stu-id="7e84b-161">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="7e84b-162">可以在恢复时间目标中执行还原过程， (RTO) 在备份和还原计划中指定的时间，并使结果满足所有业务要求。</span><span class="sxs-lookup"><span data-stu-id="7e84b-162">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="7e84b-163">备份工作表已完成并经过验证，并且它们存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="7e84b-163">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="7e84b-164">这些工作表在 [Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="7e84b-164">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="7e84b-165">还原过程已经过测试和验证，可按预期工作，就像备份和还原计划中指定的那样。</span><span class="sxs-lookup"><span data-stu-id="7e84b-165">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="7e84b-166">维护备份和还原计划</span><span class="sxs-lookup"><span data-stu-id="7e84b-166">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="7e84b-167">Lync Server 拓扑是与您的组织更改的动态环境。</span><span class="sxs-lookup"><span data-stu-id="7e84b-167">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="7e84b-168">在组织发生变化时重新评估备份和还原计划，并定期查看，以确保它继续满足您的业务需求。</span><span class="sxs-lookup"><span data-stu-id="7e84b-168">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

