---
title: Lync Server 2013：移动性的证书要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87657340205722a721485f213029220641885075
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533389"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7881f-102">Lync Server 2013 中的移动性证书要求</span><span class="sxs-lookup"><span data-stu-id="7881f-102">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7881f-103">_**上次修改的主题：** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="7881f-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="7881f-104">如果您部署移动功能并支持移动客户端的自动发现，则您需要在证书上包含某些使用者替代名称条目，以支持来自移动客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="7881f-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="7881f-105">您需要在以下证书上包含使用者替代名称条目以实现自动发现：</span><span class="sxs-lookup"><span data-stu-id="7881f-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="7881f-106">控制器池</span><span class="sxs-lookup"><span data-stu-id="7881f-106">Director pool</span></span>

  - <span data-ttu-id="7881f-107">前端池</span><span class="sxs-lookup"><span data-stu-id="7881f-107">Front End pool</span></span>

  - <span data-ttu-id="7881f-108">反向代理</span><span class="sxs-lookup"><span data-stu-id="7881f-108">Reverse proxy</span></span>

<span data-ttu-id="7881f-109">本节介绍了实现自动发现所需的证书上的使用者替代名称条目。</span><span class="sxs-lookup"><span data-stu-id="7881f-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7881f-110">使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。</span><span class="sxs-lookup"><span data-stu-id="7881f-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="7881f-111">如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则您可将反向代理配置为对初始自动发现服务请求使用 HTTP，而不是使用 HTTPS（默认配置）。</span><span class="sxs-lookup"><span data-stu-id="7881f-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="7881f-112">有关详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中的移动技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="7881f-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="7881f-113">控制器池证书要求</span><span class="sxs-lookup"><span data-stu-id="7881f-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7881f-114">说明</span><span class="sxs-lookup"><span data-stu-id="7881f-114">Description</span></span></th>
<th><span data-ttu-id="7881f-115">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="7881f-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7881f-116">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="7881f-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7881f-117">SAN = lyncdiscoverinternal.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7881f-118">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="7881f-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7881f-119">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7881f-120">或者，也可以使用 SAN = \*。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="7881f-121">前端池证书要求</span><span class="sxs-lookup"><span data-stu-id="7881f-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7881f-122">说明</span><span class="sxs-lookup"><span data-stu-id="7881f-122">Description</span></span></th>
<th><span data-ttu-id="7881f-123">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="7881f-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7881f-124">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="7881f-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7881f-125">SAN = lyncdiscoverinternal.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7881f-126">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="7881f-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7881f-127">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7881f-128">或者，也可以使用 SAN = \*。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="7881f-129">反向代理（公共 CA）证书要求</span><span class="sxs-lookup"><span data-stu-id="7881f-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7881f-130">说明</span><span class="sxs-lookup"><span data-stu-id="7881f-130">Description</span></span></th>
<th><span data-ttu-id="7881f-131">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="7881f-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7881f-132">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="7881f-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7881f-133">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7881f-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7881f-134">将此 SAN 分配给为反向代理上的 SSL 侦听器分配的证书。</span><span class="sxs-lookup"><span data-stu-id="7881f-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7881f-135">反向代理侦听器将包含外部 Web 服务 URL 的主题备用名称 (s)  (例如，如果已部署可选控制器) ，则为 SAN = lyncwebextpool01 和 dirwebexternal.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7881f-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

