---
title: 控制器常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑现有控制器的设置，您将看到以下部分：
ms.openlocfilehash: ffdfd169095175346a89eb6d6d001161bec0f465
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793850"
---
# <a name="director-general-settings-expander"></a>控制器常规设置扩展器
 
若要编辑现有控制器的设置，您将看到以下部分：
  
- 常规设置
    
- Web 服务
    

## <a name="general-settings"></a>常规设置

控制器池的完全限定的域名（FQDN）。 编辑服务器的 FQDN 以更改该值。 必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。
  
在“**关联**”中，可以编辑或指定以下内容：
  
要使用的 Director pool 的文件共享。 选择拓扑生成器中已定义的现有文件共享，或单击 "**新建**" 以创建新的文件共享定义。
  
监视 SQL Server 应用商店。
  
> [!IMPORTANT]
> 发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。 如果你创建了新的文件共享，则必须在你指定的服务器上创建文件共享。 
  
## <a name="web-services"></a>Web 服务

若要在 Director 池中编辑或指定 Web 服务的其他设置，请修改或指定内部 Web 服务和外部 Web 服务中的设置。
  
对于**内部 web 服务**，你可以指定以下内容：
  
> [!CAUTION]
> 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为**pool01.contoso.com**，则不能将**Pool01.contoso.com**用于其他前端池或前端服务器。 如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。
  
如果选择“覆盖 FQDN”，则可以为池上的“内部 Web 服务”标识指定不同的 FQDN。 默认情况下，该设置是为 Director 池定义的当前池名称。
  
你可以为你的部署所需的 HTTP 和 HTTPS 指定侦听和已发布端口。 HTTPS 的端口80和端口443的默认设置是最常见的设置，通常不需要更改，除非你在组织和基础结构设计中具有特定要求。
  
对于**外部 web 服务**，你可以指定以下内容：
  
你可以定义外部 Web 服务的 FQDN。 此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。
  
你可以为你的部署所需的 HTTP 和 HTTPS 指定侦听和已发布端口。 最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。 根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。 已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。 这些值确定了控制器池或控制器服务器将在哪些端口上侦听传入的请求。 通常情况下，不需要更改这些项，除非该池上的端口要求冲突。 需要使用相同端口值的内部和外部发布端口。 这不会出现冲突。
  

