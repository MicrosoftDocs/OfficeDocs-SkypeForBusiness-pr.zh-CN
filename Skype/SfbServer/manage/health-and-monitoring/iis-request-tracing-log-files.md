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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视 IIS 请求跟踪日志文件
 
**摘要：**了解业务服务器 2015年支持旧式客户端的移动服务 (Mcx) 在 Skype。
  
本主题仅适用于支持 Lync 2010 Lync Mobile 客户端的部署，面向的是 Mobility Service (Mcx)。
  
当启用了 Internet Information Services (IIS) 请求跟踪 Skype 业务服务器移动服务 (Mcx) 时，生成的日志文件可能会消耗达三吉字节的磁盘空间，每一天。 默认情况下，IIS 跟踪日志记录已启用。 您应该监视前端服务器，以确保他们不要运行磁盘空间不足。 
  
默认情况下，IIS 将在 %SystemDrive%\inetpub\logs\LogFiles 中存储日志文件。
  
若要对整个服务器禁用 IIS 请求跟踪，请在命令行中键入：
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

**HttpLogging**命令的详细信息，请参阅[命令参考](https://go.microsoft.com/fwlink/p/?linkId=234927)。
  

