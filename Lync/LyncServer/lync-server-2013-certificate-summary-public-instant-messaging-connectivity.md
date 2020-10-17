---
title: Lync Server 2013：证书摘要-公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512779"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="19a5c-102">证书摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="19a5c-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19a5c-103">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="19a5c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="19a5c-104">若要为公用即时消息连接配置证书，应首先注意到其他 SIP 联合类型或即使是标准边缘服务器证书没有什么不同，只是北美在线 (AOL) 需要唯一的证书配置。</span><span class="sxs-lookup"><span data-stu-id="19a5c-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="19a5c-105">除了通常的服务器增强型密钥使用 (EKU) 中，美洲 Online 还需要证书或证书 (在边缘池的情况下，) 也包含客户端 EKU。</span><span class="sxs-lookup"><span data-stu-id="19a5c-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="19a5c-106">客户端 EKU 是对证书的补充，并且是分配给边缘服务器的外部公用证书的一部分。</span><span class="sxs-lookup"><span data-stu-id="19a5c-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="19a5c-107">证书摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="19a5c-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19a5c-108">组件</span><span class="sxs-lookup"><span data-stu-id="19a5c-108">Component</span></span></th>
<th><span data-ttu-id="19a5c-109">使用者名称</span><span class="sxs-lookup"><span data-stu-id="19a5c-109">Subject name</span></span></th>
<th><span data-ttu-id="19a5c-110">使用者替代名称 (SAN)/顺序</span><span class="sxs-lookup"><span data-stu-id="19a5c-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="19a5c-111">Comments</span><span class="sxs-lookup"><span data-stu-id="19a5c-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19a5c-112">访问/边缘外部</span><span class="sxs-lookup"><span data-stu-id="19a5c-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="19a5c-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19a5c-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="19a5c-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19a5c-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="19a5c-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19a5c-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="19a5c-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="19a5c-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="19a5c-117">证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU （如果要部署具有 AOL 的公共 IM 连接）。</span><span class="sxs-lookup"><span data-stu-id="19a5c-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="19a5c-118">将证书分配给外部边缘服务器接口：</span><span class="sxs-lookup"><span data-stu-id="19a5c-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="19a5c-119">Access Edge service － 访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="19a5c-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="19a5c-120">Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="19a5c-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="19a5c-121">A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="19a5c-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="19a5c-p103">请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</span><span class="sxs-lookup"><span data-stu-id="19a5c-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19a5c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19a5c-125">See Also</span></span>


[<span data-ttu-id="19a5c-126">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="19a5c-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

