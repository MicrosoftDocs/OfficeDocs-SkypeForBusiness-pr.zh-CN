---
title: Lync Server 2013：编辑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="a7075-102">在 Lync Server 2013 中编辑设计</span><span class="sxs-lookup"><span data-stu-id="a7075-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7075-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a7075-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a7075-104">完成最初的访谈问题后，您可以编辑该网站的完全限定域名（FQDN）和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a7075-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="a7075-105">要执行此操作，请在 **“全局拓扑”** 页上双击要编辑的站点。</span><span class="sxs-lookup"><span data-stu-id="a7075-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="a7075-106">规划工具显示选定网站的站点拓扑。</span><span class="sxs-lookup"><span data-stu-id="a7075-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="a7075-107">在站点页面的底部有四个选项卡：</span><span class="sxs-lookup"><span data-stu-id="a7075-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="a7075-108">![规划工具网站拓扑](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "规划工具网站拓扑")</span><span class="sxs-lookup"><span data-stu-id="a7075-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="a7075-109">站点拓扑 – 当前显示的页面，其中包含推荐拓扑的视图概览。</span><span class="sxs-lookup"><span data-stu-id="a7075-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="a7075-110">边缘网络图–设计人员在规划工具中执行大部分工作的 "边缘网络图" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7075-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="a7075-111">该图显示了推荐的 Lync Server 2013 拓扑的网络配置，其中包含可编辑的 IP 地址和 Fqdn 的条目，以及服务器、池以及硬件和域名系统（DNS）负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="a7075-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="a7075-112">边缘管理报告 –“边缘管理报告”共包含四份报告：</span><span class="sxs-lookup"><span data-stu-id="a7075-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="a7075-113">![边缘管理报告页](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "边缘管理报告页")</span><span class="sxs-lookup"><span data-stu-id="a7075-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="a7075-114">摘要报告 - 边缘网络配置设置的常规报告。</span><span class="sxs-lookup"><span data-stu-id="a7075-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="a7075-115">如果将 "**边缘网络关系图**" 页上的值编辑为将在实际部署中使用的 "拓扑 tcp/ip" 和 "FQDN" 值，则这些地址和名称将在此处表示。</span><span class="sxs-lookup"><span data-stu-id="a7075-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="a7075-116">否则，将显示默认文本。</span><span class="sxs-lookup"><span data-stu-id="a7075-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="a7075-117">证书报告 -“证书报告”会列出拓扑所需证书的使用者名称和使用者备用名称。</span><span class="sxs-lookup"><span data-stu-id="a7075-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="a7075-118">防火墙报告 -“防火墙报告”列出在基础结构中配置外围防火墙的必要信息。</span><span class="sxs-lookup"><span data-stu-id="a7075-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="a7075-119">这包括 IP 地址（默认值或编辑的值）、服务器角色、源 IP 和端口、目标 IP 和端口、传输协议、应用程序协议和相关说明。</span><span class="sxs-lookup"><span data-stu-id="a7075-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="a7075-120">DNS 报告– DNS 报告列出您必须创建的 DNS 条目的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a7075-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="a7075-121">其中包括相应操作所需的记录类型、FQDN、IP 地址和备注。</span><span class="sxs-lookup"><span data-stu-id="a7075-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="a7075-122">网站摘要–网站摘要显示通过回答最初的调查问题或填写**设计网站**中的值所做的选择的概述。</span><span class="sxs-lookup"><span data-stu-id="a7075-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="a7075-123">还提供容量信息。</span><span class="sxs-lookup"><span data-stu-id="a7075-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7075-124">“站点摘要”页上的信息可针对每个设计进行自定义，可能不包含此处详细介绍的所有内容或信息。</span><span class="sxs-lookup"><span data-stu-id="a7075-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7075-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7075-125">See Also</span></span>


[<span data-ttu-id="a7075-126">在 Lync Server 2013 中编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="a7075-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

