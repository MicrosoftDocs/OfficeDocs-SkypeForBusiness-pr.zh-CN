---
title: 编辑 Lync Server 2010 的边缘设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803292"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="a9cd2-103">编辑适合于 Lync Server 2010 的边缘设置扩展器</span><span class="sxs-lookup"><span data-stu-id="a9cd2-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="a9cd2-104">通过配置以下属性编辑边缘服务器或边缘池的设置：</span><span class="sxs-lookup"><span data-stu-id="a9cd2-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="a9cd2-105">**常规**</span><span class="sxs-lookup"><span data-stu-id="a9cd2-105">**General**</span></span>
  
- <span data-ttu-id="a9cd2-106">内部池 **FQDN：** 内部池完全限定域名是在域名系统 (DNS) 主机 (A 或 AAAA for IPv6) 记录中定义的边缘服务器或边缘池的标识。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="a9cd2-107">如果要为边缘服务器或边缘池启用与其他会话初始协议伙伴的联盟 (端口 **5061**) ，请选择"为此边缘池启用联盟"。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cd2-108">只能为联盟主动定义一个边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="a9cd2-109">相关屏幕截图中显示的配置指示已针对联盟配置了另一台边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="a9cd2-110">联合身份验证的外部 DNS SRV 记录 (_sipfederationtls._tcp。 \<external domain name\>) 指向联盟的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="a9cd2-111">默认情况下，TCP 端口 4443 的内部配置复制端口 **(HTTPS)** 是本地 (（即中央管理存储的边缘服务器) 副本的本地）复制的端口。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="a9cd2-112">中央管理存储的本地副本位于每台计算机的 SQL Server **RTCLOCAL** 数据库中。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="a9cd2-113">复制是单向的，从中央管理服务器 (或保留中央管理服务器角色) 的前端服务器或前端池启动，是内部接口端口。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="a9cd2-114">**下一个跃点选择**</span><span class="sxs-lookup"><span data-stu-id="a9cd2-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="a9cd2-115">为“下一个跃点池”列表进行选择。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="a9cd2-116">定义控制器、控制器池、前端服务器或前端池以承担此角色。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="a9cd2-117">下一个跃点池是接受来自边缘服务器或边缘池内部接口的入站 SIP 消息并将出站 SIP 发送到边缘内部接口的服务器或服务器池。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9cd2-118">控制器是可选角色，如果您决定不部署控制器，则单个计算机或池 (前端服务器将) 控制器角色。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="a9cd2-119">**外部设置**</span><span class="sxs-lookup"><span data-stu-id="a9cd2-119">**External settings**</span></span>
  
<span data-ttu-id="a9cd2-120">通过这些属性的这一部分，您可以编辑边缘服务器或边缘池的外部设置的属性。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="a9cd2-121">可编辑以下属性：</span><span class="sxs-lookup"><span data-stu-id="a9cd2-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="a9cd2-122">如果要为每个边缘服务器服务分配不同的 IP 地址和完全限定的域名，请选中"为 Web 会议和 A/V 启用单独的 **FQDN** 和 IP 地址"复选框。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9cd2-123">如果选择不选中该复选框，则必须为每个边缘服务使用单独的端口。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="a9cd2-124">每个边缘服务将共享为访问边缘服务定义的 FQDN，因此将使用相同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="a9cd2-125">每个边缘服务都必须通过一个不同的 IP 地址和相同的端口，或相同的 IP 地址和唯一的端口值进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="a9cd2-126">如果要将 A/V 边缘服务配置为使用将隐藏在网络地址转换 (NAT) 设备的专用地址或其他地址，请选择 **"A/V** 边缘服务已启用 NAT"。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="a9cd2-127">若要编辑访问边缘服务，请为访问边缘服务定义池 **FQDN，** 如主机 (A 在 DNS 中定义，如果 IPv6 用于) 记录和端口值，则定义 AAAA</span><span class="sxs-lookup"><span data-stu-id="a9cd2-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="a9cd2-128">若要编辑 **Web** 会议边缘服务，请为 Web 会议边缘服务定义池 **FQDN，** 如主机 (A 在 DNS 中定义，如果 IPv6 用于) 记录和端口值，则定义 AAAA</span><span class="sxs-lookup"><span data-stu-id="a9cd2-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="a9cd2-129">若要编辑 **A/V** 边缘服务，请为 A/V 边缘服务定义池 **FQDN，** 如主机 (A 在 DNS 中定义，如果 IPv6 用于) 记录和端口值，则定义 AAAA</span><span class="sxs-lookup"><span data-stu-id="a9cd2-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a9cd2-130">如果选中了"为 Web 会议和 A/V 启用单独的 **FQDN** 和 IP 地址"复选框，则只有访问边缘服务池 FQDN 可供编辑。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="a9cd2-131">为三个边缘服务各自分配不同的端口。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="a9cd2-132">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="a9cd2-133">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="a9cd2-134">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="a9cd2-134">**Help** Displays this help screen.</span></span>
  

