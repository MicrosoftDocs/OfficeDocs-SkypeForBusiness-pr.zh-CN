---
title: 安装 Lync Server 2013 管理包
TOCTitle: 安装 Lync Server 2013 管理包
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205202(v=OCS.15)
ms:contentKeyID: 49314032
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync Server 2013 管理包

 

_**上一次修改主题：** 2016-12-08_

System Center Operations Manager 本身只能监控一小部分的 Windows 操作系统。但是，您可以通过安装管理包（即规定 System Center Operations Manager 可以监控的项目的软件，包括应如何监控这些项目，以及如何触发和报告警报），来扩展 System Center Operations Manager 的功能。Microsoft Lync Server 2013 包括两个可提供以下功能的 System Center Operations Manager 管理包：

  - 组件和用户管理包 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 可跟踪记录在事件日志中、由性能计数器注册，或者记录在呼叫详细信息记录 (CDR) 或体验质量 (QoE) 数据库中的 Lync Server 问题。对于严重问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或短消息服务 (SMS) 消息通知给管理员。SMS 是一种可用来将文本消息从一个移动设备发送到另一个移动设备的技术。
    
    > [!NOTE]  
    > 有关配置 Operations Manager 通知的详细信息，请参阅 TechNet 库中的“配置通知”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0x804</a>。
    


  - 主动监控包 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 会主动测试关键的 Lync Server 组件，如登录到系统、交换即时消息或对位于公用电话交换网 (PSTN) 的电话发起呼叫。这些测试是使用 Lync Server 综合事务 cmdlet 来执行的。例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。如果这种模拟的消息对话失败，则会生成一个警报。

包含在 Lync Server 2013 中的这两个管理包同与 Microsoft Lync Server 2010 结合使用的管理包相比，包含了大量的增强功能。例如，Lync Server 2013 组件管理包并不限于监控 Lync Server 本身。除了监控 Lync Server 的事件日志和性能计数器以外，该组件管理包还可以跟踪诸如以下重要项目的性能并针对其发出警报：

  - **Internet 信息服务 (IIS)**   如果 Internet 信息服务脱机，则会发出警报。这一点非常重要，因为 Lync Server Web 服务依赖于 IIS。

  - **处理程序使用情况**   如果系统资源（如可用内存）开始不足，则会发出警报。即使这种很高的系统使用率并非是由 Lync Server 所造成，也会发出这些警报。

  - **计算机故障事件**   在发生威胁到服务器可行性的硬件或软件问题时，将会发出警报。例如，如果服务器似乎可能发生硬盘故障，则会通知 Lync Server 管理员。

新管理包的主要功能还包括增强的报告功能。Lync Server 2013 的新报告包括：

  - **端到端方案可用性报告**   此报告详细介绍了关键的 Lync Server 服务（如注册或状态）的可用性/运行时间。

  - **容量报告**   通过使用性能计数器信息，此报告显示了系统组件（如内存可用性和处理器使用情况）的趋势。

  - **组件报告**   此报告列出了按 Lync Server 组件进行分组的主要警报生成器。

除了这些预定的报告之外，Lync Server 2013 的管理包还会自动报告呼叫可靠性（由呼叫详细信息记录衡量的指标）和 QoE 状态（由体验质量衡量的指标）的警报。如果已启用呼叫详细信息报告，则可以通过从 System Center Operations Manager 控制台中完成以下过程来查看“呼叫可靠性”警报：

  - 依次展开“监控”、“Microsoft Lync Server 2013 运行状况”、“呼叫可靠性和媒体质量”，然后单击“呼叫可靠性”。

要查看“体验质量”警报，请从 System Center Operations Manager 控制台中完成以下过程：

  - 依次展开“监控”、“Microsoft Lync Server 2013 运行状况”、“呼叫可靠性和媒体质量”，然后展开“媒体质量”。

Lync Server 2013 的管理包现在使用机器级别的发现，而不是 Microsoft Lync Server 2010 中所使用的中心发现机制。这意味着每个系统中心代理本质上都会发现自身并向中央管理服务器报告自己的存在性。通过使用机器级别的发现，可简化系统中心基础结构的管理，同时允许不同版本的 Lync Server 管理包（例如，Lync Server 2010 的管理包和 Lync Server 2013 的管理包）共存。

