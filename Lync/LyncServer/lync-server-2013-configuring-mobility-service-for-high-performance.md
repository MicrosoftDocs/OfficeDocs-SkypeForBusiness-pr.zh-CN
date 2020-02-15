---
title: Lync Server 2013：配置移动服务以实现高性能
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
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="37378-102">在 Lync Server 2013 中配置移动服务以实现高性能</span><span class="sxs-lookup"><span data-stu-id="37378-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37378-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="37378-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37378-104">本主题仅适用于 Lync Server 2013 移动服务（Mcx），不适用于 Lync Server 2013 的累积更新：2月2013中提供的统一通信 Web API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="37378-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="37378-105">当您在 Internet Information Services （IIS）7.5 上安装移动服务（Mcx）时，移动服务安装程序将在前端服务器上配置一些性能设置。</span><span class="sxs-lookup"><span data-stu-id="37378-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="37378-106">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="37378-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="37378-107">这些设置会影响移动服务允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="37378-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="37378-108">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="37378-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="37378-109">IIS 7.5 上的 Mcx 设置</span><span class="sxs-lookup"><span data-stu-id="37378-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="37378-110">**maxConcurrentThreadsPerCPU**设置为零（0）。</span><span class="sxs-lookup"><span data-stu-id="37378-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="37378-111">**maxConcurrentRequestsPerCPU**设置为零（0）。</span><span class="sxs-lookup"><span data-stu-id="37378-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="37378-112">ASP.NET 进程模型设置为 "自动配置" （仅适用于 IIS 7.5）。</span><span class="sxs-lookup"><span data-stu-id="37378-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="37378-113">Http.sys 队列限制设置为1000（默认情况下）。</span><span class="sxs-lookup"><span data-stu-id="37378-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

