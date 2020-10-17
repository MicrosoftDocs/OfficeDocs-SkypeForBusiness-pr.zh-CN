---
title: Lync Server 2013：配置管理
description: Lync Server 2013：配置管理。
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
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552148"
---
# <a name="configuration-management-in-lync-server-2013"></a>Lync Server 2013 中的配置管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-05-15_

配置管理是记录和跟踪硬件和软件资产以及系统配置信息的过程。 它通常用于跟踪软件许可证，维护客户端计算机和服务器的标准硬件和软件内部版本，并定义新计算机的命名标准。 配置管理通常包含以下类别：

  - **硬件**    此类别跟踪 IT 组织所拥有的设备的各个部分、设备所在的位置以及使用设备的客户。 此信息使组织能够对升级进行规划和预算、维护标准硬件版本、针对会计目的报告 IT 资产价值，并有助于防止失窃。

  - **软件**    此类别跟踪安装在每台计算机上的软件、版本号以及许可证的保留位置。 此信息有助于规划升级、确保软件的许可并检测是否存在未经授权的 (和未经许可的) 软件。

  - **标准内部版本**    此类别跟踪客户端计算机和服务器的当前标准内部版本，以及客户端计算机和服务器是否符合此标准。 定义和强制实施标准生成有助于支持人员，因为员工只需要维护每个软件的有限数量的版本。

  - **累积更新和修补程序**    此类别可跟踪测试和批准使用的 service pack 以及哪些计算机是最新的。 此信息对于降低计算机受到危害的风险以及检测已安装未经批准的更新的用户来说非常重要。

  - **系统配置信息**    此类别跟踪系统的功能、系统元素之间的交互以及依赖于正在平稳运行的系统的进程。 例如，可以在一台服务器上配置第三方代理服务器。 应了解代理服务器对此服务器的依赖关系，如果出现故障，可能需要应变计划。 如果代理服务器也可以配置为与另一台前端服务器通信，则依赖项和应变计划可能会发生变化。

<div>

## <a name="implementing-configuration-management"></a>实现配置管理

在确定需要管理的项后，通过收集数据和报告数据来实现配置管理。 小型组织的最简单方法是手动收集数据， (客户端计算机、操作系统、已安装软件) 的编号和模型，并将其保存在 Office Word 或 Office Excel 文档中。 对于较大、更复杂且不断变化的系统，资产的发现和详细信息的收集必须是自动化的。 决定与您的组织相关的信息，并将其记录在数据库中。

在以下方面，配置管理数据库是用于支持人员和管理的有用工具：

  - **安全审核**    使用数据库，可以确定运行 Lync Server 和客户端计算机系统的服务器，这些服务器必须已应用修补程序，或者缺少安装 service pack 或最新的防病毒更新。

  - **软件安装**    标识客户端软件版本并进行跟踪将有助于管理员规划版本更新和新安装，还可帮助用户获取许可文档和合规性。

  - **配置信息**    如果您维护的所有设置的最新列表均已更改，则您将能够快速、更有效地解决问题。

  - **规划升级**    如果容量审查表明您的 Lync 数据库服务器上需要额外的存储空间，请务必了解每台服务器是否具有内部 RAID 控制器。 如果是这样，那么它们是同一个模型吗？ 是否安装了相同数量的磁盘？ 配置管理数据库将指示可安装的磁盘类型、编号以及每种情况下的升级路径。

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>用于配置管理的工具

有很多工具可用于发现、审核和报告资产。 本节讨论了其中的一些工具。

  - **自动脚本**    您可以编写简单的脚本来报告诸如操作系统、service pack 级别以及特定计算机组上是否存在软件的项目。 您可以将这些脚本编写为组织的确切要求。 但是，所需数量的脚本及其复杂性可能会导致创建和维护脚本的成本高昂。

  - **自动化工具**    根据您的业务规模和组织需求，您可能需要考虑使用自动工具。 Microsoft 终结点配置管理器等工具结合了标准报告模板 (（如 service pack 级别) ），还使您能够创建自定义的报告（例如，自定义应用程序）。 Microsoft 终结点配置管理器还可以用于报告硬件和软件配置。

</div>

<div>

## <a name="relationship-with-change-management"></a>与变更管理的关系

配置管理与变更管理密切相关。 配置管理确定是否需要更改，并确定和记录发生了更改。 例如，配置管理数据库可用于标识需要修补程序的服务器。 然后，更改管理将定义应用修补程序的过程。

相反，如果新的累积更新已推出，更改管理过程应将此信息提供给配置管理系统。 配置管理工具可能需要配置为识别新的软件，以便他们能够发现和跟踪软件的部署位置和时间。

</div>

</div>

<span> </span>

</div>

</div>

</div>

