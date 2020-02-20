---
title: Lync Server 2013：支持的服务器并置边缘组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 118ed297998072edf721d0f6a254f2b66120d343
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="d1ec0-102">Lync Server 2013 中的边缘组件支持的服务器并置</span><span class="sxs-lookup"><span data-stu-id="d1ec0-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1ec0-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d1ec0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d1ec0-104">访问边缘服务、Web 会议边缘服务、A/V 边缘服务和 XMPP 代理服务在边缘服务器上并置。</span><span class="sxs-lookup"><span data-stu-id="d1ec0-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="d1ec0-105">以下服务器提供外部用户访问所需的功能，必须部署为专用服务器：</span><span class="sxs-lookup"><span data-stu-id="d1ec0-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="d1ec0-106">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d1ec0-106">Edge Server</span></span>

  - <span data-ttu-id="d1ec0-107">控制器（可选）</span><span class="sxs-lookup"><span data-stu-id="d1ec0-107">Director (Optional)</span></span>

  - <span data-ttu-id="d1ec0-108">反向代理</span><span class="sxs-lookup"><span data-stu-id="d1ec0-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1ec0-109">反向代理无需专门为 Lync Server 2013 提供服务。</span><span class="sxs-lookup"><span data-stu-id="d1ec0-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="d1ec0-110">例如，可以提供服务以发布 Lync Server Web 服务，并同时为另一个网站提供已发布的网站，而该网站根本没有任何位置上的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="d1ec0-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="d1ec0-111">如果在外围网络中已有反向代理服务器来支持其他服务，则可以将其用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d1ec0-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

