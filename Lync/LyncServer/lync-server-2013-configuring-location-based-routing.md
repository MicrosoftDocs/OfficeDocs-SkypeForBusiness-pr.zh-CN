---
title: Lync Server 2013：配置基于位置的路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b88df8bf0b8362a09ea2e5b779b7fa9d789a0a48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="781db-102">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="781db-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="781db-103">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="781db-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="781db-104">Lync Server 2013 CU1，基于位置的路由是企业语音的一项功能。</span><span class="sxs-lookup"><span data-stu-id="781db-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="781db-105">基于位置的路由是呼叫管理功能，用于控制 Lync Server 2013 CU1 路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="781db-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="781db-106">它强制实施限制，即是否可以根据 Lync 呼叫者的位置将呼叫路由到 PBX 或 PSTN 目标。</span><span class="sxs-lookup"><span data-stu-id="781db-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="781db-107">基于位置的路由根据呼叫者的网络位置将呼叫授权规则应用于 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="781db-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="781db-108">呼叫者的位置根据与呼叫者连接的网络子网关联的网络站点来确定。</span><span class="sxs-lookup"><span data-stu-id="781db-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="781db-109">配置基于位置的路由需要先部署企业语音，然后配置网络区域、站点和子网。</span><span class="sxs-lookup"><span data-stu-id="781db-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="781db-110">这将设置启用基于位置的路由的基础。</span><span class="sxs-lookup"><span data-stu-id="781db-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="781db-111">在部署基于位置的路由之前，必须先部署企业语音，并配置网络区域、站点，并将网络子网与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="781db-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="781db-112">完成后，您可以配置基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="781db-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="781db-113">有关如何配置网络区域、站点和子网的步骤，请参阅[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="781db-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="781db-114">本部分将指导您使用以下示例作为图中的基于位置的路由的配置。</span><span class="sxs-lookup"><span data-stu-id="781db-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="781db-115">![基于企业语音位置的路由示例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "基于企业语音位置的路由示例")</span><span class="sxs-lookup"><span data-stu-id="781db-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="781db-116">下表表示在此示例中定义的用户。</span><span class="sxs-lookup"><span data-stu-id="781db-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="781db-117">终结点类型</span><span class="sxs-lookup"><span data-stu-id="781db-117">Endpoint type</span></span></th>
<th><span data-ttu-id="781db-118">位置</span><span class="sxs-lookup"><span data-stu-id="781db-118">Location</span></span></th>
<th><span data-ttu-id="781db-119">用户</span><span class="sxs-lookup"><span data-stu-id="781db-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="781db-120">Lync</span><span class="sxs-lookup"><span data-stu-id="781db-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="781db-121">新德里公司办公室</span><span class="sxs-lookup"><span data-stu-id="781db-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="781db-122">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="781db-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-123">Lync</span><span class="sxs-lookup"><span data-stu-id="781db-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="781db-124">Hyderabad 企业办公室</span><span class="sxs-lookup"><span data-stu-id="781db-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="781db-125">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="781db-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781db-126">Lync</span><span class="sxs-lookup"><span data-stu-id="781db-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="781db-127">未知（例如酒店）</span><span class="sxs-lookup"><span data-stu-id="781db-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="781db-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="781db-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-129">PBX</span><span class="sxs-lookup"><span data-stu-id="781db-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="781db-130">新德里公司办公室</span><span class="sxs-lookup"><span data-stu-id="781db-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="781db-131">DEL-PBX-1，DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="781db-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781db-132">PBX</span><span class="sxs-lookup"><span data-stu-id="781db-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="781db-133">Hyderabad 企业办公室</span><span class="sxs-lookup"><span data-stu-id="781db-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="781db-134">HYD-1，HYD-2</span><span class="sxs-lookup"><span data-stu-id="781db-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="781db-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="781db-136">未知</span><span class="sxs-lookup"><span data-stu-id="781db-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="781db-137">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="781db-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="781db-138">下表表示在此示例环境中说明的系统。</span><span class="sxs-lookup"><span data-stu-id="781db-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="781db-139">系统警报</span><span class="sxs-lookup"><span data-stu-id="781db-139">System</span></span></th>
<th><span data-ttu-id="781db-140">位置</span><span class="sxs-lookup"><span data-stu-id="781db-140">Location</span></span></th>
<th><span data-ttu-id="781db-141">名称</span><span class="sxs-lookup"><span data-stu-id="781db-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="781db-142">Lync Server 2013 CU1 池</span><span class="sxs-lookup"><span data-stu-id="781db-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="781db-143">任意</span><span class="sxs-lookup"><span data-stu-id="781db-143">any</span></span></p></td>
<td><p><span data-ttu-id="781db-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="781db-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-145">Lync Server 2013 CU1，中介服务器</span><span class="sxs-lookup"><span data-stu-id="781db-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="781db-146">任意</span><span class="sxs-lookup"><span data-stu-id="781db-146">any</span></span></p></td>
<td><p><span data-ttu-id="781db-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="781db-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781db-148">PSTN 网关1</span><span class="sxs-lookup"><span data-stu-id="781db-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="781db-149">德里</span><span class="sxs-lookup"><span data-stu-id="781db-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="781db-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="781db-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-151">PSTN 网关2</span><span class="sxs-lookup"><span data-stu-id="781db-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="781db-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="781db-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="781db-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="781db-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781db-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="781db-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="781db-155">德里</span><span class="sxs-lookup"><span data-stu-id="781db-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="781db-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="781db-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781db-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="781db-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="781db-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="781db-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="781db-159">RED-PBX</span><span class="sxs-lookup"><span data-stu-id="781db-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="781db-160">本部分内容</span><span class="sxs-lookup"><span data-stu-id="781db-160">In This Section</span></span>

  - [<span data-ttu-id="781db-161">在 Lync Server 2013 中配置企业语音</span><span class="sxs-lookup"><span data-stu-id="781db-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="781db-162">在 Lync Server 2013 中部署网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="781db-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="781db-163">在 Lync Server 2013 中启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="781db-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="781db-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="781db-164">See Also</span></span>


[<span data-ttu-id="781db-165">在 Lync Server 2013 中部署高级企业语音功能</span><span class="sxs-lookup"><span data-stu-id="781db-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

