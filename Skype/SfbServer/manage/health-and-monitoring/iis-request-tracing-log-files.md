---
title: Monitoring IIS request tracing log files in Skype for Business Server 2015
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
description: 摘要：了解 2015 年 2015 年 (支持中的 Mobility Service) Mcx Skype for Business Server。
ms.openlocfilehash: 74aaca832bc7f6cfa1b9e3afbc08942ac0eceee3a655f36abb1347eab9ea5cfd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297148"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitoring IIS request tracing log files in Skype for Business Server 2015
 
**摘要：** 了解 2015 年 (2015 支持中的 Mobility Service) Mcx Skype for Business Server。
  
本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，适用于 Mobility Service (Mcx) 。

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
为 Skype for Business Server Mobility Service (Mcx) 启用 Internet Information Services (IIS) 请求跟踪时，生成的日志文件每天可能占用多达 3 GB 的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 您应监视前端服务器以确保它们不会用完磁盘空间。 
  
默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。
  
若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

有关 **httpLogging** 命令的详细信息，请参阅 [命令参考](/previous-versions/iis/settings-schema/aa347466(v=vs.90))。
