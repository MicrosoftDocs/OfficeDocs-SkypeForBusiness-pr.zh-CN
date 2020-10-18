---
title: Lync Server 2013：证书摘要-DNS 和 HLB 负载平衡
description: Lync Server 2013：证书摘要-DNS 和 HLB 负载平衡。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a89975af16b6e39625677f787d3726f00c76c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575968"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="15401-103">Lync Server 2013 中的证书摘要-DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="15401-103">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15401-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="15401-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="15401-105">具有 DNS 负载平衡和硬件负载平衡器的 Director 的证书要求将使用一个默认证书，该证书具有可接收的服务的主题名称和使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="15401-105">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="15401-106">为池中的每个控制器请求一个证书。</span><span class="sxs-lookup"><span data-stu-id="15401-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="15401-107">请务必记住，硬件负载平衡器仅对来自反向代理的流量进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="15401-107">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="15401-108">此外，还有安装在每台服务器上用于服务器到服务器身份验证的 OAuth 令牌证书。</span><span class="sxs-lookup"><span data-stu-id="15401-108">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="15401-109">控制器的证书</span><span class="sxs-lookup"><span data-stu-id="15401-109">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15401-110">组件</span><span class="sxs-lookup"><span data-stu-id="15401-110">Component</span></span></th>
<th><span data-ttu-id="15401-111">使用者名称 (SN)</span><span class="sxs-lookup"><span data-stu-id="15401-111">Subject name (SN)</span></span></th>
<th><span data-ttu-id="15401-112">使用者替代名称 (SAN)</span><span class="sxs-lookup"><span data-stu-id="15401-112">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="15401-113">Comments</span><span class="sxs-lookup"><span data-stu-id="15401-113">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15401-114">默认值</span><span class="sxs-lookup"><span data-stu-id="15401-114">Default</span></span></p></td>
<td><p><span data-ttu-id="15401-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="15401-115">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="15401-116">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="15401-116">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="15401-117">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="15401-117">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="15401-118">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15401-118">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="15401-119">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15401-119">meet.contoso.com</span></span></p>
<p><span data-ttu-id="15401-120">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15401-120">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="15401-121">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15401-121">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="15401-122">（可选）\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15401-122">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="15401-123">可以从内部托管的证书颁发机构 (CA) 或公共 CA 请求控制器证书。</span><span class="sxs-lookup"><span data-stu-id="15401-123">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="15401-124">Director 响应来自周边或边缘服务器的反向代理的请求。</span><span class="sxs-lookup"><span data-stu-id="15401-124">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="15401-125">内部客户端将不使用控制器。</span><span class="sxs-lookup"><span data-stu-id="15401-125">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="15401-126">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="15401-126">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15401-127">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="15401-127">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="15401-128">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="15401-128">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="15401-129">无条目</span><span class="sxs-lookup"><span data-stu-id="15401-129">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="15401-130">请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。</span><span class="sxs-lookup"><span data-stu-id="15401-130">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="15401-p103">OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</span><span class="sxs-lookup"><span data-stu-id="15401-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

