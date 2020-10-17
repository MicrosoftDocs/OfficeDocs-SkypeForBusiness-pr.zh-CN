---
title: Lync Server 2013：将自动客户端 Sign-In 配置为使用控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522959"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="9ef62-102">将自动客户端 Sign-In 配置为在 Lync Server 2013 中使用控制器</span><span class="sxs-lookup"><span data-stu-id="9ef62-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ef62-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9ef62-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9ef62-104">当您部署 Lync Server 2013、控制器或控制器池时，建议使用自动客户端 Sign-In 作为最佳实践。</span><span class="sxs-lookup"><span data-stu-id="9ef62-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="9ef62-105">有关如何为自动客户端登录配置 DNS 服务器的详细信息，请参阅规划文档中的 [Lync Server 2013 中的自动客户端登录的 dns 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) 。</span><span class="sxs-lookup"><span data-stu-id="9ef62-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="9ef62-106">如果已部署自动客户端登录，请参阅以下几节以在一台或多台控制器上配置自动客户端登录。</span><span class="sxs-lookup"><span data-stu-id="9ef62-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="9ef62-107">单个控制器实例</span><span class="sxs-lookup"><span data-stu-id="9ef62-107">Single Director Instance</span></span>

<span data-ttu-id="9ef62-108">如果已部署自动客户端 Sign-In 并将其指向前端服务器或前端池，则需要将 DNS SRV 记录更改为指向控制器。</span><span class="sxs-lookup"><span data-stu-id="9ef62-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="9ef62-109">控制器池</span><span class="sxs-lookup"><span data-stu-id="9ef62-109">Director Pool</span></span>

<span data-ttu-id="9ef62-110">如果已部署自动客户端 Sign-In 并将其指向前端服务器或前端池，则需要将 DNS SRV 记录更改为指向控制器池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

