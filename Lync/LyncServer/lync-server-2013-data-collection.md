---
title: Lync Server 2013：数据收集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516569"
---
# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="9e06a-102">Lync Server 2013 中的数据收集</span><span class="sxs-lookup"><span data-stu-id="9e06a-102">Data collection in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e06a-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9e06a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9e06a-104">在 Microsoft Lync Server 2013 通信软件中，可以运行 Microsoft Lync Server 2013、规划工具，而无需将现有和建议的 IP 地址和边缘服务器完全限定的域名 (Fqdn) ，但这样做很难，而不会导致配置错误。</span><span class="sxs-lookup"><span data-stu-id="9e06a-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="9e06a-105">例如，如果一段时间内需要共存，则一个常见错误是为 Lync Server 2013 Edge 部署重用现有边缘部署中的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="9e06a-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="9e06a-106">通过将现有和建议的 IP 地址和 FQDN 记录到电子表格、表或其他虚拟表单中，可有助于防止在安装期间出现设置问题。</span><span class="sxs-lookup"><span data-stu-id="9e06a-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9e06a-107">如果您使用的是规划工具的早期版本，则可能已使用该工具创建了拓扑，并导出了要在拓扑生成器中使用的拓扑文档以发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="9e06a-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="9e06a-108">从规划工具中删除了导出拓扑的功能。</span><span class="sxs-lookup"><span data-stu-id="9e06a-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="9e06a-109">强烈建议使用早期版本的规划工具为 Lync Server 2013 创建拓扑文档，并将产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="9e06a-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="9e06a-110">因此，建议的方法是使用以下与您的边缘拓扑相对应的数据收集模板，以收集您需要在规划工具中输入的各种 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9e06a-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="9e06a-111">通过记录当前和建议的配置，可在生产环境的适当上下文中输入值。</span><span class="sxs-lookup"><span data-stu-id="9e06a-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="9e06a-112">并且，您还必须思考应如何配置共存和功能，例如简单 URL、文件共享和负载平衡。</span><span class="sxs-lookup"><span data-stu-id="9e06a-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="9e06a-113">若要成功部署 Microsoft Lync Server 2013，您需要了解各个组件的交互和依赖项。</span><span class="sxs-lookup"><span data-stu-id="9e06a-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="9e06a-114">通过收集现有网络和服务器基础结构中的数据，并在这些部分中应用规划指南，可以将 Lync Server 2013 边缘服务器组件集成到您的基础结构中。</span><span class="sxs-lookup"><span data-stu-id="9e06a-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="9e06a-115">在 [Lync Server 2013 中选择拓扑](lync-server-2013-choosing-a-topology.md)时引入，有三个主要体系结构，有两种变体，共五种可能的部署方案。</span><span class="sxs-lookup"><span data-stu-id="9e06a-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="9e06a-116">这些方案中的某个方案将是数据收集的起点。</span><span class="sxs-lookup"><span data-stu-id="9e06a-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="9e06a-117">IP 地址、服务器名称和域名是与匹配的证书、防火墙和 DNS 关系图（详述完整的规划解决方案所需信息）一致的示例。</span><span class="sxs-lookup"><span data-stu-id="9e06a-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="9e06a-118">关系图的填充所需证书、DNS 和防火墙值，在跨团队交流中十分重要，证书颁发机构、防火墙配置和 DNS 的管理在跨团队交流中由规划部署的团队之外的团队进行管理。</span><span class="sxs-lookup"><span data-stu-id="9e06a-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="9e06a-119">此关系图提供有关可用于沟通跨团队协作的要求的所需组件的信息。</span><span class="sxs-lookup"><span data-stu-id="9e06a-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="9e06a-120">提供的图表专供通用，但允许用于所有相关数据的集合，这些数据是整个团队方案中通信要求所需的，其中网络、防火墙、证书创建和管理、服务器部署及服务器管理由不同的组进行处理。</span><span class="sxs-lookup"><span data-stu-id="9e06a-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="9e06a-121">在部署 Lync Server 时，有必要的网络、防火墙、端口和协议、证书和服务器配置的详细信息非常有用。</span><span class="sxs-lookup"><span data-stu-id="9e06a-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="9e06a-122">**边缘服务器和边缘池**</span><span class="sxs-lookup"><span data-stu-id="9e06a-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="9e06a-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="9e06a-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="9e06a-124">**反向代理**</span><span class="sxs-lookup"><span data-stu-id="9e06a-124">**Reverse Proxy**</span></span>

<span data-ttu-id="9e06a-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="9e06a-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="9e06a-126">**控制器或控制器池**</span><span class="sxs-lookup"><span data-stu-id="9e06a-126">**Director or Director pool**</span></span>

<span data-ttu-id="9e06a-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="9e06a-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

