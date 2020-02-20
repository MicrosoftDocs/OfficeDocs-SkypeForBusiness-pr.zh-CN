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
ms.openlocfilehash: a5eaee8ba62984ad37dc49df2ce609018dd17b79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="1ffd3-102">在 Lync Server 2013 中安装可选软件</span><span class="sxs-lookup"><span data-stu-id="1ffd3-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ffd3-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ffd3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ffd3-104">Microsoft Lync Server 2013，规划工具旨在导出到 Microsoft Excel 和 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="1ffd3-105">尽管这些应用程序不是规划工具的操作所必需的，但它们确实增加了部署和文档设计的重要价值。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="1ffd3-106">可选软件</span><span class="sxs-lookup"><span data-stu-id="1ffd3-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="1ffd3-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="1ffd3-107">Microsoft Excel</span></span>

<span data-ttu-id="1ffd3-108">将设计导出到 Microsoft Excel 会创建一个报告，该报告将在电子表格中显示七个选项卡：</span><span class="sxs-lookup"><span data-stu-id="1ffd3-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="1ffd3-109">摘要–显示有关站点配置的信息，包括用户计数、容量设置和服务器配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="1ffd3-110">硬件配置文件–显示有关拓扑中指定的服务器的建议硬件配置的报告，包括 CPU、内存、磁盘和网络接口。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="1ffd3-111">此外，还包括服务器组件的数量和建议规格。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="1ffd3-112">此外，每个服务器都由网站定义，以提供按站点的服务器要求的完整表示形式。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="1ffd3-113">端口要求–显示已启用的所有端口以及与域名系统负载平衡（DNS LB）和硬件负载平衡器（HLB）的关联的报告。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="1ffd3-114">您应使用此报告来规划防火墙和 DNS LB 和 HLB 配置。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="1ffd3-115">摘要报告–显示设置边缘服务器网络所需设置的一般摘要。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="1ffd3-116">证书报告–显示用于运行边缘服务器所需的证书所需的使用者名称和使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="1ffd3-117">防火墙报告–显示源和目标端口以及外部和内部接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="1ffd3-118">DNS 报告–显示您创建的每个 DNS 条目所需的完全限定域名（FQDN）和 IP/VIP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="1ffd3-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="1ffd3-119">Microsoft Visio</span></span>

<span data-ttu-id="1ffd3-120">将设计导出到 Microsoft Visio 将创建一个图表，以供您配置的拓扑和基础结构的文档用途使用。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-120">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="1ffd3-121">可以对导入的图表进行编辑和重新排列以满足文档需求。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-121">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="1ffd3-122">典型的 Visio 图表将包括：</span><span class="sxs-lookup"><span data-stu-id="1ffd3-122">The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ffd3-123">如果您的设计大得足以要求三台以上的前端服务器，则会为前端池、前端服务器、运行 SQL Server 的计算机、IP 地址和 Fqdn 创建一个额外的页面。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="1ffd3-124">全局拓扑-配置的 Lync Server 2013 网站的关系图。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="1ffd3-125">"站点名称" 选项卡–显示具有边缘服务器、防火墙、公共交换电话网络（PSTN）和网关的站点配置拓扑，以及内部服务器部署。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="1ffd3-126">内部部署包括已配置的服务器和池，包括前端池、基于 SQL Server 的服务器、Active Directory 域服务、控制器、Exchange 统一消息（UM）服务器、Exchange 邮箱服务器、Office Web Apps Server中介服务器和持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="1ffd3-127">边缘网络图–详细说明边缘服务器配置与关联的 IP 地址和 Fqdn 的图表。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="1ffd3-128">此外，还包括了 DNS 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="1ffd3-129">此外，还将显示 Director 和前端服务器或前端池，其中包含关联的 DNS LB 或 HLB 以及分配的 IP 地址（规划工具同时支持 IPv4 和 IPv6 地址）和 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ffd3-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ffd3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ffd3-130">See Also</span></span>


[<span data-ttu-id="1ffd3-131">在 Lync Server 2013 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="1ffd3-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

