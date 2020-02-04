---
title: Lync Server 2013：证书摘要 - 单一控制器
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
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="52896-102">Lync Server 2013 中的证书摘要 - 单一控制器</span><span class="sxs-lookup"><span data-stu-id="52896-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52896-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="52896-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="52896-104">单个控制器的证书要求包括一个默认证书，该证书为 Director 可以接收的服务提供了主题名称和使用者备用名称。</span><span class="sxs-lookup"><span data-stu-id="52896-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="52896-105">此外，还有一个用于服务器到服务器身份验证的 OAuth 令牌证书。</span><span class="sxs-lookup"><span data-stu-id="52896-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="52896-106">Director 的证书</span><span class="sxs-lookup"><span data-stu-id="52896-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52896-107">组件</span><span class="sxs-lookup"><span data-stu-id="52896-107">Component</span></span></th>
<th><span data-ttu-id="52896-108">使用者名称 (SN)</span><span class="sxs-lookup"><span data-stu-id="52896-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="52896-109">主题备用名称（SAN）</span><span class="sxs-lookup"><span data-stu-id="52896-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="52896-110">备注</span><span class="sxs-lookup"><span data-stu-id="52896-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52896-111">默认</span><span class="sxs-lookup"><span data-stu-id="52896-111">Default</span></span></p></td>
<td><p><span data-ttu-id="52896-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="52896-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="52896-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="52896-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="52896-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52896-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="52896-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52896-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="52896-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52896-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="52896-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52896-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="52896-118">（可选） \* contoso.com</span><span class="sxs-lookup"><span data-stu-id="52896-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="52896-119">可以从内部托管的证书颁发机构（CA）或公共 CA 请求控制器证书。</span><span class="sxs-lookup"><span data-stu-id="52896-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="52896-120">控制器在来自外围服务器或从边缘服务器中响应来自反向代理的请求。</span><span class="sxs-lookup"><span data-stu-id="52896-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="52896-121">内部客户端将不使用 Director。</span><span class="sxs-lookup"><span data-stu-id="52896-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="52896-122">或者是简单 Url 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="52896-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52896-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="52896-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="52896-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="52896-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="52896-125">无条目</span><span class="sxs-lookup"><span data-stu-id="52896-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="52896-126">请注意，最小键长度为1024，但你可能会收到一条警告，指出推荐的最小密钥长度为2048位。</span><span class="sxs-lookup"><span data-stu-id="52896-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="52896-127">OAuthTokenIssuer 证书是单一用途的证书，用于在大规模环境中验证服务器，并且可以从内部 CA 或公共 CA 请求。</span><span class="sxs-lookup"><span data-stu-id="52896-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="52896-128">证书是必需的。</span><span class="sxs-lookup"><span data-stu-id="52896-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

