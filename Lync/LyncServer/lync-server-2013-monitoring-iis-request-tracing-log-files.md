---
title: Lync Server 2013：监视 IIS 请求跟踪日志文件
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
ms.openlocfilehash: 76e8734c8cef93191c5e7186240c1b78529916fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531919"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中监视 IIS 请求跟踪日志文件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

当您为 Lync Server 移动 (服务 (IIS) 请求跟踪启用 Internet 信息服务时) ，生成的日志文件每日最长可消耗 3 gb 的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 应监视前端服务器，以确保它们不会用尽磁盘空间。

默认情况下，IIS 将日志文件存储在% 系统驱动器% \\ inetpub \\ 日志日志文件中 \\ 。

若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

有关 **httpLogging** 命令的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) 。

</div>

<span> </span>

</div>

</div>

</div>

