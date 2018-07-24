---
title: 在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要： 了解旧客户端的业务服务器 2015年支持 Mobility Service (Mcx) Skype 中。
ms.openlocfilehash: 5ed817290bdf86d11dd4a2cf0e95c83fb4c31d9a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983824"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="b92da-103">在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="b92da-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b92da-104">**摘要：** 了解业务服务器 2015年支持旧客户端的 Skype 中 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="b92da-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="b92da-105">本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="b92da-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="b92da-106">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="b92da-106">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b92da-107">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="b92da-107">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b92da-108">为业务服务器 Mobility Service (Mcx) 的 Skype 启用 Internet Information Services (IIS) 请求跟踪时生成的日志文件可以使用最多为三个千兆字节的每日的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b92da-108">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="b92da-109">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="b92da-109">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="b92da-110">您应监视前端服务器以确保它们不要运行磁盘空间不足。</span><span class="sxs-lookup"><span data-stu-id="b92da-110">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="b92da-111">默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。</span><span class="sxs-lookup"><span data-stu-id="b92da-111">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="b92da-112">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="b92da-112">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="b92da-113">有关**httpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="b92da-113">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

