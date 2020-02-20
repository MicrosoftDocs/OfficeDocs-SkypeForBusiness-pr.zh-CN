---
title: Lync Server 2013：部署监控
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cd492679cb412c57ea37698df198eef7721b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中部署监控

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-17_

对 Microsoft Lync Server 2013 监视基础结构进行了重大更改，从监视服务器角色已弃用这一事实开始。 不再采用不同的监控服务器角色（通常需要组织设置专用计算机来充当监控服务器），现在监控服务已并置到每台前端服务器中。 除了其他优点外，此更改还有助于：

  - 减少实现 Lync Server 2013 时所需的服务器角色数。 在此情况下，减少监控服务器角色数还可帮助降低成本，因为无需维护用于监控的专用服务器。

  - 降低 Lync Server 安装和管理的复杂性。 通过自动在每台前端服务器上并置监控服务，您不必再安装、配置和管理监控服务器角色。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，存档服务器角色也已被弃用。 与监视服务一样，Lync Server 2013 存档服务现已在每台前端服务器上并置。 注意到这一点非常重要，只是因为监控和存档通常共享同一 SQL Server 数据库实例。



</div>

正如您可能预料的那样，这些更改对监控服务的安装和管理方式具有重要影响。 例如，因为不再存在监视服务器角色，所以已从 Lync Server 拓扑生成器中删除了监视服务器节点;反过来，这意味着您不再使用拓扑生成器的新监视服务器向导，以便将新的监视服务器添加到拓扑中。 （该向导不再存在。）相反，您通常会通过完成以下两个步骤来在拓扑中实现监视服务：

1.  在设置新的 Lync Server 池的同时启用监控。 （在 Lync Server 2013 中，监视功能是逐个池启用或禁用的。请注意，您可以为池启用监控，而无需实际收集监控数据，本文档的 "配置呼叫详细信息记录" 和 "体验质量设置" 一节中所述的过程。

2.  使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。

尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。请记住，即使不再存在监控服务器角色，您仍需要创建一个或多个监控存储：用于存储监控服务所收集数据的后端数据库。可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 创建这些后端数据库。

<div>


> [!NOTE]  
> 如果已为池启用监控，则可以禁用收集监控数据的过程，而无需更改拓扑： Lync Server 命令行管理程序提供了一种禁用（随后重新启用）呼叫详细信息记录（CDR）或质量的方法的体验（QoE）数据收集。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。



</div>

Lync Server 2013 中进行监视的另一个重要改进是，Lync Server 监控报告现在支持 IPv6：使用 IP 地址字段的报表将显示 IPv4 或 IPv6 地址（具体取决于：1）所使用的 SQL 查询：1）。和（2）在监视数据库中存储 IPv6 地址的位置。

<div>


> [!NOTE]  
> 确保 SQL Server 代理服务启动类型为 "自动"，并且 SQL Server 代理服务正在为包含监视数据库的 SQL 实例运行，以便默认监视 SQL Server 维护作业可以按计划运行在 SQL Server 代理服务的控制下。



</div>

本文档将引导您完成为 Lync Server 2013 安装和配置监控和监控报告的过程。 本文提供了会对您有所帮助的分步说明：

  - 在拓扑中启用监控并使监控存储与前端池关联。

  - 安装 SQL Server Reporting Services 和 Lync Server Monitoring 报告。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。

  - 配置呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据收集。 呼叫详细信息记录提供了一种跟踪 Lync Server 功能（如 IP 语音（VoIP）电话呼叫）的使用方式的方法。即时消息（IM）;文件传输;音频/视频（A/V）会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。

  - 从监控数据库中手动清除 CDR 和/或 QoE 记录。

</div>

<span> </span>

</div>

</div>

</div>

