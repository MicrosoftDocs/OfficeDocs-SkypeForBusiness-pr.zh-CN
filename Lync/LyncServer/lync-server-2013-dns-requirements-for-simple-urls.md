---
title: Lync Server 2013：简单 Url 的 DNS 要求
description: Lync Server 2013：简单 Url 的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564958"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="e30eb-103">Lync Server 2013 中简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="e30eb-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e30eb-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e30eb-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e30eb-105">Lync Server 2013 支持简单 Url，使用户加入会议变得更加容易，并使管理员更轻松地进入 Lync Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="e30eb-105">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="e30eb-106">有关简单 Url 的详细信息，请参阅 [在 Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="e30eb-106">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="e30eb-107">Lync Server 支持以下三个简单 Url： "符合"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单 Url，并且管理员简单 URL 是可选的。</span><span class="sxs-lookup"><span data-stu-id="e30eb-107">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="e30eb-108">支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="e30eb-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="e30eb-109">简单 URL 选项 1</span><span class="sxs-lookup"><span data-stu-id="e30eb-109">Simple URL Option 1</span></span>

<span data-ttu-id="e30eb-110">在选项 1 中，为每个简单 URL 创建新的基 URL。</span><span class="sxs-lookup"><span data-stu-id="e30eb-110">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="e30eb-p103">用户单击简单 URL 会议链接时，DNS A 记录解析为的服务器会确定启动正确的客户端软件。客户端软件启动后，会自动与承载会议的池进行通信。这样，无论简单 URL DNS A 记录会解析为哪个服务器或池，用户都会定向到承载会议内容的相应服务器。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="e30eb-114">简单 URL 选项 1</span><span class="sxs-lookup"><span data-stu-id="e30eb-114">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-115"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-115"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="e30eb-116"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-116"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-117">法规</span><span class="sxs-lookup"><span data-stu-id="e30eb-117">Meet</span></span></p></td>
<td><p><span data-ttu-id="e30eb-118">https://meet.contoso.com、等， https://meet.fabrikam.com 依此类推 (组织中每个 SIP 域一个) </span><span class="sxs-lookup"><span data-stu-id="e30eb-118">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-119">拨入</span><span class="sxs-lookup"><span data-stu-id="e30eb-119">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-120">管理员</span><span class="sxs-lookup"><span data-stu-id="e30eb-120">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e30eb-121">如果使用选项 1，必须定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="e30eb-121">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="e30eb-p104">每个会议简单 URL 都需要一条将 URL 解析为控制器（如果已部署一个控制器）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="e30eb-125">如果组织中具有多个 SIP 域，并且您使用此选项，则必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="e30eb-125">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="e30eb-126">例如，如果您同时具有 contoso.com 和 fabrikam.com，则会为和同时创建 DNS A 记录 https://meet.contoso.com https://meet.fabrikam.com 。</span><span class="sxs-lookup"><span data-stu-id="e30eb-126">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="e30eb-127">或者，如果具有多个 SIP 域，并且要最大限度地减少这些简单 URL 的 DNS 记录和证书要求，请使用本主题后面所述的选项 3。</span><span class="sxs-lookup"><span data-stu-id="e30eb-127">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="e30eb-p106">拨入简单 URL 需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="e30eb-p107">管理简单 URL 仅限内部使用。它需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="e30eb-135">简单 URL 选项 2</span><span class="sxs-lookup"><span data-stu-id="e30eb-135">Simple URL Option 2</span></span>

<span data-ttu-id="e30eb-p108">在选项 2 中，会议、拨入和管理简单 URL 都具有一个通用的基 URL，如 lync.contoso.com。因此，这些简单 URL 只需要一条 DNS A 记录，以将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="e30eb-139">请注意，如果组织中具有多个 SIP 域，则仍必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="e30eb-139">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="e30eb-140">在本例中，尽管三种简单 URL 都基于 lync.contoso.com，但 fabrikam.com 的那个会议简单 URL 具有不同的基 URL。</span><span class="sxs-lookup"><span data-stu-id="e30eb-140">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="e30eb-141">在此示例中，必须为和和创建 DNS A https://lync.contoso.com 记录 https://lync.fabrikam.com 。</span><span class="sxs-lookup"><span data-stu-id="e30eb-141">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="e30eb-142">简单 URL 选项 3 提供了在具有多个 SIP 域的情况下处理命名和 DNS A 记录的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="e30eb-142">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="e30eb-143">简单 URL 选项 2</span><span class="sxs-lookup"><span data-stu-id="e30eb-143">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-144"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-144"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="e30eb-145"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-145"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-146">法规</span><span class="sxs-lookup"><span data-stu-id="e30eb-146">Meet</span></span></p></td>
<td><p><span data-ttu-id="e30eb-147">https://lync.contoso.com/Meet、等， https://lync.fabrikam.com/Meet 依此类推 (组织中每个 SIP 域一个) </span><span class="sxs-lookup"><span data-stu-id="e30eb-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-148">拨入</span><span class="sxs-lookup"><span data-stu-id="e30eb-148">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-149">管理员</span><span class="sxs-lookup"><span data-stu-id="e30eb-149">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="e30eb-150">简单 URL 选项 3</span><span class="sxs-lookup"><span data-stu-id="e30eb-150">Simple URL Option 3</span></span>

<span data-ttu-id="e30eb-p110">如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的简单 URL，同时最大限度地减少这些简单 URL 的 DNS 记录和证书要求，则选项 3 是最有用的。在本例中，只需一个 DNS A 记录，此记录可将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="e30eb-153">简单 URL 选项 3</span><span class="sxs-lookup"><span data-stu-id="e30eb-153">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-154"><strong>简单 URL</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-154"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="e30eb-155"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="e30eb-155"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-156">法规</span><span class="sxs-lookup"><span data-stu-id="e30eb-156">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e30eb-157">拨入</span><span class="sxs-lookup"><span data-stu-id="e30eb-157">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e30eb-158">管理员</span><span class="sxs-lookup"><span data-stu-id="e30eb-158">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="e30eb-159">简单 URL 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="e30eb-159">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="e30eb-160">如果您有多个包含前端池的网站，并且您的 DNS 提供程序支持 GeoDNS，则您可以设置简单 Url 的 DNS 记录以支持灾难恢复，这样即使一个完整的前端池停止运行，简单 URL 功能也会继续进行。</span><span class="sxs-lookup"><span data-stu-id="e30eb-160">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="e30eb-161">此灾难恢复功能支持“会议”和“拨入”简单 URL。</span><span class="sxs-lookup"><span data-stu-id="e30eb-161">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="e30eb-p112">若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="e30eb-167">然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e30eb-167">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="e30eb-168">如果您的网络使用<EM>发夹</EM>（通过外部链接路由所有简单 URL 通信，包括来自您组织内部的通信），您可以只配置外部 GeoDNS 地址并将“会议”简单 URL 仅解析到该外部地址。</span><span class="sxs-lookup"><span data-stu-id="e30eb-168">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="e30eb-169">使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。</span><span class="sxs-lookup"><span data-stu-id="e30eb-169">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="e30eb-170">您可以对“拨入”简单 URL 设置相同的配置。</span><span class="sxs-lookup"><span data-stu-id="e30eb-170">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="e30eb-171">为此，请创建如前一示例中的其他记录，并 `dialin` `meet` 在 DNS 记录中替换。</span><span class="sxs-lookup"><span data-stu-id="e30eb-171">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="e30eb-172">对于“管理”简单 URL，请使用本节前面所列的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="e30eb-172">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="e30eb-173">设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。</span><span class="sxs-lookup"><span data-stu-id="e30eb-173">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="e30eb-174">对于外部访问，请进行监视以确保对两个池的外部 web FQDN 或负载平衡器 IP 地址的 HTTPS GET 自动发现请求成功。</span><span class="sxs-lookup"><span data-stu-id="e30eb-174">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="e30eb-175">例如，以下请求不得包含任何 **ACCEPT** 标头且必须返回 **200 OK**。</span><span class="sxs-lookup"><span data-stu-id="e30eb-175">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="e30eb-p115">对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。如果检测到任何连接失败，这些池的 VIP 必须关闭端口 80、443 和 444。</span><span class="sxs-lookup"><span data-stu-id="e30eb-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

