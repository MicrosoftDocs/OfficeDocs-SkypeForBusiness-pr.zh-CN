---
title: 配置边缘服务器以与托管 Exchange UM 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="d6d6a-102">配置边缘服务器以与托管 Exchange UM 集成</span><span class="sxs-lookup"><span data-stu-id="d6d6a-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d6a-103">_**主题上次修改时间：** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="d6d6a-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="d6d6a-104">若要向 Lync Server 2013 用户提供托管 Exchange 统一消息（UM）上的语音邮件功能，必须在 Edge 服务器上执行以下配置任务：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="d6d6a-105">配置边缘服务器以进行联盟。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="d6d6a-106">将中央管理存储数据复制到边缘服务器并验证复制。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="d6d6a-107">在边缘服务器上创建承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="d6d6a-108">有关详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="d6d6a-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d6a-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="d6d6a-110">[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d6a-110">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d6d6a-111">在执行这些步骤之前，您必须先为托管 Exchange 服务创建一条外部 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="d6d6a-112">有关详细信息，请参阅<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">创建用于与托管 EXCHANGE UM 集成的 DNS SRV 记录</A>。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="d6d6a-113">为联盟配置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d6d6a-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="d6d6a-114">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d6d6a-p102">运行 Set-CsAccessEdgeConfiguration cmdlet 为联盟配置服务器。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="d6d6a-117">上述示例设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="d6d6a-118">\*\*UseDnsSrvRouting \*\* 指定发送和接收联盟请求时，边缘服务器将依赖 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="d6d6a-p103">\*\*AllowFederatedUsers \*\* 指定是否允许内部用户与来自联盟域的用户进行通信。此属性也可以确定内部用户是否可以与拆分域方案中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="d6d6a-121">**EnablePartnerDiscovery**指定 Lync Server 是否将使用 DNS 记录来尝试发现未在 Active Directory 允许的域列表中列出的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="d6d6a-122">如果为 False，则 Lync Server 2013 将仅与在 "允许的域" 列表中找到的域联盟。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="d6d6a-123">如果使用 DNS 服务路由，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="d6d6a-124">在大多数部署中，值会设置为 False，以避免向所有合作伙伴打开联盟。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="d6d6a-125">将数据复制到边缘服务器并验证复制</span><span class="sxs-lookup"><span data-stu-id="d6d6a-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="d6d6a-126">验证到边缘服务器的复制是否已完成。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="d6d6a-127">有关过程，请参阅[在 Lync Server 2013 中验证内部服务器和边缘服务器之间的连接](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="d6d6a-128">在边缘服务器上创建承载服务提供商</span><span class="sxs-lookup"><span data-stu-id="d6d6a-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="d6d6a-129">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d6d6a-130">运行 **New-CsHostingProvider** cmdlet 配置承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="d6d6a-131">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="d6d6a-132">上述示例设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="d6d6a-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="d6d6a-p107">\*\*Identity \*\* 为正在创建的承载服务提供商指定唯一的字符串值标识符，在此示例中为 \*\*Fabrikam.com \*\*。请注意，如果某个现有提供商已使用该 Identity 进行配置，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="d6d6a-p108">\*\*Enabled \*\* 指示您的域与承载服务提供商之间的网络连接是否已启用。除非此值设置为 \*\*True \*\*，否则无法在这两个组织之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="d6d6a-137">\*\*EnabledSharedAddressSpace \*\* 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="d6d6a-138">在设置<CODE>EnableSharedAddressSpace</CODE>为 True 之前，请尝试在内部解析联合 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="d6d6a-139">如果无法在内部解析此记录，则需要创建记录，_sipfederationtls "_tcp"。&lt;域&gt;和 _sip _tls。&lt;内部&gt; DNS 中的域。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="d6d6a-140">这些记录应指向边缘服务器的访问接口的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="d6d6a-141">**HostsOCSUsers**指示托管提供商是否用于托管 Lync Server 2013 帐户。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="d6d6a-142">如果设置为 \*\*False \*\*，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="d6d6a-p111">\*\*ProxyFQDN \*\* 为承载服务提供商使用的代理服务器指定完全限定域名 (FQDN)，在此示例中为 \*\*proxyserver.fabrikam.com \*\*。不能修改此值。如果承载服务提供商更改了其代理服务器，则您必须删除该条目，然后为提供商重新创建相应条目。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="d6d6a-146">**IsLocal**指示你的 Lync server 2013 拓扑中是否包含托管提供程序使用的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="d6d6a-147">\*\*VerficationLevel \*\* 指示在宿主提供程序中发送和接收的邮件所允许的验证级别。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="d6d6a-148">指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="d6d6a-149">如果未指定此级别，则邮件将因未验证而被拒绝。</span><span class="sxs-lookup"><span data-stu-id="d6d6a-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6d6a-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d6a-150">See Also</span></span>


[<span data-ttu-id="d6d6a-151">导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装</span><span class="sxs-lookup"><span data-stu-id="d6d6a-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="d6d6a-152">在 Lync Server 2013 中验证内部服务器与边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="d6d6a-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="d6d6a-153">[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d6d6a-153">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

