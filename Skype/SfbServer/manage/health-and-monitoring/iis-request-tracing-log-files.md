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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
 
**摘要：** 了解业务服务器 2015年支持旧客户端的 Skype 中 Mobility Service (Mcx)。
  
本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。

> [!NOTE]
> MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。 您的用户需要升级到当前客户端。
  
为业务服务器 Mobility Service (Mcx) 的 Skype 启用 Internet Information Services (IIS) 请求跟踪时生成的日志文件可以使用最多为三个千兆字节的每日的磁盘空间。 默认情况下，IIS 跟踪日志记录已启用。 您应监视前端服务器以确保它们不要运行磁盘空间不足。 
  
默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。
  
若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

有关**httpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。
  

