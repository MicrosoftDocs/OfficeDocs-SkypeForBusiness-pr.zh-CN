---
title: Lync Server 2013：获取位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="b2b94-102">在 Lync Server 2013 中获取位置</span><span class="sxs-lookup"><span data-stu-id="b2b94-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2b94-103">_**主题上次修改时间:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b2b94-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b2b94-104">在 Lync Server 2013 E9 部署中, 每个内部连接的 Lync 或 Lync Phone 版客户端都将主动获取其自己的位置。</span><span class="sxs-lookup"><span data-stu-id="b2b94-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="b2b94-105">在 SIP 注册后, 客户端 furnishes 在位置信息服务 (即由复制的 SQL Server 数据库支持的 web 服务) 的位置请求中对其自身知道的所有网络连接信息。</span><span class="sxs-lookup"><span data-stu-id="b2b94-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="b2b94-106">每个中心网站池都有一个位置信息服务, 该服务使用网络信息查询匹配位置的记录。</span><span class="sxs-lookup"><span data-stu-id="b2b94-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="b2b94-107">如果存在匹配项, 则 Location 信息服务将向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="b2b94-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="b2b94-108">如果没有匹配项，则可能会提示用户手动输入位置（取决于位置策略设置）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="b2b94-109">位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式（称为状态信息数据格式位置对象 (PIDF-LO)）传回客户端。</span><span class="sxs-lookup"><span data-stu-id="b2b94-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="b2b94-110">Lync Server 客户端将 PIDF 数据作为紧急呼叫的一部分包括在紧急呼叫中, 此数据由 E9 服务提供商用于确定相应的 PSAP 并将该 PSAP 的调用路由到该以及正确的 ESQK, 从而允许 PSAP dispatcher 获取呼叫方的位置。</span><span class="sxs-lookup"><span data-stu-id="b2b94-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="b2b94-111">下图显示了 Lync Server 客户端如何获取位置 (除第三方基于客户端 MAC 地址的位置方法除外):</span><span class="sxs-lookup"><span data-stu-id="b2b94-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="b2b94-112">![客户端如何获取位置图](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "客户端如何获取位置图")</span><span class="sxs-lookup"><span data-stu-id="b2b94-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="b2b94-113">对于获取位置的客户端，必须执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b2b94-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="b2b94-114">管理员通过网络 wiremap 填充位置信息服务数据库 (将各种类型的网络地址映射到相应的紧急响应位置 (ERLs)) 的表。</span><span class="sxs-lookup"><span data-stu-id="b2b94-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="b2b94-p102">如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="b2b94-117">在注册期间或网络更改发生时, 内部连接的客户端会将包含客户发现的网络地址的位置请求发送到位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="b2b94-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="b2b94-118">位置信息服务查询某个位置的已发布记录, 如果找到匹配项, 则以 PIDF 格式将 ERL 返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="b2b94-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

