---
title: Lync Server 2013：集成本地统一消息的指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15973bf2055339e375e4aecc7cfd1f61ac205dbb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="62192-102">集成本地统一消息与 Lync Server 2013 的指南</span><span class="sxs-lookup"><span data-stu-id="62192-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62192-103">_**主题上次修改时间:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="62192-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="62192-104">以下是部署企业语音时要考虑的准则和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="62192-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62192-105">Exchange 统一消息 (UM) 仅在你也使用 UCMA 4 时才支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="62192-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="62192-106">部署 Lync Server 2013 标准版服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="62192-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="62192-107">有关安装的详细信息, 请参阅部署文档中的 "[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) "。</span><span class="sxs-lookup"><span data-stu-id="62192-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="62192-108">与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。</span><span class="sxs-lookup"><span data-stu-id="62192-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="62192-109">在要为 Exchange UM 启用用户的每个 Exchange 统一消息 (UM) 林中部署 Exchange 邮箱服务器角色。</span><span class="sxs-lookup"><span data-stu-id="62192-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="62192-110">有关安装 Exchange server 角色的详细信息, 请参阅 Microsoft Exchange Server 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="62192-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62192-111">当安装 Exchange 统一消息 (UM) 时, 它将配置为使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="62192-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="62192-112">但是, 自签名证书不会使 Lync Server 2013 和 Exchange UM 相互信任, 这就是为什么需要从两个服务器信任的证书颁发机构请求单独的证书的原因。</span><span class="sxs-lookup"><span data-stu-id="62192-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="62192-113">如果 Lync Server 2013 和 Exchange UM 安装在不同的林中, 请将每个 Exchange 林配置为信任 Lync Server 2013 林和 Lync Server 2013 林信任每个 Exchange 林。</span><span class="sxs-lookup"><span data-stu-id="62192-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="62192-114">此外, 在 Lync Server 2013 林中的用户对象上设置用户的 Exchange UM 设置, 通常通过使用脚本或跨林工具 (如 "身份生命周期管理器 (ILM)")。</span><span class="sxs-lookup"><span data-stu-id="62192-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="62192-115">必要时，安装 Exchange 管理控制台以管理统一消息服务器。</span><span class="sxs-lookup"><span data-stu-id="62192-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="62192-116">获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。</span><span class="sxs-lookup"><span data-stu-id="62192-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="62192-117">如果你使用早于 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 的 Exchange UM 的版本, 请调整 Exchange UM SIP URI 拨号计划和企业语音拨号计划的名称。</span><span class="sxs-lookup"><span data-stu-id="62192-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="62192-118">部署冗余 Exchange UM 服务器</span><span class="sxs-lookup"><span data-stu-id="62192-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62192-119">我们建议你为你的组织配置的每个 Exchange UM SIP URI 拨号计划至少部署两台 Exchange UM 服务运行的服务器。</span><span class="sxs-lookup"><span data-stu-id="62192-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="62192-120">除了提供扩展容量之外，部署冗余服务还可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="62192-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="62192-121">在服务器出现故障时, 可以将 Lync Server 2013 配置为故障转移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="62192-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="62192-122">以下示例配置提供 Exchange UM 恢复能力。</span><span class="sxs-lookup"><span data-stu-id="62192-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="62192-123">**示例 1：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="62192-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="62192-124">![EXCHANGE UM 示例 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "EXCHANGE UM 示例 1")</span><span class="sxs-lookup"><span data-stu-id="62192-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="62192-p105">在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="62192-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62192-128">对于示例 1，还应在每台 Exchange UM 服务器上分配以下证书之一：</span><span class="sxs-lookup"><span data-stu-id="62192-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="62192-129">在使用者替代名称 (SAN) 中使用具有通配符的证书。</span><span class="sxs-lookup"><span data-stu-id="62192-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="62192-130">在 SAN 中使用四台 Exchange UM 服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="62192-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="62192-131">**示例 2：Exchange UM 恢复能力**</span><span class="sxs-lookup"><span data-stu-id="62192-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="62192-132">![EXCHANGE UM 示例 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "EXCHANGE UM 示例 2")</span><span class="sxs-lookup"><span data-stu-id="62192-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="62192-p106">在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。</span><span class="sxs-lookup"><span data-stu-id="62192-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="62192-136">有关如何在 Exchange 2013 上启用或禁用统一消息的详细信息, 请参阅 "将 Exchange 2013 UM 与 Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)相集成"。</span><span class="sxs-lookup"><span data-stu-id="62192-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="62192-137">有关如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="62192-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="62192-138">"在[http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)Exchange 2010 上启用统一消息"。</span><span class="sxs-lookup"><span data-stu-id="62192-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="62192-139">"禁用 Exchange 2010 上的统一消息" [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)。</span><span class="sxs-lookup"><span data-stu-id="62192-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62192-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62192-140">See Also</span></span>


[<span data-ttu-id="62192-141">集成本地统一消息与 Lync Server 2013 的部署过程</span><span class="sxs-lookup"><span data-stu-id="62192-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

