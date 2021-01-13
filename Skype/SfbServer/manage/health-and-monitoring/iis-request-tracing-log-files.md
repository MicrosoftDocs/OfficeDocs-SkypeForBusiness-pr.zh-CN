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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
 
**摘要：** 了解 Skype for Business Server 2015 (Mcx) 2015 中对旧版客户端的支持。
  
本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，适用于 Mobility Service (Mcx) 。

> [!NOTE]
> SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
为 Skype for Business Server Mobility Service (Mcx) 启用 Internet Information Services (IIS) 请求跟踪时，生成的日志文件每天最多会占用 3 GB 的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 您应监视前端服务器，以确保它们不会用完磁盘空间。 
  
默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。
  
若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

有关 **httpLogging 命令** 的详细信息，请参阅 [命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。
  

