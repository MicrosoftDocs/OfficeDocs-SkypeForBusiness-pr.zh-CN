---
title: 'Lync Server 2013: 通过 System Center Operations Manager 监视 Lync 服务器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d243216518137c46098edadce7a58871a2a76058
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="ea9fe-102">通过 System Center Operations Manager 监视 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea9fe-102">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea9fe-103">_**主题上次修改时间:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="ea9fe-103">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="ea9fe-104">Lync Server 管理包 (MP) 是监视任何 Lync Server 部署的首选监视解决方案。</span><span class="sxs-lookup"><span data-stu-id="ea9fe-104">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="ea9fe-105">MP 实现传统的事件日志和基于性能计数器的检测, 并在 Lync Server 中启用新可用的检测, 如几个关键运行状况指示器的配对事件 (失败/成功), 同时还完全实现新的合成事务 (Test-Cs\* Windows PowerShell cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="ea9fe-105">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="ea9fe-106">您可以在上[http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468)找到 Lync Server 2013 管理包及其相关文档。</span><span class="sxs-lookup"><span data-stu-id="ea9fe-106">You can find the Lync Server 2013 Management Pack and its related documentation at [http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="ea9fe-107">如果你运行的是 System Center Operations Manager 2012, 则建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ea9fe-107">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

