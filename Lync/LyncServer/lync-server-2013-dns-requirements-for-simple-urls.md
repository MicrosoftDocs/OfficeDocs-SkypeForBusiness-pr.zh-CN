---
title: Lync Server 2013：简单 URL 的 DNS 要求
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
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="c72c5-102">Lync Server 2013 中简单 URL 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c72c5-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c72c5-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c72c5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c72c5-104">Lync Server 2013 支持简单的 Url，从而使你的用户加入会议更容易，并且让你的管理员更容易获得 Lync Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="c72c5-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="c72c5-105">有关简单 Url 的详细信息，请参阅[在 Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="c72c5-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="c72c5-106">Lync 服务器支持以下三个简单的 Url： "开会"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单的 Url，"管理员简单 URL" 是可选的。</span><span class="sxs-lookup"><span data-stu-id="c72c5-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="c72c5-107">需要支持简单 Url 的域名系统（DNS）记录取决于你定义这些简单 Url 的方式，以及你是否希望支持简单 Url 的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="c72c5-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="c72c5-108">简单 URL 选项1</span><span class="sxs-lookup"><span data-stu-id="c72c5-108">Simple URL Option 1</span></span>

<span data-ttu-id="c72c5-109">在选项1中，为每个简单的 URL 创建一个新的基本 URL。</span><span class="sxs-lookup"><span data-stu-id="c72c5-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c72c5-110">当用户单击简单的 URL 会议链接时，DNS A 记录解析到的服务器确定正确的客户端软件以启动。</span><span class="sxs-lookup"><span data-stu-id="c72c5-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="c72c5-111">客户端软件启动后，它将自动与会议所在的池进行通信。</span><span class="sxs-lookup"><span data-stu-id="c72c5-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="c72c5-112">这样，无论简单 URL DNS A 记录解析到哪个服务器或池，用户都将定向到会议内容的相应服务器。</span><span class="sxs-lookup"><span data-stu-id="c72c5-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="c72c5-113">简单 URL 选项1</span><span class="sxs-lookup"><span data-stu-id="c72c5-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-114"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c72c5-115"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-116">会议</span><span class="sxs-lookup"><span data-stu-id="c72c5-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="c72c5-117">https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="c72c5-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-118">拨入</span><span class="sxs-lookup"><span data-stu-id="c72c5-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-119">Iis</span><span class="sxs-lookup"><span data-stu-id="c72c5-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c72c5-120">如果使用选项1，则必须定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="c72c5-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="c72c5-121">对于每个 "匹配简单 URL"，你需要一个 DNS A 记录，用于将 URL 解析为 Director 的 IP 地址（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="c72c5-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c72c5-122">否则，它应解析为前端池负载平衡器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c72c5-123">如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="c72c5-124">如果您的组织中有多个 SIP 域，并且您使用此选项，则必须为每个 SIP 域创建 "满足简单 Url"，并且对于每个 "匹配简单 URL" 都需要 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="c72c5-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c72c5-125">例如，如果你同时拥有 contoso.com 和 fabrikam.com，你将为https://meet.contoso.com and 和 AND https://meet.fabrikam.com创建 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="c72c5-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="c72c5-126">或者，如果你有多个 SIP 域，并且想要最小化这些简单 Url 的 DNS 记录和证书要求，请按照本主题后面部分所述使用选项3。</span><span class="sxs-lookup"><span data-stu-id="c72c5-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="c72c5-127">对于拨入式简单 URL，你需要一个 DNS A 记录，该记录将 URL 解析为 Director 的 IP 地址（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="c72c5-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c72c5-128">否则，它应解析为前端池负载平衡器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c72c5-129">如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="c72c5-130">管理员简单 URL 仅限内部工作。</span><span class="sxs-lookup"><span data-stu-id="c72c5-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="c72c5-131">它需要一个 DNS A 记录，该记录将 URL 解析为 Director 的 IP 地址（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="c72c5-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="c72c5-132">否则，它应解析为前端池负载平衡器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="c72c5-133">如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="c72c5-134">简单 URL 选项2</span><span class="sxs-lookup"><span data-stu-id="c72c5-134">Simple URL Option 2</span></span>

<span data-ttu-id="c72c5-135">使用选项2，"开会"、"拨入" 和 "管理员简单 Url" 都具有一个通用的基本 URL，例如 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c72c5-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="c72c5-136">因此，对于这些简单的 Url，只需要一个 DNS A 记录，用于将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="c72c5-137">如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="c72c5-138">请注意，如果你的组织中有多个 SIP 域，你仍然必须为每个 SIP 域创建 "满足简单 Url"，并且你需要针对每个 "每个简单 URL" 的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="c72c5-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="c72c5-139">在此示例中，虽然三个简单的 Url 都基于 lync.contoso.com，但 fabrikam.com 的另一个基本 url 是使用不同的基本 URL 设置的。</span><span class="sxs-lookup"><span data-stu-id="c72c5-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="c72c5-140">在此示例中，你必须为https://lync.contoso.com和https://lync.fabrikam.com的 DNS 创建 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="c72c5-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="c72c5-141">简单 URL 选项3显示了处理命名和 DNS A 记录的另一种方法（如果你有多个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="c72c5-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="c72c5-142">简单 URL 选项2</span><span class="sxs-lookup"><span data-stu-id="c72c5-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-143"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c72c5-144"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-145">会议</span><span class="sxs-lookup"><span data-stu-id="c72c5-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="c72c5-146">https://lync.contoso.com/Meet， https://lync.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="c72c5-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-147">拨入</span><span class="sxs-lookup"><span data-stu-id="c72c5-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-148">Iis</span><span class="sxs-lookup"><span data-stu-id="c72c5-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="c72c5-149">简单 URL 选项3</span><span class="sxs-lookup"><span data-stu-id="c72c5-149">Simple URL Option 3</span></span>

<span data-ttu-id="c72c5-150">如果你有多个 SIP 域，而你希望它们具有单独的简单 Url，但想要将这些简单 Url 的 DNS 记录和证书要求降到最低，则选项3非常有用。</span><span class="sxs-lookup"><span data-stu-id="c72c5-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="c72c5-151">在此示例中，只需要一个 DNS A 记录，该记录可将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="c72c5-152">简单 URL 选项3</span><span class="sxs-lookup"><span data-stu-id="c72c5-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-153"><strong>简单的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="c72c5-154"><strong>示例</strong></span><span class="sxs-lookup"><span data-stu-id="c72c5-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-155">会议</span><span class="sxs-lookup"><span data-stu-id="c72c5-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72c5-156">拨入</span><span class="sxs-lookup"><span data-stu-id="c72c5-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72c5-157">Iis</span><span class="sxs-lookup"><span data-stu-id="c72c5-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="c72c5-158">简单 Url 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="c72c5-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="c72c5-159">如果你有多个包含前端池的网站，并且 DNS 提供程序支持 GeoDNS，你可以为简单的 Url 设置 DNS 记录以支持灾难恢复，以便即使一个完整的前端池停止运行，简单的 URL 功能也会继续。</span><span class="sxs-lookup"><span data-stu-id="c72c5-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="c72c5-160">此灾难恢复功能支持 "开会" 和 "拨入" 简单 Url。</span><span class="sxs-lookup"><span data-stu-id="c72c5-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="c72c5-161">若要配置此设置，请创建两个 GeoDNS 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="c72c5-162">每个地址都有两个 DNS A 或 CNAME 记录，它们可解析为两个池，这些记录结合在一起以供灾难恢复之用。</span><span class="sxs-lookup"><span data-stu-id="c72c5-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="c72c5-163">一个 GeoDNS 地址用于内部访问，并解析为两个池的内部 web FQDN 或负载平衡器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c72c5-164">其他 GeoDNS 地址用于外部访问，并解析为两个池的外部 web FQDN 或负载平衡器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c72c5-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c72c5-165">下面是使用池的 Fqdn 的 "满足简单 URL" 的示例。</span><span class="sxs-lookup"><span data-stu-id="c72c5-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="c72c5-166">然后，创建将您的 "满足简单 URL" （如 meet.contoso.com）解析为两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="c72c5-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="c72c5-167">如果你的网络使用<EM>hairpinning</EM> （通过外部链接路由所有简单的 URL 流量，包括来自你的组织内的流量），则只需配置外部 GeoDNS 地址并将你的 "仅限" 简单 url 解析为仅外部地址即可。</span><span class="sxs-lookup"><span data-stu-id="c72c5-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="c72c5-168">使用此方法时，你可以将每个 GeoDNS 地址配置为使用循环复用方法将请求分配到两个池，或主要连接到一个池（如位于地理位置较近的池），并使用另一个池（仅限情况连接失败。</span><span class="sxs-lookup"><span data-stu-id="c72c5-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="c72c5-169">你可以为拨入式简单 URL 设置相同配置。</span><span class="sxs-lookup"><span data-stu-id="c72c5-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="c72c5-170">若要执行此操作，请创建如前面的示例中所示`dialin`的`meet`其他记录，并在 DNS 记录中替换。</span><span class="sxs-lookup"><span data-stu-id="c72c5-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="c72c5-171">对于 "管理员简单 URL"，请使用本节前面列出的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="c72c5-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="c72c5-172">设置此配置后，必须使用监视应用程序设置 HTTP 监视以监视失败。</span><span class="sxs-lookup"><span data-stu-id="c72c5-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="c72c5-173">对于外部访问，监视器确保对两个池的外部 web FQDN 或负载平衡器 IP 地址的 HTTPS 获取自动发现请求成功。</span><span class="sxs-lookup"><span data-stu-id="c72c5-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="c72c5-174">例如，以下请求不得包含任何**ACCEPT**标头，并且必须返回**200 OK**。</span><span class="sxs-lookup"><span data-stu-id="c72c5-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

<span data-ttu-id="c72c5-175">对于内部访问，你必须在两个池的内部 web FQDN 或负载平衡器 IP 地址上监视端口5061。</span><span class="sxs-lookup"><span data-stu-id="c72c5-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c72c5-176">如果检测到任何连接失败，这些池的 VIP 必须关闭端口80、443和444。</span><span class="sxs-lookup"><span data-stu-id="c72c5-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

