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

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中监视 IIS 请求跟踪日志文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

为 Lync Server 移动服务 (Mcx) 启用 Internet 信息服务 (IIS) 请求跟踪时, 生成的日志文件最多可以消耗 3 gb 的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 应监视前端服务器, 以确保它们不会用尽磁盘空间。

默认情况下, IIS 将日志文件存储在% SystemDrive\\%\\inetpub\\日志日志文件中。

若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

有关**httpLogging**命令的详细信息, 请[http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)参阅。

</div>

<span> </span>

</div>

</div>

</div>

