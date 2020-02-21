---
title: Lync Server 2013：建立备份和还原计划
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
ms.openlocfilehash: b08b2588ea7510bf2a6ac2de544d0dce7b0fe134
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>为 Lync Server 2013 建立备份和还原计划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

创建备份和还原计划包括以下步骤：

  - 制定计划。

  - 实施计划。

  - 维护计划。

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>制定备份和还原计划

在开发 Lync Server 的备份和还原策略之后，请使用它记录详细的备份和还原计划。 您的计划应清楚地传达有关备份数据和设置的优先级及要求。 您可以使用为 lync server [2013 建立备份和还原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)以及[Lync server 2013 备份和还原工作](lync-server-2013-backup-and-restoration-worksheets.md)表中的工作表，以促进策略的文档。 您的计划还应包含用于决定何时以及如何还原服务的条件。

在制定计划时，您需要考虑以下各项，并考虑以下事项：

  - 您将如何在新硬件上恢复服务器。

  - 您将如何恢复需要多个业务领域或部门采取操作的服务。

  - 您如何快速获得备用服务器。

  - 使用您的策略进行恢复所需的时间。 考虑组织对恢复时间目标（RTO）的要求。

修改本主题中的备份和还原过程，并根据需要添加和删除过程，以反映部署中的服务器和组件。 您还可以将适当的详细信息（如备份计划）添加到相应的过程，以确保信息不被忽略。

<div>


> [!NOTE]  
> 最好为尽可能多的步骤创建脚本，以帮助确保过程的质量和 reproducibility。



</div>

在您的计划中，指定负责检查计划的负责，谁负责测试和验证任何新的过程或工具，以及必须批准对计划和相关过程所做的任何更改的用户。

若要确保您的备份和还原计划完全符合所有已建立的目标和优先级，请在实施计划之前，获取组织中相应的业务决策制定者和技术决策制定者的批准。

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>实施备份和还原计划

若要实现备份和还原计划，需要执行以下步骤：

  - 测试和验证计划。

  - 传达计划。

  - 验证备份和还原操作。

<div>

## <a name="testing-and-validating-the-plan"></a>测试和验证计划

此处介绍的过程已在实验室环境中进行了测试和验证。 若要确保这些或任何其他过程在您的环境中正常运行，应测试并验证您要实现的每个过程。 在提交您的最终审批计划之前，请先完成测试和验证。

</div>

<div>

## <a name="communicating-the-plan"></a>传达计划

您的备份和还原计划应清楚地说明谁实施过程和有关执行过程的分步说明。 应确保负责备份和还原的任何方面的人了解计划、实现方式以及角色的用途。 这包括有关以下方面的所有实施要求：

  - 池和服务器备份。

  - 还原服务。

**池和服务器备份**

备份和还原计划应包括持续完成备份过程所需的所有信息。要传达给负责的团队成员的主要信息包括：

  - 负责备份每个服务器的团队或个人（指定为个人或角色）。

  - 用于备份每个服务器的特定计划。

  - 每种数据类型（设置、数据库和文件共享）的备份位置。

  - 要使用的备份过程，包括完成每个步骤所需的工具。

  - 完成备份所需的信息，如[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。

  - 验证方法用于帮助确保正确备份数据和设置并可用于还原，这可能包括定期审核和测试还原。

**服务的还原**

备份和还原计划应包含还原服务所需的所有信息，以防有一个或多个服务器遇到使服务不可用的损失。 要传达给负责的团队成员的主要信息包括：

  - 负责确定何时需要还原服务和用于还原服务的过程的团队或人员（指定为个人或角色），以及负责实施每个还原方案的过程的团队或人员。

  - 用于确定哪些还原过程最适合特定情况的条件。

  - 每个还原方案中还原服务和恢复时间目标（RTO）的时间估计。

  - 要使用的还原过程，包括完成每个过程所需的工具。

  - 还原数据和设置所需的信息。 工作表在[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>验证备份和还原操作

在生产环境中完成初始备份工作以及按指定的时间间隔（在您的备份和还原计划中指定）完成备份工作后，您应验证以下各项：

  - 按需进行备份。

  - 备份的数据和设置是可访问的。

  - 可以在备份和还原计划中指定的恢复时间目标（RTO）时间内执行还原过程，并在结果中满足所有业务要求。

  - 备份工作表已完成并经过验证，并且它们存储在安全的位置。 这些工作表在[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。

  - 还原过程已经过测试和验证，可按预期工作，就像备份和还原计划中指定的那样。

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>维护备份和还原计划

Lync Server 拓扑是与您的组织更改的动态环境。 在组织发生变化时重新评估备份和还原计划，并定期查看，以确保它继续满足您的业务需求。

</div>

</div>

<span> </span>

</div>

</div>

</div>

