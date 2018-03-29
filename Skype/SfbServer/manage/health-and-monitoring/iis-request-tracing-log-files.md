---
title: 在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要： 了解对于旧客户端的业务服务器 2015年支持 Skype 在移动服务 (Mcx)。
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="0d00d-103">在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="0d00d-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d00d-104">**摘要：**了解业务服务器 2015年支持旧式客户端的移动服务 (Mcx) 在 Skype。</span><span class="sxs-lookup"><span data-stu-id="0d00d-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="0d00d-105">本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="0d00d-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>
  
<span data-ttu-id="0d00d-106">当启用了 Internet Information Services (IIS) 请求跟踪 Skype 业务服务器移动服务 (Mcx) 时，生成的日志文件可能会消耗达三吉字节的磁盘空间，每一天。</span><span class="sxs-lookup"><span data-stu-id="0d00d-106">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="0d00d-107">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="0d00d-107">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="0d00d-108">您应该监视前端服务器，以确保他们不要运行磁盘空间不足。</span><span class="sxs-lookup"><span data-stu-id="0d00d-108">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="0d00d-109">默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。</span><span class="sxs-lookup"><span data-stu-id="0d00d-109">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="0d00d-110">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0d00d-110">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="0d00d-111">**HttpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="0d00d-111">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

