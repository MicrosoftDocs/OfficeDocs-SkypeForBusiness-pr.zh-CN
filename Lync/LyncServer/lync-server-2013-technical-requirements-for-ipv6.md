---
title: IPv6 的 Lync Server 2013 技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="672ce-102">Lync Server 2013 中 IPv6 的技术要求</span><span class="sxs-lookup"><span data-stu-id="672ce-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="672ce-103">_**主题上次修改时间:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="672ce-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="672ce-104">如果你计划为 IPv6 配置 Lync Server 2013, 请记住以下要求:</span><span class="sxs-lookup"><span data-stu-id="672ce-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="672ce-105">若要将 IPv6 地址与 Lync Server 配合使用, 你需要为必须发现和解析为 IPv6 地址的记录创建域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="672ce-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="672ce-106">IPv6 DNS 使用主机 AAAA (4A) 记录。</span><span class="sxs-lookup"><span data-stu-id="672ce-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="672ce-107">如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="672ce-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="672ce-108">即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。</span><span class="sxs-lookup"><span data-stu-id="672ce-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="672ce-p102">您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。</span><span class="sxs-lookup"><span data-stu-id="672ce-p102">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="672ce-112">每个 IPv6 地址都有一个作用域。</span><span class="sxs-lookup"><span data-stu-id="672ce-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="672ce-113">可用于 IPv6 寻址的三个作用域是 IPv6 全局地址 (类似于公用 IPv4 地址)、IPv6 唯一本地地址 (类似于专用 IPv4 地址范围) 和 IPv6 链接本地地址 (类似于中的自动专用 IP 地址)Windows Server for IPv4)。</span><span class="sxs-lookup"><span data-stu-id="672ce-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="672ce-114">池内所有服务器都应该具有作用域相同的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="672ce-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="672ce-115">IPv6 是一个复杂的主题, 需要仔细规划网络团队和 Internet 提供商, 以帮助确保你在 Windows Server 级别和 Lync Server 2013 级别上分配的地址按预期工作。</span><span class="sxs-lookup"><span data-stu-id="672ce-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="672ce-116">请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。</span><span class="sxs-lookup"><span data-stu-id="672ce-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="672ce-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="672ce-117">See Also</span></span>


[<span data-ttu-id="672ce-118">IP 版本6寻址体系结构</span><span class="sxs-lookup"><span data-stu-id="672ce-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="672ce-119">IPv6 全局单播地址格式</span><span class="sxs-lookup"><span data-stu-id="672ce-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="672ce-120">唯一本地 IPv6 单播地址</span><span class="sxs-lookup"><span data-stu-id="672ce-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

