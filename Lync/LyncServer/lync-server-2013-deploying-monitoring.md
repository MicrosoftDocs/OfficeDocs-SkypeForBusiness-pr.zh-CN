---
title: 'Lync Server 2013: 部署监视'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中部署监视

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-12-17_

对 Microsoft Lync Server 2013 监视基础结构进行了重大更改, 从监视服务器角色已弃用这一事实开始。 现在, 在每个前端服务器上 collocated, 而不是单独的监视服务器角色 (通常需要组织才能设置专用计算机作为监视服务器)。 此外, 此更改有助于:

  - 减少实现 Lync Server 2013 时所需的服务器角色数。 在这种情况下, 降低监视服务器的角色还有助于通过消除维护专用服务器来进行监视来降低成本。

  - 降低 Lync 服务器设置和管理的复杂性。 通过自动 collocating 每台前端服务器上的监视服务, 您不必再安装、配置和管理监视服务器角色。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中, 存档服务器角色也已被弃用。 与监视服务一样, Lync Server 2013 存档服务现在在每个前端服务器上 collocated。 请注意, 这一点很重要, 因为监视和存档通常共享相同的 SQL Server 数据库实例。



</div>

正如你所料, 这些更改对如何安装和管理监视服务有重大影响。 例如, 由于不再存在监视服务器角色, 已从 Lync Server 拓扑生成器中删除了 "监视服务器" 节点;这意味着你不再使用拓扑生成器的新监视服务器向导, 以便将新的监视服务器添加到你的拓扑。 (该向导不再存在。)相反, 你通常会通过完成以下两个步骤来实现拓扑内的监视服务:

1.  在设置新的 Lync 服务器池的同时启用监视。 (在 Lync Server 2013 中, 监视功能在逐个池的基础上启用或禁用。)请注意, 你可以为池启用监视, 而无需实际收集监视数据, 此过程将在本文档的 "配置呼叫详细记录" 和 "体验设置质量" 部分中介绍。

2.  使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。

尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。 如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。 请记住, 即使不再是监视服务器角色, 你仍然需要创建一个或多个监视存储: 后端数据库, 用于存储由监视服务收集的数据。 可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 创建这些后端数据库。

<div>


> [!NOTE]  
> 如果已为池启用监视, 则可以禁用收集监视数据的过程, 而无需更改拓扑: Lync Server Management Shell 提供了一种禁用 (稍后重新启用) 呼叫详细记录 (CDR) 或质量的方法的体验 (QoE) 数据收集。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。



</div>

在 Lync Server 2013 中进行监视的另一个重要增强是 Lync Server 监视报告现在支持 IPv6: 使用 "IP 地址" 字段的报表将显示 IPv4 或 IPv6 地址, 具体取决于: 1) 正在使用的 SQL 查询;和 (2) 将 IPv6 地址存储在监视数据库中的位置。

<div>


> [!NOTE]  
> 确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。



</div>

本文档将指导你完成安装和配置 Lync Server 2013 的监视和监视报告的过程。 本文提供了会对您有所帮助的分步说明：

  - 在拓扑中启用监控并使监控存储与前端池关联。

  - 安装 SQL Server Reporting Services 和 Lync Server Monitoring 报表。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。

  - 配置呼叫详细记录 (CDR) 和体验质量 (QoE) 数据收集。 呼叫详细记录为您提供了一种跟踪 Lync 服务器功能 (如 IP 语音电话 (VoIP) 电话呼叫) 的使用方式的方式。即时消息 (IM);文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。

  - 从监控数据库中手动清除 CDR 和/或 QoE 记录。

</div>

<span> </span>

</div>

</div>

</div>

