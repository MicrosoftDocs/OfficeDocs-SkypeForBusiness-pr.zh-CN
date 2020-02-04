---
title: Lync Server 2013：监视概述
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
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Lync Server 2013 中的监视概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-05_

在 Microsoft Lync Server 2013 中，"监视" 用于收集有关用户所涉及的通信会话的使用信息和体验质量（QoE）数据。 会话是涵盖用户与的连接的常规术语：

  - 会议

  - 会议模态（如音频/视频或应用程序共享）

  - 通过点对点对话（如即时消息或音频呼叫）的其他用户

<div>


> [!NOTE]  
> Lync Server 2013 跟踪有关每个会话的信息：谁称为谁;会话中使用了哪些终结点;该会话持续多长时间;会话的感知质量是多少;依此类推。 但是，Lync 服务器不会记录和存储实际呼叫本身。 同时还包括即时消息会话：尽管 Lync 服务器记录有关即时消息会话的信息，但它不保留会话期间发送的每条即时消息的记录。



</div>

Lync Server 收集的通话详细信息可用于任何数量的用途，包括：

  - **投资回报率（ROI）**。 管理员可以将监视服务器收集的使用数据与为以前的电话系统收集的类似数据进行比较，以便显示成本节约并帮助论证 Lync 服务器的部署。

  - **设备库存管理**。 资产管理信息可帮助管理员识别仍在使用的旧设备，这些设备需要被替换，并确定不会经常使用的昂贵设备。

  - 技术支持。 疑难解答数据使支持工程师能够确定用户调用失败的原因，以及执行此操作，而无需收集服务器或客户端日志。 对 Microsoft Lync 2013 和 Lync Server 2013 没有深入技术知识的支持人员可以随时访问和理解此信息。

  - **系统故障排除**。使管理员能够检测可能阻止最终用户执行基本任务（如加入会议、建立呼叫或发送即时消息）的重大问题。

除了这种基本的呼叫信息外，监视服务器还提供允许 SIP 终结点（如 Lync 2013）提供服务器无权访问的故障排除信息的机制：

  - **影响质量的媒体指标**。 这些指标涉及呼叫本身的实际传输;也就是说，它们提供一种在网络上呼叫慷慨的旅行日志种类。 这些指标（包括诸如数据包丢失、抖动和往返行程之类的内容）提供有关在呼叫离开终结点到到达其他人的终结点时所发生的情况的信息。

  - **报告给最终用户的问题**。 这些指标包括在以下情况下 Lync 2013 的质量较差通知： Lync 在以下情况下向最终用户提供的信号较差：计算机的声音太远、网络连接较差或质量较差，因为计算机上的其他程序占用可用的资源。

  - **环境信息**。这些指标详细说明了呼叫质量因素，如所使用的麦克风和扬声器的类型、用户是否通过 VPN 连接进行连接以及用户是否使用无线连接。

在每次通话结束时，SIP 兼容终结点会自动将此信息传输到主持呼叫的前端服务器。 你不必执行任何操作就能让终结点传输该信息；该行为内置于 SIP 协议中。 但是，如果要收集和存储该信息，则需要安装和启用监控。 如果确实安装并启用了监控，则呼叫信息将由前端服务器上运行的代理收集，并被中继到一对 SQL Server 数据库。

请注意，在 Lync Server 2013 中，安装和配置监视的过程已得到简化。 在以前版本的软件中，监视需要一个单独的监视服务器角色，该角色通常表示将单独的计算机用作监视服务器。 但是，在 Lync Server 2013 中，已消除了监视服务器角色。 相反，监视服务（以 "统一数据收集代理" 的形式）已 collocated 到所有前端服务器中。 这至少有两个主要优点。 监视服务的 Collocation：

  - 减少实现 Lync Server 2013 时所需的服务器角色数。 通过减少监视服务器角色，还可以通过消除维护专用服务器的需要来帮助降低成本。

  - 降低了 Lync Server 2013 设置和管理的复杂性。 通过 collocating 每个前端服务器上的监视服务，您不必再安装、配置和管理监视服务器角色。

有关详细信息，请参阅 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)主题。

</div>

<span> </span>

</div>

</div>

</div>

