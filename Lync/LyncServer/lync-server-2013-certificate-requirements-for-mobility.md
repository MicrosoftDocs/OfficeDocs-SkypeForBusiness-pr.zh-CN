---
title: Lync Server 2013：移动的证书要求
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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="b87b7-102">Lync Server 2013 中移动的证书要求</span><span class="sxs-lookup"><span data-stu-id="b87b7-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b87b7-103">_**主题上次修改时间：** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="b87b7-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="b87b7-104">如果你部署移动版功能并支持自动发现移动客户端，你需要在证书上包含特定主题备用名称条目以支持来自移动客户端的安全连接。</span><span class="sxs-lookup"><span data-stu-id="b87b7-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="b87b7-105">您需要在以下证书上包含 "使用者备用名称" 条目以自动发现：</span><span class="sxs-lookup"><span data-stu-id="b87b7-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="b87b7-106">控制器池</span><span class="sxs-lookup"><span data-stu-id="b87b7-106">Director pool</span></span>

  - <span data-ttu-id="b87b7-107">前端池</span><span class="sxs-lookup"><span data-stu-id="b87b7-107">Front End pool</span></span>

  - <span data-ttu-id="b87b7-108">反向代理</span><span class="sxs-lookup"><span data-stu-id="b87b7-108">Reverse proxy</span></span>

<span data-ttu-id="b87b7-109">本部分介绍自动发现证书所需的主题备用名称条目。</span><span class="sxs-lookup"><span data-stu-id="b87b7-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b87b7-110">通过使用内部证书颁发机构重新发起证书通常是一个简单的过程，但向反向代理使用的公共证书添加多个主题备用名称条目可能会很高。</span><span class="sxs-lookup"><span data-stu-id="b87b7-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="b87b7-111">如果您有多个 SIP 域，则添加主题备用名称非常昂贵，您可以将反向代理配置为对初始自动发现服务请求使用 HTTP，而不是使用 HTTPS （默认配置）。</span><span class="sxs-lookup"><span data-stu-id="b87b7-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="b87b7-112">有关详细信息，请参阅<A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中的移动技术要求</A>。</span><span class="sxs-lookup"><span data-stu-id="b87b7-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b87b7-113">控制器池证书要求</span><span class="sxs-lookup"><span data-stu-id="b87b7-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b87b7-114">说明</span><span class="sxs-lookup"><span data-stu-id="b87b7-114">Description</span></span></th>
<th><span data-ttu-id="b87b7-115">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="b87b7-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b87b7-116">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="b87b7-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b87b7-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87b7-118">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="b87b7-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b87b7-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b87b7-120">或者，您可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b87b7-121">前端池证书要求</span><span class="sxs-lookup"><span data-stu-id="b87b7-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b87b7-122">说明</span><span class="sxs-lookup"><span data-stu-id="b87b7-122">Description</span></span></th>
<th><span data-ttu-id="b87b7-123">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="b87b7-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b87b7-124">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="b87b7-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b87b7-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87b7-126">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="b87b7-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b87b7-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b87b7-128">或者，您可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b87b7-129">反向代理（公共 CA）证书要求</span><span class="sxs-lookup"><span data-stu-id="b87b7-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b87b7-130">说明</span><span class="sxs-lookup"><span data-stu-id="b87b7-130">Description</span></span></th>
<th><span data-ttu-id="b87b7-131">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="b87b7-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b87b7-132">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="b87b7-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b87b7-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="b87b7-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b87b7-134">将此 SAN 分配给分配给反向代理上的 SSL 侦听器的证书。</span><span class="sxs-lookup"><span data-stu-id="b87b7-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b87b7-135">你的反向代理侦听器将具有你的外部 Web 服务 URL （例如，SAN = lyncwebextpool01 和 dirwebexternal.contoso.com）的主题备用名称（如果你已部署了可选控制器）。</span><span class="sxs-lookup"><span data-stu-id="b87b7-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

