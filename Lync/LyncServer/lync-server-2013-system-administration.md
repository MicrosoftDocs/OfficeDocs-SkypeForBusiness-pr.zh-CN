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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Lync Server 2013 中的系统管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-08-18_

系统管理包括日常管理任务（计划和按需），使 IT 系统保持平稳运行是必需的。 通常情况下，系统管理任务由书面过程覆盖。 这些过程有助于确保所有支持人员都使用相同的标准工具和方法。

在 Lync 环境中，典型的系统管理任务包括备份和存档池、监视日志、创建和管理用户以及更新防病毒软件。

<div>

## <a name="system-troubleshooting"></a>系统疑难解答

组织必须准备好处理意外问题，并且应该有一个过程来从报告问题的位置管理问题，直到其解决。 有关诊断问题的支持人员的信息应在将来记录和使用，以避免不必要的重复工作。

</div>

<div>

## <a name="system-troubleshooting-process"></a>系统故障排除过程

下图显示了系统疑难解答过程以及与其他操作角色的交互。

**系统疑难解答流程图**

![系统故障排除流程图](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "系统故障排除流程图")

  - **对此任务进行分类和设置优先级**   通常由服务台执行。 例如，问题可能会被分组为软件问题或硬件问题。 然后，该问题将路由到相应的支持团队进行调查。 确定问题优先级的规则以及响应时间和解决时间的规则通常在 SLA 中定义。

  - **调查和诊断**   相应的支持团队诊断问题并建议更改以解决问题。 如果解决方案非常简单，并且不需要更改控制，则可以立即应用该解决方案。 如果解决方案不是很简单，则应引发更改请求，并且建议的工作应由更改管理过程进行管理，这些过程通常位于 "快速跟踪" 过程下方。 应使用配置管理过程记录所做的任何更改。

  - **关闭并录制**   测试分辨率后，应关闭问题。 如果有从问题中学到的课程，则应在知识库中创建一个条目。

  - **查看和趋势分析**   定期检查最近的问题，以确定问题趋势。 例如，如果用户经常遇到一些对其 Lync 网站的登录速度较慢的问题，则可能是网络带宽问题造成的。 解决问题的时间和对系统可用性的任何停机的影响都应进行检查，并与 SLA 进行比较。 与客户 liaises 服务问题（如客户经理）的人员应了解任何重大问题。

</div>

<div>

## <a name="issue-management-tools"></a>问题管理工具

服务台工具使教职员工能够记录、分类和优先处理新问题。 然后，工具将通过调查和诊断提供工作流流程来管理问题服务请求，这种情况通常由多个支持团队提供。 工具（通常提供有关分辨率时间和历史趋势的报表）也可能包含知识库数据库，可用于搜索过去的问题。

Microsoft 知识库是 Microsoft 所遇到的支持问题的有用记录。 有关详细信息，请参阅 Microsoft 支持网站（<http://go.microsoft.com/fwlink/?linkid=14898>）。

第三方软件通常需要自定义以满足组织的需求，例如团队的组织、报告要求和 SLA 所需的度量。

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>集中管理和分散式管理

执行系统管理任务的角色和职责取决于组织关注的是集中式模型、分散模型还是两者的组合。

  - **集中式模型**   在集中式模型中，一个或多个管理组保持对整个 Lync 服务器环境的完全控制。 此管理模型类似于一个数据中心，其中的所有管理任务均由单个信息技术组执行。 应根据经验和专业知识定义团队中的角色和职责。

  - **分散式模型**   分散的组织位于多个地理位置，并且在不同位置有运行的 Lync 服务器服务器和团队。 例如，可能有本地管理人员和一个或多个运行 Lync Server 2013 的服务器用于每个国家/地区。 或者，可能有运行 Lync Server 2013 的服务器池和北美和欧洲的管理团队。 有时，你可能希望管理员仅负责自己的地理区域，并限制管理其他区域中的资源的权限。

Lync 服务器还允许你通过使用基于角色的访问控制（RBAC）将特定的管理任务委派给特定人员或组。 RBAC 允许管理员向其他管理员委派特定的用户权利和权限，以执行可能的管理任务的子集。 通过使用 RBAC，用户执行特定管理任务的能力取决于分配给用户的 RBAC 角色。 RBAC 提供用户可以根据用户所属的 RBAC 角色运行的 cmdlet 的列表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

