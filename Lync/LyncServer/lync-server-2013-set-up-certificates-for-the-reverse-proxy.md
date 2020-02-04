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
ms.openlocfilehash: fe45f9e7d422da53e9dc531721d4b678685eb2b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="f5745-102">在 Lync Server 2013 中为反向代理设置证书</span><span class="sxs-lookup"><span data-stu-id="f5745-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5745-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f5745-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f5745-104">每个反向代理服务器都要求有一个 web 服务器证书供侦听服务使用。</span><span class="sxs-lookup"><span data-stu-id="f5745-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="f5745-105">Web 服务器证书必须由公共证书颁发机构（CA）颁发。</span><span class="sxs-lookup"><span data-stu-id="f5745-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="f5745-106">有关此和其他证书要求的详细信息，请参阅[Lync Server 2013 中的外部用户访问证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f5745-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="f5745-107">为反向代理设置 Web 服务证书</span><span class="sxs-lookup"><span data-stu-id="f5745-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="f5745-108">你应该已经设置了反向代理，包括设置 Web 服务证书。</span><span class="sxs-lookup"><span data-stu-id="f5745-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="f5745-109">如果在开始部署 Edge 服务器之前未执行此操作，请使用[设置 Lync Server 2013 的反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的过程来创建请求并安装 web 服务证书，然后创建每个 web 发布规则并将其配置为使用该证书。</span><span class="sxs-lookup"><span data-stu-id="f5745-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

