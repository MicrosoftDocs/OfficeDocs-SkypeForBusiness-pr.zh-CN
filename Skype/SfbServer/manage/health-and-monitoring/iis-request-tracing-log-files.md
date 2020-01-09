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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
 
**摘要：** 了解 Skype for Business Server 2015 中的移动服务（Mcx）是否支持旧版客户端。
  
本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。

> [!NOTE]
> 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
为 Skype for Business Server 移动服务（Mcx）启用 Internet 信息服务（IIS）请求跟踪时，生成的日志文件最多可以消耗 3 gb 的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 应监视前端服务器，以确保它们不会用尽磁盘空间。 
  
默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。
  
若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

有关**httpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。
  

