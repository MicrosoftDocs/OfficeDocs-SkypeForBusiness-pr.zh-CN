---
title: Lync Server 2013：监视 IIS 请求跟踪日志文件
description: Lync Server 2013：监视 IIS 请求跟踪日志文件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09692b79b1cc59ad18ad520885c0a795736b53cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569948"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="bce3a-103">在 Lync Server 2013 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="bce3a-103">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bce3a-104">_**上次修改的主题：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="bce3a-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="bce3a-105">当您为 Lync Server 移动 (服务 (IIS) 请求跟踪启用 Internet 信息服务时) ，生成的日志文件每日最长可消耗 3 gb 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="bce3a-105">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="bce3a-106">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="bce3a-106">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="bce3a-107">应监视前端服务器，以确保它们不会用尽磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="bce3a-107">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="bce3a-108">默认情况下，IIS 将日志文件存储在% 系统驱动器% \\ inetpub \\ 日志日志文件中 \\ 。</span><span class="sxs-lookup"><span data-stu-id="bce3a-108">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="bce3a-109">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bce3a-109">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="bce3a-110">有关 **httpLogging** 命令的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) 。</span><span class="sxs-lookup"><span data-stu-id="bce3a-110">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

