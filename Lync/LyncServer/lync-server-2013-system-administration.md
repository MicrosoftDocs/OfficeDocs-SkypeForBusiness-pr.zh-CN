---
title: Lync Server 2013：系统管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c830b689f0f55c2af191443583394e9f8c22eed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497499"
---
# <a name="system-administration-in-lync-server-2013"></a>Lync Server 2013 中的系统管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-18_

系统管理包括日常管理任务（规划的和按需），这是使 IT 系统平稳运行所必需的。 通常情况下，系统管理任务包含在书面过程中。 这些过程有助于确保所有支持人员都使用相同的标准工具和方法。

在 Lync 环境中，典型的系统管理任务包括备份和存档池、监视日志、创建和管理用户以及更新防病毒软件。

<div>

## <a name="system-troubleshooting"></a>系统故障排除

组织必须准备好处理意外问题，并且应具有一个过程来从报告这些问题的点开始解决这些问题。 有关如何诊断问题的支持人员的信息应记录并在将来使用，以避免不必要的重复完成工作。

</div>

<div>

## <a name="system-troubleshooting-process"></a>系统故障排除过程

下图显示了系统故障排除过程以及与其他操作角色的交互。

**系统疑难解答流程图**

![系统疑难解答流程图](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系统疑难解答流程图")

  - **分类和优先顺序**    此任务通常由服务台执行。 例如，一个问题可能会被分组为软件问题或硬件问题。 然后，将该问题路由到相应的支持团队进行调查。 通常在 SLA 中定义用于确定问题的优先级以及响应时间和解决时间的规则。

  - **调查和诊断**    相应的支持团队将诊断问题并建议更改，以解决问题。 如果解决方案简单且不需要更改控制，则可以立即应用解决方案。 如果解决方案不是很简单，应引发更改请求，并且建议的工作应由更改管理过程（通常位于 "快速跟踪" 过程下）进行管理。 应使用配置管理过程记录所做的任何更改。

  - **关闭并录制**    测试解决方法后，应关闭该问题。 如果要从问题中了解课程，应在知识库中创建一个条目。

  - **评审和趋势分析**    应定期检查最近的问题，以确定问题趋势。 例如，如果用户遇到频繁的登录到 Lync 网站时遇到的问题，则可能是网络带宽问题导致的。 解决问题的时间，应检查系统可用性中断的影响，并与 SLA 进行比较。 与与客户参与服务问题（如客户经理）的人员应了解所有重大问题。

</div>

<div>

## <a name="issue-management-tools"></a>问题管理工具

服务台工具使员工能够记录、分类和优先处理新问题。 然后，工具将提供工作流过程，通过调查和诊断（通常由多个支持团队）来管理问题服务请求。 工具（通常会提供有关解决时间和历史趋势的报告）也可能包含知识库数据库，可用于搜索过去的问题。

Microsoft 知识库是 Microsoft 遇到的支持问题的有用记录。 有关详细信息，请参阅 Microsoft 支持网站 (<https://go.microsoft.com/fwlink/?linkid=14898>) 。

第三方软件通常需要进行自定义以满足组织的需求，例如团队的组织、报告要求以及 SLA 所需的度量。

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>集中管理和分散式管理

执行系统管理任务的角色和责任取决于组织是采用集中式模型、分散模型还是二者的组合。

  - **集中式模型**    在集中式模型中，一个或多个管理组保持对整个 Lync Server 环境的完全控制。 此管理模型类似于一个数据中心，其中的所有管理任务均由一个信息技术组执行。 应根据经验和专业技能定义团队中的角色和职责。

  - **分散模型**    分散的组织位于多个地理位置，并具有在不同位置运行的 Lync Server 服务器和管理员团队。 例如，可能有本地管理人员和一个或多个运行 Lync Server 2013 的服务器，每个国家/地区。 或者，可能有一池服务器正在运行 Lync Server 2013 和面向北美的管理团队，一个用于欧洲。 有时，您可能希望管理员仅对自己的地理区域负责，并限制管理其他区域中的资源的权限。

通过使用基于角色的访问控制 (RBAC) ，Lync Server 还允许您将特定管理任务委派给特定人员或组。 RBAC 允许管理员将特定的用户权限和权限委派给其他管理员，以执行可能的一小部分管理任务。 通过使用 RBAC，用户执行特定管理任务的能力取决于分配给用户的 RBAC 角色。 RBAC 提供用户可以基于用户所属的 RBAC 角色运行的 cmdlet 的列表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

