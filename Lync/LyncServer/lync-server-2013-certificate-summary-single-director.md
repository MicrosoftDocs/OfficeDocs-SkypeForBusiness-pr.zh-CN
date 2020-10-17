---
title: Lync Server 2013：证书摘要-单个控制器
description: Lync Server 2013：证书摘要-单个控制器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572158"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="31a0f-103">证书摘要-Lync Server 2013 中的单个控制器</span><span class="sxs-lookup"><span data-stu-id="31a0f-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31a0f-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="31a0f-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="31a0f-105">单个控制器的证书要求包含一个默认证书，该证书具有可接收的服务的主题名称和使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="31a0f-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="31a0f-106">此外，还有一个用于服务器到服务器身份验证的 OAuth 令牌证书。</span><span class="sxs-lookup"><span data-stu-id="31a0f-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="31a0f-107">控制器的证书</span><span class="sxs-lookup"><span data-stu-id="31a0f-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31a0f-108">组件</span><span class="sxs-lookup"><span data-stu-id="31a0f-108">Component</span></span></th>
<th><span data-ttu-id="31a0f-109">使用者名称 (SN)</span><span class="sxs-lookup"><span data-stu-id="31a0f-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="31a0f-110">使用者替代名称 (SAN)</span><span class="sxs-lookup"><span data-stu-id="31a0f-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="31a0f-111">Comments</span><span class="sxs-lookup"><span data-stu-id="31a0f-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31a0f-112">默认值</span><span class="sxs-lookup"><span data-stu-id="31a0f-112">Default</span></span></p></td>
<td><p><span data-ttu-id="31a0f-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="31a0f-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="31a0f-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="31a0f-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="31a0f-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31a0f-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="31a0f-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31a0f-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="31a0f-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31a0f-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="31a0f-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31a0f-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="31a0f-119">（可选）\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31a0f-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31a0f-120">可以从内部托管的证书颁发机构 (CA) 或公共 CA 请求控制器证书。</span><span class="sxs-lookup"><span data-stu-id="31a0f-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="31a0f-121">Director 响应来自周边或边缘服务器的反向代理的请求。</span><span class="sxs-lookup"><span data-stu-id="31a0f-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="31a0f-122">内部客户端将不使用控制器。</span><span class="sxs-lookup"><span data-stu-id="31a0f-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="31a0f-123">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="31a0f-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31a0f-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="31a0f-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="31a0f-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="31a0f-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="31a0f-126">无条目</span><span class="sxs-lookup"><span data-stu-id="31a0f-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="31a0f-127">请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。</span><span class="sxs-lookup"><span data-stu-id="31a0f-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="31a0f-p103">OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</span><span class="sxs-lookup"><span data-stu-id="31a0f-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

