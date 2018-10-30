---
title: Lync Server 2013：监视网络性能
TOCTitle: 监视网络性能
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn720923(v=OCS.15)
ms:contentKeyID: 62246695
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中监视网络性能

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 是一种实时通信技术，很大程度上依赖于网络通过即时消息 (IM)、语音呼叫或视频通信在用户之间实现通信。因此，请持续监视网络性能以帮助确保用户选择的通信形式提供尽可能最佳的体验，这非常重要。

可以在两个级别测量网络性能：

  - **总体网络性能**   此级别的性能测量使组织能够创建其网络的宏观视图，通常通过第三方网络监视系统实施。这些系统将从路由器等远程网络设备收到性能和容量数据，并在整个网络上进行传递，这使管理员能够在一天的任何时间确定任何给定网络组件的运行状况。

  - **个别服务器性能**   此级别的性能测量限制为特定服务器，将帮助管理员测量特定服务器的网络性能以解决特定性能问题或者作为容量规划过程的一部分测量给定时间段内个别服务器的性能。

您可以使用以下部分所述的工具监视网络。

## 总体网络性能监视的工具

## System Center Operations Manager 2012

System Center Operations Manager 提供端对端服务管理，它容易自定义和扩展，从而提高 IT 环境的服务等级。这使运营和 IT 管理团队能够识别和解决影响分布式 IT 服务的运行状况。端对端服务管理并不限制于基于 Microsoft 的环境。通过对 Web 服务管理 (WS-Management)、简单网络管理协议 (SNMP) 和合作伙伴解决方案提供支持，能够实现在 System Center Operations Manager 2012 内的服务监视中包括不运行 Microsoft 操作系统和硬件的系统。

## System Center Operations Manager 2012 和第三方管理解决方案

**EMC Smarts**   适用于 Operations Manager 的 EMC 解决方案可帮助您快速解决始终影响服务等级的问题。通过使用适用于 Operations Manager 的 EMC 解决方案，您可以在一个集成的自动化解决方案中管理和监视您的整个 IT 服务链。您将轻松地识别性能和可用性问题的根本原因并快速解决它们，从而降低影响和成本。关键好处包括：

  - 管理先进且易于使用   侧重于交付战略业务价值，而不是手动排序和筛选令人困惑的警报。

  - **解决速度更快**   更快地解决 IT 问题和响应业务需求，从而降低影响和成本。

  - **操作简化**   通过综合多个管理工具、应用程序和终端来避免 IT 复杂性。

可以在这里找到更多信息：

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[适用于 Microsoft System Center Operations Manager 的解决方案](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

## 第三方解决方案

**HP 网络管理中心（以前称为 HP OpenView）**   [HP 网络管理中心](https://h10078.www1.hp.com/cda/hpms/display/main/hpms_content.jsp?zn=bto%26cp=1-11-15-119_4000_100__)提供集成的故障和性能管理，可提高网络可用性和性能。网络管理中心是 HP 自动化网络管理解决方案的一部分，它融合了故障、性能、配置和更改管理。

**Cisco 网络管理和自动化产品**   对于企业，Cisco 提供了诸多管理产品（包括 CiscoWorks LAN 管理解决方案和 Cisco 网络分析模块）来帮助提高操作效率和减少网络停机时间。有关这些产品的其他数据，请参阅 Cisco 网站，网址为 [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)。

简单网络管理协议 (SNMP)   简单网络管理协议 (SNMP) 是一种网络管理标准，它定义管理 TCP/IP 网络的战略。SNMP 使您能够捕获有关网络的配置和状态信息，并将该信息发送给指定计算机执行事件监视。这一基于标准的网络管理协议使用分布式体系结构，包括以下各项：

  - 多个托管节点，每个节点都具有称为“代理”的 SNMP 实体，它可提供对管理规范的远程访问。

  - 至少一个称为“管理器”的 SNMP 实体运行管理应用程序来监视和管理托管元素。托管元素是指主机、路由器等设备。可通过访问其管理信息来监视和控制它们。

  - 管理协议 SNMP 用于在管理站和代理之间传达管理信息。管理信息是指位于虚拟信息存储（称为管理信息基础 (MIB)）中的托管对象集合。

> [!NOTE]  
> 上面提供了第三方网络管理解决方案的示例。此列表并不是决定性的，Microsoft 并不偏向于任何特定供应商解决方案。请向网络服务提供商或您的技术提供商咨询以确定最适合您的组织的网络监视解决方案。



## 用于监视个别服务器网络性能的工具

## System Center Operations Manager 2012

System Center Operations Manager 2012 使管理员能够通过 Windows Server 2012 管理包查看个别服务器的网络性能：Windows Server 操作系统管理包包括使管理员能够监视网络适配器性能和适配器运行状况的“性能”管理包。

## Windows 网络监视器

收集、显示和分析服务器上的资源使用状况并测量网络流量。网络监视器专门监视网络活动。通过捕获和分析网络数据并将此数据和性能日志配合使用，您可以确定网络使用状况、识别网络问题和预测未来的网络需求。

有关 Network Monitor 3.4 的详细信息和要了解如何安装和配置网络监视器以及捕获和分析数据，请查看此文章：Network Monitor 3.3 概述。此外，请查看网络监视器博客，网址为 <http://blogs.technet.com/b/netmon/>。

