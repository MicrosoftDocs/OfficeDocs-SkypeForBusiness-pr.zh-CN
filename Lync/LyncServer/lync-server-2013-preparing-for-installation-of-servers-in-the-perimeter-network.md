---
title: 准备在外围网络中安装服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31c0cbd7355b5ac51908a9a7eba2ae0e6b6680ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="52240-102">准备在外围网络中为 Lync Server 2013 安装服务器</span><span class="sxs-lookup"><span data-stu-id="52240-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52240-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="52240-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="52240-104">设置边缘服务器组件之前，需要确保所设置的计算机满足系统要求，并完成部署边缘服务器组件所需的其他先决步骤。</span><span class="sxs-lookup"><span data-stu-id="52240-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="52240-105">开始之前，请查看要部署的参考体系结构的规划文档中下列主题的详细信息：</span><span class="sxs-lookup"><span data-stu-id="52240-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="52240-106">Lync Server 2013 中具有专用 IP 地址和 NAT 的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="52240-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="52240-107">Lync Server 2013 中具有公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="52240-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="52240-108">在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="52240-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="52240-109">在 Lync Server 2013 中，扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="52240-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="52240-110">Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="52240-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="52240-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="52240-111">In This Section</span></span>

  - [<span data-ttu-id="52240-112">在 Lync Server 2013 中为边缘支持配置 DNS</span><span class="sxs-lookup"><span data-stu-id="52240-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="52240-113">在 Lync Server 2013 中为扩展的边缘拓扑设置硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="52240-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="52240-114">在 Lync Server 2013 中为外部用户访问配置防火墙和端口</span><span class="sxs-lookup"><span data-stu-id="52240-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="52240-115">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="52240-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="52240-116">在 Lync Server 2013 中请求边缘组件的证书</span><span class="sxs-lookup"><span data-stu-id="52240-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

