---
title: Lync Server 2013：监控概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66dd239acbb274c7223363f1522f2d0c76590c37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Lync Server 2013 中的监控概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

在 Microsoft Lync Server 2013 中，监控用于收集有关用户涉及到的通信会话的使用信息和体验质量（QoE）数据。 会话是一个通用术语，它涉及用户与以下对象的连接：

  - 发布会

  - 会议形式（如音频/视频或应用程序共享）

  - 通过点对点对话（如即时消息或音频呼叫）的其他用户

<div>


> [!NOTE]  
> Lync Server 2013 保持跟踪每个会话的相关信息：谁称为谁;会话中使用了哪些终结点;会话持续多长时间;会议的感知质量是什么;等。 但是，Lync Server 不会记录和存储实际呼叫本身。 同时还包括即时消息会话：尽管 Lync Server 记录有关即时消息会话的信息，但它不维护会话期间发送的每条即时消息的记录。



</div>

Lync Server 收集的呼叫详细信息可用于任意数量的用途，包括：

  - **投资回报率 (ROI)**。 管理员可以将监视服务器收集的使用率数据与为其以前的电话系统收集的类似数据进行比较，以显示成本节约并帮助论证 Lync Server 的部署。

  - **设备库存管理**。资产管理信息可帮助管理员识别需要更换但仍在使用的旧设备和似乎根本就没有使用的昂贵设备。

  - 技术支持人员。 利用故障排除数据，技术支持工程师可以确定用户的呼叫失败的原因而不必收集服务器或客户端日志。 如果支持人员不了解 Microsoft Lync 2013 和 Lync Server 2013，则可以轻松访问和理解此信息。

  - **系统故障排除**。使管理员能够检测可能阻止最终用户执行基本任务（如加入会议、建立呼叫或发送即时消息）的重大问题。

除了这些基本的呼叫信息之外，监视服务器还提供了一种机制，允许 SIP 终结点（如 Lync 2013）提供服务器无权访问的故障排除信息：

  - **影响质量的媒体指标**。这些指标处理呼叫本身的实际传输；即，它们提供一种传输日志作为网络中的呼叫行程。这些指标（包括数据包丢失、抖动和来回行程时间）提供了从呼叫离开您的终结点到呼叫到达其他人员的终结点期间对呼叫执行的操作的相关信息。

  - **报告给最终用户的问题**。 这些指标包括在以下情况下，Lync 2013 发出的质量较差的通知：在以下情况下，Lync 会向最终用户呈现：声音过远、网络连接较差或质量较差，因为计算机上的其他程序使用可用的资源。

  - **环境信息**。这些指标详细说明了呼叫质量因素，如所使用的麦克风和扬声器的类型、用户是否通过 VPN 连接进行连接以及用户是否使用无线连接。

在每个呼叫结束时，符合 SIP 的终结点会自动将该信息传输到实现该呼叫的前端服务器。您不必执行任何操作就能让终结点传输该信息；该行为内置于 SIP 协议中。但是，如果要收集和存储该信息，则需要安装和启用监控。如果执行了安装并启用了监控，则呼叫信息将由前端服务器上运行的代理收集，并被中继到一对 SQL Server 数据库。

请注意，在 Lync Server 2013 中，安装和配置监视的过程已经过简化。 在软件的早期版本中，监视需要一个单独的监视服务器角色，该角色通常表示将单独的计算机预留为用于监视服务器。 但是，在 Lync Server 2013 中，已消除监控服务器角色。 相反，监视服务（以 "统一数据收集代理" 的形式）已并置到所有前端服务器中。 这至少有两个主要优点。 监视服务的并置：

  - 减少实现 Lync Server 2013 时所需的服务器角色数。 通过减少监控服务器角色的数量，用户便无需维护用于监控的专用服务器，从而帮助降低成本。

  - 降低了 Lync Server 2013 安装和管理的复杂性。 通过在每台前端服务器上并置监控服务，您便不必再安装、配置和管理控服务器角色。

有关详细信息，请参阅 Lync server 2013 2013 部署指南中的在[Lync server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)主题。

</div>

<span> </span>

</div>

</div>

</div>

