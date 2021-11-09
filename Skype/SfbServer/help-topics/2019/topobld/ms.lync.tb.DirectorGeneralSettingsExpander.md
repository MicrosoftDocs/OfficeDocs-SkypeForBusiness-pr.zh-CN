---
title: 控制器常规设置扩展器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 要编辑现有控制器的设置，可参考以下各节内容：
ms.openlocfilehash: 13c86f57084724511044d32db98b41988f3e48c0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861599"
---
# <a name="director-general-settings-expander"></a>控制器常规设置扩展器
 
要编辑现有控制器的设置，可参考以下各节内容：
  
- 常规设置
    
- Web 服务
    

## <a name="general-settings"></a>常规设置

控制器池的完全限定域名 (FQDN)。编辑服务器的 FQDN 以更改该值。必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在“关联”中，可以编辑或指定以下内容：
  
控制器池使用的文件共享。 选择已在拓扑生成器中定义的现有文件共享，或单击"新建"以创建新的文件共享定义。
  
监控 SQL Server 存储。
  
> [!IMPORTANT]
> 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。如果创建了新的文件共享，则必须在指定的服务器上创建文件共享。 
  
## <a name="web-services"></a>Web 服务

要为控制器池中的 Web 服务编辑或指定其他设置，请在内部 Web 服务和外部 Web 服务中修改或指定设置。
  
对于“内部 Web 服务”，可以指定以下内容：
  
> [!CAUTION]
> 如果您具有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 **pool01.contoso.com，** 则不能将 pool01.contoso.com 用于另一个前端池或前端服务器。 如果还要部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器是唯一的。 如果您决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。
  
如果选择“覆盖 FQDN”，则可以为池上的内部 Web 服务标识指定不同的 FQDN。默认情况下，该设置是为控制器池定义的当前池名称。
  
可以为部署所需的 HTTP 和 HTTPS 指定侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。
  
对于“外部 Web 服务”，可以指定以下内容：
  
可以定义外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。
  
可以为部署所需的 HTTP 和 HTTPS 指定侦听端口和已发布端口。最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。这些值确定了控制器池或控制器服务器将侦听哪些端口的传入请求。通常，这些值不需要更改，除非池上的端口要求有冲突。建议使用相同端口值的内部和外部已发布端口，这样不会出现冲突。
  

