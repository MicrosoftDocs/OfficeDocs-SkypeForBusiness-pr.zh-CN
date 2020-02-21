---
title: Lync Server 2013：规划边缘服务器证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ac330914a0d748c366d2a6e40ac0ad9f03543d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="bb3e4-102">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="bb3e4-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb3e4-103">_**上次修改的主题：** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="bb3e4-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="bb3e4-104">在 Lync Server 2013 中简化了为边缘创建证书。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="bb3e4-105">**边缘服务器的证书流程图**</span><span class="sxs-lookup"><span data-stu-id="bb3e4-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="bb3e4-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="bb3e4-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="bb3e4-107">使用证书向导创建单个公共证书，确保有一个证书定义的可导出私钥并将其分配到以下边缘服务器外部接口：</span><span class="sxs-lookup"><span data-stu-id="bb3e4-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb3e4-108">Lync Server 不支持通配符证书，除非使用反向代理汇总简单 Url。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="bb3e4-109">您必须为您的部署提供的每个 SIP 域名、Web 会议边缘服务、A/V 边缘服务和 XMPP 域定义不同的主题备用名称（San）。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bb3e4-110">在 Lync Server 2013 中引入，在当前证书的过期时间之前暂存音频/视频身份验证证书需要进行一些额外的规划。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="bb3e4-111">对于外部边缘接口，而不是一个具有多个用途的证书，您将需要两个证书，一个证书分配给访问边缘服务和 Web 会议边缘服务，另一个证书用于 A/V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="bb3e4-112">有关更多详细信息，请参阅<A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">set-cscertificate 中的使用中的暂存 AV 和 OAuth 证书在 Lync Server 2013</A>中</span><span class="sxs-lookup"><span data-stu-id="bb3e4-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb3e4-113">在边缘服务器池的事件中，可以将具有私钥的证书导出到每台边缘服务器，并将证书分配给每个边缘服务器服务。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="bb3e4-114">对内部边缘服务器证书执行相同操作，使用私钥导出证书，并将其分配给每个内部边缘接口。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="bb3e4-115">确保有一个分配到该证书的可导出私钥</span><span class="sxs-lookup"><span data-stu-id="bb3e4-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="bb3e4-116">访问边缘服务（在证书向导中称为 "**外部 SIP 访问边缘**"）</span><span class="sxs-lookup"><span data-stu-id="bb3e4-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="bb3e4-117">Web 会议边缘服务（称为证书向导中的 " **Web 会议边缘外部**"）</span><span class="sxs-lookup"><span data-stu-id="bb3e4-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="bb3e4-118">A/V 身份验证服务（在证书向导中称为“A/V 边缘外部”\*\*\*\*）</span><span class="sxs-lookup"><span data-stu-id="bb3e4-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="bb3e4-119">使用可导出的私钥创建单个内部证书，并将其复制和分配到每个边缘服务器内部接口：</span><span class="sxs-lookup"><span data-stu-id="bb3e4-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="bb3e4-120">边缘服务器（在证书向导中称为“边缘内部”\*\*\*\*）</span><span class="sxs-lookup"><span data-stu-id="bb3e4-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb3e4-121">可以对每个边缘服务器服务使用单独和不同的证书。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="bb3e4-122">选择单独的证书的最佳原因是要对 A/V 边缘服务证书使用新的滚动证书功能。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="bb3e4-123">在此功能的情况下，建议将 A/V 边缘服务证书与访问边缘服务和 Web 会议边缘服务相分离。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="bb3e4-124">如果您选择请求、获取并为每个服务分配单独的证书，则必须请求为 A/V 边缘服务导出私钥（同样，这实际上是 A/V 身份验证服务），并将同一证书分配给每台边缘服务器上的 A/V 边缘外部接口。</span><span class="sxs-lookup"><span data-stu-id="bb3e4-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb3e4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3e4-125">See Also</span></span>


[<span data-ttu-id="bb3e4-126">使用-Set-cscertificate 中的 Lync Server 2013 暂存 AV 和 OAuth 证书</span><span class="sxs-lookup"><span data-stu-id="bb3e4-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="bb3e4-127">Lync Server 2013 中影响边缘服务器规划的更改</span><span class="sxs-lookup"><span data-stu-id="bb3e4-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

