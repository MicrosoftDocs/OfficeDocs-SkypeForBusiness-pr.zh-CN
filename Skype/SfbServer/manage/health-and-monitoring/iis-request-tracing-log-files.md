---
title: 在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 摘要：了解 Skype for Business Server 2015 中对旧客户端 (Mc) x 服务支持。
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823502"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="cb528-103">在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="cb528-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cb528-104">**摘要：** 了解 Skype for Business Server 2015 (Mcx) 2015 中对旧版客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="cb528-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="cb528-105">本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，适用于 Mobility Service (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="cb528-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="cb528-106">SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。</span><span class="sxs-lookup"><span data-stu-id="cb528-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="cb528-107">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="cb528-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="cb528-108">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="cb528-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="cb528-109">为 Skype for Business Server Mobility Service (Mcx) 启用 Internet Information Services (IIS) 请求跟踪时，生成的日志文件每天最多会占用 3 GB 的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="cb528-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="cb528-110">默认情况下，IIS 跟踪日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="cb528-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="cb528-111">您应监视前端服务器，以确保它们不会用完磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="cb528-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="cb528-112">默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。</span><span class="sxs-lookup"><span data-stu-id="cb528-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="cb528-113">若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="cb528-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="cb528-114">有关 **httpLogging 命令** 的详细信息，请参阅 [命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。</span><span class="sxs-lookup"><span data-stu-id="cb528-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

