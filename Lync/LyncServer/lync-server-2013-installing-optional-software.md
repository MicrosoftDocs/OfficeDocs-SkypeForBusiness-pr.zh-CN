---
title: Lync Server 2013：安装可选软件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ce81d2005a9bbed5432f2c78f3d8df5507d6679
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>在 Lync Server 2013 中安装可选软件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

Microsoft Lync Server 2013，规划工具旨在导出到 Microsoft Excel 和 Microsoft Visio。 尽管这些应用程序不是规划工具的操作所必需的，但它们确实增加了部署和文档设计的重要价值。

<div>

## <a name="optional-software"></a>可选软件

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到 Microsoft Excel 会创建一个报告，该报告将在电子表格中显示七个选项卡：

  - 摘要–显示有关站点配置的信息，包括用户计数、容量设置和服务器配置文件信息。

  - 硬件配置文件–显示有关拓扑中指定的服务器的建议硬件配置的报告，包括 CPU、内存、磁盘和网络接口。 此外，还包括服务器组件的数量和建议规格。 此外，每个服务器都由网站定义，以提供按站点的服务器要求的完整表示形式。

  - 端口要求–显示已启用的所有端口以及与域名系统负载平衡（DNS LB）和硬件负载平衡器（HLB）的关联的报告。 您应使用此报告来规划防火墙和 DNS LB 和 HLB 配置。

  - 摘要报告–显示设置边缘服务器网络所需设置的一般摘要。

  - 证书报告–显示用于运行边缘服务器所需的证书所需的使用者名称和使用者替代名称。

  - 防火墙报告–显示源和目标端口以及外部和内部接口的 IP 地址。

  - DNS 报告–显示您创建的每个 DNS 条目所需的完全限定域名（FQDN）和 IP/VIP 地址。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio 将创建一个图表，以供您配置的拓扑和基础结构的文档用途使用。 可以对导入的图表进行编辑和重新排列以满足文档需求。 典型的 Visio 图表将包括：

<div>


> [!NOTE]  
> 如果您的设计大得足以要求三台以上的前端服务器，则会为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 Fqdn 创建一个额外的页面。



</div>

  - 全局拓扑-配置的 Lync Server 2013 网站的关系图。

  - "站点名称" 选项卡–显示具有边缘服务器、防火墙、公共交换电话网络（PSTN）和网关的站点配置拓扑，以及内部服务器部署。 内部部署包括已配置的服务器和池，包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息（UM）服务器、Exchange 邮箱服务器、Office Web Apps Server中介服务器和持久聊天服务器。

  - 边缘网络图–详细说明边缘服务器配置与关联的 IP 地址和 Fqdn 的图表。 此外，还包括了 DNS 负载平衡和硬件负载平衡器。 此外，还将显示 Director 和前端服务器或前端池，其中包含关联的 DNS LB 或 HLB 以及分配的 IP 地址（规划工具同时支持 IPv4 和 IPv6 地址）和 FQDN。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中安装规划工具](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

