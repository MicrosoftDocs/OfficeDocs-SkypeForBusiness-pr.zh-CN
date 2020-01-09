---
title: 在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要：了解 Skype for Business Server 2015 中的移动服务（Mcx）对旧客户端的支持。
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992177"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="a2a0c-103">在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="a2a0c-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a2a0c-104">**摘要：** 了解 Skype for Business Server 2015 中的移动服务（Mcx）是否支持旧版客户端。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="a2a0c-105">本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="a2a0c-106">在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a2a0c-107">所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a2a0c-108">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a2a0c-109">为 Skype for Business Server 移动服务（Mcx）启用 Internet 信息服务（IIS）请求跟踪时，生成的日志文件最多可以消耗 3 gb 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="a2a0c-110">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="a2a0c-111">应监视前端服务器，以确保它们不会用尽磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="a2a0c-112">默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="a2a0c-113">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a2a0c-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="a2a0c-114">有关**httpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="a2a0c-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

