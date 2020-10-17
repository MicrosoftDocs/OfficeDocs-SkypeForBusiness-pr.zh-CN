---
title: Lync Server 2013：为反向代理设置证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509869"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="994de-102">在 Lync Server 2013 中为反向代理设置证书</span><span class="sxs-lookup"><span data-stu-id="994de-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="994de-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="994de-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="994de-p101">每台反向代理服务器都需要一个 Web 服务器证书，以供侦听服务使用。该 Web 服务器证书必须是由公共证书颁发机构 (CA) 颁发的。</span><span class="sxs-lookup"><span data-stu-id="994de-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="994de-106">有关此证书和其他证书要求的详细信息，请参阅 [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="994de-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="994de-107">为反向代理设置 Web 服务证书</span><span class="sxs-lookup"><span data-stu-id="994de-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="994de-108">您应该已经设置了反向代理，包括设置 Web 服务证书。</span><span class="sxs-lookup"><span data-stu-id="994de-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="994de-109">如果在启动边缘服务器的部署之前未执行此操作，请使用为 [Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md) 中的过程来创建请求并安装 web 服务证书，然后创建每个 web 发布规则并将其配置为使用证书。</span><span class="sxs-lookup"><span data-stu-id="994de-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

