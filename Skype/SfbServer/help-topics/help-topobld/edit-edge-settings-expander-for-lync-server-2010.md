---
title: 编辑适合于 Lync Server 2010 的 Edge 设置扩展器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203128"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="3a117-103">编辑适合于 Lync Server 2010 的 Edge 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="3a117-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="3a117-104">通过配置以下属性编辑边缘服务器或边缘池的设置：</span><span class="sxs-lookup"><span data-stu-id="3a117-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="3a117-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="3a117-105">**General**</span></span>
  
- <span data-ttu-id="3a117-106">**内部池 FQDN**： 内部池完全限定的域名称是域名系统 (DNS) 主机 （A 或对于 IPv6 为 AAAA） 记录中定义的边缘服务器或边缘池的标识。</span><span class="sxs-lookup"><span data-stu-id="3a117-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="3a117-107">如果您想要启用边缘服务器或边缘池用于与其他会话初始协议合作伙伴的联盟，请选择**启用联盟，为此边缘池 （端口 5061）** 。</span><span class="sxs-lookup"><span data-stu-id="3a117-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3a117-108">仅可以定义一个边缘服务器或边缘池主动用于联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="3a117-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="3a117-109">关联的屏幕截图中所示的配置指示已为联盟配置了另一台边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="3a117-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="3a117-110">联合身份验证的外部 DNS SRV 记录 (_sipfederationtls._tcp。\<外部域名\>) 将指向边缘服务器或边缘池用于联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="3a117-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="3a117-111">**内部配置复制端口 (HTTPS)**，默认情况下，在 TCP 端口 4443，是端口的本地 (即，本地到边缘服务器) 的中央管理存储副本都通过复制。</span><span class="sxs-lookup"><span data-stu-id="3a117-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="3a117-112">在**RTCLOCAL**数据库中每台计算机上的 SQL Server 中央管理存储的本地副本。</span><span class="sxs-lookup"><span data-stu-id="3a117-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="3a117-113">复制是单向，启动从中央管理服务器 （或包含中央管理服务器角色的前端服务器或前端池） 到边缘服务器，内部接口端口。</span><span class="sxs-lookup"><span data-stu-id="3a117-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="3a117-114">**下一个跃点选择**</span><span class="sxs-lookup"><span data-stu-id="3a117-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="3a117-115">列表中选择**下一个跃点池**。</span><span class="sxs-lookup"><span data-stu-id="3a117-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="3a117-116">控制器池，假定此角色的前端服务器或前端池，您可以定义控制器。</span><span class="sxs-lookup"><span data-stu-id="3a117-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="3a117-117">下一个跃点池是服务器或将接受从边缘服务器的入站的 SIP 消息的服务器池或边缘池内部接口和发送出站 SIP 到边缘内部接口。</span><span class="sxs-lookup"><span data-stu-id="3a117-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a117-118">Director 是一个可选角色，如果您决定不部署控制器，前端服务器 （单个计算机或池） 将假定控制器角色。</span><span class="sxs-lookup"><span data-stu-id="3a117-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="3a117-119">**外部设置**</span><span class="sxs-lookup"><span data-stu-id="3a117-119">**External settings**</span></span>
  
<span data-ttu-id="3a117-120">本节中的属性，可以编辑的边缘服务器或边缘池的外部设置的属性。</span><span class="sxs-lookup"><span data-stu-id="3a117-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="3a117-121">可编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="3a117-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="3a117-122">选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，如果您想要分配不同的 IP 地址和完全限定名称到每个边缘服务器服务。</span><span class="sxs-lookup"><span data-stu-id="3a117-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a117-123">如果您选择不选中的复选框，则必须为每个边缘服务使用单独的端口。</span><span class="sxs-lookup"><span data-stu-id="3a117-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="3a117-124">每个边缘服务将共享为访问边缘服务，定义的 FQDN，因此将使用相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3a117-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="3a117-125">每个边缘服务必须唯一地标识通过不同的 IP 地址和同一个端口，或同一个 IP 地址和唯一的端口值。</span><span class="sxs-lookup"><span data-stu-id="3a117-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="3a117-126">选择**A / V 边缘服务启用 NAT**如果您想要配置 A / V 边缘服务使用专用的地址或其他将隐藏网络地址转换 (NAT) 设备的地址。</span><span class="sxs-lookup"><span data-stu-id="3a117-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="3a117-127">若要编辑**访问边缘服务**，您定义**池 FQDN**为访问边缘服务在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值</span><span class="sxs-lookup"><span data-stu-id="3a117-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="3a117-128">若要编辑**Web 会议边缘服务**，您定义一个用于 Web 会议边缘服务的**池 FQDN**在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值</span><span class="sxs-lookup"><span data-stu-id="3a117-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="3a117-129">编辑**A / V 边缘服务**，您定义**池 FQDN**的 a / V 边缘服务在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值</span><span class="sxs-lookup"><span data-stu-id="3a117-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3a117-130">如果选择了**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，只是访问边缘服务池 FQDN 以供编辑。</span><span class="sxs-lookup"><span data-stu-id="3a117-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="3a117-131">三种边缘服务的每个分配不同的端口。</span><span class="sxs-lookup"><span data-stu-id="3a117-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="3a117-132">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="3a117-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="3a117-133">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="3a117-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="3a117-134">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="3a117-134">**Help** Displays this help screen.</span></span>
  

