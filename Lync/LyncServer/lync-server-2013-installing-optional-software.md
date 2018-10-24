---
title: Lync Server 2013：安装可选软件
TOCTitle: 安装可选软件
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615032(v=OCS.15)
ms:contentKeyID: 52061104
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中安装可选软件

 

_**上一次修改主题：** 2013-02-21_

Microsoft Lync Server 2013 规划工具专为导出到 Microsoft Excel 和 Microsoft Visio 而设计。尽管这些应用程序对于 规划工具操作而言不是必需的，但它们可以显著增加设计的部署和记录价值。

## 可选软件

## Microsoft Excel

将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：

  - 摘要 – 显示有关站点配置的信息，包括用户计数、容量设置和服务器配置文件信息。

  - 硬件配置文件 – 显示有关拓扑中指定的服务器的推荐硬件配置的报告，这些配置包括 CPU、内存、磁盘和网络接口。还包括服务器组件的数量和推荐规格。此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。

  - 端口要求 – 显示所有已启用端口以及与域名系统负载平衡 (DNS LB) 和硬件负载平衡器 (HLB) 的关联的报告。应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。

  - 摘要报告 – 显示设置 边缘服务器网络所需的设置的一般摘要。

  - 证书报告 – 显示使用者名称和使用者替代名称，运行 边缘服务器所需的证书需要这些信息。

  - 防火墙报告 – 显示源端口和目标端口以及外部和内部接口的 IP 地址。

  - DNS 报告 – 显示您所创建的每个 DNS 条目所需的完全限定域名 (FQDN) 和 IP/VIP 地址。

## Microsoft Visio

将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：

> [!NOTE]  
> 如果您的设计大到需要三台以上前端服务器，则会为 前端池、 前端服务器、运行 SQL Server 的计算机、IP 地址和 FQDN 创建另一个页面。



  - 全局拓扑 – 配置的 Lync Server 2013 站点图。

  - “站点名称”选项卡 – 显示包含 边缘服务器、防火墙、具有网关的公用电话交换网 (PSTN) 及内部服务器部署的站点配置拓扑。内部部署由配置的服务器和池组成，包括前端池、基于 SQL Server 的服务器、 Active Directory 域服务、控制器、Exchange 统一消息 (UM) 服务器、Exchange 邮箱服务器、Office Web Apps Server、 中介服务器和 持久聊天服务器。

  - 边缘网络图 – 详述包含关联的 IP 地址和 FQDN 的 边缘服务器配置的图。还包括 DNS 负载平衡和硬件负载平衡器。此外，还显示控制器和 前端服务器或 前端池，及其关联的 DNS LB 或 HLB，以及分配的 IP 地址（ 规划工具同时支持 IPv4 和 IPv6 地址）和 FQDN。

## 另请参阅

#### 任务

[在 Lync Server 2013 中安装规划工具](lync-server-2013-installing-the-planning-tool.md)

