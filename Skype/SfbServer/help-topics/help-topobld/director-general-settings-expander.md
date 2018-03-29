---
title: 主任一般设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 若要编辑现有的控制器的设置，系统会提供以下各节：
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="director-general-settings-expander"></a>主任一般设置扩展器
 
若要编辑现有的控制器的设置，系统会提供以下各节：
  
- 常规设置
    
- Web 服务
    
## 

### <a name="general-settings"></a>常规设置

导演池的完全合格的域名称 (FQDN)。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在“**关联**”中，可以编辑或指定以下内容：
  
要使用的控制器池的文件共享。 选择已定义拓扑生成器中使用现有的文件共享，或单击**新建**以创建新的文件共享定义。
  
监视 SQL Server 存储区。
  
> [!IMPORTANT]
> 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。 如果您创建新的文件共享，则必须在您指定的服务器上创建文件共享。 
  
### <a name="web-services"></a>Web 服务

若要编辑或主任池上指定用于 Web 服务的其他设置，您可以修改或内部 Web 服务和外部 Web 服务中指定的设置。
  
为**内部 web 服务**可以指定以下各项：
  
> [!CAUTION]
> 如果您有多个前端池或前端服务器的外部 Web 服务 FQDN 必须是唯一的。 例如，如果您定义为**pool01.contoso.com**的外部 Web 服务前端服务器的 FQDN，则不能为另一个前端池或前端服务器使用**pool01.contoso.com** 。 如果还部署控制器、 外部 Web 服务定义的任何主管的 FQDN 或主任池必须不同于任何其他控制器池以及任何前端池或前端服务器。 如果您决定重写自定义 FQDN 内部 web 服务，每个的 FQDN 必须是唯一从任何其他前端池、 主管或导演池。
  
如果您选择重写 FQDN，可以在池上指定为内部 Web 服务标识不同的 FQDN。 默认情况下，该设置是导演池定义当前的池名称。
  
HTTP 和 HTTPS 的部署要求，您可以指定发布的侦听端口。 和默认设置端口 80 的 HTTP 端口 443 的 HTTPS 是最常用的设置，通常不需要进行更改，除非您有在您的组织和结构设计中的具体要求。
  
对于**外部 web 服务**，您可以指定以下项：
  
您可以定义外部 Web 服务的 FQDN。 此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。
  
HTTP 和 HTTPS 的部署要求，您可以指定发布的侦听端口。 最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。 根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。 已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。 这些值确定哪些端口控制器池或控制器服务器将侦听传入的请求。 通常情况下，这些不需要进行更改，除非端口要求池上的冲突。 将内部和外部发布的端口使用相同的端口值。 这不会出现冲突。
  

