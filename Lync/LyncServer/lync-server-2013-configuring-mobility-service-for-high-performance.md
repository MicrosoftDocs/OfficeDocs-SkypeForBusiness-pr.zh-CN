---
title: Lync Server 2013：配置移动服务以实现高性能
description: Lync Server 2013：配置移动服务以实现高性能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556978"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="5700a-103">在 Lync Server 2013 中配置移动服务以实现高性能</span><span class="sxs-lookup"><span data-stu-id="5700a-103">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5700a-104">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="5700a-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5700a-105">本主题仅适用于 Lync Server 2013 移动服务 (Mcx) ，不适用于 Lync Server 2013 的累积更新：二月2013中提供的统一通信 Web API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="5700a-105">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5700a-106">当您在 Internet Information Services (IIS) 7.5 上安装移动服务 (Mcx) 时，移动服务安装程序将在前端服务器上配置一些性能设置。</span><span class="sxs-lookup"><span data-stu-id="5700a-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="5700a-107">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="5700a-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="5700a-108">这些设置会影响移动服务允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="5700a-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="5700a-109">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="5700a-109">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="5700a-110">IIS 7.5 上的 Mcx 设置</span><span class="sxs-lookup"><span data-stu-id="5700a-110">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="5700a-111">**maxConcurrentThreadsPerCPU** 设置为零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="5700a-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="5700a-112">**maxConcurrentRequestsPerCPU** 设置为零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="5700a-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="5700a-113">ASP.NET 进程模型设置为仅) IIS 7.5 的自动配置 (。</span><span class="sxs-lookup"><span data-stu-id="5700a-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="5700a-114">默认情况下，HTTP.sys 队列限制设置为 1000 () 。</span><span class="sxs-lookup"><span data-stu-id="5700a-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

