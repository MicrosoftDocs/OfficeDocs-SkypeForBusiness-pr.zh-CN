---
title: Lync Server 2013：获取位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e726424e9e24c223bc7e75346bd0c2188f29ee7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="097d6-102">在 Lync Server 2013 中获取位置</span><span class="sxs-lookup"><span data-stu-id="097d6-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="097d6-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="097d6-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="097d6-104">在 Lync Server 2013 E9-1-1 部署中，每个与内部连接的 Lync 或 Lync Phone Edition 客户端主动获取其自己的位置。</span><span class="sxs-lookup"><span data-stu-id="097d6-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="097d6-105">在 SIP 注册之后，客户端会将其在位置请求中了解到的所有网络连接信息提供到位置信息服务，这是由复制的 SQL Server 数据库支持的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="097d6-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="097d6-106">每个中央站点池都有一个位置信息服务，该服务使用网络信息在其记录中查询匹配的位置。</span><span class="sxs-lookup"><span data-stu-id="097d6-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="097d6-107">如果存在匹配项，则 Location 信息服务将向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="097d6-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="097d6-108">如果没有匹配项，则可能提示用户手动输入位置（取决于位置策略设置）。</span><span class="sxs-lookup"><span data-stu-id="097d6-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="097d6-109">位置数据将以 Internet 工程任务组 (IETF) 标准化 XML 格式传输回客户端，称为“状态信息数据格式位置对象 (PIDF-LO)”。</span><span class="sxs-lookup"><span data-stu-id="097d6-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="097d6-110">Lync Server 客户端在紧急呼叫中包含 PIDF-LO-LO 数据，E9-1-1 服务提供商使用此数据来确定相应的 PSAP 并将呼叫路由到该 PSAP 以及正确的 ESQK，这将允许 PSAP 发送器获取呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="097d6-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="097d6-111">下图显示了 Lync Server 客户端如何获取位置（基于第三方客户端 MAC 地址的 location 方法除外）：</span><span class="sxs-lookup"><span data-stu-id="097d6-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="097d6-112">![客户端如何获取位置图](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "客户端如何获取位置图")</span><span class="sxs-lookup"><span data-stu-id="097d6-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="097d6-113">对于获取位置的客户端，必须执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="097d6-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="097d6-114">管理员使用网络线路映射（将各种类型的网络地址映射到相应的紧急响应位置（Erl））填充位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="097d6-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="097d6-p102">如果使用 SIP 中继 E9-1-1 服务提供商，则管理员将针对 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 数据库验证 ERL 的市政地址部分。如果使用 ELIN 网关，则管理员将确保 PSTN 运营商会将 ELIN 上载到自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="097d6-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="097d6-117">在注册过程中或在网络发生更改时，内部连接的客户端将包含客户端发现的网络地址的位置请求发送到 Location 信息服务。</span><span class="sxs-lookup"><span data-stu-id="097d6-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="097d6-118">位置信息服务查询某个位置的已发布记录，如果找到匹配项，则以 PIDF-LO 格式将 ERL 返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="097d6-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

