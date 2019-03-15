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
ms.openlocfilehash: 72d5dc8cafc0bbf0b33533d4548f2c7f1cd2d466
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226979"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="d756e-103">在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="d756e-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d756e-104">**摘要：** 了解业务服务器 2015年支持旧客户端的 Skype 中 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="d756e-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="d756e-105">本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="d756e-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="d756e-106">MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="d756e-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d756e-107">业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="d756e-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d756e-108">与使用 MCX 的旧客户端的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="d756e-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="d756e-109">为业务服务器 Mobility Service (Mcx) 的 Skype 启用 Internet Information Services (IIS) 请求跟踪时生成的日志文件可以使用最多为三个千兆字节的每日的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="d756e-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="d756e-110">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="d756e-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="d756e-111">您应监视前端服务器以确保它们不要运行磁盘空间不足。</span><span class="sxs-lookup"><span data-stu-id="d756e-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="d756e-112">默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。</span><span class="sxs-lookup"><span data-stu-id="d756e-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="d756e-113">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="d756e-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="d756e-114">有关**httpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="d756e-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

