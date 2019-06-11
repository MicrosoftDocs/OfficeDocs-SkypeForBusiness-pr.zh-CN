---
title: 'Lync Server 2013: 安装可选软件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>在 Lync Server 2013 中安装可选软件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

Microsoft Lync Server 2013、计划工具设计用于导出到 Microsoft Excel 和 Microsoft Visio。 虽然这些应用程序不是规划工具运行所必需的, 但它们确实为设计的部署和文档增加了重要价值。

<div>

## <a name="optional-software"></a>可选软件

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

将设计导出到 Microsoft Excel 时会创建一个报告，该报告在电子表格中显示 7 个选项卡：

  - 摘要 – 显示有关站点配置的信息，包括用户计数、容量设置和服务器配置文件信息。

  - 硬件配置文件 – 显示有关拓扑中指定的服务器的推荐硬件配置的报告，这些配置包括 CPU、内存、磁盘和网络接口。还包括服务器组件的数量和推荐规格。此外，还按站点定义了每台服务器，以按站点提供服务器要求的完整描述。

  - 端口要求 – 显示所有已启用端口以及与域名系统负载平衡 (DNS LB) 和硬件负载平衡器 (HLB) 的关联的报告。应使用此报告规划防火墙以及 DNS LB 和 HLB 配置。

  - 摘要报告-显示设置边缘服务器网络所需设置的一般摘要。

  - 证书报告-显示用于获取运行边缘服务器所需证书的主题名称和主题备用名称。

  - 防火墙报告 – 显示源端口和目标端口以及外部和内部接口的 IP 地址。

  - DNS 报告 – 显示您所创建的每个 DNS 条目所需的完全限定域名 (FQDN) 和 IP/VIP 地址。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

将设计导出到 Microsoft Visio 会创建在配置的拓扑和基础结构的文档中使用的图。您可以编辑和重新排列导入的图以满足文档需求。典型的 Visio 图包括：

<div>


> [!NOTE]  
> 如果你的设计足够大, 需要超过三个前端服务器, 将为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 Fqdn 创建一个额外页面。



</div>

  - 全局拓扑-已配置 Lync Server 2013 网站的图表。

  - "网站名称" 选项卡-显示 "边缘服务器"、"防火墙"、"公共交换电话网络" (PSTN) 和内部服务器部署的站点配置拓扑。 内部部署包括配置的服务器和池, 包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息 (UM) 服务器、Exchange 邮箱服务器、Office Web Apps 服务器中介服务器和持久聊天服务器。

  - 边缘网络图-详细介绍边缘服务器配置以及关联的 IP 地址和 Fqdn 的图表。 还包括 DNS 负载平衡和硬件负载平衡器。 此外, 将显示 Director 和前端服务器或前端池, 其中关联的 DNS LB 或 HLB 以及分配的 IP 地址 (计划工具支持 IPv4 和 IPv6 地址) 和 FQDN。

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

