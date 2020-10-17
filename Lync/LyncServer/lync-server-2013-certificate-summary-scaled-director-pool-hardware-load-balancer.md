---
title: 证书摘要-扩展的控制器池、硬件负载平衡器
description: 证书摘要-扩展的控制器池、硬件负载平衡器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08abc37940cd41a29d6620cfc0a2a801de4a8e38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572228"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="4e6eb-103">Lync Server 2013 中的证书摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="4e6eb-103">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e6eb-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4e6eb-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4e6eb-105">带有硬件负载平衡器的控制器的证书要求将使用一个默认证书，该证书具有一个主题名称和使用者替代名称，用于控制器池可以接收的服务。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-105">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="4e6eb-106">为池中的每个控制器请求一个证书。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="4e6eb-107">此外，每台服务器上还安装了用于进行服务器到服务器身份验证的 OAuth Token 证书。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-107">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="4e6eb-108">使用硬件负载平衡器的缩放控制器的证书</span><span class="sxs-lookup"><span data-stu-id="4e6eb-108">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e6eb-109">组件</span><span class="sxs-lookup"><span data-stu-id="4e6eb-109">Component</span></span></th>
<th><span data-ttu-id="4e6eb-110">使用者名称 (SN)</span><span class="sxs-lookup"><span data-stu-id="4e6eb-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="4e6eb-111">使用者替代名称 (SAN)</span><span class="sxs-lookup"><span data-stu-id="4e6eb-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="4e6eb-112">Comments</span><span class="sxs-lookup"><span data-stu-id="4e6eb-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e6eb-113">默认值</span><span class="sxs-lookup"><span data-stu-id="4e6eb-113">Default</span></span></p></td>
<td><p><span data-ttu-id="4e6eb-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4e6eb-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4e6eb-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4e6eb-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="4e6eb-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4e6eb-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="4e6eb-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e6eb-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4e6eb-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e6eb-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="4e6eb-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e6eb-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="4e6eb-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e6eb-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="4e6eb-121">（可选）\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e6eb-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4e6eb-122">可以从内部托管的证书颁发机构 (CA) 或公共 CA 请求控制器证书。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="4e6eb-123">Director 响应来自周边或边缘服务器的反向代理的请求。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="4e6eb-124">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="4e6eb-124">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e6eb-125">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="4e6eb-125">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="4e6eb-126">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4e6eb-126">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4e6eb-127">无条目</span><span class="sxs-lookup"><span data-stu-id="4e6eb-127">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="4e6eb-128">请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-128">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="4e6eb-p102">OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</span><span class="sxs-lookup"><span data-stu-id="4e6eb-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

