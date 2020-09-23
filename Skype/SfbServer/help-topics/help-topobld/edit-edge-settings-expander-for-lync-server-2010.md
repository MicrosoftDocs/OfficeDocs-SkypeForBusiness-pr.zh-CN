---
title: 编辑 Lync Server 2010 的边缘设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 可以通过配置以下属性来编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216113"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ec6d8-103">编辑 Lync Server 2010 的边缘设置扩展器</span><span class="sxs-lookup"><span data-stu-id="ec6d8-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ec6d8-104">可以通过配置以下属性来编辑边缘服务器或边缘池的设置：</span><span class="sxs-lookup"><span data-stu-id="ec6d8-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="ec6d8-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="ec6d8-105">**General**</span></span>
  
- <span data-ttu-id="ec6d8-106">**内部池 FQDN**：内部池完全限定域名是在域名系统中定义的边缘服务器或边缘池的标识 (DNS) 主机 (A 或 AAAA for IPv6) 记录。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="ec6d8-107">选择 " \*\*为此边缘池启用联盟" (端口 5061) \*\* 如果要为其他会话初始协议合作伙伴启用与联盟的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ec6d8-108">您只能为联合定义一个边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="ec6d8-109">相关联的屏幕截图中显示的配置指示已为联盟配置了另一台边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="ec6d8-110">联合身份验证 (_sipfederationtls _tcp 的外部 DNS SRV 记录。 \<external domain name\>) 将指向边缘服务器或边缘池以进行联盟。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="ec6d8-111">默认情况下， \*\*内部配置复制端口 (HTTPS) \*\*，默认情况下，TCP 端口4443是本地 (（即，复制中央管理存储) 副本的本地服务器的端口）。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="ec6d8-112">中央管理存储的本地副本位于每台计算机上的 SQL Server 中的 **RTCLOCAL** 数据库中。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="ec6d8-113">复制是从中央管理服务器启动的单向的 (，或者是前端服务器或前端池，它将中央管理服务器角色) 到边缘服务器，并且是一个内部接口端口。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="ec6d8-114">**下一个跃点选择**</span><span class="sxs-lookup"><span data-stu-id="ec6d8-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="ec6d8-115">为“下一个跃点池”\*\*\*\* 列表进行选择。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="ec6d8-116">您可以定义控制器、控制器池、前端服务器或前端池以承担此角色。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="ec6d8-117">下一个跃点池是服务器或服务器池，它将接受来自边缘服务器或边缘池内部接口的入站 SIP 消息，并将出站 SIP 发送到边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec6d8-118">Director 是一个可选角色，如果您决定不部署控制器，则 (单个计算机或池) 的前端服务器将承担控制器角色。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="ec6d8-119">**外部设置**</span><span class="sxs-lookup"><span data-stu-id="ec6d8-119">**External settings**</span></span>
  
<span data-ttu-id="ec6d8-120">通过此属性部分，可以编辑边缘服务器或边缘池的外部设置的属性。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="ec6d8-121">可编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="ec6d8-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="ec6d8-122">如果要将不同的 IP 地址和完全限定的域名分配给每个边缘服务器服务，请选中 " **为 web 会议和 A/V 启用单独的 FQDN 和 IP 地址** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec6d8-123">如果选择不选中该复选框，则必须为每个边缘服务使用单独的端口。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="ec6d8-124">每个边缘服务将共享为访问边缘服务定义的 FQDN，因此将使用相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="ec6d8-125">每个边缘服务都必须通过一个不同的 IP 地址和相同的端口，或相同的 IP 地址和唯一的端口值进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="ec6d8-126">如果要将 A/V 边缘服务配置为使用专用地址或其他将隐藏在网络地址转换 (NAT) 设备后面的其他地址，则选择 **a/v 边缘服务将启用 NAT** 。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="ec6d8-127">若要编辑 **访问边缘服务**，请为访问边缘服务定义按主机 (A 的 **池 FQDN** ，以及如果) 记录和端口值使用了 IPV6，则为 AAAA。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="ec6d8-128">若要编辑 **Web 会议边缘服务**，请为 Web 会议边缘服务定义 **池 FQDN** ，如 DNS 中所定义的主机 (a）和 AAAA （如果使用 IPv6）) 记录和端口值</span><span class="sxs-lookup"><span data-stu-id="ec6d8-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="ec6d8-129">若要编辑 **a/v 边缘服务**，请为主机 (a 的 DNS 中定义的 a/v 边缘服务定义 **池 FQDN** ，如果) 记录和端口值使用了 IPV6，则为 AAAA。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ec6d8-130">如果已选中 "为 **web 会议和 A/V 启用单独的 FQDN 和 IP 地址** " 复选框，则只有访问边缘服务池 FQDN 可供编辑。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="ec6d8-131">为三个边缘服务各自分配不同的端口。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="ec6d8-132">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="ec6d8-133">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="ec6d8-134">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="ec6d8-134">**Help** Displays this help screen.</span></span>
  

