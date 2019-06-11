---
title: 'Lync Server 2013: 监视 IIS 请求跟踪日志文件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="1a4af-102">在 Lync Server 2013 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="1a4af-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a4af-103">_**主题上次修改时间:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="1a4af-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="1a4af-104">为 Lync Server 移动服务 (Mcx) 启用 Internet 信息服务 (IIS) 请求跟踪时, 生成的日志文件最多可以消耗 3 gb 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="1a4af-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="1a4af-105">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="1a4af-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="1a4af-106">应监视前端服务器, 以确保它们不会用尽磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="1a4af-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="1a4af-107">默认情况下, IIS 将日志文件存储在% SystemDrive\\%\\inetpub\\日志日志文件中。</span><span class="sxs-lookup"><span data-stu-id="1a4af-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="1a4af-108">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="1a4af-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="1a4af-109">有关**httpLogging**命令的详细信息, 请[http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)参阅。</span><span class="sxs-lookup"><span data-stu-id="1a4af-109">For details about the **httpLogging** command, see [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

