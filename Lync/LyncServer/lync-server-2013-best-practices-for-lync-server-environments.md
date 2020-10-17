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
# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 环境的最佳实践

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-04_

应将以下常规原则应用于系统的日常操作：

  - **了解并利用 MOF**    MOF 是最佳做法、原则和模型的集合，为组织提供有关 IT 资产管理的技术指导，例如每日 Lync Server 2013 操作。 遵循 MOF 指南可帮助您实现 Microsoft 产品的任务关键型生产系统可靠性、可用性、可支持性和可管理性。 有关详细信息，请参阅 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)。

  - **了解 Lync Server 2013**     的最佳实践我们建议您实施实践和经验证的过程来管理 Lync Server 2013。 通过使用已尝试的、经过测试和记录的方法来管理操作，可能比开发自己的方法效率更高。

  - 将**操作分为每天、每周和每月进程**    记录您定期执行的必需的操作任务。 记录如何执行任务有助于确保在操作环境发生更改时（如部署新技术或发生人员更改时）保留信息。 我们建议将操作任务分为每天、每周和每月执行任务的可管理工作负载。 每日任务将重点放在系统功能上，每月任务将重点放在确保系统长期运行状况的详细信息中。
    
    此文档可在仅使用企业语音部署即时消息/状态 (IM/P) 组件或 IM/P 的环境中使用。 当任务或检查表项目特定于企业语音时，会提到这一点，如果您的环境不包含企业语音，则可以跳过该部分。

  - **部署运行 Lync Server 2013**     所需的工具许多工具可用于帮助解决问题、自动执行任务并帮助监视和维护 Lync Server 2013 环境。 为您的组织定义一组标准工具，以便可以准确、高效、一致且以可控方式执行操作团队执行的任务。 您还应实施流程来跟踪事件和主要配置更改。

<div>

## <a name="reference"></a>参考

对于读者尚未熟悉服务器管理基础知识的优势，我们提供了服务器管理实践的概述。 阅读者已熟悉服务器管理可能会选择跳过此部分。

最佳实践是基于 IT 专业人员在多种环境中获得的知识和体验的建议。 它们提供了有关您的 Lync Server 管理员每天都必须执行的典型任务的标准过程，并列出了用于管理 Lync Server 环境的工具。

Lync 管理员的典型任务包括以下内容：

  - **容量和可用性管理**    定义如何以及如何测量以预测未来容量需求并报告系统的容量、可靠性和可用性。 必须验证运行 Lync Server 的服务器是否已调整大小以处理系统上的负载，并且未计划的停机时间保留在服务级别协议 (SLA) 中定义的级别下。 此外，还必须升级硬件以继续满足定义的要求。

  - **更改管理和配置管理**    控制对 IT 系统进行更改的方式。 这应包括测试、应用程序反馈和应急计划、所有更改的文档以及在问题发生时的管理审批。 保留您的软件和硬件资产及其配置的记录。

  - **系统管理**    概述用于执行管理任务（如数据库管理和网站管理）的标准方法。

  - **安全管理**    具有详细的策略和规划，可保护 IT 基础结构的数据机密性、数据完整性和数据可用性。 这包括与维护和调整 IT 安全基础结构相关的日常活动和任务。

  - **系统故障排除**    用于处理意外问题的大纲方法，包括防止将来出现类似问题的步骤。

  - **服务级别协议**    维护 IT 系统性能的一组目标，并定期针对这些目标评估性能。

  - **文档**    记录标准过程（如配置信息和已学习的经验教训），并使其可供需要它们的教职员工成员使用。 在对配置进行更改后，请相应地更新文档。

</div>

<div>

## <a name="related-sections"></a>相关部分

在继续之前，请查看以下有关系统操作的主题：

  - [Lync Server 2013 中的容量和可用性管理](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013 中的更改管理](lync-server-2013-change-management.md)

  - [Lync Server 2013 中的配置管理](lync-server-2013-configuration-management.md)

  - [Lync Server 2013 中的系统管理](lync-server-2013-system-administration.md)

  - [Lync Server 2013 中的服务级别协议](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013 中的文档](lync-server-2013-documentation.md)

  - [Lync Server 2013 中的标准过程](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013 中的紧急步骤](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Microsoft Operations Framework 4。0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

