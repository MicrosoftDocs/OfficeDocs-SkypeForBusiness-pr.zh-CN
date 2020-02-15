---
title: Lync Server 2013：监视网络性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524499737ae1e52a36a80fbc636f005b687a6a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>在 Lync Server 2013 中监视网络性能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-04-27_

Lync Server 2013 是一种实时通信技术，它在很大程度上依赖于网络以启用用户之间的通信—通过即时消息（IM）、语音呼叫或视频通信。 因此，不断监视网络性能以确保用户选择的通信模态能够提供最佳体验，这一点非常重要。

可以在两个级别衡量网络性能：

  - **总体网络性能**   这一级别的性能测量将使组织能够创建其网络的 "大图" 视图，并且通常通过第三方网络监视系统实现。 这些系统将接收来自远程网络设备（如路由器）的性能和容量数据，并在整个网络中进行切换，使管理员能够在一天的任何时间确定任何给定网络组件的运行状况。

  - **单个服务器性能**   此级别的性能测量值仅限于特定服务器，可帮助管理员将特定服务器的网络性能 gauging，以帮助解决特定的性能问题，或在指定时间段内评估各个服务器的性能，作为容量规划过程的一部分。

您可以通过使用以下各节中介绍的工具来监视网络。

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>总体网络性能监控工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 提供了端到端服务管理，可轻松进行自定义和扩展，以在 IT 环境中改进服务级别。 这使操作和 IT 管理团队能够识别和解决影响分布式 IT 服务运行状况的问题。 端到端服务管理不限于基于 Microsoft 的环境。 对 Web 服务进行管理（WS-MANAGEMENT）、简单网络管理协议（SNMP）和合作伙伴解决方案的支持允许未运行 Microsoft 操作系统和硬件的系统包含在系统中心的服务监视中Operations Manager 2012。

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 和第三方网络管理解决方案

**Emc Smarts**   emc 针对 Operations Manager 的解决方案可帮助您快速解决影响服务级别的问题。 通过使用 EMC 针对 Operations Manager 的解决方案，您可以使用一个集成、自动化的解决方案管理和监控整个 IT 服务链。 您可以轻松地确定性能和可用性问题的根本原因，并更快地解决这些问题，从而降低影响和成本。 主要优点包括：

  - 高级、易于使用的管理将重点放在提供战略业务价值上，而不是手动排序和筛选混乱警报。

  - **更快的解决方案**   解决 IT 问题并更快地响应业务需求，从而降低影响和成本。

  - ****   通过组合多个管理工具、应用程序和终端，简化了操作以避免 IT 复杂性。

可在以下位置找到详细信息：

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Microsoft System Center Operations Manager 解决方案](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>第三方解决方案

**Hp 网络管理中心（以前称为 HP OpenView）**   [Hp 网络管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供集成的故障和性能管理，以提高网络可用性和性能。 网络管理中心是 HP 自动化网络管理解决方案的一部分，可统一执行故障、性能、配置和更改管理。

**适用于企业的 cisco 网络管理和自动化产品**   ，cisco 具有几个可提供的管理产品，包括 CiscoWorks LAN Management 解决方案和 Cisco 网络分析模块，以帮助提高运营效率并减少网络故障时间。 有关这些产品的其他数据，请参阅位于[http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)的 Cisco 网站。

简单网络管理协议（SNMP）简单网络管理协议（SNMP）是一种网络管理标准，用于定义用于管理 TCP/IP 网络的策略。 SNMP 使您能够捕获有关网络的配置和状态信息，并将信息发送到指定的计算机进行事件监视。 此基于标准的网络管理协议使用分布式体系结构，其中包括以下内容：

  - 多个托管节点，每个节点都有一个称为代理的 SNMP 实体，可提供对管理规范的远程访问。

  - 至少一个名为 manager 的 SNMP 实体，它运行管理应用程序来监视和控制托管元素。 托管元素为设备，如主机、路由器等。 通过访问其管理信息来监视和控制这些用户。

  - 管理协议（SNMP）用于在管理工作站和代理之间传递管理信息。 管理信息指的是驻留在称为管理信息库（MIB）的虚拟信息存储中的托管对象的集合。

<div>


> [!NOTE]  
> 上面提供了第三方网络监视解决方案的示例。 此列表不是明确的，Microsoft 不支持任何特定的供应商解决方案。 请咨询网络服务提供商和或相应的技术提供商，以确定您的组织的最佳网络监控解决方案。



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>用于监视单个服务器网络性能的工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 允许管理员通过 Windows Server 2012 管理包查看各个服务器的网络性能： Windows Server 操作系统管理包包含 "性能" 管理包这将允许管理员监视网络适配器的性能和适配器运行状况。

</div>

<div>

## <a name="windows-network-monitor"></a>Windows 网络监视器

收集、显示、分析服务器上的资源使用情况，并衡量网络流量。 网络监视器仅监视网络活动。 通过捕获和分析网络数据，并将此数据与性能日志结合使用，可以确定网络使用情况，识别网络问题，并预测未来的网络需求。

有关网络监视器3.4 的详细信息，并了解如何安装和配置网络监视器以及捕获和分析数据，请查看此会话：网络监视器3.3 概述。 此外，请查看[网络监视器博客](http://blogs.technet.com/b/netmon/)。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

