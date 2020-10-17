---
title: Lync Server 2013：验证用于负载平衡的域名系统设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc346dba48de1914f9aa5684d114e2f3466396f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508609"
---
# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="a6f3c-102">在 Lync Server 2013 中验证用于负载平衡的域名系统设置</span><span class="sxs-lookup"><span data-stu-id="a6f3c-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f3c-103">_**上次修改的主题：** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="a6f3c-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="a6f3c-p101">要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="a6f3c-106">此外，如果要对边缘池使用 DNS 负载平衡，则需要以下 DNS 条目：</span><span class="sxs-lookup"><span data-stu-id="a6f3c-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="a6f3c-107">对于 Lync Server 访问边缘服务，池中的每台服务器都必须有一个条目。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="a6f3c-108">每个条目都必须解析 Lync Server 访问边缘服务 (的 FQDN，例如，sip.contoso.com) 到池中某一台边缘服务器上的 Lync Server 访问边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="a6f3c-109">对于 Lync Server Web 会议边缘服务，池中的每台服务器都必须有一个条目。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="a6f3c-110">每个条目都必须解析 Lync Server Web 会议边缘服务 (的 FQDN，例如，webconf.contoso.com) 到池中某个边缘服务器上的 Lync Server Web 会议边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="a6f3c-111">对于 Lync Server 音频/视频边缘服务，池中的每台服务器都必须有一个条目。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="a6f3c-112">每个条目都必须解析 Lync Server 音频/视频边缘服务 (的 FQDN，例如，av.contoso.com) 到池中某一台边缘服务器上的 Lync Server 音频/视频边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="a6f3c-113">如果要在边缘池的内部接口上使用 DNS 负载平衡，则必须添加一个 DNS 记录，该记录会将边缘池的内部 FQDN 解析为池中每个服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="a6f3c-114">若要验证 DNS 是否为 DNS 负载平衡返回正确的值，应使用 nslookup 工具。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="a6f3c-115">若要使用 nslookup 返回 DNS 记录的所有值，应运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a6f3c-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="a6f3c-116">您可以对 DNS 负载平衡配置中使用的每个 FQDN 运行此命令，以验证 DNS 负载平衡的每个记录集是否返回了所有正确的条目。</span><span class="sxs-lookup"><span data-stu-id="a6f3c-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

