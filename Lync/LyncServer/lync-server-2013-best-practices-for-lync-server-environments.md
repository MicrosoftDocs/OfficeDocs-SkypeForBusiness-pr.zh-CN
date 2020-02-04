---
title: Lync Server 2013： Lync Server 环境的最佳做法
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
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 环境的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-08-04_

应将以下常规原则应用于系统的日常操作：

  - **了解和使用 mof**   mof 是最佳做法、原则和模型的集合，提供有关 IT 资产管理的技术指导（如每天 Lync Server 2013 操作）。 遵循 MOF 指南可帮助你为 Microsoft 产品实现任务关键型生产系统的可靠性、可用性、支持性和可管理性。 有关详细信息，请参阅[Microsoft 操作框架 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)。

  - **了解 lync server 2013**   的最佳做法我们建议你实施实践和经验证的过程来管理 lync server 2013。 通过使用已尝试、经过测试和记录的方法管理操作，可能比开发自己的方法更高效。

  - **将操作分为每天、每周和每月进程**   记录您定期执行的所需操作任务。 记录如何执行任务有助于确保你的信息在操作环境中发生更改时（如部署新技术或发生人员更改时）保留。 我们建议将操作任务分为每天、每周和每月执行任务的可管理工作负荷。 每日任务将重点关注系统的运行，每月任务的重点都将更详细地介绍了如何确保系统长期运行。
    
    此文档可以在仅使用企业语音部署即时消息/状态（IM/P）组件或 IM/P 的环境中使用。 当任务或核对清单项目特定于企业语音时，请注意这一点，如果你的环境不包括企业语音，则可以跳过该部分。

  - **部署运行 Lync server 2013**   所需的工具许多工具可用于帮助解决问题、自动执行任务和帮助监视和维护 Lync server 2013 环境。 为你的组织定义一组标准工具，以便操作团队执行的任务准确、高效、一致且以可控方式执行。 你还应实现进程来跟踪事件和主要配置更改。

<div>

## <a name="reference"></a>参考

对于读者尚未熟悉服务器管理基础知识的好处，我们提供了服务器管理做法的概述。 读者已熟悉服务器管理，可能会选择跳过本部分。

最佳做法是基于 IT 专业人士在许多环境中获得的知识和体验而提供的建议。 它们提供了您的 Lync Server 管理员每天必须执行的典型任务的标准过程，并列出了用于管理 Lync 服务器环境的工具。

Lync 管理员的典型任务包括以下几项：

  - **容量和可用性管理**   定义了如何以及测量哪些内容来预测未来容量需求并报告系统的容量、可靠性和可用性。 必须验证运行 Lync Server 的服务器是否已调整大小以处理系统上的负载，并且计划外停机保留在服务级别协议（SLA）中定义的级别下。 此外，你必须升级硬件才能继续满足定义的要求。

  - **更改管理和配置管理**   控制对 IT 系统进行更改的方式。 这应包括测试、应用程序反馈和应急计划、文档中的所有更改以及在出现问题时进行管理的批准。 保留你的软件和硬件资产及其配置的记录。

  - **系统管理**   概述了用于执行管理任务（如数据库管理和网站管理）的标准方法。

  - **安全管理**   具有可保护 IT 基础结构的数据机密性、数据完整性和数据可用性的详细策略和计划。 这包括与维护和调整 IT 安全基础结构相关的日常活动和任务。

  - **系统疑难解答**   用于处理意外问题的大纲方法，包括防止将来出现类似问题的步骤。

  - **服务级别协议**   维护 IT 系统性能的一组目标，并根据这些目标定期测量性能。

  - **文档**   文档标准过程（如配置信息和经验教训），并使其可供需要它们的教职员工成员使用。 对配置进行更改后，请相应地更新文档。

</div>

<div>

## <a name="related-sections"></a>相关部分

继续之前，请查看以下有关系统操作的主题：

  - [Lync Server 2013 中的容量和可用性管理](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013 中的更改管理](lync-server-2013-change-management.md)

  - [Lync Server 2013 中的配置管理](lync-server-2013-configuration-management.md)

  - [Lync Server 2013 中的系统管理](lync-server-2013-system-administration.md)

  - [Lync Server 2013 中的服务级别协议](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013 中的文档](lync-server-2013-documentation.md)

  - [Lync Server 2013 中的标准过程](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013 中的紧急过程](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Microsoft 操作框架4。0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

