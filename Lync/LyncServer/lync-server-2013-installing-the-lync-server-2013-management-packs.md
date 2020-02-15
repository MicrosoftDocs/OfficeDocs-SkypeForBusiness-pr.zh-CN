---
title: Lync Server 2013：安装 Lync Server 2013 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2324d166ab43153cf37b71500da438e6db6b4b4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>安装 Lync Server 2013 管理包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

System Center Operations Manager 本身能够仅监视 Windows 操作系统的一小部分。 但是，您可以通过安装管理包来扩展 System Center Operations Manager 的功能，该软件规定 System Center Operations Manager 可以监视的项目，包括应如何监视这些项目以及应如何使用警报触发和报告。 Microsoft Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：

  - 组件和用户管理包（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）跟踪事件日志中记录的、由性能计数器注册的 Lync Server 问题，或记录在呼叫详细信息记录（CDR）或用户体验质量（QoE）中的数据库. 对于关键问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或短信服务（SMS）消息通知管理员。 SMS 是一种可用来将文本消息从一个移动设备发送到另一个移动设备的技术。
    
    <div>
    

    > [!NOTE]  
    > 有关配置 Operations Manager 通知的详细信息，请参阅 TechNet Library 中的配置通知<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>。

    
    </div>

  - 主动监控包（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）主动测试重要的 Lync Server 组件，例如登录到系统、交换即时消息或呼叫位于公共交换电话上的电话网络（PSTN）。 这些测试通过使用 Lync Server 综合事务 cmdlet 进行。 例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。 如果这种模拟的消息对话失败，则会生成一个警报。

Lync Server 2013 附带的两个管理包包含大量针对 Microsoft Lync Server 2010 使用的管理包的增强功能。 例如，Lync Server 2013 组件管理包并不局限于监视 Lync Server 本身。 除了监视 Lync Server 的事件日志和性能计数器，组件管理包还可以跟踪关键项目的性能，并发出警报，如：

  - ****   如果 internet 信息服务脱机，将发出 internet 信息服务（IIS）警报。 这一点很重要，因为 Lync Server web 服务依赖于 IIS。

  - ****   如果系统资源（如可用内存）开始运行较低，将发出进程使用率警报。 即使 Lync Server 不负责高系统使用率，也会发出这些警报。

  - ****   在威胁到服务器的生存能力的硬件或软件问题的情况下，将发出计算机故障事件警报。 例如，如果服务器似乎有遇到硬盘故障的危险，则会通知 Lync Server 管理员。

新管理包的主要功能还包括增强的报告功能。 Lync Server 2013 的新报告包括：

  - **端到端方案可用性报告**   此报告详细介绍了关键 Lync Server 服务（如注册或状态）的可用性/正常运行时间。

  - **容量报告**   使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用情况）的趋势。

  - **组件报告**   此报告列出按 Lync Server 组件分组的顶部警报生成器。

除了这些预先设计的报告之外，Lync Server 2013 的管理包还会自动报告呼叫可靠性（按呼叫详细信息记录衡量的指标）和 QoE 状态（由经验质量度量）的警报。 如果已启用呼叫详细信息记录，可以通过 System Center Operations Manager 控制台完成以下过程来查看呼叫可靠性警报：

  - 依次展开“监控”****、“Microsoft Lync Server 2013 运行状况”****、“呼叫可靠性和媒体质量”****，然后单击“呼叫可靠性”****。

若要查看 "体验质量" 警报，请从 System Center Operations Manager 控制台完成以下过程：

  - 依次展开“监控”****、“Microsoft Lync Server 2013 运行状况”****、“呼叫可靠性和媒体质量”****，然后展开“媒体质量”****。

Lync Server 2013 的管理包现在使用计算机级发现，而不是在 Microsoft Lync Server 2010 中使用的集中发现机制。 这意味着，每个 System Center 代理实质上都会发现自己并报告它是否存在于中央管理服务器中。 使用计算机级别发现可简化对 System Center 基础结构的管理，还允许不同版本的 Lync Server 管理包（例如，lync server 2010 的管理包和 Lync Server 2013 的管理包）共存.

</div>

<span> </span>

</div>

</div>

</div>

