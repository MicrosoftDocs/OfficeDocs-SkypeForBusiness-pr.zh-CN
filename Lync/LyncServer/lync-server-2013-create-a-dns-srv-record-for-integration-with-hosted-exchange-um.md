---
title: 创建 DNS SRV 记录以与托管 Exchange UM 集成
description: 创建用于与托管 Exchange UM 集成的 DNS SRV 记录。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542138"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="595fb-103">创建 DNS SRV 记录以与托管 Exchange UM 集成</span><span class="sxs-lookup"><span data-stu-id="595fb-103">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="595fb-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="595fb-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="595fb-105">本主题介绍如何将 Lync Server 2013 边缘服务器所需的域名系统 (DNS) SRV 记录配置为路由到托管 Exchange 服务（如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="595fb-105">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="595fb-106">为承载的 Exchange 服务创建外部 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="595fb-106">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="595fb-107">以 DnsAdmins 组成员的身份登录外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="595fb-107">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="595fb-108">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\* 和“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-108">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="595fb-109">在您的 SIP 域的控制台树中，展开 " **正向查找区域**"，然后选择将在其中安装 Lync Server 2013 的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="595fb-109">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="595fb-p101">您必须在 Lync Server 所在的或将安装 Lync Server 的 SIP 域中创建 DNS SRV 记录。在创建 SRV 记录时，用于“提供此服务的主机”字段的 FQDN 必须是边缘池的外部 FQDN。例如，如果边缘池的外部 FQDN 为 edge01.contoso.net，请输入该值。此外，此记录必须位于 DNS 主机 (A) 记录所在的域中。</span><span class="sxs-lookup"><span data-stu-id="595fb-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="595fb-114">右键单击选定的域，再单击“其他新记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-114">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="595fb-115">在“资源记录类型”\*\*\*\* 中，单击“服务位置(SRV)”\*\*\*\*，再单击“创建记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-115">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="595fb-116">在 "**新建资源记录**" 中，单击 "**服务**"，然后键入\*\* \_ sipfederationtls\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-116">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="595fb-117">单击 "**协议**"，然后键入\*\* \_ tcp\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-117">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="595fb-118">单击“端口号”\*\*\*\*，再键入“5061”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-118">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="595fb-119">单击 " **主机提供此服务**"，然后键入 lync Server 2013 Edge 池 (FQDN) 的完全限定域名，该名称为受信任的外部客户端提供对 lync server 2013 系统的访问权限。</span><span class="sxs-lookup"><span data-stu-id="595fb-119">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="595fb-120">此外，还必须将域设置为 Exchange Online 设置中的权威性的接受域。</span><span class="sxs-lookup"><span data-stu-id="595fb-120">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="595fb-121">有关详细信息，请参阅在上创建接受的域 <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。</span><span class="sxs-lookup"><span data-stu-id="595fb-121">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="595fb-122">单击“确定”\*\*\*\*，再单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-122">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="595fb-123">验证是否已成功创建 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="595fb-123">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="595fb-124">登录到域中的一台客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="595fb-124">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="595fb-125">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="595fb-125">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="595fb-126">在命令提示符下，运行下列命令：</span><span class="sxs-lookup"><span data-stu-id="595fb-126">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="595fb-127">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="595fb-127">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="595fb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="595fb-128">See Also</span></span>


[<span data-ttu-id="595fb-129">在 Lync Server 2013 中为反向代理服务器创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="595fb-129">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

