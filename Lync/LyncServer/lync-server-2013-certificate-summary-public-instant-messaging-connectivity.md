---
title: 'Lync Server 2013: 证书摘要-公共即时消息连接'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="497f9-102">证书摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="497f9-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="497f9-103">_**主题上次修改时间:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="497f9-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="497f9-104">若要配置公共即时消息连接的证书, 应首先注意到其他 SIP 联合类型或标准边缘服务器证书没有什么不同, 但美国 Online (AOL) 需要唯一证书配置。</span><span class="sxs-lookup"><span data-stu-id="497f9-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="497f9-105">除了常规服务器增强型密钥用法 (EKU) 之外, 美洲在线还需要证书或证书 (对于 Edge 池) 也包含客户端 EKU。</span><span class="sxs-lookup"><span data-stu-id="497f9-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="497f9-106">客户端 EKU 是证书的补充, 并且是分配给 Edge 服务器的外部公共证书的一部分。</span><span class="sxs-lookup"><span data-stu-id="497f9-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="497f9-107">证书摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="497f9-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="497f9-108">组件</span><span class="sxs-lookup"><span data-stu-id="497f9-108">Component</span></span></th>
<th><span data-ttu-id="497f9-109">主题名称</span><span class="sxs-lookup"><span data-stu-id="497f9-109">Subject name</span></span></th>
<th><span data-ttu-id="497f9-110">使用者备用名称 (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="497f9-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="497f9-111">备注</span><span class="sxs-lookup"><span data-stu-id="497f9-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="497f9-112">外部/访问边缘</span><span class="sxs-lookup"><span data-stu-id="497f9-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="497f9-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="497f9-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="497f9-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="497f9-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="497f9-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="497f9-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="497f9-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="497f9-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="497f9-117">证书必须来自公共 CA, 并且必须具有服务器 EKU 和客户端 EKU, 前提是要部署与 AOL 的公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="497f9-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="497f9-118">证书已分配给以下对象的外部边缘服务器接口:</span><span class="sxs-lookup"><span data-stu-id="497f9-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="497f9-119">访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="497f9-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="497f9-120">Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="497f9-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="497f9-121">A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="497f9-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="497f9-122">请注意, San 会根据拓扑生成器中的定义自动添加到证书。</span><span class="sxs-lookup"><span data-stu-id="497f9-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="497f9-123">根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="497f9-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="497f9-124">主题名称是在 SAN 中复制的, 并且必须存在才能正确操作。</span><span class="sxs-lookup"><span data-stu-id="497f9-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="497f9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="497f9-125">See Also</span></span>


[<span data-ttu-id="497f9-126">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="497f9-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

