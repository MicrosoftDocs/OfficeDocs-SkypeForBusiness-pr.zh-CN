---
title: Lync Server 2013：配置管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6997f64695a4df606e6fbaa9767f22be04de6615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Lync Server 2013 中的配置管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-05-15_

配置管理是记录和跟踪硬件和软件资产以及系统配置信息的过程。 它通常用于跟踪软件许可证、维护客户端计算机和服务器的标准硬件和软件内部版本，并定义新计算机的命名标准。 配置管理通常涵盖以下类别：

  - **硬件**   此类别跟踪 IT 组织拥有的设备、设备所在的设备以及使用设备的人员。 此信息使组织能够规划和预算升级、维护标准硬件版本、报告 IT 资产价值以进行会计用途，并帮助防止盗窃。

  - **软件**   此类别跟踪安装在每台计算机上的软件、版本号以及许可证的保留位置。 此信息有助于规划升级，确保软件获得许可，并检测是否存在未经授权（和未经许可）的软件。

  - **标准版本**   此类别跟踪客户端计算机和服务器的当前标准内部版本，以及客户端计算机和服务器是否满足此标准。 定义和强制实施标准生成有助于支持人员，因为员工只需要维护每个软件的有限数量的版本。

  - **累积更新和修补程序**   此类别可跟踪测试和批准使用的服务包和哪些计算机处于最新状态。 此信息对于降低计算机遭到破坏的风险和检测已安装未经批准的更新的用户非常重要。

  - **系统配置信息**   此类别跟踪系统的功能、系统元素之间的交互以及依赖于平稳运行的系统的进程。 例如，可以在一台服务器上配置第三方代理服务器。 应了解代理服务器对此服务器的依赖，并且如果出现故障，可能需要应急计划。 如果代理服务器可以配置为同时与另一个前端服务器通信，则依赖项和应急计划可能会发生更改。

<div>

## <a name="implementing-configuration-management"></a>实现配置管理

确定需要管理的项目后，通过收集数据和报告数据来实现配置管理。 小型组织最简单的方法是手动收集数据（客户端计算机、操作系统、已安装软件的数量和型号），并将其保存在 Office Word 或 Office Excel 文档中。 对于较大、更复杂且不断变化的系统，必须自动发现资产和详细信息的收集。 确定哪些信息与你的组织相关，并将其记录在数据库中。

配置管理数据库是在以下领域支持人员和管理的有用工具：

  - **安全审核**   通过数据库，你可以确定运行 Lync Server 和客户端计算机系统的服务器，这些服务器必须已应用修补程序，或者已错过安装 service pack 或最新防病毒更新。

  - **软件安装**   识别客户端软件版本和跟踪它们将帮助管理员规划版本更新和新安装，还将帮助管理员提供许可文档和合规性。

  - **配置信息**   如果您维护的所有设置的最新列表均已更改为默认值，那么您将能够快速、高效地解决问题。

  - **规划升级**   如果容量检查发现您的 Lync 数据库服务器上需要额外的存储空间，请务必了解每台服务器是否有内部 RAID 控制器。 如果是，则它们是同一型号？ 是否已安装相同数量的磁盘？ 配置管理数据库将指示每种情况下可以安装的磁盘类型、编号和升级路径。

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>用于配置管理的工具

有许多工具可用于发现、审核和报告资源。 本部分将讨论其中的一些工具。

  - **自动脚本**   你可以编写简单的脚本来报告诸如操作系统、service pack 级别和软件是否存在于特定计算机集的项目。 你可以将这些脚本编写为组织的确切要求。 但是，所需数量的脚本及其复杂性可能会使脚本的创建和维护成本高昂。

  - **自动化工具**   根据您的企业规模和组织需求，您可能需要考虑使用自动工具。 诸如 Microsoft 终结点配置管理器之类的工具合并标准报表模板（如 service pack 级别），并允许你创建自定义报表（例如，自定义应用程序）。 Microsoft 终结点配置管理器还可以用于报告硬件和软件配置。

</div>

<div>

## <a name="relationship-with-change-management"></a>与更改管理的关系

配置管理与变更管理紧密相关。 配置管理确定需要更改，并确定和记录更改已发生。 例如，配置管理数据库可用于标识需要修补程序的服务器。 然后，更改管理定义应用修补程序的过程。

相反，如果新的累积更新已推出，则更改管理过程应将此信息提供给配置管理系统。 配置管理工具可能需要配置为识别新软件，以便他们能够发现和跟踪软件的部署位置和时间。

</div>

</div>

<span> </span>

</div>

</div>

</div>

