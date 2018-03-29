---
title: 编辑 Lync Server 2010 中的边缘设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 您可以通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d90d9-103">编辑 Lync Server 2010 中的边缘设置扩展器</span><span class="sxs-lookup"><span data-stu-id="d90d9-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d90d9-104">您可以通过配置以下属性编辑边缘服务器或边缘池的设置：</span><span class="sxs-lookup"><span data-stu-id="d90d9-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="d90d9-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="d90d9-105">**General**</span></span>
  
- <span data-ttu-id="d90d9-106">**内部池的 FQDN**： 内部池完全限定的域名是域名系统 (DNS) 主机 （A 或 AAAA ipv6） 记录中定义的边缘服务器或边缘池的标识。</span><span class="sxs-lookup"><span data-stu-id="d90d9-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="d90d9-107">如果您想要启用的边缘服务器或其他会话启动协议合作伙伴与联盟的边缘池，请选择**启用此边缘池 （端口 5061） 联盟**。</span><span class="sxs-lookup"><span data-stu-id="d90d9-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d90d9-108">您只能定义一个边缘服务器或边缘池积极为联盟。</span><span class="sxs-lookup"><span data-stu-id="d90d9-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="d90d9-109">相关的屏幕快照中所示的配置表示为联合已经配置了另一个边缘服务器或边池。</span><span class="sxs-lookup"><span data-stu-id="d90d9-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="d90d9-110">联盟的外部 DNS SRV 记录 (_sipfederationtls._tcp。\<外部域名\>) 将指向的边缘服务器或联盟的边缘池。</span><span class="sxs-lookup"><span data-stu-id="d90d9-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="d90d9-111">**内部配置复制端口 (HTTPS)**，默认情况下 TCP 端口 4443，是端口的本地 (即，边缘服务器的本地) 的中央管理存储副本复制到。</span><span class="sxs-lookup"><span data-stu-id="d90d9-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="d90d9-112">中央管理存储的本地副本是在**RTCLOCAL**中每台计算机上的 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d90d9-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="d90d9-113">复制到边缘服务器启动从中央管理服务器 （或前端服务器或前端池中包含的中央管理服务器角色） 是单向的而且是内部接口端口。</span><span class="sxs-lookup"><span data-stu-id="d90d9-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
 <span data-ttu-id="d90d9-114">**下一跃点的选择**</span><span class="sxs-lookup"><span data-stu-id="d90d9-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="d90d9-115">列表中选择您的**下一个跃点池**。</span><span class="sxs-lookup"><span data-stu-id="d90d9-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="d90d9-116">导演池、 前端服务器或前端池可承担此角色，您可以定义导演。</span><span class="sxs-lookup"><span data-stu-id="d90d9-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="d90d9-117">下一个跃点池的服务器或服务器池将接受来自边缘服务器的入站的 SIP 消息或边缘池内部接口和发送出站 SIP 与边缘的内部接口。</span><span class="sxs-lookup"><span data-stu-id="d90d9-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d90d9-118">控制器是一个可选角色和前端服务器 （单机或池） 如果您决定不将部署控制器，将假定控制器角色。</span><span class="sxs-lookup"><span data-stu-id="d90d9-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
 <span data-ttu-id="d90d9-119">**外部设置**</span><span class="sxs-lookup"><span data-stu-id="d90d9-119">**External settings**</span></span>
  
<span data-ttu-id="d90d9-120">此节的属性允许您编辑的边缘服务器或池边缘的外部设置的属性。</span><span class="sxs-lookup"><span data-stu-id="d90d9-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="d90d9-121">可编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="d90d9-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="d90d9-122">选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**为每个边缘服务器服务名称的复选框，如果您想要分配不同的 IP 地址和完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="d90d9-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d90d9-123">如果选择未选中复选框，则必须为每个边缘服务使用不同的端口。</span><span class="sxs-lookup"><span data-stu-id="d90d9-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="d90d9-124">每个边缘服务将共享访问边缘服务中，为定义的 FQDN，并因此将使用相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d90d9-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="d90d9-125">必须由一个不同的 IP 地址和同一个端口，或相同的 IP 地址和唯一的端口值唯一标识每个边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d90d9-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="d90d9-126">选择**A / V 边缘服务是启用 NAT**如果您想要配置 A / V 边缘服务要使用专用地址或其他地址将被隐藏在网络地址转换 (NAT) 设备后面。</span><span class="sxs-lookup"><span data-stu-id="d90d9-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="d90d9-127">若要编辑**访问边缘服务**，您定义访问边缘服务**池的 FQDN**在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值</span><span class="sxs-lookup"><span data-stu-id="d90d9-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d90d9-128">若要编辑**Web 会议边缘服务**，定义 Web 会议边缘服务**池的 FQDN**在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值</span><span class="sxs-lookup"><span data-stu-id="d90d9-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d90d9-129">编辑**A / V 边缘服务**，您定义一个**池的 FQDN**的 A / V 边缘服务在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值</span><span class="sxs-lookup"><span data-stu-id="d90d9-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d90d9-130">如果选择了**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，将提供用于编辑只访问边缘服务池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d90d9-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="d90d9-131">每个三个的边缘服务分配不同的端口。</span><span class="sxs-lookup"><span data-stu-id="d90d9-131">Assign distinct ports for each of the three Edge services.</span></span>
  
 <span data-ttu-id="d90d9-132">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="d90d9-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="d90d9-133">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d90d9-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="d90d9-134">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="d90d9-134">**Help** Displays this help screen.</span></span>
  

