---
title: Lync Server 2013：访问监视数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609963f3248d5bdd1c50eac45b74c188ab2e6c56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="87d02-102">访问 Lync Server 2013 中的监视数据</span><span class="sxs-lookup"><span data-stu-id="87d02-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87d02-103">_**主题上次修改时间：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="87d02-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="87d02-p101">监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别之处；也就是说您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="87d02-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="87d02-106">您应考虑访问和分析监视数据的一个工具是 Lync 服务器监视报告。</span><span class="sxs-lookup"><span data-stu-id="87d02-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="87d02-107">监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。</span><span class="sxs-lookup"><span data-stu-id="87d02-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="87d02-108">这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="87d02-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="87d02-109">与 Lync Server 2013 一起提供的监视报告，并且可以在安装 Lync Server 并配置监视后从 Lync Server 部署向导中安装。</span><span class="sxs-lookup"><span data-stu-id="87d02-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="87d02-p103">如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。</span><span class="sxs-lookup"><span data-stu-id="87d02-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="87d02-112">有关详细信息，请参阅 Lync Server 2013 部署指南中的[安装 Lync server 2013 监视报告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)主题。</span><span class="sxs-lookup"><span data-stu-id="87d02-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

