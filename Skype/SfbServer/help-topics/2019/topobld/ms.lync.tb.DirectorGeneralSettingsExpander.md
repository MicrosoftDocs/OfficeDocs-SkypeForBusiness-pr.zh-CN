---
title: 控制器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑现有控制器的设置，可参考以下各节内容：
ms.openlocfilehash: 10960d057f806b1d3cdd1b68c22f786861fe7cd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915886"
---
# <a name="director-general-settings-expander"></a>控制器常规设置扩展器
 
若要编辑现有控制器的设置，可参考以下各节内容：
  
- 常规设置
    
- Web 服务
    

## <a name="general-settings"></a>常规设置

控制器池的完全限定名称 (FQDN)。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在“**关联**”中，可以编辑或指定以下内容：
  
要使用的控制器池的文件共享。 选择现有的已在拓扑生成器中定义的文件共享或单击**新建**创建新的文件共享定义。
  
监控 SQL Server 存储。
  
> [!IMPORTANT]
> 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。 如果您创建新的文件共享，则必须在您指定的服务器上创建的文件共享。 
  
## <a name="web-services"></a>Web 服务

若要编辑或指定其他设置的 Web 服务上的控制器池，您修改或指定设置中的内部 Web 服务和外部 Web 服务。
  
**内部 web 服务**为可以指定以下各项：
  
> [!CAUTION]
> 如果您有多个前端池或前端服务器的外部 Web 服务 FQDN 必须是唯一的。 例如，如果您定义的外部 Web 服务的前端服务器的 FQDN 为**pool01.contoso.com**，不能使用**pool01.contoso.com** ，另一个前端池或前端服务器。 如果还要部署控制器、 外部 Web 服务 FQDN 定义任何控制器或控制器池必须不同于任何其他控制器池以及任何前端池或前端服务器。 如果您决定覆盖内部 web 服务与自定义的 FQDN，每个 FQDN 必须是唯一从任何其他前端池、 控制器或控制器池。
  
如果选择“覆盖 FQDN”，则可以为池上的“内部 Web 服务”标识指定不同的 FQDN。 默认情况下设置是当前的池名称，因为定义控制器池。
  
您可以指定 HTTP 和 HTTPS 部署所需侦听和已发布端口。 和默认设置的端口 80 HTTP 端口 443 用于 HTTPS 是最常用的设置，通常不需要被更改，除非您有您的组织和基础设施设计中的特定要求。
  
对于**外部 web 服务**，可以指定以下各项：
  
您可以定义的外部 Web 服务的 FQDN。 此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。
  
您可以指定 HTTP 和 HTTPS 部署所需侦听和已发布端口。 最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。 根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。 已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。 这些值确定哪些控制器池或控制器服务器的传入请求将侦听的端口。 通常，这些不需要更改，除非存在冲突的池上的端口要求。 应内部和外部使用相同的端口值的已发布的端口。 这不会出现冲突。
  

