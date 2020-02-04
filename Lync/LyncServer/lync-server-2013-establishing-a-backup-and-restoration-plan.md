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
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>为 Lync Server 2013 建立备份和还原计划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-17_

创建备份和还原计划涉及以下步骤：

  - 制定计划。

  - 实施计划。

  - 维护计划。

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>开发备份和还原计划

开发 Lync Server 的备份和还原策略后，请使用它来记录详细的备份和还原计划。 你的计划应清楚地传达备份数据和设置的优先级和要求。 你可以使用在[lync server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中为[lync server 2013 和工作表建立备份和还原策略](lync-server-2013-establishing-a-backup-and-restoration-strategy.md)的信息，以便为你的策略提供文档。 你的计划还应包含用于确定何时以及如何还原服务的条件。

开发计划时，您需要考虑以下事项和帐户：

  - 将在新硬件上恢复服务器的方式。

  - 如何恢复需要在多个业务领域或部门中执行操作的服务。

  - 如何快速获取备用服务器。

  - 使用你的策略进行恢复所需的时间。 考虑组织对恢复时间目标（RTO）的要求。

修改本主题中的备份和还原过程，根据需要添加和删除过程，以反映部署中的服务器和组件。 你还可以将相应的详细信息（如备份计划）添加到相应的过程，以确保信息不会被忽略。

<div>


> [!NOTE]  
> 最好为尽可能多的步骤创建脚本，以帮助确保过程的质量和 reproducibility。



</div>

在你的计划中，指定负责检查计划的人员，负责测试和验证任何新过程或工具的人员，以及必须批准对计划和相关过程的任何更改的人员。

为确保你的备份和还原计划完全符合所有既定的目标和优先级，请在实施计划之前，获取组织中相应的业务决策制定者和技术决策者的批准。

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>实施备份和还原计划

实现备份和还原计划需要执行以下步骤：

  - 测试和验证计划。

  - 传达计划。

  - 验证备份和还原操作。

<div>

## <a name="testing-and-validating-the-plan"></a>测试和验证计划

此处介绍的过程在实验室环境中经过测试和验证。 若要确保这些或任何其他过程在你的环境中正常工作，你应该测试并验证你要实现的每个过程。 在提交最终审批计划之前完成测试和验证。

</div>

<div>

## <a name="communicating-the-plan"></a>传达计划

你的备份和还原计划应清楚地描述执行过程的执行者和执行步骤的分步说明。 你应该确保负责备份和还原的任何方面的人了解计划、它的实现方式以及其角色。 这包括以下各项的所有实现要求：

  - 池和服务器备份。

  - 还原服务。

**池和服务器备份**

备份和还原计划应包括定期完成备份过程所需的所有信息。 要传达给负责团队成员的主要信息包括以下内容：

  - 负责备份每台服务器的团队或个人（指定为个人或角色）。

  - 备份每台服务器的特定计划。

  - 每种类型的数据（设置、数据库和文件共享）的备份位置。

  - 要使用的备份过程，包括完成每个过程所需的工具。

  - 完成备份所需的信息，如[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中所述。

  - 用于帮助确保数据和设置得到适当备份并可供还原的验证方法，其中包括定期审核和测试还原。

**还原服务**

备份和还原计划应包括还原服务所需的所有信息，以防一个或多个服务器遇到导致服务不可用的损失。 要传达给负责团队成员的主要信息包括以下内容：

  - 团队或个人（指定为个人或角色）负责确定何时需要还原服务以及用于还原服务的过程，以及负责为每个团队实施过程的团队或人员。还原方案。

  - 确定哪种还原过程最适合特定情况的标准。

  - 每个还原方案中的服务和恢复时间目标（RTO）恢复的时间估计。

  - 要使用的还原过程，包括完成每个过程所需的工具。

  - 还原数据和设置所需的信息。 在[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供了工作表。

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>验证备份和还原操作

在生产环境中按照指定的时间间隔（如备份和还原计划中所述）完成初始备份工作后，应验证以下各项：

  - 根据需要进行备份。

  - 备份的数据和设置可访问。

  - 可以在备份和还原计划中指定的恢复时间目标（RTO）时间内执行还原过程，结果满足所有业务要求。

  - 备份工作表已完成并经过验证，它们存储在安全位置。 这些工作表在[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中提供。

  - 还原过程经测试和验证为按预期工作，如备份和还原计划中所指定。

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>维护备份和还原计划

Lync Server 拓扑是与你的组织更改的动态环境。 重新评估你的组织更改的备份和还原计划，并定期检查，以确保它能够继续满足你的业务需求。

</div>

</div>

<span> </span>

</div>

</div>

</div>

