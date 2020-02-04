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
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="a91f8-102">Lync Server 2013 中的数据收集</span><span class="sxs-lookup"><span data-stu-id="a91f8-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a91f8-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a91f8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a91f8-104">在 Microsoft Lync Server 2013 通信软件中，你可以运行 Microsoft Lync Server 2013、计划工具，而无需记录现有和建议的 IP 地址和边缘服务器完全限定的域名（Fqdn），但执行此操作很难因此不会导致配置错误。</span><span class="sxs-lookup"><span data-stu-id="a91f8-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="a91f8-105">例如，如果一段时间内需要共存，则常见错误是为 Lync Server 2013 Edge 部署重用现有边缘部署中的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="a91f8-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="a91f8-106">通过在电子表格、表或其他视觉形式中向下写下已有和建议的 IP 地址和 Fqdn，可帮助防止安装期间出现设置问题。</span><span class="sxs-lookup"><span data-stu-id="a91f8-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a91f8-107">如果您使用过计划工具的早期版本，则可能已使用该工具创建拓扑和导出拓扑文档以在拓扑生成器中使用，以发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a91f8-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="a91f8-108">从规划工具中删除了导出拓扑的功能。</span><span class="sxs-lookup"><span data-stu-id="a91f8-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="a91f8-109">强烈建议使用早期版本的计划工具创建 Lync Server 2013 的拓扑文档，并将产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="a91f8-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="a91f8-110">因此，建议的方法是使用以下数据收集模板，该模板对应于你的边缘拓扑，以收集你需要在规划工具中输入的各种 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a91f8-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="a91f8-111">通过记录当前和建议的配置，你可以将值放入生产环境的正确上下文中。</span><span class="sxs-lookup"><span data-stu-id="a91f8-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="a91f8-112">并且，您将被迫考虑如何配置共存和功能，例如简单的 Url、文件共享和负载平衡。</span><span class="sxs-lookup"><span data-stu-id="a91f8-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="a91f8-113">若要成功部署 Microsoft Lync Server 2013，你需要了解各个组件的交互和依赖情况。</span><span class="sxs-lookup"><span data-stu-id="a91f8-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="a91f8-114">通过收集现有网络和服务器基础结构中的数据，并在这些部分中应用规划指南，你可以将 Lync Server 2013 Edge 服务器组件集成到你的基础结构中。</span><span class="sxs-lookup"><span data-stu-id="a91f8-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="a91f8-115">在[Lync Server 2013 中选择拓扑](lync-server-2013-choosing-a-topology.md)中引入，有三个主要体系结构具有两个变体，共五种可能的部署方案。</span><span class="sxs-lookup"><span data-stu-id="a91f8-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="a91f8-116">其中一种方案是数据收集的起始点。</span><span class="sxs-lookup"><span data-stu-id="a91f8-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="a91f8-117">IP 地址、服务器名称和域名是与匹配的证书、防火墙和 DNS 图表相符的示例，其中详细介绍了完整规划解决方案所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a91f8-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="a91f8-118">图表和填写所需证书、DNS 和防火墙值在跨团队通信中尤其重要，在这种情况下，对证书颁发机构、防火墙配置和 DNS 的管理由团队之外的团队管理，计划部署。</span><span class="sxs-lookup"><span data-stu-id="a91f8-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="a91f8-119">图表提供有关可用于为跨团队协作传递这些要求的必需组件的信息。</span><span class="sxs-lookup"><span data-stu-id="a91f8-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="a91f8-120">所提供的图表是特意通用的，但允许收集所有相关数据，以便在跨团队方案中通信要求，以便在网络、防火墙、证书创建和管理、服务器部署和服务器管理由不同组处理。</span><span class="sxs-lookup"><span data-stu-id="a91f8-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="a91f8-121">在部署 Lync 服务器时，拥有网络、防火墙、端口和协议、证书和服务器配置所需的详细信息非常有用。</span><span class="sxs-lookup"><span data-stu-id="a91f8-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="a91f8-122">**边缘服务器和边缘池**</span><span class="sxs-lookup"><span data-stu-id="a91f8-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="a91f8-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="a91f8-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="a91f8-124">**反向代理**</span><span class="sxs-lookup"><span data-stu-id="a91f8-124">**Reverse Proxy**</span></span>

<span data-ttu-id="a91f8-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="a91f8-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="a91f8-126">**导演或控制器池**</span><span class="sxs-lookup"><span data-stu-id="a91f8-126">**Director or Director pool**</span></span>

<span data-ttu-id="a91f8-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="a91f8-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

